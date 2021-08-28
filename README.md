# 플러터 UI 1권

- '모두가 할 수 있는 플러터 UI 입문'  도서 속 코드를 리뷰하며 그동안 몰랐던 내용에 대해서 정리한 내용입니다.





### 1장 플러터란
 - 소스 코드 없음

### 2장 플러터 시작하기
- 소스 코드 없음

### 3장 다트 언어
- 소스 코드 없음

### 4장 플러터 위젯 - 스토어 앱 만들기
- flutter_store

- 우측 상단 디버그 배너를 없애려면 다음과 같이 debugShowCheckedModeBanner를 false로 설정한다.

  ```dart
  return MaterialApp(
        debugShowCheckedModeBanner: false,
        home: StorePage(),
      );
  ```

- Scaffold의 body로 SafeArea를 넣어주는 것이 좋다.

- Spacer() , Flexible(), Expanded()

  어떤 위젯이 Column이나 Row 안에 포함되어있을때는 자신이 차지해야할 공간 만큼만 공간을 차지한다. 하지만 차지해야하는 공간보다 더 공간을 차지하게 하고 싶다면 이런 위젯들을 쓰면 된다. 공간비는 flex 인수를 통해 설정할 수 있다.

  - Flexible():  Flexfit.loose 는 자식 위젯이 가능한 공간에서 최대한 커질 수 있지만, 더 작아도 되게 한다.
  - Expanded()는 Flexfit.tight를 설정한 flexible() 과 같다. 가능한 공간을 최대한 꽉 채우게 강제한다.
  - Spacer()는 빈공간을 꽉 채우기 위한 위젯이다. 빈 공간 전용 Expanded 라고 생각하면 될 듯

- 위젯간 공간을 띄울 때는 보통 SizedBox를 사용한다. SizedBox()는 width와 height를 설정하지 않으면 이를 최소로 한다. (자식 위젯이 없으면 0으로, 있으면 자식 위젯의 크기에 맞춘다.)  Container()는 설정 안하면 최대로 채운다.
- 상단 메뉴 폰트를 bold로 하였다.

### 5장 플러터 위젯 - 레시피 앱 만들기
- flutter_recipe
- lib 폴더에서, components(위젯 컴포넌트들), pages(페이지들) 폴더를 나눠 파일을 관리하는 것이 좋다.
- themedata에서 fontfamily를 "PatuaOne"으로 하였다.
- 상단 여유공간을 위해서라면 Scaffold()에서 Appbar()만 설정해줘도 SafeArea를 쓰지 않아도 된다. 하지만 SafeArea()는 하단 여유공간에도 영향을 끼치기 때문에 왠만하면 쓰는 것이 좋을 듯.
  참고로 SafeArea()에서 top: / bottom: 인수를 통해 선택적으로 여유공간을 줄 수 있다.
- appBar같은 것도 그냥 바로 넣기 보다는 깔끔하게 따로 빼는 것이 좋다. 다만 앱바 정도는 다른 컴포넌트와 다르게 그냥 페이지와 같은 파일(같은 클래스)에 둬도 되는 듯. 여기선 같이 둠. 
- 앱바 elevation을 1만 주어 깔끔한 느낌이 난다.
- TODO: main.dart, pages까지 봄, components 폴더 봐야한다.

### 6장 플러터 위젯 - 프로필 앱 만들기
- flutter_profile
- 

### 7장 플러터 위젯 - 로그인 앱 만들기
- flutter_login

### 8장 플러터 위젯 - 쇼핑카트 앱 만들기
- flutter_shoppingcart

### 9장 플러터2.0 - 모두의숙소 웹 만들기
- flutter_airbnb

### 10장 모두의채팅 UI 만들어보기
- flutter_kakao

### 샘플 assets 모음
- 프로젝트에 필요한 모든 이미지, 폰트, 로고를 모아둔 폴더