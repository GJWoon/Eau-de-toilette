# Eau-de-toilette
마켓컬리 클론코딩

##  사용도구
##### OS - window
##### Language - JAVA/Spring, Html5/css3, Javascript, JQuery
##### DB - Oracle 11g, mybatis
##### Server - Apache tomcat, AWS RDS(DB서버)
##### Tool - eclipes, STS, SQL Developer


#### 기타 라이브러리 / API

| 라이브러리                    |
| ------------------------------|
| jstl                          |
| JSON-simple                   |
| cos                           |
| javaMail API                  |
| gson                          | 
| lombok                        | 
| smartEditor                   | 
| coolsms                       | 
| toast UI Chart                | 



## 👩‍💻 Member 

#### 정현봉
- 마이페이지
- - 개인정보수정(회원) 
- - 배송지 등록(회원)
- - 주문 내역(회원)
- - 이벤트 게시판(회원, 관리자)
- - 회원 관리,통계(관리자)
- - 주문 관리, 통계(관리자)

### DB 설계
![1](https://user-images.githubusercontent.com/59170160/111323357-24374c00-86ad-11eb-8ee2-8f6becdbbe08.png)

### 테이블 정의서
![2](https://user-images.githubusercontent.com/59170160/111323363-25687900-86ad-11eb-8433-3e1c6fca17f5.png)
![3](https://user-images.githubusercontent.com/59170160/111323699-77110380-86ad-11eb-9004-3a10a5d07042.png)

### 기능 설명
#### 마이페이지(회원)
![마이페이지기본](https://user-images.githubusercontent.com/59170160/111327024-60b87700-86b0-11eb-8a99-122e3a96d99d.png)
![모달](https://user-images.githubusercontent.com/59170160/111333202-d115c700-86b5-11eb-8b6b-ee3b515cff1f.png)
- 마이페이지 기본 화면입니다.
- 위의 등급 영역은 따로 jsp파일을 만들어 include 하여 ajax로 화면이 로드 될 때마다 지금 로그인 중인 회원의 세션을 사용해 DB에서 회워느이 정보를 띄워줍니다.
- 전체 등급보기 버튼을 누르면 현재 자신의 등급과 다음 등급까지의 필요한 포인트를 알려주는 팝업을 띄우게 하였습니다. 이 때 데이터는 ajax를 활용해 비동기로 처리하였습니다.
![개인정보수정](https://user-images.githubusercontent.com/59170160/111327008-5dbd8680-86b0-11eb-905b-057b833b7b1e.png)
![개인정보수정2](https://user-images.githubusercontent.com/59170160/111327011-5e561d00-86b0-11eb-8912-e6e0ddd7ca80.png)
- 마이페이지의 개인정보수정 기능입니다.
- 먼저 로그인 중인 회원의 아이디를 가져와 id input 안에 값을 넣어주고 비밀번호를 입력하면 두가지 값으로 DB에서 비밀번호와 아이디 비교 후 본인인증을 하도록 코딩하였습니다.
- 그리고 확인이 되면 아래의 페이지로 넘어가 자신의 정보를 수정하는데 자신이 수정하고 싶은 정보만 수정해도 되도록 구현하였습니다.
- 만약 이메일을 수정 할 때에는 중복확인을 하도록 코딩하였고 휴대폰은 coolsms를 활용해 문자인증을 하여 본인인증을 하도록 구현 하였습니다.
![마이페이지주문](https://user-images.githubusercontent.com/59170160/111327032-61510d80-86b0-11eb-94fe-8be1abf11237.png)
![마이페이지주문상세](https://user-images.githubusercontent.com/59170160/111327035-61e9a400-86b0-11eb-8b18-950ee0ba737a.png)
- 마이페이지의 주문 내역 기능입니다.
- 먼저 자신의 주문내역을 모두 불러와 화면에 나타내주었고 하나의 주문내역을 고르면 상세 화면으로 넘어가게 하였습니다.
- 상세 화면에서는 해당 상품에 대한 후기를 적을 수 있도록 후기 작성 버튼을 만들어 주어 해당 상품 페이지로 화면을 이동 시키도록 구현 하였습니다.
- 그리고 아래의 주문취소는 관리자가 아직 주문 확인을 하지 않은 상태에서만 버튼이 보이도록 구현하였습니다.  
![배송지관리](https://user-images.githubusercontent.com/59170160/111327038-61e9a400-86b0-11eb-81c6-3e24ed885a3f.png)
![배송지팝업](https://user-images.githubusercontent.com/59170160/111327043-62823a80-86b0-11eb-946a-174c64223d8c.png)
![배송지팝업2](https://user-images.githubusercontent.com/59170160/111327045-631ad100-86b0-11eb-985d-c4a5fe909149.png)
- 마이페이지의 배송지 관리 기능입니다.
- 위에 있는 배송지 추가 버튼이나 수정 아이콘을 누르면 배송지를 등록하거나 수정 할 수 있는 팝업을 띄워주도록 구현하였습니다.
- 팝업의 주소 검색 버튼을 누르면 도로명 주소 api를 활용해 자신의 주소를 검색 할 수 있는 팝업을 띄워주도록 구현하였습니다.
- 그리고 라디오 버튼을 활용해 기본 배송지 이외의 다른 배송지의 라디오 버튼을 선택하면 그 배송지가 기본 배송지로 변경되도록 구현하였고 변경 후엔 페이지를 reload 시켜주었습니다.
- 최대 5개의 배송지를 입력 할 수 있도록 제한을 두었습니다.
#### 마이페이지(관리자)
![관리자기본](https://user-images.githubusercontent.com/59170160/111327015-5eeeb380-86b0-11eb-926e-4576ec3e5854.png)
- 관리자가 로그인 했을 시에 볼 수 있는 마이페이지 화면입니다.
- 위는 통계 그래프를 보여주고 아래에는 관리자가 관리 할 수 있는 기능을 구현 하였습니다.
![관리자주문통계](https://user-images.githubusercontent.com/59170160/111327016-5eeeb380-86b0-11eb-8e66-6a6458b7d7e8.png)
![관리자주문확인](https://user-images.githubusercontent.com/59170160/111327017-5f874a00-86b0-11eb-943c-9a1259185210.png)
- 관리자의 주문 관리 화면입니다.
- 먼저 매 달 주문 통계를 확인 할 수 있도록 toast ui chart를 활용해 주문 횟수를 띄워주고 해당 꼭지점에 마우스를 올리면 갯수를 보여주도록 구현 하였습니다.
- 주문 관리는 주문 리스트를 모두 불러와 입금완료가 되어있는 항목은 배송중으로 처리 할 수 있는 확인 버튼을 만들고 ajax로 비동기 처리하여 배송 중으로 바뀌도록 구현하였습니다.
- 그리고 페이징 처리를 하여 한 페이지에 10개의 주문내역을 불러오도록 구현하였습니다.
![관리자회원통계](https://user-images.githubusercontent.com/59170160/111327021-601fe080-86b0-11eb-876d-9108b283dc23.png)
![관리자회원관리](https://user-images.githubusercontent.com/59170160/111327019-601fe080-86b0-11eb-95e3-00c6d2142787.png)
- 관리자의 회원 관리 화면입니다.
- 먼저 매달 회원의 유입 수를 확인 할 수 있도록 toast ui chart를 활용해 주문 관리와 동일하게 구현하였습니다.
- 그리고 모든 회원의 리스트를 불러와 화면에 보여주고 주문 관리와 동일하게 페이징 처리를 해주었습니다.
- 옆의 쓰레기통 버튼을 누르면 해당 회원은 탈퇴 처리가 되고 페이지가 reload되도록 구현하였습니다.
#### 마이페이지(회원,관리자)
![이벤트리스트](https://user-images.githubusercontent.com/59170160/111327047-631ad100-86b0-11eb-91c3-afa5b74e1ebb.png)
![이벤트상세](https://user-images.githubusercontent.com/59170160/111327050-63b36780-86b0-11eb-85d1-49fddcfa06ed.png)
![이벤트추가](https://user-images.githubusercontent.com/59170160/111327053-644bfe00-86b0-11eb-90d4-367db7b6dce9.png)
![이벤트수정](https://user-images.githubusercontent.com/59170160/111327051-644bfe00-86b0-11eb-91be-e1798a86048b.png)
![헤더이벤트](https://user-images.githubusercontent.com/59170160/111332124-daeafa80-86b4-11eb-9b37-58e3b3c33503.png)
- 관리자와 회원의 공통 메뉴입니다.
- 이벤트 리스트를 불러와 보여줍니다. 이 때 로그인 중인 정보를 가져와 회원인지 관리자인지 확인 후 삭제 버튼인 쓰레기통 아이콘을 보여줄지 말지 결정 하였습니다.
- 상세 화면에서도 마찬가지로 수정과 삭제 버튼은 관리자로 로그인 한 경우에만 보이도록 구현 하였습니다.
- 수정과 추가 기능은 스마트 에디터를 활용해 자신이 적은 스타일 그대로 DB에 저장시켜 상세 화면에서 보일 때에도 동일하게 보이도록 구현 하였습니다.
- 이렇게 수정이나 작성된 이벤트는 메인페이지의 이벤트 영역에서 마감일이 오늘 날자 이 후인 이벤트를 차례대로 불러와 javascript를  슬라이드로 보이게 구현 하였습니다.

