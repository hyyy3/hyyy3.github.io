---
title: "[CSS3] CSS3 기초 - CSS3 선택자"
excerpt: "html"

categories:
  - Web
tags:
  - [study]

permalink: /blog/programming/web/css3_post2

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
## CSS3 기본 선택자
### 전체 선택자
```css
*   /* 전체 선택자 */
```
전체 선택자는 html 안의 모든 사용 가능한 요소에 대해 선택자로 지정합니다. <br>

예시: 모든 적용 가능한 속성의 폰트 크기를 20px로 늘리고, 볼드체로 하고, 색상을 파란색으로 적용해보자 
```css
* {
  font-size: 20px;
  font-weight: bold;
  color: #0000ff;
}
```

다만, 전체 선택자는 우선순위에서 밀리게 됩니다. 
<br><br>
### 태그 선택자
특정 태그에 대해서 적용합니다. <br>
시멘틱 테그나 div, span과 같은 구조적 태그 정의를 사용할 수 있습니다.<br>

아래는 위 예제를 p 태그에 대해서만 적용하도록 수정한 것입니다. 
```css
p {
  font-size: 20px;
  font-weight: bold;
  color: #0000ff;
}
```
<br><br>
### id 선택자
id속성값 앞에 #를 붙입니다. <br>
만약 앞의 예제에서 p 태그의 id 속성이 "idid" 라면, 다음과 같이 적용하면 id가 "idid"인 속성에만 적용됩니다. <br> 물론 id는 class와 달리 하나의 요소에만 지정됩니다.

```css
#idid {
  font-size: 20px;
  font-weight: bold;
  color: #0000ff;
}
```
<br><br>
### class 선택자
class속성값 앞에 .를 붙입니다. <br>
만약 앞의 예제에서 class 속성이 "classclass" 라면, 다음과 같이 적용하면 class가 "classclass"인 속성에만 적용됩니다. <br> **class는 여러 요소가 같은 class 이름을 가질 수 있습니다.** <br>
만약 특정 p, div, nav에 classclass라는 속성 이름이 지정되었다면, 아래 스타일은 해당 요소에 모두 적용됩니다.

```css
.classclass {
  font-size: 20px;
  font-weight: bold;
  color: #0000ff;
}
```
<br><br>

### 기본 속성 선택자
대괄호 [] 안에는 속성 선택자를 사용합니다. 조건부로 적용하기 위해 주로 사용합니다. <br>
**예시1: target이 "_blank"인 &lt;a&gt; 요소에만 적용**
```css
a[target="_blank"] {
  /* style */
}
```
<br>
**예시2: &lt;a&gt; 중 class가 "classclass"인 요소에만 적용**
```css
a[class="classclass"] {
  /* style */
}
```

<br>
**예시3: id가 지정된 모든 요소에 대해 적용**
```css
[id] {
  /* style */
}
```

<br>

속성값으로 주어진 특정 문자열에 대해서도 조건을 적용할 수 있습니다.

<details>
  <summary><h4 style="display:inline;">📌 클릭하여 CSS 문자열 속성 선택자 형식 보기</h4></summary>

  <br>

  <table border="1" cellspacing="0" cellpadding="6">
    <thead>
      <tr>
        <th>선택자 형식</th>
        <th>설명</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>[attr="value"]</td>
        <td>attr 속성 값이 정확히 value인 요소를 선택</td>
      </tr>
      <tr>
        <td>[attr~="value"]</td>
        <td>attr 속성 값이 공백으로 구분된 단어 중 하나가 value인 요소를 선택</td>
      </tr>
      <tr>
        <td>[attr|="value"]</td>
        <td>attr 속성 값이 정확히 value이거나 value로 시작하고 하이픈(-)으로 연결된 요소를 선택</td>
      </tr>
      <tr>
        <td>[attr^="value"]</td>
        <td>attr 속성 값이 value로 시작하는 요소를 선택</td>
      </tr>
      <tr>
        <td>[attr$="value"]</td>
        <td>attr 속성 값이 value로 끝나는 요소를 선택</td>
      </tr>
      <tr>
        <td>[attr*="value"]</td>
        <td>attr 속성 값에 value가 포함된 요소를 선택</td>
      </tr>
    </tbody>
  </table>

</details>

<br><br>
## CSS3 조합 선택자