
팀원(총 2명) : 이재빈, 김태영<br/><br/>


Position<br/>

프론트엔드 : 이재빈<br/>
백엔드 : 김태영<br/><br/>


프로젝트에서 맡은 역할 : SpringBoot에서 JPA로 적은 것 빼고 전부 다<br/><br/>


프로그램 툴 : React, SpringBoot 이용해 구현<br/><br/>


협업 툴 : GitHub<br/><br/>


프로젝트 기간 : 2024년 01월 05일 ~ 2024년 01월 16일 (12일)<br/><br/>


프로젝트 목적<br/>

1. miniproject2에서 구현했던 것을 React로 변환하기
2. 헤더 요소 클릭 시 해당 주제와 같은 container로 스크롤링이 되는 기능 추가
3. 스크롤 시 헤더의 요소와 container의 주제가 동일하다면 background-color 추가 및 color 변경하는 기능 추가
4. container 안에 있는 h1과 플러스, 마이너스 요소 클릭 시 display가 block, none 상태로 바뀌는 기능 추가
5. 로그인, 아이디 및 비밀번호 찾기, 내 정보 이외의 모든 요소를 한 페이지에 넣는 작업
6. DB와 정보를 불러오거나 수정 시 Alert을 띄우는 작업
7. JS코드를 이용해 API의 값을 신청하여 DB의 값을 불러오기, 수정, 삭제 기능 구현<br/><br/>


미구현 기능<br/>

miniproject2에서 구현했던 게시판은 여러 버그를 발생해 구현하지 않았고 구독 변경, 구독 취소는 시간이 모자랐기에 미구현 상태입니다. 
구독 변경, 구독 취소를 구현하지 못한 이유는 총 3가지 입니다.

1. 구독 신청을 하면 구독 기간이 기본 30일인데 그것이 하루가 지날 때마다 하루씩 줄어들어야 하는 기능 추가 필요
2. 구독 변경은 구독의 종류를 변경하는 것인데 전에 있던 구독에서 구독 종류와 가격만 바뀌고 나머지는 유지해야 하는 이슈 발생(일관성 문제)
3. 구독 취소 시 기간이 남아있더라도 구독 내역을 다 없애는 것이 맞는지에 대한 이슈 발생<br/><br/>

이는 초기에 구독에 대한 논의가 부족했다는 점과 12일이라는 짧은 기간 내에 2명이서 프로젝트를 진행해야 했기에 발생한 이슈입니다. 이 3가지 이유로 이번 프로젝트에서는 구독 변경, 구독 취소 기능은 구현하지 못했습니다.<br/><br/>



프로젝트 설명<br/>

 이번 프로젝트는 miniproject2에서 구현했던 부분들을 가져와 로그인, 회원가입 등과 같이 백엔드 부분의 예외 사항 조건이 부실했던 점을 보완하는 것과 자율 주행 자동차 같이 이동하는 것에 어울리는 스크롤 기능을 구현하여 더 나은 프로젝트로 만드는 것이 목적이었습니다. 백엔드 부분의 예외 사항 조건의 보완은 특수 문자 제외, 빈 값 제외, 로그인 상태가 아닐 시 내 정보로 갈 수 없게 막음 등등이 있습니다. 로그인, 아이디 및 비밀번호 찾기, 내 정보 이외에는 모두 한 페이지에 구현되어 있는 것은 miniproject2에서는 너무나도 많은 파일로 수정, 삭제에 어려움이 있었습니다. 또한 저번 프로젝트 때 다른 페이지로 딱딱하게 넘어가는 순간이 사용자 경험에 악영향을 준다고 느꼈고 이와 반대로 이번 프로젝트에서는 최대한 한 페이지에 구현해 봤습니다. 마지막으로 리액트로 DB에 있는 데이터를 불러오고 수정한 방식은 POST, PUT, DELETE의 방식으로 서버에 요청한 후 DB에서 session에 저장한 후 값을 가져오거나 수정했습니다. 관리자 도구를 통해 볼 수 있는 점에서 보안은 취약했지만 12일이라는 짧은 기간 내에 DB의 값을 불러오고 수정하는 기능을 구현할 수 있었기 때문에 session에 저장하는 방식을 선택했습니다.<br/><br/>


어려웠던 점<br/>

 가장 어려웠던 건 역시 비밀번호 재설정이었습니다. 재설정 form을 말씀드리자면 아이디, 전화번호, 비밀번호 재설정이라는 3개의 input이 있었습니다. 여기서 비밀번호 재설정만 기본 display: none 상태였고 아이디와 전화번호를 입력하면 아이디와 전화번호 input은 display: none으로 된 후 비밀번호 재설정은 display: block으로 변경되게 설정했습니다. 그러나 조건으로 none일 때를 적지 않으면 아이디와 전화번호를 입력했을 때의 alert과 비밀번호 재설정 값을 입력하지 않았을 때의 alert이 다 실행되는 등의 문제가 있었기에 input들이 none일 때의 조건을 전부 작성하는 작업에 어려움이 있었습니다.<br/><br/>


 배웠던 점<br/>

 이번 프로젝트를 진행하며 개념이 헷갈리던 백엔드를 프론트쪽에서 DB의 값을 불러오거나 수정하려고 API로 신청하면 백엔드는 API를 통해 값을 받고 DB의 값을 보내거나 수정한다는 사실에 대해 아는 계기가 됐습니다. 이외에도 프론트쪽에서 외래키 값을 불러올 때는 param 값에서 외래키의 기본키의 값을 적는다던가, 백엔드에서 String으로 반환한 값이 아닌 JS 코드에서 다른 String으로 반환할 수 있다던지 하는 점, 특수문자 입력을 막는 방법 등을 알게 됐습니다.
