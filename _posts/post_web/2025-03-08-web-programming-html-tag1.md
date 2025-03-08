---
title: "[HTML5] HTML 기초 - 태그 기본1"
excerpt: "html"

categories:
  - Web
tags:
  - [study]

permalink: /blog/programming/web/html_1

toc: true
toc_sticky: true

published : true

date: 2025-03-08 12:00:01+0900
last_modified_at: 2025-03-08 20:00:01+0900
---

<style>
    table {
        width: 100%; /* 테이블을 페이지 전체 너비에 맞춤 */
        border-collapse: collapse; /* 테두리 겹침 제거 */
        border: 0px solid #000;
        table-layout: fixed;
    }
    th, td {
        border: 1px solid #000; /* 테두리 추가 */
        padding: 10px; /* 내부 여백 */
        text-align: left; /* 텍스트 왼쪽 정렬 */
        word-wrap: break-word; /* 긴 단어 자동 줄바꿈 */
    }
    th {
        background-color: #f4f4f4; /* 헤더 배경색 */
        font-weight: bold;
    }
</style>

<!-- <br> <a></a> -->


## 본문에 텍스트 작성하기
- 기본적으로, body 태그 안에 본문을 작성합니다.

```html
...
<body>
body 태그 안에 특별한 태그 없이도 텍스트를 바로 작성할 수 있습니다.
그런데, 단락을 사용하지 않으면, 실제로 줄 바꿈이 적용되지 않습니다.
</body>
```


## 단락
- 단락(paragraph)는 **<p>...</p>** 태그로 정의됩니다.
- 단락을 사용하면, 웹 브라우저는 자동으로 단락의 전후에 빈 줄을 추가합니다.

```html
...
<body>
<p>이렇게 하면 p 태그 안의 내용은 하나의 단락이 됩니다.</p>
<p>실제로 이 단락은 바로 위 단락의 다음 줄부터 출력됩니다.</p>
</body>
```

## 줄 바꾸기
- **&lt;br&gt;** 태그를 사용하여 줄을 바꿀 수도 있습니다. 주로 하나의 단락 안에서 사용하거나, 빈 줄을 추가할 때 사용합니다.

```html
...
<body>
<p>이렇게<br>단락 안에서도<br>break 태그로 줄 바꿈을<br>할 수 있습니다.</p>
<br><br>
<p>위 단락은 총 4줄이며, 단락 간 빈 줄을 추가할 수도 있습니다.</p>
</body>
```

<br><br>
- 기본적으로 **HTML 코드에서 space bar로 줄 바꿈을 할 수 없습니다.**
- 다만, <pre> 태그 안에 작성한다면, space나 tap 등 입력한 그대로 출력할 수 있습니다.

```html
...
<body>
<pre>
pre 태그를 사용하면

이렇게 space bar로 줄바꿈해서 작성한 html 파일도


줄 바꿈이 적용되어 출력됩니다.
</pre>
</body>
```


## Heading
- h1부터 h6까지 6가지 종류의 태그로 작성 가능
- h1이 가장 큰 텍스트 사이즈, h6이 가장 작은 텍스트 사이즈이다.
<hr>
<h1>h1로 작성한 텍스트입니다. (가장 큰 텍스트)</h1>
<h6>h6로 작성한 텍스트입니다. (가장 작은 텍스트)</h6>
<hr>

```html
<body>
<h1>h1로 작성한 텍스트입니다. (가장 큰 텍스트)</h1>
<h2>h2로 작성한 텍스트입니다.</h2>
<h3>h3로 작성한 텍스트입니다.</h3>
<h4>h4로 작성한 텍스트입니다.</h4>
<h5>h5로 작성한 텍스트입니다.</h5>
<h6>h6로 작성한 텍스트입니다. (가장 작은 텍스트)</h6>
</body>
```

## 텍스트 서식
```html
<b>...</b> <!-- 볼드체로 만든다 -->
<i>...</i> <!-- 이탤릭체로 만든다 -->
<strong>...</strong> <!-- 텍스트를 강하게 표시한다 -->
<em>...</em> <!-- 텍스트를 강조한다 -->
<code>...</code> <!-- 텍스트가 코드임을 표시한다 -->
<sup>...</sup> <!-- 위첨자(superscript) -->
<sub>...</sub> <!-- 아래첨자(subscript) -->
```

- 사용 예시
<blockquote style="background-color: #f5f5f5; padding: 10px; border-left: 4px solid #ccc; font-style: normal;">
    <b>볼드체로 만든다</b><br>
    <i>이탤릭체로 만든다</i><br>
    <strong>strong 텍스트</strong><br>
    <em>emphasized 텍스트</em><br>
    <code>This text is code</code><br>
    <sup>subscript</sup> 와 <sub>superscript</sub><br>
</blockquote>

<br>

## 수평선 : <hr> 사용

```html
<p>수평선은 horizontal line 입니다.</p>
<p>바로 아래 수평선이 있습니다.</p>
<hr>      <!-- 수평선을 추가하고 줄을 바꿉니다. -->
<p>바로 위에 수평선이 있습니다.</p>
```


## 특수 문자
<table>
    <thead>
        <tr>
            <th>HTML 코드</th>
            <th>실제 문자</th>
            <th>설명</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>&amp;lt;</td>
            <td>&lt;</td>
            <td>Less Than (작다)</td>
        </tr>
        <tr>
            <td>&amp;gt;</td>
            <td>&gt;</td>
            <td>Greater Than (크다)</td>
        </tr>
        <tr>
            <td>&amp;amp;</td>
            <td>&amp;</td>
            <td>Ampersand (앤퍼샌드)</td>
        </tr>
        <tr>
            <td>&amp;quot;</td>
            <td>&quot;</td>
            <td>Quotation Mark (큰따옴표)</td>
        </tr>
        <tr>
            <td>&amp;apos;</td>
            <td>&apos;</td>
            <td>Apostrophe (작은따옴표)</td>
        </tr>
        <tr>
            <td>&amp;nbsp;</td>
            <td>(공백)</td>
            <td>Non-Breaking Space (줄바꿈 없는 공백)</td>
        </tr>
    </tbody>
</table>
<details>
  <summary>📌 클릭하여 더 자세한 표 보기</summary>
<br>
<table>
    <thead>
        <tr>
            <th>HTML 코드</th>
            <th>실제 문자</th>
            <th>설명</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>&amp;lt;</td>
            <td>&lt;</td>
            <td>Less Than (작다)</td>
        </tr>
        <tr>
            <td>&amp;gt;</td>
            <td>&gt;</td>
            <td>Greater Than (크다)</td>
        </tr>
        <tr>
            <td>&amp;amp;</td>
            <td>&amp;</td>
            <td>Ampersand (앤퍼샌드)</td>
        </tr>
        <tr>
            <td>&amp;quot;</td>
            <td>&quot;</td>
            <td>Quotation Mark (큰따옴표)</td>
        </tr>
        <tr>
            <td>&amp;apos;</td>
            <td>&apos;</td>
            <td>Apostrophe (작은따옴표)</td>
        </tr>
        <tr>
            <td>&amp;nbsp;</td>
            <td>(공백)</td>
            <td>Non-Breaking Space (줄바꿈 없는 공백)</td>
        </tr>
        <tr>
            <td>&amp;copy;</td>
            <td>&copy;</td>
            <td>Copyright (저작권)</td>
        </tr>
        <tr>
            <td>&amp;reg;</td>
            <td>&reg;</td>
            <td>Registered Trademark (등록 상표)</td>
        </tr>
        <tr>
            <td>&amp;trade;</td>
            <td>&trade;</td>
            <td>Trademark (상표)</td>
        </tr>
        <tr>
            <td>&amp;cent;</td>
            <td>&cent;</td>
            <td>Cent (센트)</td>
        </tr>
        <tr>
            <td>&amp;pound;</td>
            <td>&pound;</td>
            <td>Pound (파운드)</td>
        </tr>
        <tr>
            <td>&amp;yen;</td>
            <td>&yen;</td>
            <td>Yen (엔화)</td>
        </tr>
        <tr>
            <td>&amp;euro;</td>
            <td>&euro;</td>
            <td>Euro (유로화)</td>
        </tr>
        <tr>
            <td>&amp;deg;</td>
            <td>&deg;</td>
            <td>Degree (도)</td>
        </tr>
        <tr>
            <td>&amp;plusmn;</td>
            <td>&plusmn;</td>
            <td>Plus-Minus (플러스 마이너스)</td>
        </tr>
        <tr>
            <td>&amp;times;</td>
            <td>&times;</td>
            <td>Multiplication (곱하기)</td>
        </tr>
        <tr>
            <td>&amp;divide;</td>
            <td>&divide;</td>
            <td>Division (나누기)</td>
        </tr>
        <tr>
            <td>&amp;sum;</td>
            <td>&sum;</td>
            <td>Summation (시그마, 합계)</td>
        </tr>
        <tr>
            <td>&amp;infin;</td>
            <td>&infin;</td>
            <td>Infinity (무한대)</td>
        </tr>
        <tr>
            <td>&amp;alpha;</td>
            <td>&alpha;</td>
            <td>Greek Alpha (알파)</td>
        </tr>
        <tr>
            <td>&amp;beta;</td>
            <td>&beta;</td>
            <td>Greek Beta (베타)</td>
        </tr>
        <tr>
            <td>&amp;gamma;</td>
            <td>&gamma;</td>
            <td>Greek Gamma (감마)</td>
        </tr>
        <tr>
            <td>&amp;delta;</td>
            <td>&delta;</td>
            <td>Greek Delta (델타)</td>
        </tr>
        <tr>
            <td>&amp;pi;</td>
            <td>&pi;</td>
            <td>Greek Pi (원주율)</td>
        </tr>
        <tr>
            <td>&amp;radic;</td>
            <td>&radic;</td>
            <td>Square Root (제곱근)</td>
        </tr>
        <tr>
            <td>&amp;hearts;</td>
            <td>&hearts;</td>
            <td>Heart Symbol (하트)</td>
        </tr>
        <tr>
            <td>&amp;spades;</td>
            <td>&spades;</td>
            <td>Spade Symbol (스페이드)</td>
        </tr>
        <tr>
            <td>&amp;clubs;</td>
            <td>&clubs;</td>
            <td>Club Symbol (클로버)</td>
        </tr>
        <tr>
            <td>&amp;diams;</td>
            <td>&diams;</td>
            <td>Diamond Symbol (다이아몬드)</td>
        </tr>
    </tbody>
</table>

</details>


## 리스트
- &lt;ul&gt; : 번호 없는 리스트 (unordered list)
- &lt;ol&gt; : 번호 있는 리스트 (ordered list)
<blockquote style="background-color: #f5f5f5; padding: 10px; border-left: 4px solid #ccc; font-style: normal;">
    <p><b>&lt;ol&gt; 태그에는 type 속성을 지정할 수 있다.</b></p>

    <details>
        <summary>📌 클릭하여 설명 보기 </summary>
    <table border="1">
    <thead>
        <tr>
            <th>타입 (type 속성)</th>
            <th>설명</th>
            <th>예제</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>type="1"</code></td>
            <td>숫자 리스트</td>
            <td>
                <ol type="1">
                    <li>첫 번째 항목</li>
                    <li>두 번째 항목</li>
                    <li>세 번째 항목</li>
                </ol>
            </td>
        </tr>
        <tr>
            <td><code>type="a"</code></td>
            <td>소문자 알파벳 리스트</td>
            <td>
                <ol type="a">
                    <li>첫 번째 항목</li>
                    <li>두 번째 항목</li>
                    <li>세 번째 항목</li>
                </ol>
            </td>
        </tr>
        <tr>
            <td><code>type="A"</code></td>
            <td>대문자 알파벳 리스트</td>
            <td>
                <ol type="A">
                    <li>첫 번째 항목</li>
                    <li>두 번째 항목</li>
                    <li>세 번째 항목</li>
                </ol>
            </td>
        </tr>
        <tr>
            <td><code>type="i"</code></td>
            <td>소문자 로마 숫자 리스트</td>
            <td>
                <ol type="i">
                    <li>첫 번째 항목</li>
                    <li>두 번째 항목</li>
                    <li>세 번째 항목</li>
                </ol>
            </td>
        </tr>
        <tr>
            <td><code>type="I"</code></td>
            <td>대문자 로마 숫자 리스트</td>
            <td>
                <ol type="I">
                    <li>첫 번째 항목</li>
                    <li>두 번째 항목</li>
                    <li>세 번째 항목</li>
                </ol>
            </td>
        </tr>
    </tbody>
    </table>
</details>
<details>
    <summary>📌 코드 블럭 보기</summary>
    <pre style="background-color: #f5f5f5; padding: 10px; border-left: 4px solid #ccc; font-size: 1em;">
&lt;ol type="1"&gt;
    &lt;li&gt;첫 번째 항목&lt;/li&gt;
    &lt;li&gt;두 번째 항목&lt;/li&gt;
    &lt;li&gt;세 번째 항목&lt;/li&gt;
&lt;/ol&gt;

&lt;ol type="a"&gt;
    &lt;li&gt;첫 번째 항목&lt;/li&gt;
    &lt;li&gt;두 번째 항목&lt;/li&gt;
    &lt;li&gt;세 번째 항목&lt;/li&gt;
&lt;/ol&gt;

&lt;ol type="A"&gt;
    &lt;li&gt;첫 번째 항목&lt;/li&gt;
    &lt;li&gt;두 번째 항목&lt;/li&gt;
    &lt;li&gt;세 번째 항목&lt;/li&gt;
&lt;/ol&gt;

&lt;ol type="i"&gt;
    &lt;li&gt;첫 번째 항목&lt;/li&gt;
    &lt;li&gt;두 번째 항목&lt;/li&gt;
    &lt;li&gt;세 번째 항목&lt;/li&gt;
&lt;/ol&gt;

&lt;ol type="I"&gt;
    &lt;li&gt;첫 번째 항목&lt;/li&gt;
    &lt;li&gt;두 번째 항목&lt;/li&gt;
    &lt;li&gt;세 번째 항목&lt;/li&gt;
&lt;/ol&gt;
    </pre>

</details>
    
</blockquote>

- &lt;li&gt; : 리스트 항목 (list)

```html
<ul>
    <li>번호 없는 리스트 항목1</li>
    <li>번호 없는 리스트 항목2</li>
    ...
</ul>

<ol>
    <li>번호 있는 리스트 항목1</li>
    <li>번호 있는 리스트 항목2</li>
    ...
</ol>
```

<details>
  <summary>📌 클릭하여 실제 출력 결과 보기</summary>
<ul>
    <li>번호 없는 리스트 항목1</li>
    <li>번호 없는 리스트 항목2</li>
</ul>

<ol>
    <li>번호 있는 리스트 항목1</li>
    <li>번호 있는 리스트 항목2</li>
</ol>
</details>

<br>

- 정의 리스트(definition lists) 

```html
<dl>
    <dt>California</dt>
    <dd>Los Angeles, Sacramento, San francisco</dd>
    <dt>Texas</dt>
    <dd>Houston, Austin, Dallas</dd>
</dl>
```

<details>
  <summary>📌 클릭하여 실제 출력 결과 보기</summary>
<dl>
    <dt>California</dt>
    <dd>Los Angeles, Sacramento, San francisco</dd>
    <dt>Texas</dt>
    <dd>Houston, Austin, Dallas</dd>
</dl>
</details>
<br><br>
<a id="linksection">-------이곳으로 이동했습니다.-------</a>
<br>
## 링크
- &lt;a&gt; 태그로 하이퍼링크를 정의한다. a는 anchor를 의미한다.
- href 속성은 hyper reffernce를 의미한다.
- target 속성은 링크 클릭 시, 페이지가 열리는 장소를 지정한다.
<table border="1">
    <thead>
        <tr>
            <th>속성</th>
            <th>설명</th>
            <th>예제</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>_blank</code></td>
            <td>새로운 탭(또는 창)에서 링크를 엽니다.</td>
            <td><a href="https://www.naver.com" target="_blank">네이버 링크</a></td>
        </tr>
        <tr>
            <td><code>_self</code></td>
            <td>현재 창(또는 현재 프레임)에서 링크를 엽니다. (기본값)</td>
            <td><a href="https://www.naver.com" target="_self">네이버 링크</a></td>
        </tr>
        <tr>
            <td><code>_parent</code></td>
            <td>부모 프레임에서 링크를 엽니다. (프레임이 없으면 <code>_self</code>와 동일)</td>
            <td><a href="https://www.naver.com" target="_parent">네이버 링크</a></td>
        </tr>
        <tr>
            <td><code>_top</code></td>
            <td>전체 창에서 링크를 엽니다. (프레임 구조를 무시하고 최상위 창에서 열림)</td>
            <td><a href="https://www.naver.com" target="_top">네이버 링크</a></td>
        </tr>
    </tbody>
</table>


```html
<!-- 새로운 창에서 네이버 홈으로 가는 링크를 설정한다 -->
<a href="https://www.naver.com" target="_blank">네이버 링크 바로가기</a>
```
<details>
  <summary>📌 클릭하여 실제 출력 결과 보기</summary>
<br>
<a href="https://www.naver.com" target="_blank">네이버 링크 바로가기</a>
<br>
</details>

- &lt;a&gt; 태그를 사용해 사용자를 **현재 페이지의 다른 위치**로도 이동시킬 수 있다.

```html
<a href="#linksection">링크 목차로 다시 이동합니다.</a>
```
<a href="#linksection">직접 해보기</a>

- 이메일 링크, 다운로드 링크

```html
<a href="mailto:(메일주소)?subject=Feedback">메일 보내기</a>
<a href="(파일 주소)">파일 다운로드</a>
```

## 이미지
- 이미지는 **&lt;img&gt;** 태그로 정의된다.
- **src 속성** 으로 이미지 파일 이름을 지정하고, **width, height** 속성으로 이미지의 가로,세로 크기를 지정할 수 있다.