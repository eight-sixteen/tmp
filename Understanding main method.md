# Java의 main 메소드 이해하기

자바 프로그램에서 프로그램 실행이 시작되는 곳이 main() 메소드이다. 따라서, main() 메소드는 자바에서 가장 중요한 메소드 중에 하나이고 이 메소드를 잘 이해하는게 무척 중요하다.

대부분 main() 메소드의 문법:

```java
class GeeksforGeeks {
  public static void main(String[] args) {
    System.out.println("I am a Geek");
  }
}
```

> I am a Geek



### 설명

public static void main 구문에 있는 모든 단어가 JVM에 의미를 갖고있다.

1. public : 접근 제한자로 누가 어디서 접근할 수 있는지 명시한다. main() 메소드를 public 으로 선언하면 전역적으로 사용할 수 있다. 지금 클래스에서는 안보이지만 JVM이 이 class 바깥에서 호출할 수 있도록 public으로 만들어졌다.

   ```java
   class GeeksforGeeks {
     private static void main(String[] args) {
       System.out.println("I am a Geek");
     }
   }
   ```

   > 오류: 기본 클래스 GeeksforGeeks.class을(를) 찾거나 로드할 수 없습니다.
   > 원인: java.lang.ClassNotFoundException: GeeksforGeeks.class

2. static : 이 키워드는 . main() 메소드가 static 이어야 JVM이 이 클래스를 인스턴스화 하지 않고도 호출할 수 있다. 또한 쓸데없는 메모리 낭비를 줄일 수 있다. JVM에 의해 main() 메소드만 호출하기 위해 선언되어 있는 오브젝트에 쓰였을 메모리 말이다.

   ```java
   class GeeksforGeeks {
     public void main(String[] args) {
       System.out.println("I am a Geek");
     }
   }
   ```

   > 오류: 기본 클래스 GeeksforGeeks.class을(를) 찾거나 로드할 수 없습니다.
   > 원인: java.lang.ClassNotFoundException: GeeksforGeeks.class

3. void : 이 키워드는 메소드가 아무것도 반환하지 않음을 명시한다. main() 메소드가 아무것도 반환하지 않기 때문에 반환형이 void이다. main() 메소드가 종료 되자마자 자바 프로그램도 종료된다. 따라서, main() 메소드가 반환값을 넘긴다는게 말이 되지 않는다. JVM이 반환받은 값으로 할 수 있는게 아무것도 없기 때문이다.

   ```java
   class GeeksforGeeks {
     public static int main(String[] args) {
       System.out.println("I am a Geek");
       return 1;
     }
   }
   ```

   > 오류: 기본 클래스 GeeksforGeeks.class을(를) 찾거나 로드할 수 없습니다.
   > 원인: java.lang.ClassNotFoundException: GeeksforGeeks.class

4. main : Java main 메소드의 이름이다. JVM이 자바 프로그램의 시작 포인트로 찾을 수 있는 식별자이다. 키워드는 아니다. 그냥 메소드의 이름이다.

   ```java
   class GeeksforGeeks {
     public static void myMain(String[] args) {
       System.out.println("I ama Geek");
     }
   }
   ```

   > 오류: 기본 클래스 GeeksforGeeks.class을(를) 찾거나 로드할 수 없습니다.
   > 원인: java.lang.ClassNotFoundException: GeeksforGeeks.class

5. String[] args : 자바 커맨드 라인 인자를 저장하는 java.lang.String 타입의 배열이다. 여기서의 이름은 args 지만, 정해진 값은 아니고 사용하는 사람에 따라 다르게 지정할 수도 있다.

   ```java
   class GeeksforGeeks {
     // javac GeeksforGeeks.java
     // java GeeksforGeeks 1 2 3
     public static void main(String[] args) {
       for (String ele : args) {
         System.out.println(ele);
       }
     }
   }
   ```

   > 1
   >
   > 2
   >
   > 3

   ---
   출처 : https://www.geeksforgeeks.org/understanding-public-static-void-mainstring-args-in-java/
