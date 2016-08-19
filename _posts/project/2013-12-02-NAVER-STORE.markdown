---
layout: project
title:  "NAVER STORE"
date:   2013-12-02
author: MJKIM
categories:
- project
img: portfolio_01.jpg
carousel:
- store01.jpg
- store02.jpg
- store03.jpg
tagged: 가변, UI, Development
client: NAVER Corp.
website: http://naverstore.naver.com
---
### NAVER STORE
>Key point : main page image resize

가로 해상도 1280px일 경우와 1920px 이상일때

    <body class="wide">
    
위 코드와 같은 형식으로 해당 해상도에 따라 class를 삽입/제거 제어.

- 이미지 영역이 3단으로 컬럼으로 나누어질때 %적용시 크로스브라우징 이슈 발생(ie7까지 대응)
- 서브 페이지 가변에 따라 가운데 정렬
- 제품 상세 페이지 이미지 중앙 리사이즈
- faq 페이지 클래스 하나로 질문 답변 on/off 제어

*생각을 한번 더 할수록 class 제어 하는 부분이 줄어들었다.*
