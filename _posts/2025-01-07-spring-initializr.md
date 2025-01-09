---
title: "Spring - Initializr"
excerpt: "Spring"

categories:
  - Spring
tags:
  - [study]

permalink: spring/initializr

toc: true
toc_sticky: true

published : true

date: 2025-01-07 10:00:01+0900
last_modified_at: 2025-01-07 02:05:01+0900
---



## **Spring Initializr로 프로젝트 생성하기**

<img src="{{ site.baseurl }}/assets/images/spring/sample_initspring.jpg" alt="Spring Initializr" width="600" height="450">

[Spring Initializr](https://start.spring.io)에 접속하면 위와 같은 설정 화면이 보일 것이다.
각 항목의 요소는 다음과 같습니다.

---

### **Project**
**Maven**, **Gradle** 중 원하는 빌드 도구를 선택한다.

---

### **Language**
사용할 언어를 선택한다. 거의 대부분 Java일 것이고, Kotlin을 사용하는 경우도 있다.

---

### **Spring Boot**
사용할 **Spring Boot 버전**을 선택한다. SNAPSHOT이 아닌 버전을 고르면 된다.
참고로 2025년 현재 Spring Boot 3 이전 버전은 지원하지 않는다. 그래서 Java 17 이상이 필요하다.

---

### **Project Metadata**


| 항목            | Description                                                      |
|-----------------|-----------------------------------------------------------|
| **Group**       | 프로젝트의 그룹 ID. 일반적으로 **도메인 역순**으로 작성합니다. 예: `com.example` |
| **Artifact**    | 프로젝트의 식별자이며, 기본적으로 생성될 **JAR 파일 이름**입니다. |
| **Name**        | 프로젝트 이름. 주로 Artifact와 동일하게 설정합니다. |
| **Description** | 프로젝트에 대한 간단한 설명입니다.                        |
| **Package Name**| 기본 패키지 이름이다. Group과 Artifact를 조합하여 설정됩니다. |
| **Packaging**   | 프로젝트의 출력 형태를 선택합니다. <br> - **JAR**: 일반적으로 Spring Boot 프로젝트는 JAR로 배포합니다. <br> - **WAR**: 서블릿 컨테이너에서 동작하는 Web Application Archive 형태입니다. |
| **Java**        | 사용할 **Java 버전**을 선택한다. 현재 17이나 21 버전이 권장된다. |

---

### **Dependencies**
필요한 **의존성(Dependencies)**을 추가한다. 
여기서 추가하지 않고, 직접 빌드 설정 파일에서 입력하거나, 필요 시 추가해도 된다. 
- 의존성은 Spring Boot 애플리케이션에서 사용할 라이브러리 모음입니다.
- 주요 의존성 예시:
  - **Spring Web**: RESTful 웹 애플리케이션을 개발할 때 필요한 의존성입니다.
  - **Spring Data JPA**: 데이터베이스와의 연동을 위한 ORM(Object-Relational Mapping) 라이브러리입니다.
  - **Spring Security**: 인증 및 권한 부여를 위한 보안 프레임워크입니다.
  - **Thymeleaf**: 서버 사이드 템플릿 엔진으로, HTML 뷰를 렌더링할 때 사용됩니다.

---

모든 설정을 완료한 후 **"Generate"** 버튼을 클릭하면 위 설정 내용에 따라 zip 파일로 다운로드 받을 수 있다.
압축을 푼 폴더를를 IDE (IntelliJ IDEA / Eclipse)에서 열면 기본 설정은 끝난다.

