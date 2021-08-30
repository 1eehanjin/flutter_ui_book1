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

- 위젯을 const로 하면 가비지 컬렉터가 덜 작동하는 부분에서 약간의 성능 향상을 기대할 수 있다. 하지만 아주아주아주 미세하다. 근데 EdgeInsects에는 보통 const 붙이는 듯

- AspectRatio 위젯은 자식 위젯의 가로:세로 비율을 일정한 비율로 하기 위한 위젯이다. 가로 크기는 가능한 공간을 최대한 차지한 뒤, 세로 크기는 주어진 비율에 따라 정해진다.

  

### 6장 플러터 위젯 - 프로필 앱 만들기
- flutter_profile
- 다양한 기기 화면 테스트를 위해선 device_preview 패키지를 이용한다.
- 어떤 클래스 안에서 쓸 위젯을 클래스 내부에서 build() 함수 바깥에 따로 widget함수로 구현할 때는 _를 붙여서 해당 클래스 안에서만 접근하게 한다.
- ThemeData를 별개의 파일로 분리한다.
- InkWell()은 터치가 되는 영역을 나타내기 위해서 터치되면 동그란 그림자가 퍼져나가는 위젯이다.
- container로 가능한 영역을 다 채울때는 double.infinity 사용
- 동그란 유저 프로필 이미지를 나타내기 위한 CircleAvatar()란 위젯이 있다. 이미지를 동그란 칸 안에 넣을 때 쓰는 위젯이라 생각하면 될 듯

### 7장 플러터 위젯 - 로그인 앱 만들기
- flutter_login
- size 조절용 변수만 따로 저장하는 파일 만들면 관리 편함
- themeData에는 textButtonTheme도 설정 가능하다. 또 TextButton.styleFrom()의 minimumSize 인수 이용하면 최소 크기도 설정 가능함
- Form()은 입력 칸 양식이 유효한지 확인하기 위해 사용하는 위젯. 보통 globalKey나 Form.of()를 사용하여 접근한다. [Form cookbook](https://flutter.dev/docs/cookbook/forms/validation)
- //TODO: [key 이해하기](https://www.youtube.com/watch?v=lQB6HjleLMs)

### 8장 플러터 위젯 - 쇼핑카트 앱 만들기
- flutter_shoppingcart

- 색상 변수만 따로 저장하는 파일 만들면 관리 편함

- ClipOval: 하위 위젯을 동그라미나 타원 모양으로 하기 위한 위젯

- 한 페이지에서만 쓰는 위젯 컴포넌트는 그 페이지 클래스 안에다 만들어도 되지만, 여러 페이지에서 쓰는 공용 위젯 컴포넌트는 별개의 파일로 뽑아서 저장하자 !

-  텍스트 버튼 꾸미기 ... 참고로 테마데이터에도 설정 가능, 최소 사이즈도 설정 가능

  ```dart
  TextButton(
  	style: TextButton.styleFrom()
  )
  ```

- Align: 자식 위젯 위치 조절용 위젯

### 9장 플러터2.0 - 모두의숙소 웹 만들기

- flutter_airbnb

### 10장 모두의채팅 UI 만들어보기
- flutter_kakao

### 샘플 assets 모음
- 프로젝트에 필요한 모든 이미지, 폰트, 로고를 모아둔 폴더
- 