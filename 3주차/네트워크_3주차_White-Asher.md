# 1. HTTP HTTPS, HTTP Method

## 1.1 HTTP

서버/클라이언트 모델을 따라 데이터를 주고 받기 위한 프로토콜

### 프로토콜 (Protocol)

- 둘 이상의 통신개체간에 교환되는 메세지 포멧과 순서뿐 아니라, 메세지의 송수신과 이벤트에 따른 행동들을 정의한다. 
- 여러 계층으로 나눠진 네트워크 구조에서 동일 계층에서 사용하는 표준화된 통신 규약으로,네트워크 기능을 효율적으로 발휘하기 위한 협정
- 프로토콜의 주요기능
    - 단편화와 재합성
    - 캡슐화
    - 주소지정, 순서지정, 흐름제어
    - 연결제어, 오류제어, 동기화, 다중화

## HTTP 기본 구조

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-21-42-03.png)

- 시작 라인 (Start line)
    - 기본적으로 HTTP 버젼에 대한 정보를 가지고 있으며, Response인지 Request인지에 따라 약간 형태가 다르다.
- 헤더 (Header)
    - header-field : field-value 으로 구성되어 있다.
    - HTTP 전송에 필요한 모든 부가정보를 가지고 있다.
- 메시지 본문 (Message Body)
    - 메세지의 본문, 통신을 통해 보내고자 하는 Data를 담고 있다.


## HTTP Request 구조

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-21-41-15.png)

### Start Line

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-21-32-43.png)

- HTTP Method: 요청시 보내는 HTTP 메소드 형태 (GET, POST, PUT, PATCH, DELETE, 기타)
- Request Target: 어디로 보내는지에 대한 URI
- HTTP Version: HTTP 버젼으로 현재까지는 대부분이 HTTP/1.1이고 HTTP/2, HTTP/3 까지도 있음.

### Header

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-21-34-14.png)

- Host: 호스트 URL
- User-Agent: 클라이언트 정보
- Accept: 서버에서 해당 타입에 데이터를 보내달라고 요청하는 헤더
- Authorization: JWT 같은 인증 토큰을 서버로 보낼 때 사용하는 헤더
- etc...

## HTTP Response 구조

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-21-44-32.png)

### Start Line

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-21-45-12.png)

- HTTP Version: Response 메시지의 HTTP 버젼 정보
- Status Code: 응답 코드 ex)200, 404(Not Founded)
- Status text: 응답 상태

### Header

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-22-01-45.png)

- Date: 응답온 일시
- Content-Type: 응답 데이터의 타입
- Cache-Control: 캐시용 헤더
- etc..

### Body

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-22-02-22.png)

- Content-Type에 맞는 응답 메세지에 실어서 보낸 Data

## HTTPS

- HTTP 프로토콜의 문제점
    - 서버에서부터 브라우저로 전송되는 정보가 암호화되지 않는다는 점이다.
    - 이 말은 즉, 데이터가 쉽게 도난당할 수 있다는 것이다. 
- HyperText Transfer Protocol over Secure Socket Layer, HTTP over TLS, HTTP over SSL, HTTP Secure 등으로 불리는 HTTPS는 HTTP에 데이터 암호화가 추가된 프로토콜이다. 
- HTTPS 프로토콜은 SSL(보안 소켓 계층)을 사용함으로써 이 문제를 해결했다. 
- SSL은 서버와 브라우저 사이에 안전하게 암호화된 연결을 만들 수 있게 도와주고 서버 브라우저가 민감한 정보를 주고받을 때 이것이 도난당하는 것을 막아준다. 
- HTTPS는 HTTP와 다르게 443번 포트를 사용하며, 네트워크 상에서 중간에 제3자가 정보를 볼 수 없도록 암호화를 지원하고 있다.
- 그리고 HTTPS는 TLS(전송 계층 보안) 프로토콜을 사용해서 보안을 유지한다. TLS는 데이터 무결성을 보장해서 데이터가 전송 중에 수정되거나 손상되는 것을 방지하며 사용자가 접속하려는 웹사이트와 통신하고 있음을 증명할 수 있는 인증 기능도 가지고 있다.


### 대칭키 암호화와 비대칭키 암호화

- HTTPS는 대칭키 암호화 방식과 비대칭키 암호화 방식을 모두 사용하고 있다.
- 대칭키 암호화
    - 클라이언트와 서버가 동일한 키를 사용해 암호화/복호화를 진행함
    - 키가 노출되면 매우 위험하지만 연산 속도가 빠름
- 비대칭키 암호화
    - 1개의 쌍으로 구성된 공개키와 개인키를 암호화/복호화 하는데 사용함
    - 키가 노출되어도 비교적 안전하지만 연산 속도가 느림
    - 공개키: 모두에게 공개가능한 키
    - 개인키: 나만 가지고 알고 있어야 하는 키
    - 공개키와 개인키로 암호화하면 각각 다음과 같은 효과를 얻을 수 있다.
        - 공개키 암호화: 공개키로 암호화를 하면 개인키로만 복호화할 수 있다. -> 개인키는 나만 가지고 있으므로, 나만 볼 수 있다.
        - 개인키 암호화: 개인키로 암호화하면 공개키로만 복호화할 수 있다. -> 공개키는 두에게 공개되어 있으므로, 내가 인증한 정보임을 알려 신뢰성을 보장할 수 있다.

        ![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-09-18.png)

## HTTP VS HTTPS

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-05-34.png)

- HTTP는 암호화가 추가되지 않았기 때문에 보안에 취약한 반면, HTTPS는 안전하게 데이터를 주고받을 수 있다. 
- 하지만 HTTPS를 이용하면 암호화/복호화의 과정이 필요하기 때문에 HTTP보다 속도가 느리다. (물론 오늘날에는 거의 차이를 못느낄 정도이다.) 
- 또한 HTTPS는 인증서를 발급하고 유지하기 위한 추가 비용이 발생하다.
- 개인 정보와 같은 민감한 데이터를 주고 받아야 한다면 HTTPS를 이용해야 하지만, 노출이 되어도 괜찮은 단순한 정보 조회 등 만을 처리하고 있다면 HTTP를 이용하면 된다.

## HTTP Method

### GET

서버에게 Resource를 보내도록 요청하는데 사용 (서버의 Resource를 읽음)

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-13-30.png)

### HEAD
GET과 동일하지만 서버에서 Body를 Return 하지 않음

- Resource를 받지 않고 오직 찾기만 원할때
- object가 존재할 경우 응답의 상태 코드를 확인할때
- 서버의 응답 헤더를 봄으로써 Resource가 수정 되었는지 확인

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-14-34.png)

### PUT

서버에 문서를 쓸때 사용 (GET과 반대)

- PUT 메소드는 서버가 Client 요청의 Body를 확인한다.
- 요청된 URL에 정의된 새로운 Resource를 생성하기 위함
- 요청된 URL이 존재할 경우 대체하여 사용

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-19-21.png)


### POST
Server에 Input Data를 보내기 위함 (HTML form에 많이 사용)

- PUT vs. POST
    - PUT은 서버의 Resource에 Data를 저장하기 위한 용도
    - POST는 서버에 DATA를 보내기 위한 용도

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-20-12.png)

### TRACE
Client로 부터 Request Packet이 방화벽, Proxy Server, Gateway등을 거치면서 packet의 변조가 일어날 수 있는데, 이 때 Server에 도달 했을 때의 최종 Packet의 Request Packet을 볼수 있다.

- 즉, Original Data와 서버에 도달했을 때의 비교본 Data를 서버의 응답 Body를 통해 확인 할 수 있다.
- 요청의 최종 수신자는 반드시 송신자에게 200(OK) 응답의 내용(Body)로 수신한 메세지를 반송해야 한다.
- 최초 Client의 요청에는 Body가 포함될수 없다.

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-23-35.png)

### OPTION

Target Server의 지원 가능한 method(ex> GET, POST …)를 알아보기 위함

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-24-17.png)

### DELETE

- 요청 Resource를 삭제하도록 요청
- 그러나!! HTTP 규격에는 Client의 요청에도 서버가 무효화 시킬수 있도록 정의되어 있음
- DELETE Method는 항상 보장되지 않는다.

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-26-47.png)

# 2. TCP, UDP

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-37-16.png)

- 전송 계층(Transport Layer)에서 데이터를 보내기 위해 사용하는 프로토콜
- 전송 계층? : 전송계층은 송신자와 수신자를 연결하는 통신서비스를 제공하는 계층으로, 쉽게 말해 데이터의 전달을 담당

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-33-22.png)

## TCP (Transmission Control Protocol)

- 인터넷상에서 데이터를 메세지의 형태로 보내기 위해 IP와 함께 사용하는 프로토콜
- 연결형 서비스를 지원하는 프로토콜
- TCP는 연속성보다 신뢰성있는 전송이 중요할 때에 사용하는 프로토콜

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-35-39.png)

- 연결 지향 방식이다.
- 3-way handshaking과정을 통해 연결을 설정하고 4-way handshaking을 통해 해제한다.
    -  3-way handshaking과정 -> 목적지와 수신지를 확실히 하여 정확한 전송을 보장하기 위해서 세션을 수립하는 과정을 의미
- 흐름 제어 및 혼잡 제어.
- 높은 신뢰성을 보장한다.
- UDP보다 속도가 느리다.
- 전이중(Full-Duplex), 점대점(Point to Point) 방식.

```
전이중 통신방식
- 접속된 두 대의 단말기들 간에 동시에 데이터를 송수신하는 통신
- 두 개의 통신 채널을 이용하여 양방향으로 동시에 송수신
- 전송 효율이 높고 데이터 양이 많을 때 사용

반이중 통신방식
- 통신 채널에 접속된 두 대의 단말기 중 어느 한쪽이 데이터를 송신하면 상대편은 수신만 가능한 통신
- 송신측과 수신측이 정해져 있지 않으며 양 단말기의 상호 협력에 의해 송수신 방향 전환
- 하나의 통신 채널을 이용하여 교대로 데이터 송수신
```

### TCP 서버의 특징
- 서버소켓은 연결만을 담당한다.
- 연결과정에서 반환된 클라이언트 소켓은 데이터의 송수신에 사용된다
- 서버와 클라이언트는 1대1로 연결된다.
- 스트림 전송으로 전송 데이터의 크기가 무제한이다.
- 패킷에 대한 응답을 해야하기 때문에(시간 지연, CPU 소모) 성능이 낮다.
    - 패킷: 인터넷 내에서 데이터를 보내기 위한 경로배정(라우팅)을 효율적으로 하기 위해서 데이터를 여러 개의 조각들로 나누어 전송을 하는데 이때, 이 조각을 패킷이라고 합니다.
- Streaming 서비스에 불리하다.(손실된 경우 재전송 요청을 하므로)

## UDP (User Datagram Protocol)

- 데이터를 데이터그램 단위로 처리하는 프로토콜
- 데이터그램: 독립적인 관계를 지니는 패킷
- 비연결형 프로토콜
- 연결을 위해 할당되는 논리적인 경로 없음
- 각각의 패킷은 다른 경로로 전송되고, 각각의 패킷은 독립적인 관계를 지님

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-47-02.png)

- 비연결형 서비스로 데이터그램 방식을 제공한다
- 정보를 주고 받을 때 정보를 보내거나 받는다는 신호절차를 거치지 않는다.
- UDP헤더의 CheckSum 필드를 통해 최소한의 오류만 검출한다.
- 신뢰성이 낮다
- TCP보다 속도가 빠르며 네트워크 부하가 적음
- 흐름 제어 및 혼잡 제어 지원 X
- 신뢰성보다는 연속성이 중요한 서비스 예를 들면 실시간 서비스(streaming)에 자주 사용

### UDP 서버의 특징

- UDP에는 연결 자체가 없어서(connect 함수 불필요) 서버 소켓과 클라이언트 소켓의 구분이 없다.
- 소켓 대신 IP를 기반으로 데이터를 전송한다.
- 서버와 클라이언트는 1대1, 1대N, N대M 등으로 연결될 수 있다.
- 데이터그램(메세지) 단위로 전송되며 그 크기는 65535바이트로, 크기가 초과하면 잘라서 보낸다.
- 흐름제어(flow control)가 없어서 패킷이 제대로 전송되었는지, 오류가 없는지 확인할 수 없다.
- 파일 전송과 같은 신뢰성이 필요한 서비스보다 성능이 중요시 되는 경우에 사용된다.

### 흐름제어(Flow Control)와 혼잡제어(Congestion Control)이란?

흐름제어는 데이터를 송신하는 곳과 수신하는 곳의 데이터 처리 속도를 조절하여 수신자의 버퍼 오버플로우를 방지하는 것입니다. 예를 들어 송신하는 곳에서 감당이 안되게 데이터를 빠르게 많이 보내면 수신자에서 문제가 발생하기 때문입니다.
혼잡제어는 네트워크 내의 패킷 수가 넘치게 증가하지 않도록 방지하는 것입니다. 만약 정보의 소통량이 과다하면 패킷을 조금만 전송하여 혼잡 붕괴 현상이 일어나는 것을 막습니다.

- Flow Control

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-52-47.png)

- Congestion Control

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-54-20.png) <br>

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-54-37.png)

## TCP VS UDP 

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-25-23-56-14.png)


# 3. TCP 3way / 4way handshake

## TCP 3 way handshake

연결하고자 하는 두 장치 간의 논리적 접속을 성립하기 위해 사용하는 연결 확인 방식으로, 3번의 확인 과정을 거친다고 해서 3 way handshake라고 부른다.

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-26-00-06-13.png)

- SYN (synchronize sequence numbers) - 연결 확인을 위해 보내는 무작위의 숫자값 (내 말 잘 들려?)
- ACK (acknowledgements) - Client 혹은 Server로부터 받은 SYN에 1을 더해 SYN을 잘 받았다는 ACK (잘 들려)
- ISN (Initial sequence numbers) - Client와 Server가 각각 처음으로 생성한 SYN

###  TCP 3 way handshake 과정 

- [STEP 1] (SYN)
    - A클라이언트는 B서버에 접속을 요청하는 SYN 패킷을 보낸다. 이때 A클라이언트는 SYN 을 보내고 SYN/ACK 응답을 기다리는SYN_SENT 상태  가 되는 것이다.
- [STEP 2] (SYN + ACK)
    - 이때 서버는 Listen 상태로 포트 서비스가 가능한 상태여야 한다. (Closed :닫힌상태) B서버는 SYN요청을 받고 A클라이언트에게 요청을 수락한다는 ACK 와 SYN flag 가 설정된 패킷을 발송하고 A가 다시 ACK으로 응답하기를 기다린다. 이때 B서버는 SYN_RECEIVED 상태가 된다.
- [STEP 3] (ACK)
    - A클라이언트는 B서버에게 ACK을 보내고 이후로부터는 연결이 이루어지고 데이터가 오가게 되는것이다. 이때의 B서버 상태가 ESTABLISHED 이다.

위와 같은 방식으로 통신하는것이 신뢰성 있는 연결을 맺어 준다는 TCP의 3 Way handshake 방식이다.

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-26-00-06-59.png)


# 4. 쿠키와 세션

## 쿠키와 세션을 왜 사용하는가? 

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-26-00-18-11.png)
- HTTP 프로토콜의 특성이자 약점을 보완하기 위해서 쿠키 또는 세션을 사용합니다.
- 기본적으로 HTTP 프로토콜 환경은 "connectionless, stateless"한 특성을 가지기 때문에 서버는 클라이언트가 누구인지 매번 확인해야합니다. 이 특성을 보완하기 위해서 쿠키와 세션을 사용하게됩니다.

### connectionless
- 클라이언트가 요청을 한 후 응답을 받으면 그 연결을 끊어 버리는 특징
- HTTP는 먼저 클라이언트가 request를 서버에 보내면, 서버는 클라이언트에게 요청에 맞는 response를 보내고 접속을 끊는 특성이 있다.
- 헤더에 keep-alive라는 값을 줘서 커넥션을 재활용하는데 HTTP1.1에서는 이것이 디폴트다.
- HTTP가 tcp위에서 구현되었기 때문에 (tcp는 연결지향,udp는 비연결지향) 네트워크 관점에서 keep-alive는 옵션으로 connectionless의 연결비용을 줄이는 것을 장점으로 비연결지향이라 한다.

### stateless
- 통신이 끝나면 상태를 유지하지 않는 특징
- 연결을 끊는 순간 클라이언트와 서버의 통신이 끝나며 상태 정보는 유지하지 않는 특성이 있다.
- 쿠키와 세션은 위의 두 가지 특징을 해결하기 위해 사용함.
- 예를 들어, 쿠키와 세션을 사용하지 않으면 쇼핑몰에서 옷을 구매하려고 로그인을 했음에도, 페이지를 이동할 때 마다 계속 로그인을 해야 한다.
- 쿠키와 세션을 사용했을 경우, 한 번 로그인을 하면 어떠한 방식에 의해서 그 사용자에 대한 인증을 유지한다.

## 쿠키

- HTTP의 일종으로 사용자가 어떠한 웹 사이트를 방문할 경우, 그 사이트가 사용하고 있는 서버에서 사용자의 컴퓨터에 저장하는 작은 기록 정보 파일이다.
- HTTP에서 클라이언트의 상태 정보를 클라이언트의 PC에 저장하였다가 필요시 정보를 참조하거나 재사용할 수 있다.

### 쿠키 특징
- 이름, 값, 만료일(저장기간), 경로 정보로 구성되어 있다.
- 클라이언트에 총 300개의 쿠키를 저장할 수 있다.
- 하나의 도메인 당 20개의 쿠키를 가질 수 있다.
- 하나의 쿠키는 4KB(=4096byte)까지 저장 가능하다.

### 쿠키의 동작 순서
1. 클라이언트가 페이지를 요청한다. (사용자가 웹사이트에 접근)
2. 웹 서버는 쿠키를 생성한다.
3. 생성한 쿠키에 정보를 담아 HTTP 화면을 돌려줄 때, 같이 클라이언트에게 돌려준다.
4. 넘겨받은 쿠키는 클라이언트가 가지고 있다가(로컬 PC에 저장) 다시 서버에 요청할 때 요청과 함께 쿠키를 전송한다.
5. 동일 사이트 재방문 시 클라이언트의 PC에 해당 쿠키가 있는 경우, 요청 페이지와 함께 쿠키를 전송한다.

### 사용 예시
- 방문 사이트에서 로그인 시, "아이디와 비밀번호를 저장하시겠습니까?"
- 팝업창을 통해 "오늘 이 창을 다시 보지 않기" 체크

## 세션

- 일정 시간 동안 같은 사용자(브라우저)로부터 들어오는 일련의 요구를 하나의 상태로 보고, 그 상태를 유지시키는 기술이다.
- 여기서 일정 시간은 방문자가 웹 브라우저를 통해 웹 서버에 접속한 시점부터 웹 브라우저를 종료하여 연결을 끝내는 시점을 말한다.
- 즉, 방문자가 웹 서버에 접속해 있는 상태를 하나의 단위로 보고 그것을 세션이라고 한다.

### 세션 특징
- 웹 서버에 웹 컨테이너의 상태를 유지하기 위한 정보를 저장한다.
- 웹 서버의 저장되는 쿠키(=세션 쿠키)
- 브라우저를 닫거나, 서버에서 세션을 삭제했을 때만 삭제가 되므로, 쿠키보다 비교적 보안이 좋다.
- 저장 데이터에 제한이 없다. (서버 용량이 허용하는 한에서)
- 각 클라이언트에 고유 Session ID를 부여한다. Session ID로 클라이언트를 구분해 각 요구에 맞는 서비스를 제공

### 세션의 동작 순서
- 클라이언트가 페이지에 요청한다. (사용자가 웹사이트에 접근)
- 서버는 접근한 클라이언트의 Request-Header 필드인 Cookie를 확인하여, 클라이언트가 해당 session-id를 보냈는지 확인한다.
- session-id가 존재하지 않는다면 서버는 session-id를 생성해 클라이언트에게 돌려준다.
- 서버에서 클라이언트로 돌려준 session-id를 쿠키를 사용해 서버에 저장한다.
- 클라이언트는 재접속 시, 이 쿠키를 이용해 session-id 값을 서버에 전달

### 사용 예시

- 화면을 이동해도 로그인이 풀리지 않고 로그아웃하기 전까지 유지

## 쿠키 VS 세션

- 쿠키와 세션은 비슷한 역할을 하며, 동작원리도 비슷합니다. 그 이유는 세션도 결국 쿠키를 사용하기 때문입니다.
- 가장 큰 차이점은 사용자의 정보가 저장되는 위치입니다. 때문에 쿠키는 서버의 자원을 전혀 사용하지 않으며, 세션은 서버의 자원을 사용합니다.
- 보안 면에서 세션이 더 우수하며, 요청 속도는 쿠키가 세션보다 더 빠릅니다. 그 이유는 세션은 서버의 처리가 필요하기 때문입니다.
- 보안, 쿠키는 클라이언트 로컬에 저장되기 때문에 변질되거나 request에서 스니핑 당할 우려가 있어서 보안에 취약하지만 세션은 쿠키를 이용해서 sessionid 만 저장하고 그것으로 구분해서 서버에서 처리하기 때문에 비교적 보안성이 좋습니다.
- 라이프 사이클, 쿠키도 만료시간이 있지만 파일로 저장되기 때문에 브라우저를 종료해도 계속해서 정보가 남아 있을 수 있다. 또한 만료기간을 넉넉하게 잡아두면 쿠키삭제를 할 때 까지 유지될 수도 있습니다.
- 반면에 세션도 만료시간을 정할 수 있지만 브라우저가 종료되면 만료시간에 상관없이 삭제됩니다. 예를 들어, 크롬에서 다른 탭을 사용해도 세션을 공유됩니다. 다른 브라우저를 사용하게 되면 다른 세션을 사용할 수 있습니다.
- 속도, 쿠키에 정보가 있기 때문에 서버에 요청시 속도가 빠르고 세션은 정보가 서버에 있기 때문에 처리가 요구되어 비교적 느린 속도를 가집니다.

# 5. www.naver.com에 접속할 떄 생기는 일

면접 단골 질문

# 6. OSI 7계층

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-26-00-22-59.png)

## OSI & Layer model?
- Open Systems Interconnection(개방 시스템 연결)로 일컫는 새로운 네트워크 모델이다.
- 컴퓨터 네트워크 프로토콜의 국제적인 표준안이다.
- 각종 네트워크 장비 및 컴퓨터 등의 모든 통신 관련 시스템에 적용되는 개념이다.
- OSI 모델은 하나의 컴퓨터에서 다른 컴퓨터로 데이터가 전송될 때, 데이터의 생성 및 전송 과정을 표준화한 모델로 사용된다.
- 데이터 통신 기능을 수직적으로 계층화시켜서 각 계층별로 기능들을 수행하여 전달하는 통신 개념이다.

## 목적 및 특징
- 목적
    - 초기의 OSI 모델은 통신 장비들이 범용적으로 호환되지 않고 자신의 업체 장비만 호환되도록 모델링 되었다.
    - 이에 따라 여러 통신 업체 장비들간의 호환성이 필요하게 되어 OSI 모델이 탄생하게 되었다.
- 특징
    - 7 계층으로 구분함으로써 관리 및 사용상의 효율성을 높였다.
    - 계층 구분을 통해 계층간의 독립성을 확보하고 다른 계층에 영향을 최소화하였다.

## OSI 모델 구조

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-26-00-27-45.png)

### 구조 및 동작

- OSI 참조모델은 총 7계층의 구조로 구성되어 있다.
- 상위 계층(응용층, 표현층, 논리 접속층) : 호스트 내부에서 처리되는 기능 수행
- 전송 계층 : 두 장비의 연결을 확인하고 유지하는 기능 수행
- 하위 계층(네트워크 계층, 데이터 연결 계층, 물리 계층) : 패킷의 전달 기능 수행

### Application Layer (L7)
- 역할 : 응용 프로세스간 인터페이스와 통신을 위한 기능을 수행하며, 파일 전송이나 이메일과 같은 엔드 유저(end-user) 서비스를 제공한다.
- 프로토콜 : TELNET, FTP, SMTP, WWW, HTTP

### Presentation Layer (L6)
- 역할 : 응용계층에서 전달된 데이터를 공통된 형식으로 변환, 압축, 암호화하는 기능 수행
- 프로토콜 : JPEG. MPEG

### Session Layer (L5)
- 역할 : 응용 프로그램간에 사용할 데이터 교환을 위한 세션과 대화 방식을 결정
- 데이터 전송 단위 : 데이터(Data)
- 프로토콜 : SSH, TLS

### Transport Layer (L4)
- 역할 : 신뢰성 있는 전송을 보장하기 위해 오류 검출 및 복구와 흐름 제어 수행
- 데이터 전송 단위 : 세그먼트(Segment)
- 프로토콜 : TCP, UDP
- 장비 : 게이트웨이, L4스위치

### Network Layer (L3)
- 역할 : 네트워크의 혼잡 제어 및 데이터 전송 경로를 설정하는 기능 수행
- 데이터 전송 단위 : 패킷(Packet)
- 프로토콜 : IP, ICMP, ARP
- 장비 : 라우터

### DataLink Layer (L2)
- 역할 : 물리 계층 간에 정확한 데이터 전송이 보장되도록 하는 기능 수행
- 데이터 전송 단위 : 프레임(Frame)
- 프로토콜 : 이더넷
- 장비 : 브릿지, 스위치

### Physical Layer (L1)
- 역할 : 전송할 데이터를 통신 케이블에 맞게 변환하여 비트 정보가 케이블을 통해 효율적으로 - 전송되도록 지원해주는 기능 수행
- 데이터 전송 단위 : 비트(Bit)
- 장비 : 허브

# 7. DNS

- 도메인 네임 시스템 (Domain Name System, DNS) 은 호스트의 도메인네임 (www.example.com)을 네트워크주소(192.168.1.0)로 변환하거나, 그 반대의 역할을 수행하는 시스템이다.
- 예를 들면 우리가 자주 접하는 naver.com , google.com 모두 DNS을 가진 DN(Domain Name)이라고 할 수 있다.
- 문자열의 탈을 쓴 IP

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-26-00-34-41.png)

## 과정

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-26-00-39-18.png)

사용자가 웹브라우저에 도메인 'naver.com'을 입력하면 아래와 같은 과정을 거치게 된다.

1. 도메인 주소 naver.com을 브라우저에 입력하게 되면, 도메인 주소들을 가지고 있는 네임서버(DNS 서버)에 접속
2. 네임서버에 접속한 도메인(naver.com)과 연결된 IP 정보(223.130.192.200)를 확인하고, IP를 사용자 PC에 전달
3. 사용자 PC는 전달받은 서버의 IP 주소로 접속
4. 서버의 IP로 연결된 브라우저에 서버의 내용(홈페이지)을 출력

## DNS 작동원리

![](./%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_3%EC%A3%BC%EC%B0%A8_White-Asher_Asset/2023-04-26-00-40-04.png)

# 8. 라우터 / 라우팅 알고리즘

# 9. 웹소켓


## 본문 및 이미지 출처

- [CS] HTTP / HTTPS - [https://velog.io/@leeyoungwoozz/CS-HTTP-HTTPS](https://velog.io/@leeyoungwoozz/CS-HTTP-HTTPS) <br>
- HTTP 구조 정리 - 삽질중인 개발자 [https://programmer93.tistory.com/60](https://programmer93.tistory.com/60)
- HTTPS - [https://brunch.co.kr/@hyoi0303/10](https://brunch.co.kr/@hyoi0303/10)
- HTTP Header - [https://medium.com/@lyhlg0201/http-method-d561b77df7](https://medium.com/@lyhlg0201/http-method-d561b77df7)
- [TCP/UDP] TCP와 UDP의 특징과 차이 - [https://mangkyu.tistory.com/15](https://mangkyu.tistory.com/15)
- TCP 3way handshake [https://sleepyeyes.tistory.com/4](https://sleepyeyes.tistory.com/4)
- [네트워크] TCP 3-way & 4-way handshake란? - [https://seongonion.tistory.com/74](https://seongonion.tistory.com/74)
- 쿠키(Cookie)와 세션(Session)의 차이 - [https://dev-coco.tistory.com/61](https://dev-coco.tistory.com/61)
- 쿠키와 세션 개념 - [https://interconnection.tistory.com/74](https://interconnection.tistory.com/74)
- OSI 7 Layer model - [https://incheol-jung.gitbook.io/docs/q-and-a/computer-science/osi-7-layer-todo](https://incheol-jung.gitbook.io/docs/q-and-a/computer-science/osi-7-layer-todo)
- DNS 개념 & 동작 ★ 알기 쉽게 정리 - [Inpa Dev](https://inpa.tistory.com/entry/WEB-%F0%9F%8C%90-DNS-%EA%B0%9C%EB%85%90-%EB%8F%99%EC%9E%91-%EC%99%84%EB%B2%BD-%EC%9D%B4%ED%95%B4-%E2%98%85-%EC%95%8C%EA%B8%B0-%EC%89%BD%EA%B2%8C-%EC%A0%95%EB%A6%AC)