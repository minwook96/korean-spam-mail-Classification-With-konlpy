# korean-spam-mail-Classification-With-konlpy

한글 자연어 처리를 위한 Konlpy가 필요하다.   
Konlpy 공식 사이트   
> https://konlpy-ko.readthedocs.io/ko/v0.4.3/#

![다운로드](https://user-images.githubusercontent.com/49277505/137443549-4baefd9b-9954-45e7-b9b3-62746d4a8c16.png)
## Sample Data
> https://github.com/jordi-angmond/KoreanOpinionSpamData

-----------------------------------------------
## 이론

베이지안 필터(Baysian Filter)

학습을 시킬수록 필터의 분류 능력이 오르는 특징을 가지고 있다. 때문에 메일 서비스에서 스팸 메일을 구분하거나/커뮤니티 사이트에서 스팸 글을 구분할 때 많이 사용된다. 이외에도 문장의 카테고리 분류에도 사용된다.

*교사학습, 비교사학습, 강화학습 중 "교사학습에"에 해당된다.

​

1. 베이즈 정리 : 조건부 확률과 관련된 이론으로, 토머스 베이즈에 의해 정리된 이론

P(B|A)=P(A|B)P(B) / P(A)

P(A) : A가 일어날 확률

P(B) : B가 일어날 확률(사전확률)

P(A|B) : B가 일어난 후 A가 일어날 확률(조건부확률, 사후확률)

P(B|A) : A가 일어난 후 B가 일어날 확률(조건부확률, 사전확률)

​

2. 조건부확률 : <어떤 A라는 사건이 일어났다는 조건>에서 <다른 사건 B가 일어날 확률>을 나타냄

Ex) 비가 내릴 확률: P(비)

교통사고가 발생할 확률: P(교통사고)

비가 내리는 날에 교통사고가 발생할 확률: P(교통사고|비)

​

알고리즘 : 나이브 베이즈 분류(Naive Bayes Classifier)

베이즈 정리를 사용한 분류 방법

텍스트 내부에서 단어 출현 비율을 조사 -> 이를 기반으로 해당 텍스트를 어떤 카테고리로 분류하는 것이 적합한지 조사

실제로 판정을 할 때 P(B|A)는 1개의 확률이 아니라 여러 개의 카테고리 중에 어떤 카테고리에 속할 확률이 가장 큰지를 나타내는 정보다.

따라서 베이즈 정리의 분모에 있는 P(A)는 입력 텍스트가 주어질 확률이다.

다만 어떤 카테고리를 판정하든 같은 입력 텍스트가 주어지는 것이므로 같은 값으로 생각하면 된다.

정리하면, P(B|A)=P(A|B)P(B)

P(A|B)=P(B) / P(B|A) -> 단순한 출현율 = 단어의 출현횟수 / 카테고리 전체 단어 수


​

구글 Colab환경으로 구현하였습니다.

--------------------------------------------

## 텍스트 학습

학습 방법
    bf.fit("스팸내용", "광고or중요")
    
![noname01](https://user-images.githubusercontent.com/49277505/137443735-ca097d92-c2e2-425e-b388-1c618ccd0a03.png)

-----------------------------------------
## 중요 메일 예측

![SE-504f5c4a-7c21-4c53-bc4f-e1de5202a7d5](https://user-images.githubusercontent.com/49277505/137443918-223d2681-1e92-4756-8b1b-545099425161.png)

![SE-fec63a12-b7d8-4428-9c63-da57a43016c7](https://user-images.githubusercontent.com/49277505/137443927-72db4c3d-9831-40eb-87b9-04b51560a89a.png)

-----------------------------------------
## 스팸 메일 예측

![noname01](https://user-images.githubusercontent.com/49277505/137444006-b80c8620-a8ca-42aa-b06a-ffb4541866cd.png)

![noname01 (1)](https://user-images.githubusercontent.com/49277505/137444014-38bd56f2-9ffa-4665-941e-77b24b79bebf.png)

-----------------------------------------
## 메일함에 없는 예제 예측

![noname01 (2)](https://user-images.githubusercontent.com/49277505/137444060-1ce5fbd4-6eed-4a60-a63a-4c345ed8ff46.png)

