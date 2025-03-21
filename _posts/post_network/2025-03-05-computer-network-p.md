---
title: "Computer Network - 1. 컴퓨터 네트워크와 인터넷"
excerpt: "Network"

categories:
  - Network
tags:
  - [study]

permalink: /blog/cs/network/post0

toc: true
toc_sticky: true

published : true

date: 2025-01-07 10:00:01+0900
last_modified_at: 2025-01-07 02:05:01+0900
---

 <style>
        body{
            font-family: 'GowunDodum-Regular';
        }
        h2 {
           font-family: 'BMHANNAAir';
            /* border: 2px solid blue;   파란색 테두리 */
            /* padding: 8px;            텍스트와 테두리 간격 */
            /* display: inline-block;    텍스트 크기에 맞는 테두리 */
            /* border-radius: 10px; 둥근 테두리 */
            /* display: inline-block;   텍스트 크기에 맞게 박스화 */
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin: 16px 0;
            font-size: 14px;
            text-align: left;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 10px;
        }
        th {
            background-color: #f4f4f4;
        }
        tr:nth-child(even) {
            background-color: #f9f9f9;
        }
    </style>


# 컴퓨터 네트워크 요약 1

## 인터넷이란 무엇인가?

인터넷은 전 세계적으로 수십억 개 이상의 장치들을 연결하는 **컴퓨터 네트워크**입니다.

### Host (End System)
- 인터넷에 연결되는 많은 장치들을 **호스트(End System)**라고 합니다.
- **Host = End System**
- 인터넷은 **"network of networks"**(네트워크들의 네트워크)입니다.
- **호스트는 ISP(인터넷 서비스 제공자)를 통해 인터넷에 접속합니다.**

### End System 연결 방식
End System은 **통신 링크**와 **패킷 스위치**의 네트워크로 연결됩니다.

- **각 ISP(인터넷 서비스 제공자)**는 통신 링크와 패킷 스위치로 이루어진 네트워크입니다.
- **통신 링크(Communication Link)**: 동축 케이블, 구리선(copper), 광케이블(fiber cable), 무선(radio), 위성(satellite) 등  
  - 각각의 링크는 서로 다른 전송률을 가집니다.
- **패킷 스위치(Packet Switch)**: 라우터(router), 링크 계층 스위치(link-layer-switch) 등

---

## 프로토콜 (Protocol)

네트워크에서 **프로토콜(Protocol)**은 필수적이며, 모든 통신 과정에서 사용됩니다.

### 프로토콜의 정의
**프로토콜은 둘 이상의 통신 개체 간에 교환되는 메시지의 형식과 순서뿐 아니라, 메시지의 송수신 및 특정 이벤트 발생 시의 행동을 정의합니다.**

<details>
  <summary>📌 프로토콜의 정의 (Eng)</summary>
  <p><strong>Protocols</strong> define the <strong>format</strong>, <strong>order</strong> of <strong>messages sent and received</strong> among network entities, and <strong>actions taken</strong> on message transmission and receipt.</p>
</details>

### 프로토콜의 예시
- **HTTP(Web), Streaming Video, Skype, TCP, IP, WiFi, 4G, Ethernet** 등 다양한 네트워크 환경에서 사용됩니다.

<details>
  <summary>📌 프로토콜: 사람과의 비교</summary>
  <ul>
    <li><strong>Human Protocols:</strong> 인사하기, 대화 순서 지키기</li>
    <li><strong>Network Protocols:</strong> 데이터 송수신의 규칙</li>
  </ul>
</details>

---

## Internet Standard

### RFCs (Requests for Comments)
- **RFCs**는 인터넷 표준을 정의하는 IETF(Internet Engineering Task Force) 문서
- **TCP, IP, HTTP, SMTP** 같은 핵심 프로토콜이 **RFCs**에서 정의되었다.

### IETF (Internet Engineering Task Force)
- 인터넷 표준을 개발하고 관리하는 기구

---

## Infrastructure that provides services to applications

### 분산 애플리케이션 (Distributed Application)
- Web, Streaming Video, Multimedia, Teleconferencing, Email, Games, E-Commerce, Social Media, Interconnected Appliances 등
- 이러한 애플리케이션은 여러 호스트에서 실행되며 **분산 애플리케이션(Distributed Application)**이라고 한다.
- **분산 애플리케이션은 호스트에서 실행된다.**

---

## Network Edge

- **Host(호스트)**는 **Client**와 **Server**로 구성되었다고 말할 수도 있다.

---

## Access Network

- **접속 네트워크(Access Network)**: 호스트에서 멀리 떨어진 다른 호스트까지의 경로에 있는 첫 번째 라우터에 연결하는 네트워크
- **Edge Router**라고도 한다.






어떻게 End System을 Edge Router에 연결하는가?
> cable-based Access : 
network of cable, fiber attaches homes to ISP router
homes share access network to cable headend
> DSL :
한국에서는 DSL 방식을 주로 사용
> HFC (Hybrid Fiber Coax) : asymmentic, up to 40 Mbps - 1.2Gbs downstream transmission late, 30-100Mbps upstream transmission late 
> FTTH :

<table>
        <tr>
            <th>항목</th>
            <th>DSL</th>
            <th>케이블 인터넷</th>
        </tr>
        <tr>
            <td><b>전송 매체</b></td>
            <td>전화선(구리선)</td>
            <td>동축 케이블(Coaxial Cable)</td>
        </tr>
        <tr>
            <td><b>속도</b></td>
            <td>최대 100Mbps (전화선 거리 영향)</td>
            <td>최대 1Gbps 이상 (다운로드 속도 빠름)</td>
        </tr>
        <tr>
            <td><b>대역폭 공유</b></td>
            <td>개별 회선 사용 (속도 일정)</td>
            <td>같은 지역 사용자와 공유 (혼잡 시 속도 저하)</td>
        </tr>
        <tr>
            <td><b>지연 시간 (레이턴시)</b></td>
            <td>낮음 (거리 영향 있음)</td>
            <td>보통 (네트워크 혼잡 시 증가)</td>
        </tr>
        <tr>
            <td><b>설치 및 유지보수</b></td>
            <td>전화선 활용 (설치 간편)</td>
            <td>케이블 TV 인프라 필요</td>
        </tr>
        <tr>
            <td><b>사용 지역</b></td>
            <td>도시 및 농촌</td>
            <td>주로 도심 및 인구 밀집 지역</td>
        </tr>
    </table>