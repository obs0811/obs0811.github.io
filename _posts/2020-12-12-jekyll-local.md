---
layout: post
title: Jekyll 로컬에서 빌드하기
categories: [ Tech ]
tags: [ jekyll ]
permalink: /:categories/:title/
---

Jekyll 블로그를 로컬에서 빌드하는 방법

- 로컬 IDE에서 작업을 하고 `git push`하면 github page build를 통해 블로그 내용이 렌더링됨
- 렌더링 내용을 항상 git에 push하여 확인하는 것이 불편하기 때문에 로컬에서 빌드하는 방법을 확인 (OS: 윈도우 10)

### Ruby와 Jekyll 설치
<https://jekyllrb.com/docs/installation/windows/> 설명대로 `RubyInstaller`를 활용해 설치

1. <https://rubyinstaller.org/downloads/>에서 왼쪽의 WITH DEVKIT인 패키지 설치
2. 설치 마지막 단계에서 CMD 창이 하나 열리고 `ridk install` 실행: 엔터 누르면 필요한 것 알아서 설치됨
3. 새로운 CMD 창 열고 `gem install jekyll bundler` 입력하여 Jekyll과 Bundler 설치
4. Jekyll이 잘 설치됐는지 `jekyll -v` 통해 확인

이 방법 말고 `Windows Subsystem for Linux`를 활용한 설치도 가능. 위 jekyllrb.com 링크에서 확인 가능

### Jekyll 빌드 및 실행
터미널로 로컬에 `git clone` 한 디렉토리에 접속하여 (커맨드 창 또는 IDE의 terminal) `jekyll serve` 명령 입력
> 나의 경우 다음과 같은 에러가 발생
> - `Could not find gem 'jemoji x64-mingw32' in any of the gem sources listed in your Gemfile. (Bundler::GemNotFound)`  
>   - `bundle install` 통해 missing gem 설치
> - 위 에러 해결하고 다시 `jekyll serve` 했지만 다음과 같은 에러 발생:  
> `Dependency Error: Yikes! It looks like you don't have jekyll-paginate or one of its dependencies installed. In order to use Jekyll as currently configured, you'll need to install this gem. If you've run Jekyll with `bundle exec`, ensure that you have included the jekyll-paginate gem in your Gemfile as well.`
>   - `Gemfile`에 (없다면 생성) `gem 'jekyll-paginate'` 추가하여 빠졌다고 하는 gem 추가 & `bundle` 명령 입력하여 설치
>   - 위와 동일한 설치를 하나의 명령어로: `gem install jekyll-paginate`로 설치

Dependency와 관련된 위 두 에러 해결 후 `jekyll serve` 하니 다음과 같이 서버 시작
```
Configuration file: C:/Users/obs08/Documents/blog/obs0811.github.io/_config.yml
            Source: C:/Users/obs08/Documents/blog/obs0811.github.io
       Destination: C:/Users/obs08/Documents/blog/obs0811.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
                    done in 0.684 seconds.
  Please add the following to your Gemfile to avoid polling for changes:
    gem 'wdm', '>= 0.1.0' if Gem.win_platform?
 Auto-regeneration: enabled for 'C:/Users/obs08/Documents/blog/obs0811.github.io'
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```

- 브라우저에서 http://127.0.0.1:4000/로 들어가면 github page를 통해 빌드한 것과 동일하게 렌더링된 블로그 페이지 확인 가능
- 이렇게 서버가 ON 되어있는 상태에서 새로운 수정 사항을 [저장] 하기만 하면 해당 변경 내용이 로컬 블로그에 반영됨
