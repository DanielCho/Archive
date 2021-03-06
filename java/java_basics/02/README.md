# 자바스크립트 개발자가 배워본 자바의 특징
<br>

## JAVA의 기본 데이터형
자바스크립트 에는 데이터형의 개념이 약하다. 데이터 형이 없는건 아니지만 변수를 선언하거나 값을 가져와 사용할때 자동형 변환때문에 크게 신경쓸 일이 없다.

1. 정수형
    - byte, short, int ,long  (아무것도 쓰지않으면 int 로 잡는다)
    - 소수점에 없는 정수
    - 10진수, 16진수, 8진수, 2진수
    - 기본적으로 사용하는기준 : int
        
    | 데이터 타입 | 길이 | 범위 |
    |---|:---:|---:|
    | `byte` | 8bit  | -128 ~127  |
    | `short ` | 16bit  | -32768~32767 |
    | `int` | 32bit  | -2147483648~21483647  |
    | `long` | 64bit  | -9223372036854775808~9223372036854775807 |
    
    
2. 실수형
    - float, double (아무것도 쓰지않으면 double 로잡는다) 
    - 소수점이 있는 실수, 지수 
    -  기본본적으로 사용하는 기준 : double
    
    | 데이터 타입 | 길이 | 범위 |
    |---|:---:|---:|
    | `float` | 32bit   | 1.40239846e-45f ~3.40282347e+38f  |
    | `double  ` | 64bit   | 4.94065645841246544e-324~1.79769313486231570e+308 |

3. 논리형
    - boolean
    - true / false (논리형 리터럴) [리터널=값 ]   

4. 문자형
    - char
    - 문자 한자 
    - 유니코드 / escape 코드
    - 'a' (단일 따음표 안에 있어야한다)

5. 문자열
    -  String (혼자만 대문자를 쓴다)
    - 문자열
    -"string"
   
   
### 기억하기 
```
1. byte -> short -> int -> long -> float -> double 순으로 형변환이 가능하지만 역으로는 불가능하다, 자신보다 더 큰 수를 표현할 수 없기 때문이다.

2. 기본적으로 정수를 표현할때 상수의 데이터형은 int로 설정되어 있다. 하지만 byte나 short를 사용할때 자동으로 상수의 데이터형을 변환해준다.
   하지만 long을 사용하고싶은 경우 상수의 데이터형을 long을 사용한다는 의미의 L을 붙여주어야한다. 예) long a = 100L; 과 같이 상수값 뒤에 long상수타입이라는 것을 표시하시 위해 L을 붙여주어야 한다.
   실수를 사용할때 에도 기본적으로 double타입으로 상수의 데이터타입을 설정하기 대문에 float형을 쓰고싶다면 F를 붙여야 한다. 예) float a = 2.5F;
   참고로 char변수를 int로 변형할 수 있지만 int가 char 변수가 될수는 없다. 결국 문자열도 숫자로 인식해 표현하기 때문이다.
```

## 접근제어자(Access Modifier) 와 패키지(package)

자바에서는 디렉토리대신 패키지라는 개념을 사용한다. 윈도우를 사용할때 폴더를 만들어 파일을 관리하는것 처럼 자바에서 파일을 관리할때 package를 이용해
관리한다. 디렉토리=패키지 라고 생각해도 무방할 것 같다. 그리고 자바의 클래스앞에는 접근제어자 라고하는 것들이 붙게되고 접근제어자에 따라 다른 패키지에서 사용할 수 있는지의 유무가 변하게된다.

클래스앞에 public, protected, default, private 와 같은 키워드를 붙여 접근제어자를 정할 수 있다.

![접근제어가 표](../images/Access%20Modifier.png)

<br>

- public : 다 사용이 가능하다
- protected : 다른 패키지에 있는 경우 클래스를 상속하면 사용이 가능하다
- default : 같은 패키지만 사용 가능하며 상속하더라도 사용 할 수 없다, (클래스 앞에 아무것도 안붙이면 자동으로 default가 됨)
- private : 자기가 속한 클래스 내부에서만 사용할 수 있다.

글쓴이가 느끼기엔 평소 public과 private만 사용했는데 다른 프레임워크나 모듈을 사용하다보면 protected나 default로 작성된 클래스들이 있어 개념을 이해하는것도 필요한것 같다.