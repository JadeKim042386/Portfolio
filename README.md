# [백엔드 개발자] 김주영

## 목차

- [중고 상품 거래/경매 웹 서비스](#-중고-상품-거래경매-웹-서비스)
- [3D 모델 공유 게시판 웹 서비스](#-3d-모델-공유-게시판-웹-서비스)
- [계좌 관리 시스템 API](#-계좌-관리-시스템-api)
- [공공 와이파이 검색 웹 서비스](#-공공-와이파이-검색-웹-서비스)

그 밖의 개발 경험은 다음과 같습니다.

1. [AI](./AI.md)
2. [Flutter](./Flutter.md)
3. [Open Source Contribution](./Open%20Source%20Contribution.md)

## JAVA

### ✨ 중고 상품 거래/경매 웹 서비스

**`[소개]`**

중고 상품을 게시글로 등록하여 1:1 채팅으로 거래하거나 경매를 올려 입찰/낙찰 과정을 통해 판매/구매할 수 있는 웹 서비스입니다.

백엔드 개발을 담당했으며 프론트엔드 개발자들과 협업하여 기획부터 배포까지 진행했습니다.

**`[기간]`**

2024.03.21 ~ 2024.07.01 (3개월)

**`[인원]`**

4명 (프론트엔드 2명, 백엔드 2명)

**`[담당 주요 업무]`**

- Spring Boot, JPA, MariaDB 기반 REST API 개발
- ERD 설계, API 명세서 작성
- 회원, 알림, 채팅, 중고 상품 거래 & 경매, 후기 도메인 개발
- 테스트 코드 작성 및 코드 커버리지 관리
- AWS 배포 및 CI/CD 파이프라인 구축 

**`[개발 내용]`**

- OAuth 기능을 사용한 네이버, 카카오, 구글 로그인과 JWT 토큰을 이용한 Access Token 기반 로그인/회원가입 기능 개발
- 최초 로그인 시 유저 정보를 Redis에 캐싱하여 매번 DB를 조회하지 않도록하고 토큰의 Payload에 담는 유저 정보를 최소화
- WebSocket, STOMP를 이용하여 실시간 채팅 기능을 구현하고, 외부 브로커로 RabbitMQ 적용
- SSE(Server-Sent Events), Spring AMQP(RabbitMQ)를 이용한 알림 전송 기능 구현
- 이벤트 종류에 따라 수행되는 알림 전송 로직을 Template Method 패턴을 적용하여 분리 
- JaCoCo 라이브러리를 사용한 코드 커버리지 측정과 CodeCov로 측정 결과 기록
- 효율적인 코드 리뷰를 진행하기위해 ChatGPT 4o로 먼저 리뷰를 받도록 적용

**`[트러블슈팅]`**

- RabbitMQ를 사용하며 메시지를 소비하는 부분에 예외가 발생하는 문제를 겪고 RetryPolicy를 적용 ([블로그 링크](https://kjy042386.tistory.com/534))
- 프론트엔드와 백엔드 연동 시 발생하는 CORS 에러를 Reverse Proxy로 Nginx를 적용하고 설정해줌으로써 해결 ([블로그 링크](https://kjy042386.tistory.com/535))
- Nginx에 기본으로 HTTP/1.0을 사용함으로써 발생하는 SSE, WebSocket 지속연결 끊김 문제 해결 경험 ([블로그 링크](https://kjy042386.tistory.com/542))
- Redis의 OOM(Out Of Memory) 문제를 예방하기위한 Memory 설정 경험 ([블로그 링크](https://kjy042386.tistory.com/539))
- 경매 입찰 기능에서 발생하는 DB 동시성 문제를 해결하기위해 낙관적 락과 Spring Retry를 적용한 재시도 전략 적용 경험 ([블로그 링크](https://kjy042386.tistory.com/543))
- JMeter를 사용한 부하 테스트를 통해 Nginx에서 설정한 keep-alive의 문제를 발견하고 해결한 경험 ([블로그 링크](https://kjy042386.tistory.com/549))

**`[사용 기술]`**

- Framework: `SpringBoot 2.x`, `SpringSecurity`, `Spring Mail`, `SpringDataJPA`, `QueryDSL`, `Spring WebSocket`, `Spring Actuator`, `Spring AMQP (RabbitMQ)`, `SSE(Server-Sent Event)`
- Database: `MariaDB`, `H2`, `Redis`
- Container: `Docker`
- Proxy: `Nginx`
- AWS: `EC2`, `S3`, `RDS`, `ElastiCache`
- CI/CD: `GithubAction`, `CodeDeploy`
- Testing: `JUnit5`, `Mockito`, `JaCoCo`, `CodeCov`, `Jmeter`
- Monitor: `Grafana`, `Prometheus`
- Tool: `Notion`, `Postman`

**`[Github 링크]`**

- https://github.com/fresh-trash-project/fresh-trash-backend

**`[데모 Notion 링크]`**

- https://sticky-amusement-21c.notion.site/Demo-Fresh-Trash-3cd71413eefe4bc385d13e7b2ea59bd4?pvs=4

---

### ✨ 3D 모델 공유 게시판 웹 서비스

**`[소개]`**

누구나 3D 모델을 공유하고 다운로드받을 수 있도록하는 게시판 웹 서비스입니다. 개인 프로젝트로 진행했으며 서버 사이드 렌더링(SSR) 방식으로 프론트엔드와 백엔드 개발을 했습니다.

**`[기간]`**

2023.08.03 ~ 2024.04.26 (9개월)

**`[인원]`**

1명

**`[담당 주요 업무]`**

- Thymeleaf, javascript 기반 서버 사이드 렌더링 방식의 프론트엔드 개발
- Spring Boot, JPA, MariaDB 기반 REST API 개발
- 회원, 게시판, 댓글, 알림 도메인 개발
- AWS 배포 및 CI/CD 파이프라인 구축

**`[개발 내용]`**

백엔드

- OAuth 소셜 로그인과 JWT 토큰을 이용한 Access Token, Refresh Token 기반 로그인/회원가입 기능 개발
- SSE(Server-Sent Events) 방식의 댓글 알림 전송 기능 구현
- QueryDSL을 사용하여 게시글 검색/정렬 기능 구현
- Spring Mail을 사용하여 회원가입 시 인증 코드 발송

프론트엔드

- Thymeleaf를 이용하여 렌더링한 페이지를 반환하고, javascript 기반으로 버튼, 입력 폼 등 화면 동작을 구현
- `online-3d-viewer` 라이브러리를 사용하여 3D 모델 뷰 구현
- 페이지네이션을 구현하여 최대 5개 페이지 숫자가 나타나도록 반영했으며, 페이지당 9개의 게시글이 3x3 형태의 그리드로 표시되도록 구현
- 읽지 않은 알림의 존재 여부에 따라 알림 아이콘을 구분하여 표시되도록 구현
- 게시글 수정 시 파일이 수정되지 않았을 경우, 이를 서버에 알리기위해 임의로 "NotUpdated" 내용을 가지는 파일을 생성하여 API 요청 바디에 추가
- 국세청 사업자등록번호 공공데이터 API를 사용하여 사업자 인증 기능 구현
- Kakao Map API를 사용하여 주소 입력 기능 구현

**`[트러블슈팅]`**

- Spring Mail 전송 시 발생하는 레이턴시 문제를 비동기 처리를 적용하여 해결
- CodeDeploy를 이용하여 배포를 진행할 때, 저장되는 파일 개수를 지정하여 용량을 절약 ([블로그 링크](https://kjy042386.tistory.com/506))
- JPA N+1 문제 해결 ([블로그 링크](https://kjy042386.tistory.com/514))
- 게시글의 좋아요 수를 업데이트할 떄 발생하는 동시성 문제 해결 ([블로그 링크](https://kjy042386.tistory.com/532))

**`[사용 기술]`**

- Frontend: `Javascript`, `HTML`, `CSS`, `Bootstrap`
- Backend:
    - Framework: `SpringBoot 2.x`, `SpringSecutiry`, `SpringDataJpa`, `QueryDSL`, `SpringMail`
    - Database: `MySQL`, `MariaDB`
    - Proxy: `Nginx`
    - AWS: `EC2`, `S3`, `RDS`
    - CI/CD: `GithubAction`, `CodeDeploy`
    - Testing: `Junit5`, `Mockito`

**`[Github 링크]`**

- https://github.com/JadeKim042386/My3d
- 추가로 백엔드 파트만 따로 작업: https://github.com/JadeKim042386/My3d-BACKEND

---

### ✨ 계좌 관리 시스템 API

**`[소개]`**

계좌를 개설/해지하거나 개설한 계좌의 잔액을 사용하기위한 REST API 

**`[기간]`**

2024.12.26 ~ 2024.01.04 (2주)

**`[인원]`**

1명

**`[담당 업무]`**

- Spring Boot, JPA, H2 기반 REST API 개발
- 계좌 생성/삭제/조회 API 개발
- 계좌의 잔액 사용하거나 취소하는 거래 처리 API 개발

**`[개발 내용]`**

- 동시에 같은 계좌의 잔액을 사용하는 경우 발생하는 동시성 문제를 Redis의 분산락을 활용하여 해결
- 분산락 적용의 재사용성을 고려하여 AOP로 구현

**`[사용 기술]`**

- Framework: `SpringBoot 2.x`, `SpringDataJPA`
- Database: `H2`, `Redis(embedded)`

---

### ✨ 공공 와이파이 검색 웹 서비스

**`[소개]`**

사용자 위치를 중심으로 가장 가까운 공공 와이파이 정보를 제공하는 웹 서비스

**`[기간]`**

2023.11.28 ~ 2023.12.17 (3주)

**`[인원]`**

1명

**`[담당 업무]`**

- Java, JSP, MySQL 기반 웹 서비스 개발
- ERD, 주요 핵심 기능 설계
- 공공와이파이 OpenAPI를 활용하여 DB에 변경분만 업데이트하도록 구현
- Spring의 RestTemplate을 이용해 API 요청
- 즐겨찾기, 와이파이, 거리 계산, 히스토리 도메인 개발

**`[사용 기술]`**

- Framework: `JSP`, `SpringBoot 2.x`, `SpringDataJPA`
- Database: `MySQL`
- Etc: `공공데이터 OpenAPI`

**`[Github 링크]`**

- https://github.com/JadeKim042386/PublicWifiService
