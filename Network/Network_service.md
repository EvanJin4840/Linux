1. SSH (Secure Shell)
- 서버와 클라이언트 간에 네트워크를 통해 암호화된 원격 접속 및 명령어 실행을 가능하게 하는 프로토콜임.

| 프로토콜/서비스 | 대표 포트      | 주요 특징/용도                                 | 보안 쟁점                                |
|-----------------|---------------|-----------------------------------------------|-------------------------------------------|
| **SSH**         | 22            | 암호화 원격 접속, 서버관리, 파일전송(SCP/SFTP)    | 약한 패스워드, 키 관리, 버전 취약점        |
| **HTTP**        | 80, 443       | 웹서비스, HTML/REST, API 통신                   | 평문 위협(HTTP), 인증·웹취약점            |
| **MQTT**        | 1883, 8883    | IoT/센서 데이터, 경량 Pub/Sub 메시징             | 미인증 접근, 암호화 미적용, 정보 유출 가능  |
| **AMQP**        | 5672          | 고급 메시징 큐, 브로커, 트랜잭션 메시지 처리      | 미인증, SSL 미적용, 데이터 유출 위험        |
| **HTTP (Jetty)**| 8161 등       | 자바 기반 웹서버, 관리 콘솔, REST·웹소켓 지원     | 관리 콘솔 취약점, 인증 설정                |
| **tcpwrapped**  | 가변(임의)    | 서비스 정보 은폐, 접근통제(중간 프록시/보안툴)    | 정책 Bypass, 서비스 탐지 불가              |
