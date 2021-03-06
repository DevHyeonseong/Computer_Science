# MVVM : Model, View, ViewModel



## 1. MVVM이란?
Model, View, ViewModel 의 줄임말으로써, 하나의 소프트웨어를 최대한 기능적으로 작은 단위로 나누어 테스트가 쉽고 큰 프로젝트도 상대적으로 관리하기가 좋은 구조
## 2. MVVM의 구조

### 2.1. Model
	* 프로그램 내부적으로 쓰이는 데이터 저장 및 처리
	* ViewModel에서 데이터를 가져갈 수 있게 데이터를 준비하고 "이벤트" 를 보냄

### 2.2 View
	* UI를 담당하며 Activity, Fragment 등이 있다
	* UI 변경과 관련된 일부 로직은 포함될 수 있음.
	* ViewModel을 관찰하고 있다가 상태 변화가 전달되면 화면을 갱신해야함

### 2.3 ViewModel
	* Model과 View 사이의 매개체
	* 모든 View와 관련된 비즈니스 로직은 이 곳에 들어가게 되며 데이터를 잘 가공해서 View에서 뿌리기 쉬운 Model로 바꾸는 역할을 함
	* View와 ViewModel은 1:n의 관계를 가질 수 있음
	* ViewModel은 View가 데이터 바인딩 할 수 있는 속성과 명령으로 구성되어 있음.

![Alt text](https://media.vlpt.us/images/jojo_devstory/post/5d3e1aa5-28bc-45d3-964f-36e60e4e9088/%EC%BA%A1%EC%B2%98.PNG)

## 3. MVVM으로 개발된 앱의 특징
	* 하나의 소프트웨어를 최대한 기능적으로 작은 단위로 나눈다
	* 테스트가 쉬워지고 큰 프로젝트도 상대적으로 관리하기 좋다
	* SOLID 원칙을 지향한다
	* 앱이 구조적으로 약한 결합의 컴포넌트로 나눠진다

## 4. MVVM 기본 원칙
	* View에서 액션을 받으면 ViewModel에서 비즈니스 로직을 실행한다
	* ViewModel은 Model의 데이터를 수정한다
	* ViewModel은 데이터 바인딩과 노티피케이션을 통해 View를 수정한다
	* 오직 ViewModel만이 Model에 접근할 수 있다.
	* View는 Model에 접근할 수 없다.

## 5. MVVM의 장점
가장 좋은 장점은 Model과 View, ViewModel과 View 사이의 의존성이 없는 것 입니다. 또한 Databinding 라이브러리를 이용함으로써, 유닛 테스트를 더욱 쉽게 작성할 수 있고 UI 코드는 네이티브 코드에 관여하지 않아도 됩니다. 중복되는 코드를 모듈화 할 수 있습니다.

## 6. MVVM의 단점
View가 변수와 표현식 모두에 binding 될 수 있으므로 시간이 지남에 따라 관계없는 Presentation Logic이 늘어나고 이를 보완하기 위해 XML에 코드를 추가하게 됩니다. 이때 난해하게 코드가 증가된다면 유지보수 단계에서 어려움을 겪을 수 있습니다. 또 ViewModel은 설계하기가 어려운 문제도 있습니다. 다행히 요즘은 잘 설계된 구조가 샘플 코드로 많이 나와 있기 때문에 해결이 가능합니다.

## 7. MVVM 등장 배경
전통적인 UI개발에서 개발자는 윈도우, 사용자 컨트롤, 페이지를 사용해서 View를 만들곤 했다. 그리고 모든 논리 로직이 들어간 코드를 뷰 클래스에 정의한다. 이러한 방법은 뷰 클래스의 크기를 늘리고 UI와 데이터, 비즈니스 로직 사이의 매우 강한 의존성을 형성한다. 이와 같은 상황에서 여러 개발자들은 동시에 같은 뷰에서 작업하기 힘들어 질 것이다. 즉, 협업하는 상황에서 같은 화면을 함께 개발하지 못하고 서로 다른 화면을 개발해야 하는 비효율적인 상황이 발생할 것이다. 또한, 다른 개발자가 코드를 바꾸면 다른 부분을 망가뜨릴 위험도 존재한다. 이처럼 모든 코드들이 한 클래스에 있는 것은 유지보수 및 테스트를 하는데 있어서 좋지 않다. 따라서 앞서 나온 상황 들을 해결하기 위해 MVVM같은 디자인 패턴이 등장하게 되었다.

## 8. 참고
[안드로이드 아키텍처 패턴 - MVVM이 뭘까?](https://velog.io/@jojo_devstory/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98-%ED%8C%A8%ED%84%B4-MVVM%EC%9D%B4-%EB%AD%98%EA%B9%8C)

[MVVM Part.1](https://woovictory.github.io/2019/06/09/What-is-MVVM/)

