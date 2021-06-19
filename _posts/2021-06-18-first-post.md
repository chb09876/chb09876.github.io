---
title: "github.io 블로그 첫 글"
excerpt: "github.io 배우고 있습니다"

categories:
  - Blog
tags:
  - Blog
last_modified_at: 2021-06-18-T08:06:00-05:00
---

github blog 서비스인 github.io 블로그를 사용  
github blog 서비스의 이름은 Pages이다.

YFM에서 정의한 제목을 이중 괄호 구문으로 본문에 추가할 수 있다.
이 글의 제목은 '{{page.title}}'이고
마지막으로 수정된 시간은 {{page.last_modified_at}}이다.

Jekyll이 해석하는 YFM(YAML Fornt Matter) 포맷이 있다.
YFM은 markdown 파일의 최상단에 위치하며 3개의 하이픈(---)으로 시작과 끝을 표시한다.
YAML은 오픈소스프로젝트에서 많이 사용하는 구조화된 데이터 형식.
YFM은 이 YAML을 이용해 글의 제목, 날짜, 카테고리, 태그, 레이아웃 등을 정의할 수 있다.
