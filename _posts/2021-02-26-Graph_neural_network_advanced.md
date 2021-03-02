[→ Open in Slid](https://slid.cc/vdocs/8d2e3412c6f742819845bcf2ade95d1f)


---

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/7ed1f441-c344-4885-a8e6-bfdbb798451a.png "그래프 신경망 (심화) image")


그래프 어텐션 신경망

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/a0b4d9b1-0147-4348-a386-0b3a706521cb.png "그래프 신경망 (심화) image")





멀티헤드 어텐션&nbsp;

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/b0f0a97b-332b-412a-acf3-e3290a599e81.png "그래프 신경망 (심화) image")


어텐션을 통해서 이웃별 가중치를 계산하는 것

## 그래프 표현 학습과 그래프 풀링


## 그래프 표현학습/ 그래프 임베딩

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/51700862-64a1-4f9a-831a-b62255ddfb32.png "그래프 신경망 (심화) image")


## 그래프 풀링(Graph Pooling)

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/d025ef2b-c4f7-478b-9fed-24ef600932f3.png "그래프 신경망 (심화) image")

## 지나친 획일화 문제

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/3bcc745e-8315-4aee-a155-f702a3bbfb61.png "그래프 신경망 (심화) image")

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/97141510-c88c-4262-88e0-db66df70a0d7.png "그래프 신경망 (심화) image")


## 지나친 획일화 문제에 대한 대응

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/51b25c20-0f90-475b-aa3e-d85d428cb9ab.png "그래프 신경망 (심화) image")

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/296f7d79-3005-45ad-95e0-c8cb89c0fd48.png "그래프 신경망 (심화) image")

## 그래프 데이터의 증강


그래프 데이터 증강<br>그래프 데이터 증강에 따른 효과

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/b305bab7-6208-4bcc-8845-e7eb32694c46.png "그래프 신경망 (심화) image")


그래프 데이터 증강의 효과

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/2c982954-8209-47e5-b105-d5c939e25f13.png "그래프 신경망 (심화) image")

## 실습: GraphSAGE의 집계 함수 구현


데이터 불러오기

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/bb950dbd-868f-413c-aaed-8840a5c6cd9e.png "그래프 신경망 (심화) image")

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/528d6a00-5f0d-4052-afc3-4d72d2751ba3.png "그래프 신경망 (심화) image")





GraphSAGE 구현

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/16f05819-e55a-4e79-9530-9ff8cb78e532.png "그래프 신경망 (심화) image")

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/8bc19593-cf85-4af4-aa75-6164e8bc142f.png "그래프 신경망 (심화) image")

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/93f40baf-86c3-492d-92c1-c241e08d4c00.png "그래프 신경망 (심화) image")

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/7d482e7f-3768-46e8-ab1e-5a9d26abe921.png "그래프 신경망 (심화) image")

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/4408ea8f-4afb-4bf5-b629-c9399295148d.png "그래프 신경망 (심화) image")


GraphSAGE 학습

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/0bbaa10e-32e6-4b94-ac7e-42c6f77c8fd1.png "그래프 신경망 (심화) image")


GraphSAGE 평가

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/1b513c19-8028-42ce-a90f-525b824b6fd9.png "그래프 신경망 (심화) image")

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/d2d556b1-bd0c-4e23-b670-4972af179591.png "그래프 신경망 (심화) image")


정리

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/deb45b20-eb2f-4f55-91e8-c8f71081f08d.png "그래프 신경망 (심화) image")


# 그래프 복습


그래프란 무엇이고 왜 중요할까?

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/6a1634f9-89bb-4414-b09f-5ad981c607d9.png "그래프 신경망 (심화) image")


실제 그래프는 어떻게 생겼을까?

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/3191b161-2b5e-4771-b882-df07a32d4b1a.png "그래프 신경망 (심화) image")


검색 엔진에서는 그래프를 어떻게 활용할까?

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/e132311b-b4cc-4adc-bcd3-aaa044553d25.png "그래프 신경망 (심화) image")


그래프를 바이럴 마케팅에 어떻게 활용할까?

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/c1b8ccb3-0f5a-483f-910d-1f409a4274b3.png "그래프 신경망 (심화) image")


그래프의 구조를 어떻게 분석할까?

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/98ba96bd-325e-4205-b853-d6f593744780.png "그래프 신경망 (심화) image")


그래프를 추천시스템에 어떻게 활용할까? (기본)

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/f1b67a31-bbb8-4c4a-ba74-335361c424a3.png "그래프 신경망 (심화) image")


그래프의 정점을 어떻게 벡터로 표현할까?

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/e564c862-18f8-44f9-afbb-9b367b2501f3.png "그래프 신경망 (심화) image")


(인접성 중첩 거리 경로 임의보행기반)


그래프를 추천 시스템에 어떻게 활용할까? (심화)

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/f7a8177f-3808-4832-b36d-9afabc379896.png "그래프 신경망 (심화) image")


그래프 신경망이란 무엇일까? (기본)

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/857a5faf-c121-41d6-bde6-5f5ffce534d9.png "그래프 신경망 (심화) image")


그래프 신경망이란 무엇일까? (심화)

![](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8d2e3412c6f742819845bcf2ade95d1f/8fe1c844-16d0-47cf-a092-5016e01f1f8a.png "그래프 신경망 (심화) image")


Reference


* Mining of Massive Datasets 2nd Ed<br>Jure Leskovec, Anand Rajaraman, Jeffrey David Ullman


* Networks Crowds and Markets<br>Reasoning about a Highly Connected World<br>David Easley, Jon Kleinberg<br>


Further Lecture<br>CS224W: Machine Learning with Graphs (Stanford / Winter 2021)


CS246W: Mining Massive Data Sets<br>(Stanford / Winter 2020)
