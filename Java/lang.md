 ## String,StringBuilder,StringBuffer
 - [참고](https://github.com/luna-young/LearnAlgorithm/blob/master/문제풀이/JulyWeek3/Reverse%20Words%20in%20a%20String.md)
   - [공홈: java.lang](https://docs.oracle.com/javase/8/docs/api/)
     - [String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)
       - Strings are **constant; their values cannot be changed after they are created**. 
     
     - [StringBuffer](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuffer.html)
       - **A thread-safe, mutable sequence of characters**. A string buffer is like a String, but can be modified. 
       At any point in time it contains some particular sequence of characters, 
       but the length and content of the sequence can be changed through certain method calls.
       String buffers are **safe for use by multiple threads**. 
       The methods are synchronized where necessary so that all the operations on any particular instance 
       behave as if they occur in some serial order that is consistent with the order of the method calls made by each of the individual threads involved.

     - [StringBuilder](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html)

       - A mutable sequence of characters. This class provides an API compatible with StringBuffer, 
       **but with no guarantee of synchronization**. 
       This class is designed **for use as a drop-in replacement for StringBuffer**
       in places where the string buffer was being used by a single thread (as is generally the case). 
       Where possible, it is **recommended that this class be used in preference to StringBuffer 
       as it will be faster under most implementations**.
       - public StringBuilder()
          - Constructs a string builder with no characters in it and **an initial capacity of 16 characters**.

     
   - [점프 투 자바: 03-4 문자열 (String)](https://wikidocs.net/205) 
     -  int, long, double, float, boolean, char 등을 자바는 primitive 자료형 이라고 부른다. 이런 primitive 자료형은 new 키워드로 생성할 수 없다.
     primitive 자료형은 다음과 같이 리터럴(literal)로 값을 세팅할 수 있다. (※ 리터럴은 계산식 없이 소스코드에 표기하는 상수 값을 의미한다.)
     String 은 "Happy Java"와 같이 리터럴로 표기가 가능하지만 primitive 자료형은 아니다. 
     (String은 리터럴 표현식을 사용할 수 있도록 자바에서 특별 대우 해 주는 자료형이다.)
     - 문자열 a와 b는 모두 "hello"로 같은 값이지만 equals 를 호출했을 때는 true 를 == 연산자를 이용했을 때는 false를 리턴한다. a와 b는 값은 같지만 서로 다른 객체이다. 
     == 은 두개의 자료형이 동일한 객체인지를 판별할 때 사용하는 연산자이기 때문에 false를 리턴하게 되는 것이다.
     
   - [점프 투 자바: 03-5 StringBuffer](https://wikidocs.net/276)
     - ※ String 자료형은 한번 값이 생성되면 그 값을 변경할 수가 없다. 이렇게 값을 변경할 수 없는 것을 immutable 하다고 한다. 
     trim, toUpperCase 등의 메소드를 보면 문자열이 변경되는 것 처럼 생각 될 수도 있겠지만 해당 메소드 수행 시 또 다른 String 객체를 생성하여 리턴할 뿐이다. 
     StringBuffer 는 이와 반대로 값을 변경할 수 있다(mutable 하다). 즉 한번 생성된 값을 언제든지 수정할 수 있다.
     - new StringBuffer() 로 객체를 생성하는 것은 일반 String을 사용하는 것보다 메모리 사용량도 많고 속도도 느리다.
     
   - [Java에서 String, StringBuilder, StringBuffer의 차이](https://novemberde.github.io/2017/04/15/String_0.html)
     -  String은 새로운 값을 할당할 때마다 새로 생성되기 때문이다. 
     이와 달리 StringBuffer는 값은 memory에 append하는 방식으로 클래스를 직접생성하지 않는다. 
     논리적으로 따져보면 클래스가 생성될 때 method들과 variable도 같이 생성되는데, StringBuffer는 이런 시간을 사용하지 않는다.
     또한 지금은 한 번만 생성되었지만 
     **수십번 String이 더해지는 경우에는 각 String의 주소값이 stack에 쌓이고 클래스들은 Garbage Collector가 호출되기 전까지 heap에 지속적으로 쌓이게** 된다. 
     메모리 관리적인 측면에서는 치명적이라고 볼 수 있다.
     - String class의 내부
     - ![](https://novemberde.github.io/images/java/string/String2.png)
     - String에서 저장되는 문자열은 알고보면 char의 배열형태로 저장되며 이 값들은 외부에서 접근할 수 없도록 private으로 보호된다. 
     또한 final형이기 때문에 초기값으로 주어진 String의 값은 불변으로 바뀔 수가 없게 되는 것이다.
     - **StringBuilder는 변경가능한 문자열이지만 synchronization이 적용되지 않았다**. 
     하지만 **StringBuffer는 thread-safe**라는 말에서처럼 변경가능하지만 multiple thread환경에서 안전한 클래스라고 한다. 
     이것이 StringBuilder와 StringBuffer의 가장 큰 차이점이다.
     - StringBuilder와 StringBuffer를 테스트 해보자. 아래의 결과를 보면 다른 값이 나온 것을 볼 수 있다. 
     StringBuilder의 값이 더 작은 것을 볼 수 있는데 이는 **쓰레드들이 동시에 StringBuilder클래스에 접근할 수** 있기 때문에 일어난 결과다. 
     이와 달리 **StringBuffer는 multi thread환경에서 다른 값을 변경하지 못하도록** 하므로 
     web이나 소켓환경과 같이 비동기로 동작하는 경우가 많을 때는 StringBuffer를 사용하는 것이 안전할 것이다.
     
   - [StringBuilder](http://wiki.gurubee.net/display/DEVSTUDY/StringBuilder?)
     - ![](http://wiki.gurubee.net/download/attachments/983129/StringBuilder01.jpg)  
     
   - [Java heap space](https://plumbr.io/outofmemoryerror/java-heap-space)
     - Java applications are only allowed to use a limited amount of memory. 
     This limit is specified during application startup. 
     To make things more complex, Java memory is separated into two different regions. 
     These regions are called Heap space and Permgen (for Permanent Generation):
     ![](https://plumbr.io/app/uploads/2014/04/java-lang-outofmemoryerror-java-heap-space.png)
     - The size of those regions is set during the Java Virtual Machine (JVM) launch and 
     can be customized by specifying JVM parameters -Xmx and -XX:MaxPermSize. 
     If you do not explicitly set the sizes, platform-specific defaults will be used.
     - The java.lang.OutOfMemoryError: Java heap space error will be triggered 
when the application attempts to add more data into the heap space area, but there is not enough room for it.
     - Note that there might be plenty of physical memory available, 
     but the java.lang.OutOfMemoryError: Java heap space error is thrown whenever the JVM reaches the heap size limit.
   
   - [Java Heap Space Setting](http://cmshelpcenter.saas.hp.com/CMSBP/Content/CMS_BP/CMSJavaHeap.html)
     - ![](http://cmshelpcenter.saas.hp.com/CMSBP/Content/CMS_BP/images/heap.PNG)

     
   - [[자료구조] 힙(heap)이란](https://gmlwjd9405.github.io/2018/05/10/data-structure-heap.html)
     - 자료구조 ‘힙(heap)’이란?
       - 완전 이진 트리의 일종으로 우선순위 큐를 위하여 만들어진 자료구조이다.
       - 여러 개의 값들 중에서 최댓값이나 최솟값을 빠르게 찾아내도록 만들어진 자료구조이다.
       - 힙은 일종의 반정렬 상태(느슨한 정렬 상태) 를 유지한다.
       - 큰 값이 상위 레벨에 있고 작은 값이 하위 레벨에 있다는 정도
       - 간단히 말하면 부모 노드의 키 값이 자식 노드의 키 값보다 항상 큰(작은) 이진 트리를 말한다.
       - **힙 트리에서는 중복된 값을 허용한다. (이진 탐색 트리에서는 중복된 값을 허용하지 않는다.)**
     - 우선순위 큐: 우선순위의 개념을 큐에 도입한 자료 구조
        - 데이터들이 우선순위를 가지고 있고 우선순위가 높은 데이터가 먼저 나간다.
        - ![](https://gmlwjd9405.github.io/images/data-structure-heap/data-structure-heap-compare.png)
        - 우선순위 큐는 배열, 연결리스트, 힙 으로 구현이 가능하다. 이 중에서 힙(heap)으로 구현하는 것이 가장 효율적이다.
        
        
   - 기타 자료
     - [Youtube: Java Tutorial # 24 | Thread Safety and code synchronization in java | Multithreading in Java part 3](https://youtu.be/IYBrtzOvfqo)      
