### 워드프레스의 개념 및 구조

워드프레스는 콘텐츠 관리 시스템(CMS)의 하나로서, 프로그래밍 지식이 없이도 웹사이트나 블로그 등을 쉽게 만들고 관리할 수 있게 해줍니다. PHP로 개발되었으며, MySQL 데이터베이스를 사용하고, 테마와 플러그인(CMS에 새로운 기능을 추가하는 확장 프로그램)을 통해 기능과 디자인을 확장할 수 있는 구조입니다. 워드프레스는 매우 보편적이고, 오픈 소스이므로, 누구나 소스를 보고 테마/플러그인을 개발하거나 수정할 수 있습니다. 이러한 광범위한 사용과 개방성 때문에 보안상 중요한 대상이 되며, 취약점이 발견될 경우, 파급력이 매우 큽니다.

## 주요 보안 취약점

* 크로스 사이트 스크립팅(XSS): 워드프레스의 댓글 기능이나 게시물 입력란 등에 악성 스크립트를 삽입함으로써 발생하는 취약점. 공격자가 XSS를 통해 관리자나 방문자의 브라우저에서 사용자 세션 탈취, 웹사이트 변조 등의 공격을 할 수 있음.
