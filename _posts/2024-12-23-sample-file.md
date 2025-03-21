---
title: "blog test용 샘플 파일"
excerpt: "NP"

categories:
  - Projects
tags:
  - [study]

permalink: /blog/project/projects/sample

toc: true
toc_sticky: true

date: 2024-12-22 10:00:01+0900
last_modified_at: 2024-12-23 02:05:01+0900
---


## This is just TESTFILE
## This is just TESTFILE

## 10. NIO 개요

### 강의 내용
```
- NIO 패키지 소개
- Blocking Java IO
- IO 향상을 위한 운영체제 수준의 기술
- Java의 변화
```

#### NIO 패키지
- JDK 1.4에서 새로 추가, Java 성능 개선
- Non Blocking IO 지원
- 제공되는 기능:
    - **버퍼 관리 클래스**  
      효율적인 데이터 관리를 위한 버퍼 관리 기능을 제공합니다.
    - **채널 기반의 확장된 네트워크 및 파일 IO**  
      네트워크와 파일 입출력을 확장된 채널 기반 구조로 처리할 수 있습니다.
    - **문자집합 지원**  
      다양한 문자집합(Charset)을 지원하여 텍스트 데이터 처리의 유연성을 제공합니다.
    - **정규식 문자 표현에 새로운 특징들과 개선된 성능 제공**  
      정규 표현식(Regex)의 새로운 기능과 향상된 성능으로 문자열 처리를 더욱 빠르고 강력하게 수행합니다.

      
- NIO 패키지의 구성 개요(간단히):
  - **package** : channels, charset, file
  - **class** : Buffer, 관련 클래스
- spi : Service Provider Interface, 프로그래머가 제공하는 클래스로 대체할 수 있는 기능을 제공 (추상 클래스로 되어있다.)

#### Blocking Java IO
- Blocking 자바 IO 영역
  - **User 영역, Kernel 영역**  (OS의 그것이다)
  - **User** : 일반적인 프로세스들이 존재하는, 제한된 권한을 갖는 영역
  - **Kernel** : 운영체제에 존재하는 영역, h/w에 직접적으로 접근하고 다른 프로세스를 제어할 수 있는 권한을 가짐


- 그런데, 모든 IO는 반드시 Kernel 영역을 직간접적으로 가짐.

  - **파일 읽기 시도에서**
    > 1. 프로세스를 JVM으로 가정 (파일 읽기 시도에서) 커널에 명령 전달 
    > 2. 커널이 read() 시스템 콜을 사용해서 읽어온 데이터를 커널 버퍼에 저장 
    > 3. 모든 파일 데이터가 커널 안의 버퍼로 복사되면 JVM(프로세스) 안의 버퍼로 복사 시작

- 즉, Java의 버퍼를 통해 데이터를 직접 가져오는 것이 아니라, 커널 영역의 버퍼와 연결하여 수신을 함

<br>

- Java 파일 읽기의 비효율성
    > - 커널 영역의 버퍼에서 프로세스(User) 영역 안의 버퍼로 데이터를 복사하는 점
    > > - 물리적 디스크에서, 커널 영역 버퍼로 데이터 저장하는 것은 DMA 기술로 CPU 도움 없이 처리 가능
    > > - 커널 영역에서 프로세서 영역 버퍼로의 데이터 전달은 *CPU* 관여
    > > - 커널 영역의 버퍼에 저장된 데이터를 직접 사용 하면 복사 시간 단축, 복사 대상의 데이터 가비지 컬렉션 불필요, CPU 자원의 효율성 향상
    > - 디스크 컨트롤러에서 커널 영역의 버퍼로 데이터를 복사하는 동안 프로세스 영역은 블로킹 되는 점 
    > >디바이스의 파일 데이터를 커널 영역 안의 버퍼로 복사할 때 까지 Java 프로세스는 Blocking

#### IO 향상을 위한 운영체제 수준의 기술
- Buffer
  - 버퍼 : 효율적으로 데이터를 전달하기 위한 객체, 데이터를 한개씩 여러 번 보내는 것보다는<br> 버퍼를 두고 데이터를 모아 한 번에 보내는 것이 효율적임
  - 운영체제를 포함하여, 데이터를 전송하는 곳에서는 대부분 버퍼를 기본적으로 사용

- > 다음 예제로 버퍼 사용에 따른 성능차이 확인
  > > **CopyNonBuf [None], CopySmallBuf [1024],  CopyLargeBuf [filesize]**
  > > <br> 실행: **BufferTime** 
  > > <br> 실행 결과(복사 시간): **Large-Buffer >> Small Buffer >>>>> non-buffer**
  
- Scatter / Gather
  - 예를 들어, Java 프로그램 안에 버퍼 3개를 만들어 사용 하는데 <br>
  만약 동시에 각각의 데이터를 읽거나 쓰면 System call이 3 번 발생 (상당히 비효율적) <br>
  - 그래서 **시스템 콜을 한 번만 호출**하기 위해 **Scatter / Gather** 사용 <br>
  - java.nio.channels 에 있는 ScatteringByteChannel, GatheringByteChannel 인터페이스 사용


적용예 :   

> This is a first
>   > This is a second 
>   >   > This is a third 

- 가상 메모리
  - 프로그램에서 가상메모리를 사용하게 되면 유저 영역 버퍼와 커널 영역 버퍼를 mapping 시킴으로써 커널 영역에서 유저 영역으로 데이터를 복사하지 않아도 된다.
  - 디스크 컨트롤러부터 읽어온 데이터를 커널 영역에 전달하는 것은 곧 동시에 유저 영역 버퍼에 저장하는 것이다.

- 매모리 맵 파일
  - 빈번한 시스템 콜, 커널 영역과 유저 영역의 불필요한 복사가 계속되면 많은 가비지 발생
  - 가비지를 제거하는 것은 상당히 느린 작업이다.
  - 이 문제점을 해결하기 위해 Memmory-Mapped IO 이용
  - 사용시 장점
    - 1. read(), write() 등의 시스템 콜 불필요
    - 2. 매우 큰 파일을 복사하기 위한 많은 양의 메모리 소비를 하지 않음


- 파일락
  - 동기화 비슷한 개념
  - 한 프로세스가 어떤 파일에 락(lock) 획득시 다른 프로세스가 동시에 파일로 접근하는 것을 막거나 또는 접근 방식에 제한을 두는 것
  - 파일락은 크게 공유(shared) lock 과 배타(exclusive) lock이 있다.
  - shared lock은 읽기작업에, exclusive lock은 쓰기 작업에 사용