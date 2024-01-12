- OSI 7 layer 모델
    - 네트워크 시스템 구성을 위한 범용적인 개념적인 모델
    - ISO/IEC에서 OSI 모델 관리
- TCP/IP Stack 모델
    - 인터넷이 발명되면서 함께 개발된 프로토콜 스택
    - IETF에서 인터넷 표준을 관리 (RFC)
    - TCP, UDP, IP 스펙은 RFC에서 정의
      <br/>

> TCP/IP Stack 모델을 집중적으로 살펴볼 것

- application layer (APPLICATION)
    - 애플리케이션 레벨에서 구현/관리
    - 네트워크 기능 사용하는데 목적
- transport layer, internet layer, link layer (SYSTEM)
    - 하드웨어/펌웨어, OS 레벨에서 구현/관리
    - 네트워크 기능을 지원하는데 목적
      <br/>


- Port
    - 프로세스와 연결된 data path 혹은 data channel
- Internet Protocol
    - unreliable
        - data loss (데이터 손실)
        - out-of-order (데이터 순서 보장 X)
    - 데이터에 대해 신뢰할 수 없음
    - 프로세스간 통신에서 데이터를 안정적(reliable)으로 주고 받을 수 있는 프로토콜 필요
        - TCP 프로토콜 등장 배경
          <br/>


- connection
    - 프로세스 간의 안정적이고 논리적인 통신 통로
    - 동작 (connection-oriented)
        1. connection 열기 (3-way handshake)
        2. 데이터 주고 받기
        3. connection 닫기 (4-way handshake)
    - 인터넷 상 port를 유니크하게 식별하는 방법
        - port (number) 정의: 16bits로 이루어진 숫자 (0 ~ 65535)
            - port의 원론적인 의미와 헷갈릴 수 있어 숫자 port를 말할 땐 'number'를 붙임
        - port number 만으로는 유니크하게 식별할 수 없음
            - internet address로 각 host를 유니크하게 식별 가능
        - internet address 와 port number 개념을 합친 것을 `Socket`임
            - 각 socket은 인터넷 상에서 유니크
              <br/>


- connection & socket
    - 각 connection을 유니크하게 식별할 수 있어야 함
    - 한 쌍의 socket은 connection을 유니크하게 식별함
        - src socket(src internet addr, src port), dest socket (dest internet addr, dest port)
    - 하나의 socket은 동시에 여러 connection들에서 사용될 수 있음
      <br/>


- UDP (user datagram portocol)
    - connectionless
        - 연결을 맺지 않고 바로 데이터를 주고 받음
    - unreliable
        - internet protocol을 거의 그대로 사용
    - UDP 표준(RFC 768)을 보면 socket 단어가 등장하지 않음
    - 그러나 이후에 자연스럽게 UDP에도 socket 개념을 쓰기 시작
      <br/>


- Socket (TCP/IP stack)
    - (protocol, ip address, port number)로 유니크하게 식별