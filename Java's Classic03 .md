2021/02/28 Java의 정석 

p 36 ~ 41

2.3 형식화된 출력 - printf()
printf() 는 지시자를 통해 변수의 값을 여러가지 형식으로 변환해서 출력하는 기능을 가지고 있다.
%b = 불리언
%d = 10진수
%o = 8진수
%x, %X = 16진수
%f = 10진수, float
%e, %E = 지수형태표현
%c = 문자
%s = 문자열

10진수를 2진수로 출력해주는 지시자는 없다
Integer.toBinaryString(int i ) 를 사용해서 정수를 2진수로 변환해서 문자열로 받고 %s를 사용한다.
ex) System.out.printf("binNum=%s \n", Integer.toBinaryString(binNum));

char타입 값을 %d 로 출력하려면 형변환이 필수다
ex) System.out.printf("c = %cm %d \n", (int) c);

실수형 출력 지시자는 %f 가 가장많이 쓰이고
%e는 지수형태로 출력할때
%g는 값을 간략하게 표현할 때 쓰인다.

2.4 화면에서 입력받기 - Scanner

스캐너 클래스를 사용하려면 한 문장을 추가해줘야 한다.
import java.util.*; // 스캐너를 사용하기 위해 추가

그다음 스캐너 클래스 객체를 생성한다.
Scanner sc = new Scanner(System.in); // 스캐너 클래스 객체를 생성

nextLine() 메서드 호출하면 입력 대기 상태로 변한다. 다 입력하고 엔터를 누르면 입력한 내용이 문자열로 변한다.
String input = Scanner.nextLine(); // 입력받은 내용을 input에 저장
int num = Integer.parseInt(input); // 입력받은 내용을 int 타입의 값으로 변환

만약 입력받은 문자열을 숫자로 변환하려면 Integer.parseInt() 라는 메소드를 이용해서 int 타입의 정수로 변환한다.

nextInt() 나 nextFloat() 같이 변환없이 숫자로 바로 입력받을 수 있는 메소드를 사요하면 
변환하는 과정의 수고를 덜을 수 있지만 연속적으로 값을 입력받아 사용하기 까다롭다.
차라리 nextLine() 으로 모두받아 적절히 변환하는게 더 낫다.
