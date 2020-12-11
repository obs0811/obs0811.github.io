---
layout: post
title: About CS Conferences
categories: [ Research ]
tags: [ conference ]
permalink: /:categories/:title/
---

Computer Science에서는 conference를 통해 주요한 연구 성과가 공유된다. 변화의 주기가 짧은 CS 분야에서는 매년 학회를 통해 연구자들이 한자리에 모여 연구 성과를 공유하면서 함께 성장하는 문화가 잘 갖춰진 것 같다. 

연구 분야 별로 다양한 학회가 있다. 좋은 연구가 많이 게재되는 학회들이 있고 상대적으로 그렇지 않은 학회들도 있다. 그렇기 때문에 분야 별로 어떤 학회에서 대체로 좋은 (많이 읽히고 영향력 있는) 연구가 나오는지에 대해 알고 있으면 논문을 찾아볼 때 도움이 되는 면이 있는 것 같다. 대학원에서 연구를 처음 시작할 때 어떤 학회에서 나온 어떤 논문들 보는게 좋을지 몰라서 연구실 선배님께 도움을 구했던 기억이 난다. 그렇게 알게된 정보가 연구를 하고 논문을 낼 때 실제로 도움이 많이 되었다. 이 글을 통해 이러한 정보를 간단하게 공유해 보려고 한다. 

### 평가 기준
학회의 신뢰도를 판단하기 위해 활용할 수 있는 기준들이 몇 가지 있다. 

(1) Ranking: 다양한 기관에서 학회의 다양한 실적을 바탕으로 ranking을 산정하여 제공한다. 이와 같은 ranking은 절대적이라 할 수는 없지만 분야별 top-tier 학회를 구분하기 위한 데이터로는 적합하다고 할 수 있다. 
- [Google Scholar Top Publications](https://scholar.google.co.uk/citations?view_op=top_venues&hl=en): CS 뿐만 아니라 여러 도메인에 걸쳐 세부 연구 분야별 top publication venue 리스트를 제공. 학회 뿐만 아니라 저널도 포함
- [CORE](http://portal.core.edu.au/conf-ranks/): 호주 정부에서 운영하는 Computing Research & Education 그룹에서 관리하는 CS conference ranking 데이터베이스로 A* (7%), A (19%), B (29%), C (26%), others (17%)로 등급 구분한다. CS conference 평가 공신력 높다. 

다음 두 사이트도 많이 활용된다. 

- [Guide2Research](http://www.guide2research.com/topconf/)
- [Microsoft Academic](https://academic.microsoft.com/conferences/41008148)

이와 같은 ranking 정보를 통해 관심 분야의 top-tier 학회 목록을 파악하는 것도 연구를 처음 시작하는 입장에서는 큰 도움이 되는 것 같다. 

(2) 몇 해 동안 이어져 온 학회인지
- CS 분야는 역사가 짧은 편이지만 그 가운데에서도 오랜 기간 지속되는 학회들은 어느 정도 신뢰성을 보장한다고 할 수 있다. 
  - e.g. VLDB, SIGMOD: 1975~ / ISCA: 1973~ / NeurIPS (formerly NIPS): 1987~ / INFOCOM: 1979~ / CHI: 1983~ 등은 각자의 분야 (DB / Architectures / AI / Network / HCI)에서 수십년에 걸쳐 성공적으로 운영되고 영향력 있는 논문이 발표되는 top-tier conference 이다. 
  - CS 분야에서 학회의 시작 연도가 이와 같이 20~30년 이전인데 아직도 존재하는 경우 저명한 venue인 경우가 많은 것 같다. 
- 전통적인 computing 분야와 차별화되는 새로운 패러다임이 등장하면 이에 맞춰 새로운 학회들이 생겨나는데, 해당 분야가 학계 / 산업에서 많은 관심을 끌고 단기간에 주목할만한 성과가 나타나면 이와 같이 오래 되지 않은 학회들도 높은 명성을 얻게 되는 경우도 있다. 
  - e.g. Cloud computing 분야의 ACM Symposium on Cloud Computing (SoCC)와 같은 학회는 2010년에 시작됐지만 분야의 빠른 성장과 함께 짧은 시간에 주목 받는 학회가 되었다. 

(3) 인용 수 관련
- 학회에 대한 `H5-index`: 지난 *5년* 동안 해당 학회에서 publish 된 논문 중 *최소 n 편이 n번 이상 인용된 n의 최대값*을 `H5-index` 라고 한다. 예를 들면, 어떤 학회에서 지난 5년간 논문 5편이 publish 되었는데 인용 횟수가 각각 [5, 3, 2, 0, 0]이라면 해당 학회의 `H5-index`는 2이다. 인용이 3번 이상된 것은 2편밖에 안되므로 3이 될 수 없다. 
    > H-index 개념은 researcher 개인의 연구 성과를 표현하는 지표로도 널리 활용되고 있다. 즉, 어떤 연구자가 publish 한 논문 중 *최소 n 편이 n번 이상 인용된 n의 최대값*을 해당 연구자의 h-index라고 한다. 
- Impact factor (journal): Journal의 실적을 표현하는 지표로 지난 2년 동안 해당 journal에 게재된 논문의 평균 인용 횟수 (전체 인용 횟수 / 전체 논문 갯수)

(4) Acceptance rate: 학회에 submit 된 논문 수 대비 accept 된 논문 비율

### 검색 방법
다음과 같은 사이트 (third-party services)에서 다양한 기준으로 (연구 키워드 / conference venue / 저자 / 논문 제목 등) 논문을 검색할 수 있다. 
- [Google Scholar](https://scholar.google.com/)
- **[DBLP](https://dblp.org/)**: 개인적으로 많이 사용하는 검색 서비스 -- CS 분야 학회 / 저널에 특화되어 있고 publication provider인 IEEE / ACM 등의 공식적인 논문 업데이트와의 싱크가 정확하고 빠른 편
- [ResearchGate](https://www.researchgate.net/)

논문들이 *공식적으로* publish 되는 공간
- [IEEE Explorer](https://ieeexplore.ieee.org/Xplore/home.jsp)
- [ACM Digital Library](https://dl.acm.org/)

### 논문 제출할 venue 찾기
(분야별) 논문 제출 일정 확인할 수 있는 사이트
- [Conference Partner (Myhuiban)](https://www.myhuiban.com/)
- [WikiCFP](http://www.wikicfp.com/cfp/call?conference=computer%20science)
- [ACM upcoming submission deadline](https://www.acm.org/conferences/upcoming-submission-deadlines)
- [Lucjaulmes](https://lucjaulmes.github.io/core-cfp/)

특정 분야에 한정하여 리스트 정리한 사이트
- [Systems](http://www.cs.technion.ac.il/~dan/index_sysvenues_deadline.html)
- [AI](https://jackietseng.github.io/conference_call_for_paper/conferences.html) 
