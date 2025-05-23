# 👟 SHOEBOX - 신발 쇼핑몰 플랫폼

사용자 친화적인 UI/UX 기반의 **신발 쇼핑몰 웹 플랫폼**입니다.  
회원, 관리자, 브랜드, 상품, 주문, 리뷰 등 다양한 기능을 갖춘 통합 쇼핑몰 서비스를 제공합니다.

---

##  주요 기술 스택

- **Backend**: Java 17, Spring Boot, Spring Security, JPA (or MyBatis)
- **Frontend**: Thymeleaf, HTML5, CSS3, JavaScript
- **Database**: Oracle
- **Build Tool**: Gradle
- **Infra/Deploy**: GitHub Actions (CI/CD), Docker (optional)

---

## 👟 주요 기능

###  사용자 (회원)
- 회원가입 / 로그인 / 로그아웃
- 마이페이지 (포인트, 주문, 배송 조회)
- 장바구니 담기 / 삭제
- 상품 Q&A 작성 및 조회
- 주문 결제 및 쿠폰 적용

###  상품
- 카테고리 / 브랜드 기반 상품 조회
- 상품 상세 보기 (이미지 슬라이드, 사이즈 옵션, 리뷰 포함)
- 실시간 재고 확인

###  주문
- 장바구니 기반 주문 생성
- 쿠폰 및 포인트 할인 적용
- 결제 수단 선택 및 배송지 입력
- 주문 상태 관리 (결제완료 → 배송중 → 배송완료)

###  관리자
- 상품 등록 / 수정 / 삭제
- 메인 배너, 팝업 공지, 이벤트 관리
- 회원 등급 / 포인트 관리
- 주문 현황 조회 및 배송 시나리오 관리
- 후기 블라인드 처리 및 신고 관리

---

## 👟 데이터베이스 주요 테이블

- **Members**: 회원 정보
- **Product / ProductStock / ProductImage**: 상품, 재고, 이미지
- **Orders / ProductStockOrder**: 주문, 주문 상세
- **Coupon / IssuedCoupon**: 쿠폰, 발급 쿠폰
- **OrderReview / OrderReviewImage / OrderReviewReport**: 리뷰, 리뷰 사진 및 신고
- **ChatRoom / ChatMessage**: 상담 채팅 시스템
- **Notice / EventPost / PopupNotice**: 공지, 이벤트, 팝업

> 상세한 DDL 구조는 [shoebox_DDL wiki](https://github.com/dnjs0/shoebox/wiki) 을 참조해주세요.

---

## 📈 프로젝트 구조 (예시)

shoebox/<br>
├── src/<br>
│ ├── main/<br>
│ │ ├── java/com/test/shoebox/<br>
│ │ ├── resources/templates/<br>
│ │ ├── resources/static/<br>
│ │ └── resources/application.yml<br>
├── build.gradle<br>
├── README.md<br>
└── shoebox_DDL.sql

---

## ✨ 향후 개선 방향

- 소셜 로그인 (OAuth2) 연동
- Redis를 이용한 캐싱 적용
- 검색 기능 향상 (상품명 + 키워드 검색)
- 실시간 상담 WebSocket 도입

---

## 📸 시연 화면

> 시연 이미지, GIF 또는 링크 추가 가능  
> 예: `/static/images/demo1.gif`

---

## 📜 라이선스

해당 프로젝트는 **MIT License**로 배포됩니다.

