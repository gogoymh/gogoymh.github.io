---
layout: post
title: "[논문리뷰] Semi-Supervised Semantic Segmentation with Cross Pseudo Supervision"
use_math: true
tags:
- 딥러닝
- 논문리뷰
---

## 프레임워크
> [![framework](/../public/images/posts/Cross-framework.JPG)](/../public/images/posts/Cross-framework.JPG)
  Framework of cross pseudo supervision

## 방법
* 레이블이 있는 데이터는 평범하게 supervised setup으로 학습하고\\
  레이블이 없는 데이터는 한 데이터를 두 개의 모델에 통과한\\
  각 예측값을 서로 다른 모델의 수도 레이블로 보고 교차하여 학습한다.
  

## 작성중

---

## Reference
1. Xiaokang Chen, Yuhui Yuan, Gang Zeng, Jingdong Wang\\
   Semi-Supervised Semantic Segmentation with Cross Pseudo Supervision\\
   [https://arxiv.org/abs/2106.01226](https://arxiv.org/abs/2106.01226)

---

<script src="https://utteranc.es/client.js"
        repo="gogoymh/gogoymh.github.io"
        issue-term="pathname"
        label="Comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
    </script>
