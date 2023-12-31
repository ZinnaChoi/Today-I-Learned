### 1. 라우팅(routing)

> 네트워크에서 데이터를 보낼 때 **최적의 경로**를 선택하는 과정. 라우터가 이를 수행

- 데이터는 보통 출발지에서 목적지로 가는 동안 여러 개의 라우터를 거치며, 여러 번의 라우팅을 수행. (라우팅은 보통 초당 수백만번 발생)
- 라우터: 라우팅을 수행하는 네트워크 장치
- 홉바이홉 통신이라고도 한다

### 2. 라우터

> 네트워크 사이에서 데이터를 전달하는 장치. 보통 둘 이상의 서로 다른 네트워크에 연결됨

- 데이터를 목적지로 보낼 때 최적의 경로를 결정하고 경로가 결정되면 해당 경로로 데이터를 넘겨주는 일 (라우팅)을 수행.
- 라우터는 라우팅테이블을 기반으로 데이터를 다음 목적지에게 전달

### 3. 라우팅 테이블

> IP주소를 기반으로 라우터의 위치를 저장한 테이블 또는 데이터베이스

- 다양한 네트워크에 대한 정보와 해당 네트워크에 연결하는 방법을 포함

ex)
PC1 (10.0.0.4)에서 101.25.67.0 네트워크에 있는 PC3 101.25.67.7 에 패킷을 보내고자 할 때, router A를 거쳐 전달된다

#### 라우팅 테이블의 구성 요소

![](https://velog.velcdn.com/images/zinna_1109/post/64c41fc0-04b5-4190-a949-d348cfa673fb/image.png)

ex)

| Network Destination | Netmask       | Gateway  | Interface | Metric |
| ------------------- | ------------- | -------- | --------- | ------ |
| 101.25.67.0         | 255.255.255.0 | 10.0.0.2 | eth3      | 1      |

- 네트워크 대상 (Network Destination): **목적지** 네트워크의 IP 주소
- 서브넷 마스크 (Netmask): 대상 주소를 설명할 때 쓰이는 값 (주소 부연 설명)
- 게이트웨이 (Gateway): 이 장치와 연결되어있는 홉. 패킷이 전달되는 다음 IP 주소 (외부 네트워크와 연결된 장치). 만약 목적지가 로컬 네트워크라면 '연결됨(connected)'라고 표기되며 다른 네트워크라면 해당 네트워크의 게이트웨이를 가리킴
- 인터페이스(interface): 게이트웨이로 가기 위해 거치는 장치
  cf) 10.0.0.2는 eth3(인터페이스 중 하나)를 통해 접근이 가능
- 메트릭(Metric): 우선순위라고도 불림. 패킷 전송을 위해 최적의 경로가 선택되도록 참고되는 값 동일한 라우팅 테이블 요소가 2개가 있을 때, 이 값이 낮은 요소가 선택된다. 메트릭은 일반적으로 홉 수 (hop count)가 들어가며, 지연시간, 처리량 등이 들어갈 수 있음

### 4. 게이트웨이

> =프로토콜 변환기. 네트워크와 네트워크를 잇는 장치. 라우터와 하는 기능 자체가 비슷

### 5. 홉 (hop)

> 네트워크에서 출발지와 목적지 사이에 위치한 장치

- hop count = 데이터가 출발지와 목적지 사이에서 통과해야 하는 홉의 개수
- hop count는 적을수록 좋음
