# TCP와 UDP

TCP와 UDP는 **OSI 7계층 중 4계층 (전송 계층)** 에 해당되는 프로토콜이다. <br>
컴퓨터 간 데이터를 주고 받을 때 사용되는 핵심 프로토콜이다.

<br>

## TCP (Transmission Control Protocol) 특징

### 연결 지향형 프로토콜
- 데이터를 전송하기 전에 **3-way handshake**를 통해 연결을 확인한다.

### 신뢰성 높은 전송
- 데이터의 순서를 보장하며, 손실된 패킷은 다시 전송한다.

### 3-Way Handshake동작 방식

- **ACK**: 접속 수락
- **SYN**: 접속 요청

| 이름 | 의미 |
| --- | --- |
| SYN | 연결할 때 클라이언트가 서버에 시퀸스 번호를 보내는 패킷 |
| SYN-ACK | 시퀸스 번호를 받은 서버가 ACK 값을 생성하여 클라이언트에게 응답하는 패킷 |
| ACK | ACK 값을 사용하여 응답하는 패킷 |
1. 클라이언트가 서버에게 연결 요청을 보낸다. **(SYN) 클라이언트 → 서버**
2. 서버가 클라이언트의 요청을 받고, 승낙하며 동시에 서버도 연결 요청을 보낸다. **(SYN-ACK)**
    
    **서버 → 클라이언트**
    
3. 클라이언트가 서버의 응답을 확인했다는 메세지를 보낸다. **(ACK) 클라이언트 → 서버**

<br>

## UDP (User Datagram Protocol) 특징

### 비연결형 프로토콜
- 연결을 설정하지 않고 데이터를 바로 전송한다.

### 신뢰성 없음
- 패킷이 유실되거나 순서가 바뀌어도 재전송하지 않는다.