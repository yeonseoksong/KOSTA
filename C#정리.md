# C\# 프로그래밍

* Intro
  - Java = C/C++ - Pointer
  - 인기가 많은 이유 = 무료 + Runtime Library
  - Java는 UNIX 베이스에서 개발된 언어이므로 리눅스 환경에서도 사용 가능하고, 윈도우, 맥 등에서도 사용이 가능하다.

  - Java의 인기에 배아픈 Microsoft가 만든 것이 C#이다. (실제)
  - 그래서 C#이 Java와 거의 같다.
  - C#은 C#을 위한 .NET FrameWork이란 환경이 필요하다.(현재 7버전 출시)
  - C#의 단점은 .NET Framework가 지원이 되어야만 사용이 가능하다. 그래서 아직 리눅스 환경에서는 완벽하게 작동되지는 않는다.
  - C#의 단점에 비해 장점이 매우 많다.


  - 개발 환경이 기존 java보다 좋다. java를 개발하기 위해서는 eclipse를 사용해야만 했고, Visual Studio보다 기능이 좋지는 않다고 한다.
    - 한때는 visual studio에서 java를 사용할 수 없었지만, visual studio code를 개발하여 사용할 수 있게 되었다. 
      - 이것으로 java, JS, html를 사용한다.


* C# 개요
  * C# : 형식 안정 객체 지향 언어로, 기존 언어들의 생산성을 개선하여 성능을 향상시킨다.
  * 초기 : Windows에서만 지원 -> 현재 : Windows, Linux, mac, android, etc... 등 지원 가능하지만, Windows 전용임은 틀림없다.
  * C#에서도 포인터라는 개념은 없어졌다.

  * 닷넷 플랫폼 + 클래스 라이브러리 => 닷넷 프레임워크(Runtime 환경)
    * 응용프로그램 프레임워크 : 윈도 폼, WPF, 윈도10 유니버셜 응용프로그램
    * 웹 응용프로그램 프레임워크 : 실버라이트
    * 웹 서버 프레임워크 : ASP.NET, ASP.NET MVC
    * 웹 서비스 프레임워크 : WCF
    * GUI 개발 (윈도 폼, WPF)
    * 웹 개발 (ASP.NET, ASP.NET MVC)
    * 게임 개발(**유니티** 등장 -> C# 영향력 커짐)
    * IoT 개발
 
  * .NET Framework 버전별 기능
    * .NET 2.0부터 본격적으로 현재의 틀, 64비트 플랫폼을 지원한다.
    * .NET 3.5부터 윈도우 10 지원
    * .NET 4.5
      * 64비트 플랫폼에서 2GB보다 큰 배열 지원
      * 콘솔에서 유니코드(UTF-16) 인코딩 지원

## C/# 프로그래밍 기초
* C# 자료형
  * 기본 자료형 -> GetType()
    * 참고 : C#에서의 char은 C/C++의 char과 달리 문자에서는 2byte이다! (주의)
    * 즉, C#에서 char은 문자라는 것을 강조한다. 그리고 C/C++과 달리 C#에서의 char은 문자열만 처리한다.
      * 변수간의 제약사항이 C/C++보다 더 타이트해졌다.
    
    | 자주 사용하는 자료형 | 설명 |
    |:---:|:---:|
    | int| 정수(4byte)|
    |long|정수(8byte)|
    |float|실수(4byte)|
    |double|실수(8byte)|
    |char|문자(c#에서는 2byte)|
    |string|문자열|
    |bool|불|

  * C# 리터럴 데이터
    * C# 코드에서 123, true, "ABC"와 같이 값을 직접 써주는 것을 **리터럴(Literal)**이라고 한다.
    * C#에서 리털러 데이터를 사용할 때, 별도의 접미어 표시(Suffix)가 없는 경우는 C# 컴파일러는 int, double, char, string, bool 데이터 타입에 기본적으로 그 값을 할당한다.
    * 따라서 특정 데이터 타입을 지정하고 싶다면 리터럴 데이터 뒤에 1~2자의 타입 지정 접미어(Suffix)를 추가해야 한다. (Suffix는 대소문자 구분이 없다.)

    ```C#
    // 디폴트 리터럴 타입
    123       // int 리터럴
    12.3      // double 리터럴
    "A"       // string 리터럴
    'a'       // char 리터럴
    true      // bool 리터럴
    ```
    
    | C# 리터럴 데이터 타입 | Suffix | ex |
    |:--|:--|:--|
    |long | L | 1024L|
    |uint|U|1024U|
    |ulong|UL|1024UL|
    |float|F|10.24F|
    |double|D|10.24D or 10.24|
    |decimal|M|10.24M|
    |char|''|'a'|
    |string|""|"Hello"|
    
  * 최댓값과 최솟값
    * 숫자형 데이터 타입의 최댓값/최솟값을 알아내기 위해선 .NET 데이터 타입 클래스들의 MaxValue, MinValue 프로퍼티를 사용한다.
    * 사용법
      ```C#
      int i = int.MaxValue;
      float f = float.MinValue;
      ```
    
  * NULL : 어떤 변수가 메모리 상에 어떤 데이터도 가지고 있지 않다는 의미로 사용 (C#에서는 소문자 null이라는 키워드를 사용)
    * C#에서는 모든 데이터 타입이 NULL를 가질 수 있는 것이 아니다.
      * Reference 타입 : NULL을 가질 수 있는 타입
        ```C#
        // string : reference 타입
        string s;
        s = null;
        ```
        
      * Value 타입 : NULL을 가질 수 없는 타입

  * Var 키워드 : 초기화할 때 자료형을 자동으로 지정. 선언과 동시에 초기화
    * 비정형 데이터이다. (이유 : 똑같은 var타입인 변수인데, 지정한 숫자 형태에 따라 자료형을 지동으로 지정할 수 있다.)
    * 중요한 것 : 선언과 동시에 초기화, 초기화할 때 자료형을 자동으로 지정한다는 것. -> 잘못하면 오류가 발생할 수도 있다.
    * 그래서 Var 키워드보다 자료형을 지정하는 것을 추천 (Var : 간편함, 관리하는 데는 불편)
      * <pre>자료형[] 이름 = {자료, 자료}</pre>

  ```C#
  Static void Main(string[] args)
  {
      var number = 20;
  }
  ```

  * 자료형 변환 메서드
  
  | 자료형 변환 | 방법 (parsing) |
  |:--:|:---|
  | 문자열 -> 숫자 | int.Parse(), double.Parse()|
  |다른 자료형 -> 문자열 | ToString() |
  | 문자열 -> 불 | bool.Parse()|
  
  ```C#
  // example.cs
  int.Parse("123")  // => 숫자 123됨
  int.Parse("3.14") // => 실수 3.14됨
  ```
  
  * C#의 복합 대입 연산자, 증감 연산자, 삼항 연산자, 조건문, 반복문 -> C, Java와 동일하다.
    * C#에서 반복문 추가된 것 : for, foreach(배열 처리할 때 유용)

  * 키 입력 메서드 : ReadKey()



  * Nullable Type
     * 정수(int)나 날짜(DataTime)와 같은 *Value Type*은 일반적으로 NULL을 가질 수 없다. 
     * C# 2.0에서부터 이러한 타입들에 NULL을 가질 수 있게 하였늗네, 이를 **Nullable Type**이라 부른다.
     * C#에서 물음표(?)를 int나 DataTime 타입명 뒤에 붙이면 Nullable Type이 된다. (int? DataTime?)
     * Nullable Type(int?)을 일반 Value Type(int)으로 변경하기 위해서는 Nullable의 .Value 속성을 사용한다.
      ```C#
      // Nullable 타입
      int? i = null;
      i = 101;
      
      bool? b = null;
      
      // int?를 int로 할당
      Nullable<int> j = null;
      j = 10;
      int k = j.Value;
      ```
* 변수와 상수
  * C/C++와 같다.
  * C#에서 상수를 지정할 때 const와 readonly 키워드를 사용할 수 있다.
    * const는 앞에 붙여서 사용한다. 필드 선언부에서 사용되거나 메서드 내에서 사용될 수 있으며, 컴파일시 상수값이 결정된다.
    * readonly 키워드를 사용하여 읽기 전용 필드를 만들 수 있다. (개념적으로 상수와 비슷하다.)
      * readonly는 필드 선언부나 클래스 생성자에서 그 값을 지정할 수 있고, 런타임시 값이 결정된다.

    ```C#
    using System;
    
    namespace ConsoleApplication1
    {
      class CSVar
      {
        // 상수 : const
        const in MAX_VALUE = 1024;
        
        // readonly 필드
        readonly int Max;
        public CSVar()
        {
          Max = 1;
        }
        //...
      }
    }
    ```
* 배열 
  * 배열 : 일련의 **동일한 데이터 타입 요소**들로 구성된 데이터 집합, 인덱스를 통하여 개개의 배열요소(Element)를 엑세스할 수 있다.
  ```C#
  // 1차 배열
  string[] players = new string[10];
  string[] Regions = {"서울", "경기", "부산"};
  
  // 2차 배열 선언 및 초기화
  string[,] Depts = {{"김과장", "경리부"}, {"이과장", "총무부"}};
  
  // 3차 배열 선언
  string[,,] Cubes;
  ```
 
  * 가변 배열(Jagged Array)
    * 배열 요소 크기가 동일한 **Rectangular 배열은 C#에서 [,]와 같이 괄호 안에 콤마로 분리하여 (C Style)** 다차원을 표현한다.
    * 각 차원별 배열 요소 크기가 가변적인 **가변 배열**의 경우 [][]와 같이 각 차원마다 괄호를 별도로 사용한다. (Java 언어 스타일)

    * 가변 배열 = 배열의 배열(array of arrays)
      * 첫 번째 차원의 크기 : 컴파일 타임에 확정되어야 하고, 그 이상 차원은 런타임시 동적으로 서로 다른 크기의 배열로 지정할 수 있다.
      * 가변 배열은 각 차원별 배열 요소가 불규칙하여 Rectangular 배열처럼 고정된 크기를 사용하면 메모리의 낭비가 심한 경우에 사용하면 유용함.
        ```C#
        // Jagged Array (가변 배열)
        // 1차 배열 크기(3)는 명시해야 한다.
        int[][] A = new int[3][];
        
        // 각 1차원 배열 요소당 서로 다른 크기의 배열 할당 가능
        A[0] = new int[2];
        A[1] = new int[3] {1, 2, 3};
        A[2] = new int[4] {1, 2, 3, 4};
        
        A[0][0] = 1;
        A[0][1] = 2;
        
        ```
  * C# 배열의 사용
    * C# 배열은 각 요소를 인덱스를 사용하여 엑세스한다.
    * 모든 C# 배열은 내부적으로 .NET Framework의 System.Array에서 파생된 것이다. 따라서 System.Array의 메서드, 프로퍼티 사요 가능함
    ```C#
    // 예시
    ststic void Main(string[] args)
    {
      int sum = 0;
      int[] scores = {80, 78, 60, 90, 100};
      for (int i = 0;i< scores.Length;i++)
      {
        sum += scores[i];
      }
      Console.WriteLine(sum);
    }
    
    ```
    
  * C# 배열의 전달
    * C#에서 배열 전체를 전달하기 위해서는 보내는 쪽에서는 배열명을 사용하고, 받는 쪽에서 동일한 배열타입의 배열을 받아들이면 된다.
    * 배열은 **reference 타입**이기 때문에, 배열을 다른 객체나 메서드에 전달할 때, 직접 모든 배열 데이터를 복사하지 않고, 배열 전체를 가리키는 참조 값(Reference pointer)만을 전달한다.
    * 즉, 전달하는 쪽에서는 단순히 레퍼런스인 배열명을 사용하며, 받는 쪽에서는 아래 예제와 같이 배열 데이터 타입 및 배열 파라미터명을 사용한다.

    ```C#
    static void Main(string[] args)
    {
      int[] scores = {80, 78, 60, 90, 100};
      int sum = CalculateSum(scores); // 배열 전달: 배열명 사용
      Console.WriteLine(sum);
    }
    
    static int CalculateSum(int[] scoresArray) // 배열 받는 쪽
    {
      int sum = 0;
      for (int i = 0; i< scoresArray.Length;i++)
      {
        sum += scoresArray[i];
      }
      return sum;
    }
    ```

* C# 문자열
  * C#의 키워드 String = .NET의 System.String 클래스와 동일 -> System.String 클래스의 모든 메서드, 속성(Property)을 사용 가능
    * 일정 문자열 부분만 뽑아내는 ```Substring()```메서드, 문자열 길이를 구하는 ```Length```속성 등을 모두 사용할 수 있다.
  
  * **C# 문자열은 Immutable하다. 즉, 한번 문자열이 설정되면, 다시 변경할 수 없다.** (이것은 다른 언어에서도 마찬가지)
  ```c#
  using System;
  
  namespace MySystem
  {
    class Program
    {
      static void Main(string[] args)
      {
        // 문자열(string) 변수
        string s1 = "C#";
        string s2 = "Programming";
        
        // 문자(char) 변수
        char c1 = 'A';
        char c2 = 'B';
        
        // 문자열 결합
        string s3 = s1 + " " + s2;
        Console.WriteLine("String: {0}", s3);
        
        // 부분 문자열 발췌
        string s3substring = s3.Substring(1, 5);
        Console.WriteLine("Substring: {0}", s3substring);
      }
    }
  }
  ```

  * C#의 문자열, 문자, 문자배열
    * 문자열(string) = 문자(character)의 집합체 -> 문자열 안에 있는 각 문자를 엑세스하기 위해 인덱스를 사용할 수 있다.
    * 문자배열(char array)을 문자열(string)으로 변환하기 위해서는 ```new string(문자 배열)```을 사용한다.

    ```C#
    using System;
    
    namespace MySystem
    {
      class Program
      {
        static void Main(string[] args)
        {
          string s = "C# Studies";
          
          // 문자열을 배열 인덱스로 한문자 엑세스
          for (int i = 0; i < s.Length;i++)
          {
            Console.WriteLine("{0}: {1}", i, s[i]);
          }
          
          // 문자열을 문자배열로 변환
          string str = "Hello";
          char[] charArray = str.ToCharArray();
          
          for (int i = 0;i<charArray.Length;i++)
          {
            Console.WriteLine(charArray[i]);
          }
          
          // 문자배열을 문자열로 변환
          char[] charArray2 = {'A', 'B', 'C', 'D'};
          s = new string(charArray2);
          
          Console.WriteLine(s);
          
          // 문자 연산
          char c1 = 'A';
          char c2 = (char)(c1 + 3); // ascii 값을 사용하기 때문에 가능한 일
          Console.WriteLine(c2);    // D 출력
        }
      }
    }
    ```
    
  * C# StringBuilder 클래스
    * 문자열을 다루는데 중요한 클래스 중 하나. System.Text.StringBuilder 클래스
    * String 클래스는 Immutable이므로 문자열 갱신을 많이 하는 픞로그램에는 적당하지 않음
    * 반면 Mutable 타입인 **StringBuilder 클래스**는 문자열 갱신이 많은 곳에서 자주 사용되는데 이는 이 클래스가 별도 메모리를 생성 및 소멸하지 않고 일정한 버퍼를 자고 문자열 갱신을 효율적으로 처리하기 때문

    * 루프 안에서 계속 문자열을 추가 변경하는 코드에선 string 대신 StringBuilder를 사용해야 한다.
    ```C#
    using System;
    using System.Text;
    
    namespace MySystem
    {
      class Program
      {
        static void Main(string[] args)
        {
          StringBuilder sb = new StringBuilder();
          for (int i=1;i<=26;i++)
          {
            sb.Append(i.ToString());
            sb.Append(System.Environment.NewLine);
          }
          string s = sb.ToString();
          
          Console.WriteLine(s);
        }
      }
    }
    
    ```
    
* C# 열거형 enum
  * C#의 키워드 enum은 열거형 상수(constant)를 표현하기 위한 것, 이를 **이용하면 상수 숫자들을 보다 의미있는 단어들로 표현**할 수 있어서 프로그램을 읽기 쉽게 해준다.
  * **enum의 각 요소는 별도의 지정 없이는 첫번째 요소가 0**, 두번째 요소가 1, 세 번째 요소가 2 등과 같이 1씩 증가된 값들을 할당받는다. 물론 개발자가 임의대로 의미있는 번호를 지정해줄 수도 있다.
  * enum문은 클래스 안이나 네임스페이스 내에서만 선언될 수 있다. 즉, 메서드 안이나 속성 안에서는 선언되지 않는다.

  * 아례 예제에는... Category라는 enum 타입을 정의한 예인데, Cake는 숫자 0을 갖고, IceCream은 1, Bread는 2라는 값을 갖는다. 프로그램상에서 Category 값을 0, 1 처럼 직접 쓰는 대신 Category.Cake, Category.IceCream과 같이 사용하면, 그 의미를 파악하기가 훨씬 쉬워진다.
  ```C#
  public enum Category
  {
    Cake,
    IceCream,
    Bread
  }
  ```
  
  * C# enum의 사용
  * **enum 타입은 숫자형 타입과 호환가능하다.** 만약 enum 타입의 변수를 int로 캐스팅하면 해당 enum값의 숫자 값을 얻게 된다. 또한, enum 타입의 변수는 enum 리터럴값과 서로 비교할 수 있다.
    * Casting : 한 타입을 다른 타입으로 변경하는 것. 타입 변환이 실패할 수도 있다.
  
  * 아래 코드는 enum 변수 myCity가 리터럴 City.Seoul과 같은지 체크하는 예제이다.
  ```C#
  class Program
  {
      enum City
      {
          Seoul,        // 0
          Daejun,       // 1
          Busan = 5,    // 5
          Jeju = 10     // 10
      }
      
      static void Main(string[] args)
      {
          City myCity;
          
          // enum 타입에 값을 대입하는 방법
          myCity = City.Seoul;
          
          // enum을 int로 변환(Casting)하는 방법
          // (int)를 앞에 지정
          int cityValue = (int) myCity;
          
          if (myCity == City.Seoul) // enum 값을 비교하는 방법
          {
              Console.WriteLine("Welcome to Seoul");
          }
      }
  }
  ```
  
  * 플래그(flag) enum
    * enum의 각 멤버들은 각 비트별로 구분되는 값들 (ex : 1, 2, 4, 8, ...)을 갖을 수 있는데, 이렇게 enum 타입이 비트 필드를 갖는다는 것을 표시하기 위해 enum 선언문 바로 위에 [Flags]라는 Attribute (주 : Type 혹은 그 멤버를 선언할 때 그 위에 붙이는 특별한 특성값으로 해당 타입 혹은 멤버가 어떤 특성을 갖고 있는지 나타내게 된다)를 지정할 수 있다.

    * [Flags] 특성을 갖는 플래스 enum은 **OR 연산자를 이용해서 한 enum 변수에 다중값(ex : 1+4)을 가질 수** 있으며, **AND 연산자를 이용하여 enum 변수가 특정 멤버를 포함하고 있는지 체크할 수** 있다.

    * 아래 예제는 Border라는 플래스 enum으로 OR 연산을 통해 다중값을 표현하고, AND 연산을 통해 특정멤버를 체크해보는 코드를 보여주고 있다. 또한, 플래그 enum에 대해 ```.ToString()``` 메서드를 사용하면 해당 플래그 멤버명들을 문자열로 보여준다는 것이다. [Flags]가 없으면 1+4 즉, 5를 출력한다.
    ```C#
    [Flags]
    enum Border
    {
        None =0,
        Top = 1,
        Right = 2,
        Bottom = 4,
        Left = 8
    }
    
    static void Main(string[] args)
    {
        // OR 연산자로 다중 플래그 할당
        Border b = Border.Top | Border.Bottom;
        
        // & 연산자로 플래그 체크
        if ((b & Border.Top) != 0)
        {
            // HasFlag() 이용 플래그 체크
            if (b.HasFlag(Border.Bottom))
            {
                // "Top, Bottom" 출력
                Console.WriteLine(b.ToString());
            }
        }
    }
    ```
------------------


* 클래스
  * 클래스 - C++의 클래스와 동일
  ```C#
  //Test(클래스) test(인스턴스) = new(New 키워드) Test() (생성자)
  
  class Test
  {
      public string name = "default;
      public int number = 1000;
  }
  ```
    * C#은 인스턴트를 생성할 때 값을 초기화할 수 있는 기능이 있다.
    * 다만 C++과 다르게 C#에서 클래스 안에서는 public, private, protected를 하나의 멤버변수마다 일일이 다 지정해 주어야 한다.

  ```C#
  Ramdom random = new Random();
  List <>list = new list<>();
  Math.abs(5);
  
  ```
  
  * 메서드의 기본 형태 (class의 멤버변수)
    ```C#
    //[접근 제한자] [반환형] [메서드 이름] ([매개변수])
    //{
    //          [메서드 코드]
    //}
    ```
    * 클래스 이름으로 곧바로 사용하는 변수와 메서드 -> 클래스 변수클래스 메서드 (static 키워드)

  * 생성자
    ```
    Public [클래스 이름] ([매개 변수])
    {
    
    }
    ```
    * 이름은 클래스 이름과 같게
    * 인스턴스 변수를 초기화...
    * (후에 필기)

  * 소멸자 

  * C#의 자료형 (class)
    * 값 : int/float 등 기본 자료형 : 변수 자체에 객체의 값이 들어감
    * 참조 : 클래스로 만들어진 인스턴스 : 객체의 메모리 위치를 나타내는 참조가 들어감

  * 객체 지향 언어
  * is / as
  * 이름 재사용
  * 상속과 오버라이딩 제한 (가급적 쓰지 않는 것이 좋다.)
    * virtual : 가상함수 (필요한 경우를 제외하고 가급적 사용하지 않는 것을 권장)

* 클래스 심화
  * 제네릭 <> : 클래스 내부의 자료형에 별칭을 저장하는 기능 (매크로 + 오버로드)
    ```C#
    class Test<T>
    {
      public T Value;
      public Wanted(T value)
      {
        this.Value = value;
      }
      
    class Program
    {
      static void Main(string[] args)
      {
        // 제네릭을 사용해 변수 Value의 자료형을 원하는 자료형으로 지정
        Test<string> testString = new Test<string>("String");
        Test<int> testInt = new Test<int>("Int");
        
        Console.WriteLine(testString.Value);
        Console.WriteLine(testInt.Value);
      }
    }
    }
    ```

  * out 키워드 (포인터 대신 사용)
    * C#은 메서드를 호출 후 반환시 하나의 값만 반환
    * 값을 여러 개 반환하고 싶은 경우 사용
    * 매개변수로 넣은 변수에 값을 넣어줌

    * 값 : 변수 자체에 객체의 값이 들어감
    * 참조 : 객체의 메모리 위치를 나타내는 참조가 들어감
    * Out 참조
      * 객체의 메모리 위치를 나타내는 참조가 들어감
      * 참조할 변수를 초기화 할 필요가 없다는 점에서 참조와 차이가 있다.

  * 구조체 (C#에서는 구조체가 쉽지 않다.)
    * 상속 불가능
    * 매개변수 없는 생성자 선언X(자동으로 생성)
    * 선언과 동시에 멤버변수를 초기화할 수 없음
    * 값 복사가 이루어짐

    ```C#
    struct Test
      {
        public int x;
        public int y;
        public string test = "test";  // 오류 발생 : 선언과 동시에 초기화 불가능 (클래스가 아니므로)
        public Test(); // 오류 발생
      }
    ```

* 예외 처리 (세상엔 악질 사용자가 많으므로... 돌발 상황에 예측을 하여 대비를 할 수 있어야 한다.)
  * 예외 처리 : 프로그램이 실행되는 동안 발생하는 오류를 예외라고 하는데, 이러한 예외에 대처하는 방법을 의미한다.
  * 이때 사용하는 것이 try ~ catch를 사용해서 예외 처리를 진행한다.

  * 예외 객체 : exception, 모든 예외를 처리할 수 있음
  * 예외 강제 발생 : throw 키워드를 사용하여 무조건적으로 예외를 발생시키는 것
  
  ```C#
  class Program
  {
    static void Main(string[] args)
    {
      Console.Write("숫자 입력 : ");
      string test = Console.ReadLine();
      
      Console.WriteLine(int.Parse(test));   // 문자 입력 시 예외 발생
    }
  }
  ```

  ```C#
    class Program
  {
    static void Main(string[] args)
    {
      Console.Write("숫자 입력 : ");
      string test = Console.ReadLine();
      
      // try ~ catch문
      try
      {
        // try : Main, 예외 발생
        Console.WriteLine(int.Parse(test));
      }
      catch(Exception exception)  // 예외 객체 exception
      {
        // catch : 오류 발생시 동작
        Console.WriteLine("예외 발생!!");
        Console.WriteLine(exception.GetType());
      }
      finally
      {
        // finally : 종료할 때 에러 여부와 상관없이 무조건 수행
        Console.WriteLine("프로그램 종료");
      }
    }
  }
  ```

* 델리게이트와 람다
  * 델리게이트 
    * 메서드를 참조하는 변수
    * C++의 함수 포인터와 비슷 -> 함수의 별명이라고 생각하면 된다.
      * ```(*func)() = sub``` -> 함수
    * 메서드를 대신해서 호출(메서드의 대리인)
    * [접근 제한자] delegate [반환형] [델리게이트 이름]([매개변수]);
    * 델리게이트를 사용할 때 invoke 호출자를 사용해야 한다.

    * 사용처 : 쓰레드(Thread)를 다룰 때가 있다. 하나의 thread에서 다른 form에 변수를 넣는다던지 access할 때 direct로 허용이 불가능한데, 이 때 사용
      * 즉, 네트워크 프로그래밍을 진행할 때
      
      ```C#
      class Program
      {
        public delegate int mydelegate(int a, int b);
        
        public static int plus(int a, int b) {return a+b;}
        public static int minus(int a, int b) {return a-b;}
        
        static void Main(string[] args)
        {
          mydelegate calculate;
          
          calculate = new mydelegte(plus);
          Console.WriteLine(calculate(11, 3));
          
          calculate = new mydelegate(minus);
          Console.WriteLine(calculate(11, 3));
        }
      }
      ```

  * 무명 델리게이트와 람다
    * 무명 델리게이트 : 무명 메서드를 참조

    * 람다
      * 델리게이트를 짧게 쓰는 방식
      * 매개변수의 자료형을 지정할 필요가 없다.

  * 일반화 델리게이트
  * 콜백 메서드
    * 델리게이트를 사용하여 구현
  
  * 델리게이트 체인

* Linq
  * Linq (Database Style로 DB관리 가능, 배열 객체 조작)
    * 조건에 맞는 데이터 추출
    * C# 객체의 집합 쉽게 관리가 가능하다.
    * SQL 서버와 함께 연동하여 DB관리 가능
    * 하지만 DB를 다룬다면 SQL과 비슷하게 해야 한다고 생각하지만, 다른 점이 있기 때문에 잘 사용하지 않는 것으로 보인다.
    
    ```C#
    class Program
    {
      static void Main(string[] args)
      {
        List<int> num = new List<int>() {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};  // 리스트 제네릭으로 구성되어 있다.
        
        // 밑은 SQL문과 유사하다.
        var output = from item in num
                    where item > 5
                    orderby item descending
                    select item;
                    
        // 위를 SQL문으로 바꾼다면
        // select * from num where item > 5 orderby item desc
        
        foreach(var item in output)
        {
          Console.WriteLine(item);
        }
      }
    }
    ```
    
    ```
    // 결과
    10
    9
    8
    7
    6
    계속하려면 아무 키나 누르십시오 . . .
    ```
    
  * 익명 객체
  * 클래스 활용
    * C#은 무조건 클래스이다. 클래스에서 시작하여 클래스로 끝나기 때문. 그 이유는 Program 클래스로 시작하기 때문
    * 프로그램 진입점 : Class Program -> static void Main(string[] args) (class -> main)

* C#은 Form 기반이다.  

# C/# 객체지향
* 
    
    
    
