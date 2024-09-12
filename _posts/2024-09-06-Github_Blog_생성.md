---
title: "Github Blog 생성"
date: 2024-09-06 02:00:00 +0900
last_modified_at: 2024-09-08 22:32:00 +0900
categories: [Github Blog, 블로그 생성]
tags: [github, jekyll, chirpy, blog]
author: BaeYD
toc: ture
---

> Github 블로그를 만들기 위해 Jekyll 테마 중 마음에 드는 테마인 Chirpy를 적용하여   
> 블로그를 생성해보는 게시글이며, 다른 블로그를 참고하여 진행하였을 때 발생하는 오류에 대한 대처 방법을 정리하였다.

## Github 계정 생성
[Github](https://github.com/ "Github") 사이트에 접속하여 회원가입을 진행한다.   
회원가입은 특별하게 어려운 것이 없고, 가입 시 무료 또는 유료(월,4$)가 있는데 개인적으로 사용하기에 무료로 진행한다.

## Jekyll Themes
[Jekyll Themes](http://jekyllthemes.org/ "Jekyll Themes")에 접속하면 수많은 테마들을 확인할 수 있다.   
마음에 드는 테마를 클릭 후 Demo 버튼을 누르면 해당 테마를 블로그에 적용하였을 때 모습을 미리 볼 수 있다.

### Themes TOP 5
사람들이 주로 사용하는 테마는 아래와 같은것으로 보여진다.   
각 테마별 장점이라고 하는 부분을 확인해 봤는데 잘 모르겠고 그냥 본인 기준으로 마음에 드는 것을 고르면 될 것 같다.   
나는 "Lanyon" 테마를 먼저 적용하였다가 이후 "Chirpy" 테마가 더 마음에 들어 해당 테마로 새로 블로그를 생성하였다.
- [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/ "Minimal Mistakes") : 깔끔하고 사용자 맞춤형 설정이 가능
- [Just the Docs](https://just-the-docs.github.io/just-the-docs/ "Just the Docs") : 문서화에 최적화된 테마
- [Tale](https://chesterhow.github.io/tale/ "Tale") : 간결하고 우아한 디자인
- [Chirpy](https://chirpy.cotes.page/ "Chirpy") : 블로그와 포트폴리오용으로 인기
- [Beautiful Jekyll](https://beautifuljekyll.com/ "Beautiful Jekyll") : 다양한 기능과 쉬운 설정 제공

## Jekyll Chirpy Themes 적용
Chirpy 테마를 적용하여 Github 블로그를 생성해보자.   
전체적인 순서를 정리해보면 아래와 같다.

- Chirpy Repository Fork
- Repository 설정 변경 (Build and deployment, _config.yml)
- Repository Local Clone 진행 후 Local에서 초기화하고 Github Repository 동기화 및 배포 (Github Desktop, Ruby, Jekyll 등 설치)

### Chirpy Repository Fork

**< Step 1 >**   
Chirpy를 Fork하기 위해 [Chirpy Repository](https://chirpy.cotes.page/ "Chirpy")로 접속 후 Fork 버튼을 클릭한다.   
<br/>
![Fork_img](https://github.com/user-attachments/assets/10c09848-e0e8-41ec-91f4-8a76a4f35e70)
<br/><br/>

**< Step 2 >**   
Github Blog의 주소와 같이 Repository 이름을 변경한다.   
Github 계정 ID와 Repository 이름이 동일할 경우 블로그의 주소는 **계정ID.github.io**가 되는것이고,   
Github 계정 ID와 Repository 이름이 다를 경우에는 블로그의 주소는 **계정ID.github.io/Repository name**처럼 별도의 Path가 추가되어야 한다.   
일반적으로 Blog의 주소는 Github 계정 ID와 Repository 이름을 동일하게 하기에 아래와 같이 동일하게 수정한다.   
<br/>
![Repository Creat](https://github.com/user-attachments/assets/f4ea094a-6c2a-45d9-8ce2-c4ef1e67b675)
<br/><br/>

**< Step 3 >**   
생성이 완료되었다면 Github계정의 Repository에 보면 Fork된 것을 확인할 수 있다.   
<br/>
![Repository Creat Success](https://github.com/user-attachments/assets/b13c671b-0989-43c9-83e6-c4f823f58488)
<br/><br/>

### Repository 설정 변경
Fork 후 생성한 블로그가 정상적으로 나오는지 확인할려고 접속을 하면 404 Error가 발생하는 것을 확인할 수 있을 것이다.   
Jekyll의 테마들은 대부분 추가적인 Plugin이 필요하고, Chirpy 테마처럼 커스텀 빌드가 필요한 경우 Github Actions 없이 정상적인 배포가 진행되지 않을 수 있다.   
따라서 Github Repository의 Setting(Page)에 있는 Build and deployment 설정을 변경하여야 한다.

**< Step 1 >**   
생성된 Repository를 클릭하면 상단에 Settings 버튼이 있다.   
해당 버튼을 클릭한 후 좌측 Code and automation에서 Pages를 클릭한다.   
이후 Build and deployment에서 Github Actions으로 수정한다.   
<br/>
![Github Actions](https://github.com/user-attachments/assets/d426c0f9-c64b-4028-b705-8ddea7157ae4)
<br/><br/>

**< Step 2 >**   
Github Actions으로 수정하면 이제 Github가 사이트를 빌드하고 배포하는 과정을 자동화할 수 있다.   
이를 위해 Github가 워크플로우 파일인 jekyll.yml를 인식하고 해당 파일에 설정에 따라 동작을 진행한다.   
현재 단계에서는 jekyll.yml 파일을 수정할 필요는 없고 최초 생성만 진행하면 되는데 생성을 위해서는 최초 Commit을 진행하기 위해,   
Configure버튼을 클릭하고 이후 Commit버튼을 클릭한다.   
<br/>
![Jekyll Configure](https://github.com/user-attachments/assets/a309aaea-5224-433f-b127-548856ebac0a)
<br/>
![Jekyll Configure Commit](https://github.com/user-attachments/assets/18668439-2b13-4bfc-8e72-4edec5f07f7e)
<br/><br/>

**< Step 3 >**   
정상적으로 진행이 된 것을 확인하기 위해 Action에 들어가서 확인해보면 Jekyll.yml 파일 생성에 실패한 것을 볼 수 있다.   
Error를 확인해보면 "Error: Can't find stylesheet to import."로 인해 생성에 실패하였다고 하는데,   
이를 해결하기 위해 다음 단계를 진행한다.   
<br/>
![Fail Build](https://github.com/user-attachments/assets/045e0018-56b9-4376-a81f-2295a8c0a4f4)

### Chirpy 초기화

<!---```shell
$ ruby -v
ruby 3.1.3p185 (2022-11-24 revision 1a6b16756e) [i386-mingw32]
```--->

