# TCP의 연결 성립: 3-웨이 핸드쉐이크

> 3단계의 과정을 거쳐 연결 성립
> SYN : synchronization의 약자. 연결 요청 플래그
> ACK: acknowledgement의 약자. 응답 플래그

![](https://velog.velcdn.com/images/zinna_1109/post/6f93c4d9-1501-466f-8e3c-1ff3d33bf77c/image.png)

### 1. SYN (씬) 단계 (요청)

- 클라이언트는 서버에 클라이언트의 ISN(고유번호)을 담아 SYN을 보냄

### 2. SYN + ACK 단계 (응답)

- 서버는 클라이언트의 SYN을 수신하고, 서버의 ISN을 보내며 승인 번호(ACK)로 클라이언트의 ISN + 1을 보냄
- 서버는 listen 상태이어야지만 씬을 받을 수 있다

### 3. ACK 단계 (확인)

- 클라이언트는 서버의 ISN + 1한 값인 승인번호(ACK)를 서버에 보냄

#### ISN

- TCP 기반 데이터 통신에서 각각의 새 연결에 할당된 **고유한** 32 비트 시퀀스 번호
- TCP 연결을 통해 전송되는 다른 데이터 바이트와 충돌하지 않는 시퀀스 번호를 할당하는데 도움이 된다

> 이러한 서버와 클라이언트 간의 연결 설정 과정이 있기 때문에 TCP는 신뢰성이 있다. 이러한 연결 과정이 없는 UDP는 신뢰성이 없다

#### LISTEN

- 서버가 클라이언트의 연락을 기다리는 상태. 이를 기반으로 서버 메서드의 이름이 결정됨.
