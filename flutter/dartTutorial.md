# 개요

Flutter는 dart라는 프로그래밍언어에 기반한 FrameWork이다. react를 사용하기 위해선 javascript를 알아야하는것 처럼 dart라는 언어를 익혀야 Fluter를 사용 할 수 있다. dart를 공부하며 기본적인 개념을 알아가며 학습한 내용을 기록으로 남기고자 작성된 문서이다

## Dart 기본기

- 주의사항
  코드가 끝나는 부분에 ;(세미콜론)을 붙여주지 않으면 애러가 나기때문에 항상 ;(세미콜론)을 붙여줘야한다

- dart로 콘솔 찍는법

js에서는 console.log를 이용해 브라우저 console창에 내용을 출력하지만 dart는 print라는 명령어를 사용한다

```dart
void main() {
  print('dart로 콘솔 찍어보기 test');
}
```

- 변수
  - 변수의 공통점 : dart에 변수들은 선언된 변수의 type을 타입추론을 이용해 변수에 type을 추론한다 한번 추론된 타입을 계속 유지하기 떄문에 형변환(데이터가 다른타입으로 변경되는것)을 허용하지않는다
  - var : 재할당은 가능하지만 재선언은 불가능한 변수
  - const, final : 재할당 재선언이 불가능한 변수
  - const와 final의 차이 : const로 선언된 변수는 빌드타임에 값을 알아야하고 final은 빌드타임에 값을 몰라도된다 <br> => 개인적으로 해당부분은 빌드타임에 대한 이해도가 떨어져서 이해가 안감 때문에 나중에 다시보기

```dart
void main() {
 var name = 'gdgd';
 var name = 'bdbd';

 print(name); // name이라는 변수가 이미선언되었다는 애러 출력
}
```

- dart 타입
  - int : 정수(소수점을 허용하지않는 자연수)를 표현하는 type
  - double : 실수(소수점을 허용하는 자연수)를 표현하는 type
  - bool : true 또는 false와 같이 참 거짓을 표현하는 type
  - String : 문자열을 표현하는 type
  - dynamic : typescript에 any와 같이 어떤 타입이든 허용하는 type이다 형변환을 허용한다
  - List :

```dart
void main() {
 double number = 1.1
 String strTest  = 'hello dart';

 print(number); // 1.1
 print(strTest); // hello dart
}
```

- 타입체크 : js에 typeof와 같이 dart에서도 runtimeType이라는 매소드를 이용해 변수에 타입을 체크 할 수 있음

```dart
void main() {
  double number = 1.1;

  print(number.runtimeType); // duuble
}
```

- 문자열에 변수 적용하는법 : js에서 문자열에 변수를 적용하고자하면 ``(백틱)을 이용하지만 dart는 그냥 ''(따옴표)에 바로 적용 할 수 있음 만약 메소드를 사용하지않는 단순한 불변데이터라면 ${}가아닌 $변수명 으로도 출력이 가능함

```dart
void main() {
  String testStr1 = 'dart is';
  String testStr2 = '$testStr1 easy';

  print(testStr2); // dart is easy
}
```

- null값 허용하는법 : dart에서 모든 타입들은 null 값을 허용하지않는다 null 값을 허용하기위해선 타입뒤에?를 붙여야함 그렇지 않다면 애러를 출력한다

```dart
void main() {
  String testStr1 = null ;
  String? testStr2 = null ;

  print(testStr1);  // error
  print(testStr2);  // null
}
```

- 연산자 : 연산자의 경우 기본적으로 js와 동일함
  - ??= : 연산자의 좌항값이 null인경우 우항에 있는 값을 할당하는 연산자
  - is : 좌항의 변수와 우항의 타입이 일치하는지 boolean값으로 표현해줌

```dart
  void main() {
  int? number = 1;
  print(number); // 1

  number = null;
  print(number); // null

  number ??= 3;
  print(number); // 3
}
```

```dart
  void main() {
  int number = 1;
  print(number is int); // true
  print(number is! int); // false
  print(number is String); // false
  print(number is! String); // true
}
```
