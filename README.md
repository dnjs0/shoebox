# 👟 SHOEBOX - 신발 쇼핑몰 플랫폼

사용자 친화적인 UI/UX 기반의 **신발 쇼핑몰 웹 플랫폼**입니다.
회원, 관리자, 브랜드, 상품, 주문, 리뷰 등 다양한 기능을 갖춘 통합 쇼핑몰 서비스를 제공합니다.

복잡한 정보 구조와 광고 배너 중심의 기존 쇼핑몰과 달리,
**몰입감 있는 쇼핑 경험**을 위한 **심플하고 직관적인 UI**를 지향하며,
**모바일 환경까지 고려한 반응형 구성**을 목표로 개발했습니다.

> \[화면사진: 메인 페이지]
> \[화면사진: 상품 상세 페이지]
> \[화면사진: 장바구니 / 주문 페이지]
> \[화면사진: 관리자 상품 등록]
> \[화면사진: 관리자 주문 상세]

---

## 👟 주요 기술 스택

* **Backend**: Java 17, Spring Boot, Spring Security, JPA, MyBatis
* **Frontend**: Thymeleaf, HTML5, CSS3, JavaScript
* **Database**: Oracle
* **Build Tool**: Gradle
* **Infra/Deploy**: GitHub Actions (CI/CD), Docker (optional)

---

## 👟 주요 기능

### 사용자 (회원)

* 회원가입 (중복 검사, 비밀번호 확인, 소셜 로그인 선택)
* 로그인 / 로그아웃 / 아이디·비밀번호 찾기
* 마이페이지 (포인트, 주문, 배송 조회, 후기 및 Q\&A 관리)
* 장바구니 담기 / 삭제 / 일괄 구매
* 상품 Q\&A 작성 및 조회
* 주문 결제 (쿠폰/포인트 적용, 결제 수단 선택)

### 상품

* BEST / MEN / WOMEN / KIDS / BRAND 등 카테고리별 탐색
* 브랜드 필터, 정렬 기능 (신상품순, 할인율순 등)
* 상세페이지에서 이미지 슬라이드, 재고 수량 확인, 사이즈 선택
* 상품 후기, 별점, 문의 기능

### 주문

* 장바구니 기반 주문 생성
* 결제 수단: 카드, 무통장입금, 카카오페이 등
* 배송지 입력, 포인트 및 쿠폰 할인
* 주문 상태 관리 (결제완료 → 배송중 → 배송완료)
* 주문 취소 및 환불 요청 처리

### 관리자

* 관리자 로그인 전용 화면
* 상품 등록 / 수정 / 삭제
* 할인율 / 재고 실시간 수정
* 공지사항, 이벤트, 배너, 팝업 등록
* 회원 등급, 포인트 내역, 쿠폰 발급 및 통계 관리
* 후기 블라인드 처리, 신고 내역 확인
* 고객 문의(Q\&A, 1:1) 응답 처리

---

## 👟 데이터베이스 주요 테이블

* **Members, MemberGrade, MemberAddress**: 회원, 등급, 배송지
* **Product / ProductImage / ProductStock**: 상품, 이미지, 재고
* **Orders / ProductStockOrder / DeliveryProgress**: 주문, 상세, 배송
* **Coupon / IssuedCoupon**: 쿠폰 시스템
* **OrderReview / ReviewImage / Report**: 후기, 사진, 신고
* **Notice / Event / PopupNotice / Banner**: 메인 콘텐츠
* **ChatRoom / ChatMessage**: 실시간 고객상담
* **CustomerService**: 1:1 문의

> 전체 DDL은 [ShoeBox-DDL wiki](https://github.com/dnjs0/shoebox/wiki/ShoeBox-DDL) 참고

---

## 👟 프로젝트 구조

```
shoebox/
├── src/main/java/com.test.shoebox/
│   ├── config/              # 시큐리티, MVC 설정
│   ├── controller/          # Admin/Member 등 역할별 컨트롤러
│   ├── dto/                 # DTO 계층
│   ├── entity/              # JPA 엔티티
│   ├── repository/          # JpaRepository 정의
│   ├── service/             # 비즈니스 로직
│   └── ShoeboxApplication.java
├── resources/
│   ├── static/              # CSS/JS/이미지
│   ├── templates/           # Thymeleaf 템플릿
│   └── application.yml
├── shoebox\_DDL.sql
└── build.gradle
```

---

## 👟 담당 업무 및 기여도 (관리자 페이지 중심)

* **전체 관리자 페이지 전담 개발**

  * 상품, 주문, 리뷰, 회원 관리 등 **통합 대시보드 설계**
  * 사이드바 + 조각 템플릿(Fragment) 구조 구현
  * Thymeleaf Layout Dialect 도입으로 **모듈형 템플릿 구조화**

* **주문 상세/검색/엑셀 출력 등 복합 기능 구현**

  * 주문 상태 필터, 조건별 검색 및 페이징 구조 설계
  * fetch API 기반 비동기 송장 등록 / 주문 상태 변경 구현
  * 검색 조건 기반 엑셀 다운로드 기능

* **트러블슈팅 및 문제 해결**

  * Thymeleaf fragment 랜더링 오류 → Layout Dialect로 전환
  * 주문 상태가 실시간 반영되지 않던 문제 → fetch + 자동 새로고침
  * HashMap → LinkedHashMap 변경으로 정렬 문제 해결

---

## 👟 테스트 및 개선 경험

* `JUnit`을 활용해 주문 상태 변경 로직 단위 테스트 진행
  → 데이터베이스에 상태값이 정확히 반영되는지 검증
* 예외 처리 및 UI 반영까지 **엔드투엔드 흐름 검증 경험**

---

## 👟 실행 방법

1. **DB 설정 및 테이블 생성**

   * Oracle DB 설치 후 `shoebox_DDL.sql` 실행

2. **프로젝트 Import**

   * STS4 또는 IntelliJ에서 Gradle 프로젝트로 Import

3. **application.yml 수정**

   * DB 접속 정보, 포트, 시큐리티 설정 등

4. **서버 실행**

   * ShoeboxApplication.java 실행 또는 `./gradlew bootRun`

5. **접속 경로**

   * 사용자: [http://localhost:8090/main/](http://localhost:8090/main/)
   * 관리자: [http://localhost:8090/admin/](http://localhost:8090/admin/)

---

## 👟 시연 화면

> \[화면사진: 관리자 상품 등록 페이지]
> \[화면사진: 주문 상세 모달 UI]
> \[화면사진: 주문 상태 변경 fetch 처리 예시]
> \[화면사진: 쿠폰 관리 / 포인트 관리]
> \[화면사진: 관리자 사이드바 구조]

---

## 👟 향후 개선 방향

* OAuth2 소셜 로그인 완전 적용
* Redis 기반 캐싱 및 세션 관리 도입
* Elasticsearch 활용한 고도화된 상품 검색
* 실시간 채팅 WebSocket 연동

