---
layout: post
title: Starting Github.io Blog
---

Github.io로 블로그를 시작하기 위한 절차를 간단히 정리

### Jekyll 테마 찾기
Jekyll 테마를 검색해서 원하는 테마 찾기 (데모 확인 가능)

참고 사이트:
- https://jekyllthemes.io/
- https://jekyll-themes.com/blog/top-jekyll-themes/

### 해당 Repository Fork 및 설정 변경
1. 원하는 Jekyll 테마의 github repository로 이동하여 오른쪽 상단의 Fork 버튼 클릭
2. Fork 완료되면 Settings에서 `Repository name`을 `{user-id}.github.io`로 변경 (user-id는 내 github ID)
3. 잠시 기다리면 Settings 하단에 "Your site is published at `{user-id}.github.io`"와 같이 표시됨

### Config 수정
Repository의 source root에 `_config.yml` 파일이 있는데 `url` 정보 다음과 같이 수정 필요
```yaml
# Setup
...
url:     'http://{user-id}.github.io'
baseurl: ''
...
```
수정 사항 저장 (commit) 완료 후 `{user-id}.github.io`에 방문하면 데모에서 봤던 것과 같은 테마로 내 블로그 생성되어 있음을 확인 가능

### 원하는 대로 Customize
`_config.yml` 내용 / layout 등을 원하는 내용으로 편집하기

### IDE를 사용한 작업
Github repository 내에서 직접 파일 편집 및 commit을 통해 블로그 관리할 수 있지만, 평소에 편하게 사용하는 IDE (e.g. visual studio code 등) 이용해 작업도 가능 (git 사용이 익숙하다면 추천할만한 방법인 것 같음)
- git 설치
- 해당 repository를 local로 git clone
- local에서 작업 후 git add / commit / push

### Source 구성
기본 구성 요소: 
- `_config.yml`: 기본 설정 (title / tagline / description / url 등)
- `_includes` 폴더: Head / Sidebar 등에 대한 HTML 파일로 구성
- `_layouts` 폴더: TBD
- `_posts` 폴더: 실제로 블로그 글이 추가되는 공간
  - Markdown (*.md) 파일로 내용 작성


### 참고
https://dreamgonfly.github.io/blog/jekyll-remote-theme/