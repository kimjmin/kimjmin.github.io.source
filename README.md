ELASTICSEARCH KOREA
===================

[![Build Status](https://travis-ci.org/kimjmin/kimjmin.github.io.source.svg?branch=master)](https://travis-ci.org/kimjmin/kimjmin.github.io.source)


HOW TO CONTRIBUTE
-----------------

### 1. 준비 ###

- Node.js
- Bower
- Docpad

[Node.js](http://nodejs.org/)를 설치한 후,
Bower와 Docpad를 다음과 같이 설치하면 된다.

```
npm install -g bower
npm install -g docpad
```

### 2. 진짜 준비 ###

소스코드를 **체크아웃** 한 후,
`npm install`과 `bower install`를 수행한다.

```
git clone https://github.com/kimjmin/kimjmin.github.io.source.git
cd kimjmin.github.io.source
npm install
bower install
```

### 3. 로컬 실행 ###

DocPad로 **실행**해 본다.

```
docpad run
```

브라우저를 띄워 다음 주소로 확인하면 된다.

[http://localhost:9778/](http://localhost:9778/)

### 4. 프리젠테이션 추가 ###

프리젠테이션 기능은 [Reveal.js](http://lab.hakim.se/reveal-js/)를 이용해 만들어졌다.
Reveal.js를 이용한 프리젠테이션 작성 방법을 미리 숙지하기를 바란다.

먼저 `src/documents/presentations` 디렉토리에 새로운 HTML 파일을 추가한다.
예제로 포함되어 있는 `2014-04-22-sample.html` 파일을 복사해서 만들면 된다.
관리를 위해서 파일 이름 형식을 샘플과 같이 _날짜와 제목을 결합한 형태_로 만드는 것이 좋겠다.

그리고 **헤더**를 변경하자. 아래 부분이 헤더 부분이다.

```
---
title: Reveal.js Sample
description: Reveal.js - The HTML Presentation Framework
date: 2014-04-22
author: Reveal.js
layout: presentation
theme: default
transition: default
---
```

`title`, `description`, `date` 및 `author`는 임의로 설정하면 되지만,
`layout`는 반드시 `presentation`이어야 한다.

`theme`은 디자인 테마로, 다음 값 중에서 선택 가능하다.

- default
- beige
- blood
- moon
- night
- serif
- simple
- sky
- solarized

`transition`은 페이지 전환 방법으로, 다음 값 중에서 선택 가능하다.

- default
- cube
- page
- concave
- zoom
- linear
- fade
- none

마지막으로 **내용**을 작성하면 된다.

```
<section>
  <h1>Reveal.js</h1>
  <h3>HTML Presentations Made Easy</h3>
  <p>
    <small>Created by <a href="http://hakim.se">Hakim El Hattab</a> / <a href="http://twitter.com/hakimel">@hakimel</a></small>
  </p>
</section>
```

이렇게 하나의 `section` 태그로 하나의 프리젠테이션 페이지를 만들 수 있다.
자세한 내용은 샘플 프리젠테이션이나 Reveal.js 홈페이지를 참고하라.

그리고 참고로 `index.html` 페이지에 따로 링크를 추가할 필요는 없다.
자동으로 추가가 될 것이므로. +\_+

작업할 때 `docpad run` 명령으로 서버를 실행해 놓으면,
`livereload`가 동작해 파일을 수정할 때 마다 변경 사항을 반영하고 브라우저를 새로 고침해 준다. +\_+

하지만 약간의 딜레이가 있으니 조금 기다려야 한다.
_만약 `livereload`가 동작하지 않는다면 묻고 따지지 말고 그냥 그런가보다 하고 브라우저를 직접 새로 고침하길 바란다._

##### 이미지와 첨부 파일 #####

만약 이미지와 첨부 파일을 포함하는 경우에는 반드시 **절대 경로**를 사용하자.

예를 들어, `src/documents/presentations` 디렉토리에 작업 중인 HTML 파일이 있고,
`src/documents/presentations/images` 디렉토리에 이미지나 첨부 파일이 있다고 하자.

이 때, HTML 파일에서 `images/...`으로 접근할 경우엔,
로컬에서는 잘 되지만 서버에 반영할 경우 제대로 동작하지 않는다.
서버 반영 시 DocPad의 Cleanurl 플러그인이 디렉토리 구조를 변경하기 때문이다.

그러므로 이 경우엔 반드시 `/presentations/images/...`으로 접근해야 한다.

### 5. 반영 ###

작성 완료하면 이제 서버에 반영을 해야겠지.
변경 사항을 `master` 브랜치에 반영해 푸시하면 Travis-CI가 자동으로 빌드 후 배포할 것이다.

참고로 Travis-CI에서 빌드되는 속도는 느리다. 제법 느리다.
대신 빌드 상황을 실시간으로 조회할 수 있다.
다음 주소에서 조회하면 된다.

[https://travis-ci.org/kimjmin/kimjmin.github.io.source](https://travis-ci.org/kimjmin/kimjmin.github.io.source)

그리고 배포되는 리포지토리의 주소는 다음과 같다.

[https://github.com/kimjmin/kimjmin.github.io](https://github.com/kimjmin/kimjmin.github.io)

또, 배포가 완료되면 다음 주소에서 조회할 수 있다.

[http://kimjmin.github.io/](http://kimjmin.github.io/)


TECHNOLOGY
----------

이 사이트는 다음 기술들을 이용해 만들어졌다.

- [DocPad](http://docpad.org/)
- [Node.js](http://nodejs.org/)
- [Bower](http://bower.io/)
- [Bootstrap](http://getbootstrap.com/)
- [CoffeeScript](http://coffeescript.org/)
- [Jade](http://jade-lang.com/)
- [Stylus](http://learnboost.github.io/stylus/)
- [highlight.js](http://highlightjs.org/)
- [reveal.js](http://lab.hakim.se/reveal-js/)
- ...


LICENSE
-------

The MIT License (MIT)

Copyright (c) 2014 Elasticsearch Korea

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
