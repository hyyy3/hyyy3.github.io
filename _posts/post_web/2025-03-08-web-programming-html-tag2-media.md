---
title: "[HTML5] HTML 기초 - 태그 기본2 - 미디어"
excerpt: "html"

categories:
  - Web
tags:
  - [study]

permalink: /blog/programming/web/html_2

toc: true
toc_sticky: true

published : true

date: 2025-03-08 12:01:01+0900
last_modified_at: 2025-03-08 20:01:01+0900
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

## 이미지
- 이미지는 **&lt;img&gt;** 태그로 정의된다.
- **src 속성** 으로 이미지 파일 이름을 지정하고, **width, height** 속성으로 이미지의 가로,세로 크기를 지정할 수 있다.