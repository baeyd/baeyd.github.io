---
title: "Github Blog 댓글 사용"
date: 2024-09-30 15:20:00 +0900
last_modified_at: 2024-09-30 15:20:00 +0900
categories: [Github Blog, 댓글기능]
tags: [github, jekyll, chirpy, blog, Disqus, Utterances]
author: BaeYD
toc: ture
---

> 작성한 게시글에서 댓글 기능을 사용하기 위핸 게시글이며,   
> 주로 사용하는 댓글 종류에 대해 살펴보고 적용해보는 방법에 대해 정리하였다.
> 참고로 나는 개발자와 기술 블로그에서 주로 사용한다고 하는 Utterances를 적용하였다.   

## 댓글 종류
대표적으로 사용하는 댓글의 종류는 아래와 같은것으로 보여진다.   
블로그를 생성하고 한번도 사용해보지 않은 것들이라서 뭐가 좋고 나쁜지는 직접 적용해보고 사용해봐야 할 것 같은데,   
우선 적용해보기 전 각각의 장단점에 대해서 간략하게 확인해봤다.   

- **Disqus**   
  - 장점
    - 사용자 친화적: 많은 사이트에서 사용해 익숙함.
    - 다양한 기능: 통계, 스팸 필터링 등 제공
  - 단점
    - 광고 포함: 무료 버전에서 광고가 나타날 수 있음.
    - 데이터 저장 문제: 개인 정보 보호 우려.
  
- **Utterances**   
  - 장점
    - 간편한 설치: 짧은 코드로 쉽게 추가 가능.
    - GitHub 이슈 활용: 댓글이 GitHub 이슈로 관리되어 투명함.
  - 단점
    - 로그인 필요: 모든 사용자가 GitHub 계정을 가지고 있어야 함.
    - 기능 제한: 기본적인 댓글 기능에 초점 맞춤.
   
## 적용방법
위에 설명한 것과 같이 나는 Utterances를 적용해서 사용하는데 각각 사용하고자 하는것이 다를 수 있기에,   
대표적인 Github Blog의 댓글기능인 Disqus, Utterances를 직접 적용해보고 방법에 대해서 설명하겠다.   

### Disqus

참고 : https://help.disqus.com/en/articles/1717056-publisher-quick-start-guide

### Utterances

참고 : https://utteranc.es/
