# 내일배움캠프 240422 TIL
Java 1일차
Java란.. 자바, 변수와 상수 이해하기
-------------------------------------------

- Java는 A언어의 기능 + B언어의 기능 + C언어의 기능에 JAVA 언어의 기능을 추가한 언어입니다.
  핵심 기능 : C언어 기능 + 공통 실행환경🗺️(놀이터), 클래스🗑️(바구니 틀), 객체🪣(바구니)
  C언어 기능에 여러 기기에서 실행 가능하도록 도와주는 공통 실행환경🗺️, 그리고 데이터🔢와 메서드🎁를 담는 클래스🗑️(바구니 틀)를 통해 객체🪣(바구니)를 만들 수 있는 언어

  
- 저장 공간의 선언
  Java 프로그램에서 값을 다루기 위해서는 값을 저장해둘 **저장 공간(그릇)**의 선언이 필요합니다.
  선언할 때는 **저장 공간(그릇)**에 담을 **값의 타입**과 **이름**을 명시하여 선언합니다.
  int number; // number 라는 이름의 int(숫자)타입의 저장공간을 선언
  String name; // name 이라는 이름의 String(문자열)타입의 저장공간을 선언
- 값의 저장
  Java 프로그램에서 저장 공간에 값을 저장하는 방법은 2가지입니다.
  int number = 10; // 1. 선언과 동시에 값을 저장공간에 저장 (=초기화)
  number = 11; // 2. 선언 이후에 다른값을 저장공간에 저장

- 변수 : 변하는 저장 공간🍽️
  🍽️접시라는 공간에서 내가 먹을 음식을 자유롭게 담았다가 먹어 치우고 다시 다른 음식을 담는 걸 반복하는 것과 비슷하다고 보시면 됩니다.
  “저장 공간”이라고 표현한 이유는 “변하는 것”이라는 의미에 맞게 저장하고 있는 값이 달라질 수 있기 때문입니다.
  int number = 10; // 1. 변수로 선언 및 초기화
  number = 11; // 2. 변수의 값을 바꾼다. (덮어쓰기)
- 상수 : 변하지 않는 저장 공간🥘
  🥘냄비에는 찌개를 담아놓고 식사를 다할 때까지 다른 걸 담지 않는 것과 비슷하다고 보시면 됩니다.
  “변하지 않는 저장 공간”이라고 표현한 이유는 저장 효율을 위해 “변하지 않을 값”을 따로 저장하는 공간이 있기 때문입니다.
  final int number = 10; // 1. 상수로 선언 (데이터 타입 앞에 final 을 붙이면 됩니다.)
  number = 11; // e2. 변수의 값을 바꾸려고하면 에러가 납니다!

- 변수의 종류와 범위

- 기본형 변수
  1. 논리형 변수 : boolean  // True/False 값만 저장합니다.
     boolean flag = true; // 1. 논리형 변수 boolean 으로 선언 및 True 값으로 초기화
      flag = false; // 2. False 값으로도 저장할 수 있습니다.
  
  2. 문자형 변수 : char
     ‘A’, ‘1’ 와 같은 문자 하나만 저장합니다.
      char alphabet = 'A'; // 문자 하나를 저장합니다.
​
  3. 정수형 변수 : byte, short, int, long
     0,1,2,99 와 같은 정수형 숫자 값을 저장합니다.
      정수형 변수 표현 범위
      📌각 변수 표현 범위를 넘는 숫자를 넣게 되면 오버플로우가 발생하고, 해당 숫자를 출력해 보면 입력값과 다른 값으로 표현됩니다. 
      (표현 범위를 초과한 것이기 때문에 입력한 값보다 작거나 음수인 값이 표현됩니다.)
      💁‍♂️ 그렇기 때문에 각 변수들의 표현 범위를 잘 알아야 버그가 생기지 않습니다!
      byte : -128 ~ 127 범위의 숫자만 저장 가능합니다.
      short (2byte)는 -32,768~32,767 범위의 숫자만 저장 가능합니다.
      int (4byte)는 -21억~21억 범위의 숫자만 저장 가능합니다.
      long (8byte)은 9백경 정도의 매우 큰 수를 저장 가능합니다.
        byte byteNumber = 127; // byte 는 -128 ~ 127 범위의 숫자만 저장 가능합니다.
        short shortNumber = 32767; // short 는 -32,768~32,767 범위의 숫자만 저장 가능합니다.
        int intNumber = 2147483647; // int 는 -21억~21억 범위의 숫자만 저장 가능합니다.
        long longNumber = 2147483647L; // long 은 숫자뒤에 알파벳 L 을 붙여서 표기하며 매우 큰수를 저장 가능합니다.

  4. 실수형 변수 : **float, double**
      0.123, 0.99999 와 같은 소수점 실숫값을 저장합니다.
  실수형 변수의 표현 범위
    📌 실수도 동일하게 각 변수 표현 범위를 넘는 숫자를 넣게 되면 오버플로우가 발생하고, 해당 숫자를 출력해 보면 입력값과 다른 값으로 표현됩니다.
       특히, 실수는 표현 범위가 매우 넓어서 정수형 변수에서 담지 못할 수 있습니다.
      float (4byte) : `3.4 * -10^38` ~ `3.4 * 10^38`(long 보다 큼) 범위의 숫자 저장이 가능합니다.
      double (8byte) :  `1.7 * -10^308` ~ `1.7 * 10^308`(long 보다 큼) 범위의 숫자 저장이 가능합니다.
    ✋ float 가 long 보다 더 넓은 범위를 표현하기 때문에 자동 형변환이 안됩니다.
        long longNumber = 3.14f; // long < float 자동 형변환 불가
  float floatNumber = 0.123f; // float 는 4byte 로 3.4 * 10^38 범위를 표현하는 실수값
  double doubleNumber = 0.123123123; // double 은 8byte 로 1.7 * 10^308 범위를 표현하는 실수값

 - 참조형 변수
    1. 문자열 변수 : String
     “Apple”, “텍스트” 와 같은 문장을 저장합니다.
    String message = "Hello World"; // 문자열을 저장합니다.

​    2. 그 외 : Object, Array, List …
    객체, 배열, 리스트와 같은 단일 저장공간에 담을 수 없는 값을 저장합니다.
    List<int> alphabet = [0,1,2,3]; // 기본형 변수 여러개를 저장합니다.

- 래퍼 클래스 변수
    📌 래퍼 클래스(Wrapper Class)라는 말 그대로 “기본형 변수를 클래스로 한번 랩핑(감싸는) 변수”라고 생각하시면 됩니다.
       기본형 변수 타입명에서 첫 글자를 대문자로 바꾸어서 래퍼 클래스를 정의해 주었습니다.
       박싱 VS 언박싱
          기본 타입에서 래퍼 클래스 변수로 변수를 감싸는 것을 “박싱”이라고 부르며
          래퍼 클래스 변수를 기본 타입 변수로 가져오는 것을 “언박싱”이라고 부릅니다.
        **[코드 스니펫]** 박싱 vs 언박싱
  
            // 박싱
            // Integer 래퍼 클래스 num 에 21 의 값을 저장
            int number = 21;
            Integer num = new Integet(number);

            // 언박싱
            int n = num.intValue(); // 래퍼 클래스들은 inValue() 같은 언박싱 메서드들을 제공해줍니다.
            
          실습한 int, Integer 외에도 모든 기본 타입에는 래퍼 클래스가 있습니다.
            | 기본 타입	| 래퍼 클래스 |
            | --- | --- |
            | byte | Byte |
            | short | Short |
            | int | Integer |
            | long | Long |
            | float | Float |
            | double | Double |
            | char | Character |
            | boolean | Boolean |
  
        -❓ 왜, 굳이 래퍼 클래스를 사용하는 건가요?
          클래스는 객체지향 언어인 Java의 핵심 기능인데요. 그렇기 때문에 클래스로 변수를 관리하면 객체지향의 많은 기능을 사용할 수 있게 됩니다!! 👍
        
---------------------------------------------------------------------------------------------------------------------------------------
아직까지 이해하고 정리해서 쓰기엔 무리... 오늘은 이론만.. 비록 복붙이지만 나중에 혼자 할 수 있는 그날까지 ~
  
  
