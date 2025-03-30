---
title: "[CSS3] CSS3 기초 - CSS3이란?"
excerpt: "html"

categories:
  - Web
tags:
  - [study]

permalink: /blog/programming/web/css3_post1

toc: true
toc_sticky: true

published : true

date: 2025-03-08 12:01:01+0900
last_modified_at: 2025-03-08 20:01:01+0900
---


<link rel="stylesheet" href="{{ '/assets/css/post_main1.css' | relative_url }}">


<style>
</style>
<!-- <br> <a></a> -->

## CSS3이란?
  <blockquote>CSS3는 Cascading Style Sheets Level 3의 약자로, 웹 페이지의 디자인과 레이아웃을 정의하기 위한 CSS의 최신 표준 버전입니다. <br>
  CSS의 이전 버전인 CSS2.1의 기능을 확장하여 보다 강력하고 편리한 스타일링 기능을 제공합니다.</blockquote>
<br>
간단하게 말하면 **스타일을 도와주는 양식** 이라고 보면 되겠습니다. <br>
CSS3은 현재도 개발중인 규격이지만, 대부분의 모듈과 속성들은 웹 브라우저에서 모두 지원한다고 생각하면 편합니다.


## CSS3 기본
### 기본 문법 형식

CSS3의 기본 문법 형식은 다음과 같다. 
<br>
<hr style="border: 1px solid #777777;">
```css3
Selector {
  property1: value1;
  property2: value2;
  ...
}
```
<hr style="border: 1px solid #777777;">

위와 같은 **선택자{속성:값}** 형태가 여러개 배치되어 CSS3 파일을 구성합니다. <br>
value까지 작성하면 반드시 세미콜론 **;**을 붙여주어야 합니다.
<br><br>
<p style="font-size:20px; font-weight:bold; color:#0000ff;"> 예시: 이 문장처럼 폰트 크기를 20px로 늘리고, 볼드체로 하고, 색상을 파란색으로 적용해보자 </p>

```css3
p {
  font-size: 20px;
  font-weight: bold;
  color: #0000ff;
}
```

다음과 같이 설정하면 **모든 p 태그에 대해, 20px 폰트 사이즈와 bold체, 텍스트 색상은 파란색**으로 적용되는 것을 알 수 있습니다.

#### 주석 달기

주석은 주요 프로그래밍 언어와 동일한 방식입니다. 다만 //을 통한 한줄 주석은 지원하지 않습니다.

```css3
CSS3에서 ..
/* annotation comments */
```

<br>
### CSS3 적용하기
css 양식은 크게 3가지 방식으로 적용 가능합니다.
- 외부 css 파일 이용
- 내부 style 시트 사용
- 인 라인 스타일 적용

#### 1. 외부 스타일 적용
html 파일 외부에 **확장자가 css**인 파일을 만들고, html에 css파일의 참조를 전달하는 방식입니다. <br><br>   

```html
<link rel="stylesheet" href="{파일 경로}.css">
```
다음과 같이 link 태그를 통해 css 파일을 html 문서에 전달합니다. <br>

예를 들어, **html 파일과 같은 디렉터리 위치에 있는 mystyle.css** 라는 외부 css 파일을 적용하려면, <br>
```html
<link rel="stylesheet" href="mystyle.css">
```


#### 2. 내부 스타일 시트 사용
html 문서의 head 안에, &lt;style&gt; 태그  내부에 직접 css 스타일을 설정하는 방식입니다. <br>
외부 스타일 시트와 같이, 해당 html 파일 전체에 적용됩니다.
<br><br>
예를 들어, 아까 해보았던 파란색 20px 볼드체를 html 안에서 적용한다면 다음과 같이 하면 됩니다.
```html
<head>
  ...
  <style>
    p {
      font-size: 20px;
      font-weight: bold;
      color: #0000ff;
    }
  </style>
  ...
</head>
```

#### 3. 인 라인 스타일 적용
html 특정 태그 내부에서 사용할 수 있습니다. <br>
전체 범위 적용에는 매우 번거롭기 때문에, 잘 쓰이지 않습니다. <br>
특정 태그에 대해서만 적용할 때에는 유리합니다.

```html
<tag style=" CSS code "></tag>
```

위의 내용을 인 라인 스타일에 적용하면 다음과 같습니다. 앞선 방식들은 모든 p 태그에 적용되지만, 이렇게 하면 해당 p에서만 적용됩니다.

```html
<p style="font-size: 20px; font-weight: bold; color: #0000ff;"></p>
```
<br>

<blockquote>만약 여러 CSS3 적용방식이 중복된다면, <strong>인 라인 범위 >> 내부 스타일 시트 >> 외부 스타일 시트</strong> 순으로 우선순위가 적용됩니다.<br> 즉, 인 라인 스타일 정의가 있다면 우선 적용되고, 없으면 style 태그를 찾고, 없으면 외부 css파일 참조를 찾고, 그래도 없으면 웹 브라우저의 기본 속성을 적용합니다. (어떤 속성은 적용되지 않습니다.)</blockquote>