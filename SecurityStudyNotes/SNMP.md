# SNMP (Simple Network Management Protocol) 정리

## 📌 SNMP란?
- 네트워크 장비(라우터, 스위치, 서버 등)를 **모니터링 및 제어**하기 위한 **응용 계층 프로토콜**
- **Manager - Agent - MIB** 구조
- 전송 계층: **UDP 사용**
  - Port 161: 요청(GET, SET 등)
  - Port 162: Trap(이벤트 알림)

---

## 🧩 SNMP 구성 요소
| 구성 요소 | 설명 |
|-----------|------|
| **Manager** | 중앙 제어 시스템 (ex. Zabbix, PRTG 등) |
| **Agent** | 네트워크 장비 안에서 동작, MIB 정보를 응답 |
| **MIB** (Management Information Base) | 관리 정보 사전 (트리 구조, OID 기반) |
---
OID는 Object Identifier의 줄임말이야.
→ SNMP에서 정보 항목을 구분하기 위한 고유 주소라고 보면 돼
## OID (Object Identifier)
- SNMP 정보 항목을 식별하는 고유 번호 (트리 구조 기반)
- 예:
  - `1.3.6.1.2.1.1.5.0` → `sysName` (시스템 이름)
  - `1.3.6.1.2.1.2.2.1.10.X` → `ifInOctets` (인터페이스 수신 바이트 수)
- OID는 Object Identifier의 줄임말이야.
→ SNMP에서 정보 항목을 구분하기 위한 고유 주소라고 보면 돼
---

## 📡 SNMP 동작 방식
- Manager가 Agent에 요청 → Agent가 MIB에서 응답
- 주요 명령:
  - `GET`: 정보 요청
  - `SET`: 값 설정
  - `GETNEXT`: 다음 항목 요청
  - `TRAP`: Agent가 Manager에게 알림 전송
  - `WALK`: 여러 `GETNEXT`를 반복하여 트리 순회

---

## 🔒 SNMP 버전 비교

| 버전 | 특징 | 보안 | 비고 |
|------|------|------|------|
| **v1** | 최초 버전 | 낮음 (평문 community string) | 거의 사용 안 함 |
| **v2c** | 성능 향상, bulk 지원 | 낮음 | 일부 사용 |
| **v3** | 인증, 암호화 지원 | **강력** (권장) | 실제 운영 환경 권장 |

---

## 🧮 네트워크 인터페이스 바이트 수

| 항목 | 설명 |
|------|------|
| `ifInOctets` | 해당 포트로 **수신된 바이트 수 (누적)** |
| `ifOutOctets` | 해당 포트에서 **전송된 바이트 수 (누적)** |
- 단위: 바이트 (1 Octet = 8비트)
- SNMP가 주는 값은 **누적값** → 직접 계산 필요

```text
bps = (현재값 - 이전값) * 8 / 측정간격(초)
