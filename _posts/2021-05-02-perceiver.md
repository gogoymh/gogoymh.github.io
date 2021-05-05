---
layout: post
title: [논문리뷰] Perceiver: General Perception with Iterative Attention
---

## 요약 먼저!
방법
1. Input을 1차원의 array로 만들어 key와 value를 얻고 learnable한 latent vector에서 query를 얻는 Cross Attention을 적용하고, 그 output에 transformer를 적용한다.
2. 이 과정을 weight sharing을 사용하여 iterative하게 진행해준다.
3. Position Encoding은 fourier encoding을 사용하되, parameterization을 이용하여 신경망이 input array의 maximum frequency를 확인하여
   모든 position에서 값을 비교할 수 있게 한다. 또한 더하지 않고 concatenate해준다.

결과
1. 일반 ImageNet에서는 ViT-B-16: 77.9% > ResNet-50: 76.9% > Perceiver 76.4% 순으로 약간 뒤쳐지지만,
   Permuted ImageNet(Fixed)에서는 Perceiver: 76.4% > ViT-B-16: 61.7% > ResNet-50: 39.4%
   Permuted ImageNet(Random)에서는 Perceiver: 76.4% > ViT-B-16: 16.1% > ResNet-50: 14.3% 순으로 압도적인 성능을 보여주었다.
   특히 Randomly Permuted는 모든 픽셀을 뒤섞는 것으로, positional encoding에 반영되지 않은 spatial information를 이용하는 것을 완전히 막은 것이다.
   이 결과는 Perceiver가 domain-specific assumption 없이 강력한 퍼포먼스를 보여주는 것을 의미한다.
   이러한 양상은 Sound와 Video, Point clouds에서도 동일하게 나타났다.
2. Cross attention은 input보다 작은 차원의 latent vector에서 query하기 때문에 complexity를 줄이는데 매우 효과적이며,
   여기서 줄인 complexity 덕분에 전체 구조에 transformer를 deep하게 사용할 수 있었다.
   또한 weight sharing으로 transformer를 iterative하게 사용하는 것은 파라미터 수를 줄일 뿐만 아니라, overfit을 방지하는데 효과적이었다.
   


## 아키텍쳐 그림
작성중

## 부연 설명
작성중

## 관련 링크
작성중
