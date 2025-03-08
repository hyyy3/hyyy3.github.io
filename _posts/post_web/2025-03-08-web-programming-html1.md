---
title: "[HTML5] HTML 기초 - 기본 구조"
excerpt: "html"

categories:
  - Web
tags:
  - [study]

permalink: /blog/programming/web/html_0

toc: true
toc_sticky: true

published : true

date: 2025-03-08 10:00:01+0900
last_modified_at: 2025-03-08 19:05:01+0900
---

## HTML이란 ? 
- Hypertext Markup Language, WWW 에서 사용하는 마크업 언어
- 용량이 매우 작음, 하이퍼링크 기능을 사용하여 문서 간 이동 가능
- 인터넷 망에서 샤용되는 웹 페이지 구조를 표현하기 위한 언어
- 웹 브라우저는 HTML 문서에서 태그를 해석하여 해석된 내용으로 출력한다.

## HTML5
- CSS3 스타일시트 지원
- 별도의 플러그인 없이 미디어 재생 가능
- 2차원, 3차원 그래픽 구현 가능
- Sementic Web 구현
- 웹 애플리케이션 개발에 사용 - 운영체제에 독립적인 애플리케이션 제작 가능
* 참고, 네이티브 앱, 모바일 앱, 하이브리드 앱, 웹 앱

<hr>

## HTML 문서의 기본 구조
```html
<!DOCTYPE HTML>           <!-- 각각의 역할은 밑에서 바로 설명합니다 -->
<html>
    <head>
        <title> 제목 </title>
    </head>

    <body>
    ...
    </body>

</html>
```
- 이 html 기본 구조 안에 여러 요소(태그 등)을 넣게 된다.
- **요소란?** <br>

```html
<title>이 웹페이지의 제목</title>
```
이 있다면, <title>, </title> 태그가 요소, 태그 사이에 내용을 넣는 것이다.

- 태그는 대소문자를 구분하지 않는다.
- **태그는 교차될 수 없다.**

```html
<p> 이렇게  <em> 태그를 교차하게 되면 </p> 화면에 표시되지 않습니다 </em>

<p><em> 이런 방식으로 사용해야 합니다. </em></p>

```
<br><br>

### 속성
- 속성은 요소에 대해 추가적인 기능 제공
- 항상 시작태그에 **이름="값"** 과 같이 기술해야 한다.
```html
<a href = "https://www.naver.com">네이버 링크</a>
```
<br><br>

### HTML의 주석
```html
<!-- 여기에 주석 처리할 내용 입력 -->
<!-- 대부분의 프로그래밍 언어에서 쓰는 /* */ 라고 생각하면 됩니다 -->
```
<br><br>

### <!DOCTYPE> 선언
```html
<!DOCTYPE html>
```
- html 문서를 보면 항상 위 문구로 시작하는 것을 볼 수 있다.
- 이 선언은, **이 문서가 html5 라는 것을** 웹 브라우저 등에 알려준다.
<br><br>

### <head>
- HTML은 head와 body로 구분되는데, <head> 태그는 **HTML 문서의 메타데이터**를 포함한다.
- 메타데이터는 화면에 직접 표시되지 않는 부분이며, 웹 페이지의 동작과 스타일을 설정하는 역할을 하게 된다.
- **<head> 예시**

```html
<head>
<meta charset="UTF-8">  <!-- 문자 인코딩 설정 -->
<meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- 반응형 디자인 설정 -->
<title>웹페이지 제목</title> <!-- 브라우저 탭 제목 -->
<link rel="stylesheet" href="styles.css"> <!-- 외부 CSS 파일 -->
<script src="script.js" defer></script> <!-- 외부 JavaScript 파일 -->
</head>
```

<br><br>

### <body>
- HTML에서 화면에 표시되어 사용자가 볼 수 있는 모든 요소를 포함한다.
- **<body> 예시**

```html
<body>
<h1>안녕하세요!</h1> <!-- 웹페이지의 제목 -->
<p>이곳은 HTML 문서의 본문입니다.</p> <!-- 본문 텍스트 -->
<img src="image.jpg" alt="이미지 설명"> <!-- 이미지 삽입 -->
<a href="https://www.naver.com">네이버 링크</a> <!-- 링크 -->
</body>
```