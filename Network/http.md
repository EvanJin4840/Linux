#### HTTP 메서드 (GET, POST 등)
"어떤 동작을 할지" 를 나타내는 것

요청의 목적과 방식을 지정

예: GET (조회), POST (생성), PUT (수정), DELETE (삭제)

HTTP 헤더
"추가적인 메타정보" 를 담는 부분

요청이나 응답에 대한 상세 정보를 제공

예: Host, Content-Type, Authorization, User-Agent 등

POST /api/users HTTP/1.1          ← 요청 라인 (메서드 포함)
Host: example.com                 ← 헤더
Content-Type: application/json    ← 헤더  
Authorization: Bearer token123    ← 헤더
Content-Length: 45                ← 헤더

{"name": "Alice", "age": 25}      ← 바디

#### HTTP 4xx 클라이언트 에러

| 코드      | 이름                              | 의미(요약)        | 흔한 원인                  | 해결 포인트                               |
| ------- | ------------------------------- | ------------- | ---------------------- | ------------------------------------ |
| **400** | Bad Request                     | 요청 형식이 잘못됨    | JSON 파싱 실패, 필수 파라미터 누락 | 스키마 검증, 요청 예시 문서화                    |
| **401** | Unauthorized                    | 인증 필요/실패      | 토큰 없음·만료, 잘못된 자격증명     | 로그인/토큰 재발급, `WWW-Authenticate` 헤더 제공 |
| **402** | Payment Required                | 결제 필요(예약/확장용) | 유료 플랜/쿼터 초과            | 결제 유도, 사용량/플랜 정보 제공                  |
| **403** | Forbidden                       | 인증돼도 접근 금지    | 권한 없음, IP 차단, CSRF 실패  | 권한 체크·ACL 수정, 상세 사유(가능 범위 내) 안내      |
| **404** | Not Found                       | 리소스 없음        | 잘못된 URL/ID, 비공개 리소스    | 존재 숨김이 목적이면 404 유지, 링크/ID 검증         |
| **405** | Method Not Allowed              | 메서드 불가        | `GET`만 지원하는데 `POST` 사용 | `Allow` 헤더로 허용 메서드 명시                |
| **408** | Request Timeout                 | 클라이언트 응답 지연   | 느린 네트워크, 대기 초과         | 타임아웃 연장, 재시도 가이드                     |
| **409** | Conflict                        | 상태 충돌         | 중복 생성, 버전 충돌           | 낙관적 락, 리소스 상태 반환                     |
| **410** | Gone                            | 영구 삭제         | 영구 제거된 페이지             | 대체 경로 안내, 링크 정리                      |
| **415** | Unsupported Media Type          | 지원 안 되는 MIME  | `Content-Type` 불일치     | 지원 타입 명시, 업로드 검증                     |
| **422** | Unprocessable Content           | 의미는 맞지만 처리 불가 | 비즈니스 규칙 위반             | 필드별 에러 상세 반환                         |
| **429** | Too Many Requests               | 과도한 요청        | 레이트 리밋 초과              | `Retry-After` 제공, 백오프 안내             |
| **431** | Request Header Fields Too Large | 헤더 과다/초과      | 거대 쿠키/헤더               | 쿠키 슬림화, 헤더 제한                        |
| **451** | Unavailable For Legal Reasons   | 법적 이유로 제한     | 지역/법률 제한               | 법적 고지, 문의 경로 안내                      |

### 403 · 401 · 404 빠른 구분
- 401: “누구인지 증명부터 해주세요.” (인증 실패/필요)
- 403: “당신인 건 알지만 권한이 없습니다.” (인가 실패)
- 404: “그런 리소스 없는 것처럼 응답합니다.” (보안상 존재 숨김에 사용되기도)
* 실무 팁
- 보안상 정보 과다 노출 금지: 403 사유를 과하게 상세히 쓰지 않기(예: “admin만 접근 가능” 등은 최소화).
* 헤더 활용
- 401에는 WWW-Authenticate(예: Bearer realm="api", error="invalid_token").
- 405에는 Allow: GET, POST.
- 429에는 Retry-After: 120.
- 일관 응답 포맷: 에러 바디는 { code, message, details } 등 표준화.