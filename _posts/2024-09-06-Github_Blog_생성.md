---
title: "Github Blog 생성"
date: 2024-09-06 02:00:00 +0900
last_modified_at: 2024-09-22 16:42:00 +0900
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
Error를 확인해보면 "Error: Can't find stylesheet to import."로 인해 생성에 실패하였다고 하는데
이를 해결하기 위해 다음 단계를 진행한다.   
<br/>
![Fail Build](https://github.com/user-attachments/assets/045e0018-56b9-4376-a81f-2295a8c0a4f4)

### Chirpy 초기화
위에서 발생한 Error를 해결하기 위해서는 기존에 Fork 해서 생성한 Repository를 Local 환경에 Clone 하여 초기화 작업을 진행해야한다.   
초기화를 하기 위해 Local 환경에 **Github Desktop**, **Ruby**, **Jekyll**, **git**를 설치하여 환경을 구성해야하는데 방법은 다음과 같다.   

**< Step 1 >**   
Repository를 Local 환경에 쉽게 Clone하기 위해 [Guthub Desktop](https://desktop.github.com/download/ "Github Desktop")로 접속 후 설치를 진행한다.   
설치를 완료한 후 본인 Github의 계정으로 로그인하면 해당 계정에 생성된 Repository 목록이 보인다.   
아래 Local Path의 경로를 확인하고 Clone을 진행하면 해당 경로에 Repository가 Clone된 것을 확인할 수 있다.   
<br/>
※ 해당 과정이 귀찮으면 Github Repository에 접속하여 **Code**버튼을 클릭하여 Fork된 Chirpy를 직접 다운로드 받을 수 있다.   
<br/>
![Github Desktop](https://github.com/user-attachments/assets/35c9da5a-532b-4236-9189-2f6ea8f76596)

**< Step 2 >**   
Local에 Clone한 Jekyll Chirpy를 초기화 하기 위해서는 Jekill를 설치해야 하는데 Jekyll은 Ruby로 개발되었기 때문에,
Ruby Interpreter가 없으면 Jekyll가 동작하지 않기에, 먼저 Ruby 설치를 진행해야한다.   
Ruby 설치를 위해 [Ruby](https://rubyinstaller.org/downloads/ "Ruby")로 접속하여 설치를 진행한다.   
설치파일 다운로드를 진행할 때 **with Devkit**에서 Ver 3이상을 선택하여야 하고 나는 3.3.51버전으로 선택하였다.   
다운로드가 완료되었다면 해당 파일을 실행하여 모두 체크한 후 설치 진행하면 되고 설치가 완료되면 아래와 같이 확인할 수 있는데,
Consol 창에서 **3**을 입력한 후 엔터를 누르면 추가적인 설치가 진행이 되고 마지막에 **Install MSYS2 and MINGW development toolchain succeeded** 문구가 확인되면 설치가 완료된 것이다.   
정상적으로 설치가 되었는지 확인하기 위해 cmd에서 아래와 같이 입력하면 설치된 버전이 나올 것이다.   
<br/>
![Ruby](https://github.com/user-attachments/assets/ad15a97e-9671-476b-a050-ac67ccc77c1d)

```shell
$ ruby -v
ruby 3.3.5 (2024-09-03 revision ef084cc8f4) [x64-mingw-ucrt]
```
<br/>

**< Step 3 >**   
다음은 Jekyll 설치를 진행해야한다.
설치를 하기 위해서 윈도우 실행키를 눌러 **Start Command Prompt with Ruby**를 검색하면 Ruby를 설치할 때 함께 설치된 것을 확인할 수 있는데,
이를 실행하여 아래의 명령어를 입력하여 Jekyll 및 의존성 충돌을 방지하기 위한 bundler를 설치한다.   
설치가 정상적으로 되었는지 확인하기 위해 설치한 Jekyll와 bundler의 버전을 확인해보면 아래와 같이 나타날 것이다.   
<br/>
```shell
$ gem install jekyll
$ gem install bundler

$ jekyll -v
jekyll 4.3.4

$ bundler -v
Bundler version 2.5.19
```
<br/>

**< Step 4 >**   
기본적으로 필요한 것을 설치하였고 이제 Local에 Clone한 Repository에 있는 tools 경로안에 init.sh를 실행하여 초기화를 진행해야한다.   
해당 파일을 실행하기 위해서 cmd 및 powershell에서 실행을 해보면 정상적으로 동작하지 않는데 쉘 스크립트 파일은 Linux 및 Unix 기반이기에,
git bash를 통하면 큰 문제 없이 실행할 수 있을 것이다. git bash를 사용하기 위해서는 [Git](https://git-scm.com/downloads "Git")에 접속하여 설치하면 된다.   
설치된 git bash를 실행하여 위에서 말한 init.sh가 있는 경로로 이동하여 실행을 해보면 **npm**이 없다는 메시지(Command 'npm' not found! Hint: you should install it.)가 나오면서 실행이 되지 않을 것이다.   
<br/>
```shell
BYD_PC@BYD MINGW64 ~/Documents/GitHub/baeyds.github.io/ (master)
$ pwd
/c/Users/BYD_PC/Documents/GitHub/baeyds.github.io/

BYD_PC@BYD MINGW64 ~/Documents/GitHub/baeyds.github.io/ (master)
$ tools/init.sh
Command 'npm' not found! Hint: you should install it.
```
<br/>

**< Step 5 >**   
**npm**을 설치하기 위해서는 **node.js**를 설치하면 된다.   
설치를 하기 위해 [Node js](https://nodejs.org/en/ "Node.js")에 접속하여 설치 파일을 다운로드 하고 Default로 설치를 진행하면 된다.   
설치가 완료되면 **node.js**와 **npm**의 버전을 확인하여 정상 설치가 되어 있는지 확인한다.   
<br/>
```shell
$ node -v
v20.17.0

$ npm -v
10.8.2
```
<br/>

**< Step 6 >**  
npm을 설치하였으니 다시 **step 5**의 init.sh를 실행한다.   
실행을 하면 시간이 조금 걸리긴 하는데 하단 부분에 **Initialization successful!**라는 메시지를 확인할 수 있을 것이다.   
그 다음 **bundle** 명령어를 입력하여 Jekyll Chirpy에 필요한 파일들을 다운로드를 받는다.   
정상적으로 진행이 될 줄 알았는데 **An error occurred while installing wdm (0.1.1), and Bundler cannot continue.**라는 메시지가 출력이 된다.   
원인을 확인하기 위해 현재 설치된 wdm의 버전을 확인해보면 **wdm-0.2.0**가 설치되어 있으나 사용하고자 하는 wdm의 버전은 **wdm-0.1.1** 버전을 사용할려는 것을
확인할 수 있고 이를 해결하기 위해서는 git bash에서 Repository(Chirpy)의 Root 경로에 가보면 **Gemfile**이 있는데 해당 파일을 vi로 열어 참조하는 버전을
기존 **wdm-0.1.1**버전을 설치되어 있는 **wdm-0.2.0**버전으로 변경해 다시 **bundle**명령어를 입력해주면 **bundle complete** 성공한 메시지를 확인할 수 있다.   
<br/>
```shell
# frozen_string_literal: true

source "https://rubygems.org"

gemspec

gem "html-proofer", "~> 5.0", group: :test

platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

gem "wdm", "~> 0.2.0", :platforms => [:mingw, :x64_mingw, :mswin]

#참고 : 기존에 wdm 버전 0.1.1로 되어 있는 부분을 0.2.0으로 변경하여 저장
```
<br/>

**< Step 7 >**  
이제 모든것을 완료하였다.   
Jekyll Chirpy가 Local에서 정상적으로 동작하는지 확인하기 위해서 구동을 한번 해보자.   
구동을 하기 위해 아래와 같이 **bundle exec jekyll serve --liveReload** 명령어를 입력하고 실행이 되면 아래 접속할 수 있는 주소가 확인된다.   
**Server address: http://127.0.0.1:4000/** 주소를 확인하였으면 브라우저에 해당 주소를 입력하여 접속하면 블로그 화면이 보인다.   
<br/>
![local](https://github.com/user-attachments/assets/f7f00ca7-eb5b-4557-bbb9-1710439cff8b)
<br/>
```shell
$ bundle exec jekyll serve --liveReload
C:/Ruby33-x64/bin/jekyll:32: warning: logger was loaded from the standard library, but will no longer be part of the default gems starting from Ruby 3.5.0.
You can add logger to your Gemfile or gemspec to silence this warning.
C:/Ruby33-x64/bin/jekyll:32: warning: csv was loaded from the standard library, but will no longer be part of the default gems starting from Ruby 3.4.0.
You can add csv to your Gemfile or gemspec to silence this warning.
C:/Ruby33-x64/lib/ruby/gems/3.3.0/gems/safe_yaml-1.0.5/lib/safe_yaml/load.rb:22: warning: base64 was loaded from the standard library, but will no longer be part of the default gems starting from Ruby 3.4.0.
You can add base64 to your Gemfile or gemspec to silence this warning.
Configuration file: C:/Users/BYD_PC/Documents/GitHub/baeyds.github.io/_config.yml
 Theme Config file: C:/Users/BYD_PC/Documents/GitHub/baeyds.github.io/_config.yml
            Source: C:/Users/BYD_PC/Documents/GitHub/baeyds.github.io
       Destination: C:/Users/BYD_PC/Documents/GitHub/baeyds.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 5.183 seconds.
 Auto-regeneration: enabled for 'C:/Users/BYD_PC/Documents/GitHub/baeyds.github.io'
C:/Ruby33-x64/lib/ruby/3.3.0/win32/registry.rb:2: warning: fiddle was loaded from the standard library, but will no longer be part of the default gems starting from Ruby 3.5.0.
You can add fiddle to your Gemfile or gemspec to silence this warning.
LiveReload address: http://127.0.0.1:35729
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
        LiveReload: Browser connected
```
<br/>

### 재배포
블로그 화면까지 Local에서 정상적으로 나오는것을 확인하였으면 이제 Github에 Local에서 수정된 부분들을 Push하여 반영하면 된다.   
간단하게 진행하기 위해 위 설명에서 설치한 Github Desktop을 실행하고 아래 사진의 위치에 있는 **Push origin**을 클릭하면 된다.   
Github에서 Repository의 Action 탭에 들어가면 정상적으로 build 및 deploy가 된 것을 볼 수 있고 위에서 설명한 **계정ID.github.io**으로 접속하면 Local에서 확인한 것처럼 정상적으로 나타난다.   
<br/>
![github desktop push](https://github.com/user-attachments/assets/1a89bf4a-0972-4868-b5d0-ac8ca5eed828)
<br/>

## END
이렇게 Github 블로그를 생성하고 Jekyll Chirpy 테마를 적용하는 방법에 대해서 정리하였다.   
게시글을 보면서 따라하는데 문제가 발생하거나 틀린 부분이 있을 시 알려주시면 감사하겠습니다.   
