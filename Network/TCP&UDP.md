| 기능                          | TCP  | UDP  |
| --------------------------- | ---- | ---- |
| **연결 설정 (3-way handshake)** | ✅ 있음 | ❌ 없음 |
| **데이터 순서 보장**               | ✅ 있음 | ❌ 없음 |
| **재전송 (손실 시 복구)**           | ✅ 있음 | ❌ 없음 |
| **혼잡 제어 (네트워크 상태 고려)**      | ✅ 있음 | ❌ 없음 |
| **오류 검사 후 복구 시도**           | ✅ 있음 | ❌ 없음 |
| **속도 빠름**                   | ❌ 느림 | ✅ 빠름 |

Certainly. Here is an explanation of TCP and UDP in English.

TCP (Transmission Control Protocol)
TCP is a reliable, connection-oriented protocol. It guarantees that data packets are delivered in the correct order and without any loss.

Key Features:
Connection-Oriented: It establishes a connection with the other party before transmitting data using a process called "three-way handshaking."
Reliable: It verifies that all data packets have been successfully delivered. If a packet is lost, it will be resent.
Order Guaranteed: It numbers the data packets to ensure they arrive in the correct sequence.
Use Cases: It's used for applications where data accuracy is crucial, such as file transfers (FTP) and web browsing (HTTP).

UDP (User Datagram Protocol)
UDP is a fast, connectionless protocol. It prioritizes speed and efficiency over reliability. It sends data without first establishing a connection and doesn't verify if the data was received.

Key Features:
Connectionless: It sends data immediately without any setup process.
Unreliable: It doesn't check for lost or out-of-order packets.
Datagrams: It sends data in independent units called "datagrams."
Use Cases: It's used for real-time applications where speed is more important than perfect accuracy, such as video streaming, online gaming, and DNS (Domain Name System).