---
layout: post
title: Jekyll 블로그에 카테고리 추가
categories: [ Tech ]
tags: [ jekyll ]
permalink: /:categories/:title/
---

Jekyll 블로그에 카테고리 추가하기 위한 방법

### Goal
1. Post 작성 시 특정 카테고리 (미리 정의) 지정 가능해야 함
2. 이와 같이 카테고리 지정된 post를 모아서 보여줄 수 있는 카테고리 페이지 생성

### Category 만들기
Post를 쓸 때 `_posts` 디렉토리에서 `layout`으로 `post`를 지정하고 내용을 작성함 (markdown). Category를 만드는 것도 post를 생성하는 것과 유사함: category에 대한 공통 템플릿이라 할 수 있는 layout 작성 필요

(1) Category layout 생성
   - "Category"라는 class를 만든다고 생각해도 됨
   - 이 class의 instance로 실제 여러 종류의 카테고리 (e.g. Tech / Research / Misc.)를 생성하고 post에서 이를 사용하는 방식
   - 예시: `_layouts/category.html`
     ```
     TBD
     ```
   - 동작 방식: TBD 

(2) Category 생성
   - 최상위 디렉토리에 category를 관리하기 위한 `category/` 디렉토리 생성
   - 이 안에 category file (.md) 생성
   - 예시: `category/tech.md`
     ```yaml
     ---
     layout: category
     title: tech
     ---
     ```

(3) Post에서 category 지정: 
   - 예시: 
     ```yaml
     ---
     layout: post
     title: Jekyll 블로그에 카테고리 추가
     categories: [ tech ]
     permalink: /:categories/:title/
     ---
     ...
     ```
     > (참고) permalink: 해당 post의 URL 형식 지정 가능. 위 예의 경우 {base-url}/tech/jekyll-category 와 같은 형태

### Category Page 만들기
지금까지 layout을 만들어서 category를 생성하고 post에서 이를 지정하는 과정 정리함. 이렇게 만든 category 및 category에 속하는 post를 확인할 수 있는 페이지를 만들어야 함  
- 이 페이지는 `page` layout을 사용해서 만듦
- Blog에서 생성한 post list 중 category를 명시 (e.g. `categories: [ tech ]`) 한 것을 찾아서 출력
- 최상위 디렉토리에 `categories.html` 파일 작성
- 예시: 
  ```
  TBD
  ```

### Summary
1. Category layout 생성
2. Category 생성 (`layout: category`인 매우 짧은 markdown 문서)
3. Post 작성 시 category 명시 (e.g. `categories: [ tech]`)
4. Category page 만들기 (HTML)
