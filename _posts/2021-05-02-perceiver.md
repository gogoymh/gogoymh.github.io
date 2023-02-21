---
layout: post
title: "[논문리뷰] Perceiver: General Perception with Iterative Attention"
use_math: true
tags:
- 딥러닝
- 논문리뷰
date:   2021-05-02 12:00:00 
lastmod : 2021-05-02 12:00:00
sitemap :
  changefreq : daily
  priority : 1.0
---

## 아키텍쳐
> [![architecture](/../public/images/posts/perceiver_fig1.PNG)](/../public/images/posts/perceiver_fig1.PNG)
  Perceiver 모델 구조

## 방법
* 1차원 array로 만든 input에서 key와 value를 얻고,\\
  learnable한 latent vector에서 query를 얻어서 Cross-attention을 적용하고,\\
  그 output에 transformer를 적용한다.\\
  즉, Complexity를 줄이기 위해,\\
  <span class="highlight-yellow">Cross-attention을 통해 latent space로 input의 정보를 축소 입력하여\\
  Self-attention을 latent dimension에서 하는 방식이다.</span>
* Cross-attention과 Self-attention을 RNN처럼\\
  weight sharing을 사용하여 iterative하게 진행해준다.\\
  이 과정을 통해 input이 반복적으로 여러번 입력된다.
* Position Encoding은 fourier encoding을 사용하되\\
  frequency band의 길이를 parameterize한다.\\
  $[-1,1]$ 사이의 순차적인 값을 가진 raw position value $x_d$를 얻고,\\
  frequency value $f_k$를 얻어서,
  $[sin(f_k \pi x_d), cos(f_k \pi x_d)]$의 수식을 얻는다.\\
  $f_k$는 $1$과 $\frac{\mu}{2}$ 사이에서 log-linearly하게 놓인 $k^{th}$번째 band다.\\
  이를 통해 신경망이 input의 maximum frequency($\mu$)를 확인해\\
  모든 position의 값을 비교할 수 있다.\\
  실제로는 raw position까지 결합해 $[sin(f_k \pi x_d), cos(f_k \pi x_d), x_d]$을 사용하며\\
  input에 더하지 않고 concatenate해준다.

## 결과
* 일반 ImageNet에서는 약간 뒤쳐지지만\\
  Permuted ImageNet에서는 압도적인 성능을 보여주었다.
  
> [![result1](/../public/images/posts/perceiver_fig2.PNG)](/../public/images/posts/perceiver_fig2.PNG)
  일반 ImageNet

> [![result2](/../public/images/posts/perceiver_fig3.PNG)](/../public/images/posts/perceiver_fig3.PNG)
  Permuted ImageNet

* 특히 Randomly Permuted는 모든 픽셀을 뒤섞는 것으로,\\
  positional encoding에 반영되지 않은 spatial information를\\
  이용하는 것을 완전히 막은 것이다.\\
  이 결과는 <span class="highlight-red">Perceiver가 domain-specific assumption 없이\\
  강력한 퍼포먼스를 보여주는 것</span>을 의미한다.\\
  이러한 양상은 Sound와 Video, Point clouds에서도 동일하게 나타났다.
* Cross attention은 input($M=50176=224\times224$ in ImageNet)보다\\
  작은 차원의 latent vector($N=1024 \ll M$)에서 query하기 때문에\\
  asymmetric한 matrix multiplication을 통해 $O(M^2)$ &rarr; $O(MN)$만큼\\
  complexity를 줄이고, 그 덕분에 전체 구조에다 비교적 저렴한\\
  (latent) transformer($O(N^2)$)를 deep하게 사용할 수 있었다.
* Weight sharing으로 transformer를 iterative하게 사용하는 것은\\
  파라미터 수를 줄일 뿐만 아니라, overfit을 방지하는데 효과적이었다.
   

## 텐서 차원으로 이해하기
{% highlight python %}
# Batch size B인 ImageNet 이미지 데이터
Input = (B, 3, 224, 224) 
# 픽셀을 합친다.
Input = (B, 3, 50176)

# 2차원 Image에 대한 Positional Encoding이 B만큼 expand된 것
Positional Encoding(PE) = (B, bands * 2 * 2 + 2, 50176)

# Input과 PE의 concatenation
Concatenated Input(CI) = (B, 5 + 4 * bands, 50176) 
# CI를 d_models feature dimension으로 embedd한 것
Embedded Input(EI) = (B, d_models, 50176) 

# 학습되는 latent vector가 B만큼 expand된 것
Latent(L) = (B, d_models, 1024) # 1024는 hyperparameter다

# 간단한 Pseudocode
Given EI, L
Instantiate Cross Attention, Self Attention
for i in range(repeat):
    L = Cross Attention(q=L,k=EI,v=EI)
    L = Self Attention(q=L,k=L,v=L)
output = Logit(L)

{% endhighlight %}



---

## Reference
1. Andrew Jaegle, Felix Gimeno, Andrew Brock, Andrew Zisserman, Oriol Vinyals, Joao Carreira\\
   Perceiver: General Perception with Iterative Attention\\
   [https://arxiv.org/abs/2103.03206](https://arxiv.org/abs/2103.03206)

---

<script src="https://utteranc.es/client.js"
        repo="gogoymh/gogoymh.github.io"
        issue-term="pathname"
        label="Comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
    </script>
