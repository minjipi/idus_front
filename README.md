# 🍦 A Little Vanilla : Frontend

> 👉🏻 Summary <br />
> 이 프로젝트는 스프링부트와 리액트로 회원가입, 로그인, 카카오로그인, 상품 등록/조회/수정/삭제/좋아요/장바구니/구매 등 <br />
> 다양한 쇼핑몰 서비스를 제공하기 위해 만들어졌습니다. <br />
> 현재 [I am port](https://www.iamport.kr/?gclid=CjwKCAjws8yUBhA1EiwAi_tpEawr0NbpwdG_4bW9KRPVRXXVEdwQ32yO8SyXEhMBfxiqHIml3c8uxhoC2nYQAvD_BwE, "Iamport link") 결제 API를 연동하여 실제 거래까지 이루어지지만, 현재 배포된 사이트에서는 당일 자정에 모두 환불됩니다.<br />
> 안심하고 테스트 해보세요!
> <br />

## 사용 기술 스택

- **React**
  - Spring Framework에서 클래스패스의 라이브러리를 자동으로 인식하여 설정해주고 내장 서버를 제공하는 등 많은 편의성을 제공하기 때문에 빠른 개발이 가능하다고 생각하여 Spring Boot를 사용했습니다.
    서비스에서 회원 기능을 지원하기 때문에 이에 필수적인 인증, 인가 기능을 적용하기 위해 사용했습니다.
- JWT
  - 토큰 기반 인증을 구현하기 위해 사용하였습니다. Session 방식보다 확장성이 높고, 자원낭비가 덜하다고 생각해 (세션 클러스터링 등) 로그인 방식으로 JWT를 사용했습니다. [JWT](https://blog.naver.com/ghdalswl77/222517833354)
- **MySQL 8.0.26**
  - 상품 검색 기능을 지원하기 때문에 보다 편리한 검색을 위해 문자열 비교에서 대소 문자를 구분하지 않는다는 장점이 있는 MySQL을 사용했습니다.

<br />

## 상세 기능
> [A Little Vanilla](http://www.alittlevanilla.kro.kr, "Iamport link") 사이트에서 실제 기능 확인 하실 수 있습니다. <br />

### 📍 일반 회원가입 <br />
![회원가입](https://user-images.githubusercontent.com/68539040/174229163-87deaa3e-713b-428f-8bce-c2c0478e492d.gif) <br />  <br />

### 📍 회원 정보 변경 <br />
![정보변경](https://user-images.githubusercontent.com/68539040/174230527-aedc5dc0-8883-4a3e-bac6-e682ff4d28fc.gif)  <br />  <br />


### 🛍 상품 업로드
상품 업로드는 회원 가입 후 가능합니다. <br />
실제 쇼핑몰에서는 일반 회원가 아닌 판매자 role만 가능한 기능이지만 원활한 테스트의 진행을 위해 일반 회원도 글 작성이 가능하게 구현했습니다. <br />

![ezgif com-gif-maker](https://user-images.githubusercontent.com/68539040/174232925-6e9cb0d1-d92c-46bc-8f24-d53ba1322936.gif)  <br />  <br />

### 🧺 서랍

['서랍' 기능이란?](https://blog.naver.com/ghdalswl77/222695713878, "link")
| Feature | Request | API | 설명 | 체크 |
| ------ | -- | -- | -- | ----------- |
| 서랍 추가 | GET | /cabinet/add/{cbn_name} | 상품 1개 장바구니 담기 | ☑️ |
| 서랍 상품 추가 | PATCH | /cabinet/update/{product_idx}/{cbn_idx} | 서랍에 상품 추가. | ☑️ |
| 서랍 목록 | GET | /cabinet/cbnlist | 내 서랍 목록 조회 | ☑️ |
| 서랍 내 상품 목록 | GET | /cabinet/{cabinet_idx} | 서랍idx를 통한 서랍 내 상품 조회 | ☑️ |

<br />

### 🛒 장바구니

| Feature       | Request | API                | 설명                               | 체크 |
| ------------- | ------- | ------------------ | ---------------------------------- | ---- |
| 장바구니 추가 | POST    | /cart/in           | 상품 1개 장바구니 담기             | ☑️   |
| 장바구니 취소 | PATCH   | /cart/cancel/{idx} | 상품 idx를 통한 상품 장바구니 취소 | ☑️   |
| 장바구니 목록 | GET     | /cart/list         | 내 장바구니 목록 조회              | ☑️   |

<br />

### 📝 상품주문

| Feature  | Request | API | 설명      | 체크 |
| -------- | ------- | --- | --------- | ---- |
| 상품주문 | POST    | /   | 상품 주문 | ☑️   |
| 상품     | PATCH   | /   | 상품      | ☑️   |
| 상품     | GET     | /   | 상품      | ☑️   |

<br />

### 💳 결제

| Feature  | Request | API | 설명      | 체크 |
| -------- | ------- | --- | --------- | ---- |
| 상품결제 | POST    | /   | 상품 결제 | ☑️   |
| 상품     | PATCH   | /   | 상품      | ☑️   |
| 상품     | GET     | /   | 상품      | ☑️   |

<hr />
