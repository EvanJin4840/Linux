HTTP 메서드 (GET, POST 등)
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
