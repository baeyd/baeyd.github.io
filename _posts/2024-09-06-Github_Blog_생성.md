---
title: "Github Blog 생성"
date: 2024-09-06 02:00:00 +0900
last_modified_at: 2024-09-06 02:43:00 +0900
categories: [Github Blog, Jekyll]
tags: [github, jekyll, chirpy, blog]
author: BaeYD
toc: ture
---

> Github 블로그를 만들기 위해  
> Jekyll 테마 중 마음에 드는 테마인 Chirpy를 적용하여   
> 블로그를 생성해보는 게시글이며, 다른 블로그를 참고하여 진행하였을 때 발생하는 오류에 대한 대처 방법을 정리하였다.

# Github 계정 생성
[Github](https://github.com/ "Github") 사이트에 접속하여 회원가입을 진행한다.   
회원가입은 특별하게 어려운 것이 없고, 가입 시 무료 또는 유료(월,4$)가 있는데 개인적으로 사용하기에 무료로 진행한다.

# Jekyll Themes
[Jekyll Themes](http://jekyllthemes.org/ "Jekyll Themes")에 접속하면 수많은 테마들을 확인할 수 있다.   
마음에 드는 테마를 클릭 후 Demo 버튼을 누르면 해당 테마를 블로그에 적용하였을 때 모습을 미리 볼 수 있다.

## Themes TOP 5
사람들이 주로 사용하는 테마는 아래와 같은것으로 보여진다.   
각 테마별 장점이라고 하는 부분을 확인해 봤는데 잘 모르겠고 그냥 본인 기준으로 마음에 드는 것을 고르면 될 것 같다.   
나는 "Lanyon" 테마를 먼저 적용하였다가 이후 "Chirpy" 테마가 더 마음에 들어 해당 테마로 새로 블로그를 생성하였다.
- [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/ "Minimal Mistakes") : 깔끔하고 사용자 맞춤형 설정이 가능
- [Just the Docs](https://just-the-docs.github.io/just-the-docs/ "Just the Docs") : 문서화에 최적화된 테마
- [Tale](https://chesterhow.github.io/tale/ "Tale") : 간결하고 우아한 디자인
- [Chirpy](https://chirpy.cotes.page/ "Chirpy") : 블로그와 포트폴리오용으로 인기
- [Beautiful Jekyll](https://beautifuljekyll.com/ "Beautiful Jekyll") : 다양한 기능과 쉬운 설정 제공

# Jekyll Chirpy Themes 적용
Chirpy 테마를 적용하여 Github 블로그를 생성해보자.   
전체적인 순서를 정리해보면 아래와 같다.

- Chirpy Repository Fork
- Repository 설정 변경 (Build and deployment, _config.yml)
- Repository Local Clone 진행 후 Local에서 초기화하고 Github Repository 동기화 및 배포 (Github Desktop, Ruby, Jekyll 등 설치)

## Chirpy Repository Fork
Chirpy를 Fork하기 위해 [Chirpy Repository](https://chirpy.cotes.page/ "Chirpy")로 접속한다.   
접속하면 아래와 같은 화면이 보이게 될 텐데 

