
## 자바의 입출력  
![](http://1.bp.blogspot.com/-CUOcdfUmkts/Th-grqzF2RI/AAAAAAAACWI/F8UdF7Qlnj8/s1600/Bit-byte-word.jpg)
- [Java: InputStream](https://docs.oracle.com/javase/7/docs/api/java/io/InputStream.html)
			- This abstract class is the superclass of all classes **representing an input stream of bytes**.  
			Applications that need to define a subclass of InputStream must always provide a method that returns the next byte of input.
		- [Java: InputStreamReader](https://docs.oracle.com/javase/7/docs/api/java/io/InputStreamReader.html)
			- **An InputStreamReader is a bridge from byte streams to character streams:**  
			**It reads bytes and decodes them into characters using a specified charset**.   
			The charset that it uses may be specified by name or may be given explicitly, or the platform's default charset may be accepted.  
			Each invocation of one of an InputStreamReader's read() methods may cause one or more bytes 	
			to be read from the underlying byte-input stream.   
			To enable the efficient conversion of bytes to characters, more bytes may be read ahead from the underlying stream than are necessary to satisfy the current read operation.  
			**For top efficiency, consider wrapping an InputStreamReader within a BufferedReader**. 
		- **[TCP School: 스트림]**(http://tcpschool.com/java/java_io_stream)
		- https://little-village.tistory.com/136 : 콘솔 입출력 - InputStream, System.in
		- [구루비 지식창고: InputStreamReader, OutputStreamWriter](http://wiki.gurubee.net/display/SWDEV/InputStreamReader%2C+OutputStreamWriter)
		- [문자 Stream : InputStreamReader / OutputStreamWriter](https://hyeonstorage.tistory.com/247)
			- ![](https://t1.daumcdn.net/cfile/tistory/224E004B5323CF5423)  
		- [자바의 입/출력(I/O), InputStream, OutputStream](https://blog.naver.com/hunter0931/30030467880)  
		
		```sh   
		- 2. java.io 패키지의 주요 클래스  
			 ▶ File : 물리적인 파일과 directory 처리  
			 ▶ InputStream - 바이트 단위로 데이터를 읽는다. 외부로부터 읽어 들이는 기능관련 클래스들  
			 ▶ OutputStream - 외부로 데이터를 전송한다. 외부로 데이터를 전송하는 기능 관련 클래스들  
			 ▶ Reader - 문자기반(2bytes)으로 읽어들이는 기능  
			 ▶ Write - 문자기반으로 출력하는 기능
		```


- Scanner
    - [Java: 공식 홈페이지](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html)
        - public final class Scanner extends Object implements Iterator<String>, Closeable
        - A simple text scanner which can **parse primitive types and strings using regular expressions**.  
        A Scanner breaks its input into tokens using a delimiter pattern, which by default matches whitespace.    
        The resulting tokens may then be converted into values of different types using the various next methods.   
        - A scanner can read text from any object which implements the Readable interface. If an invocation of the underlying readable's Readable.read(java.nio.CharBuffer) method throws an IOException then the scanner assumes that the end of the input has been reached. The most recent IOException thrown by the underlying readable can be retrieved via the ioException() method.
        - When a Scanner is closed, it will close its input source if the source implements the Closeable interface.
        - A Scanner is not safe for multithreaded use without external synchronization.
        - Unless otherwise mentioned, passing a null parameter into any method of a Scanner will cause a NullPointerException to be thrown.
- BufferedReader
    - [Java: 공식 홈페이지](https://docs.oracle.com/javase/7/docs/api/java/io/BufferedReader.html)
        - Reads text **from a character-input stream, buffering characters so as to provide for the efficient reading of characters, arrays, and lines**.
        - The buffer size may be specified, or the default size may be used. The default is large enough for most purposes.
        - In general, each read request made of a Reader causes a corresponding read request to be made of the underlying character or byte stream. **It is therefore advisable to wrap a BufferedReader around any Reader whose read() operations may be costly**, such as FileReaders and InputStreamReaders. For example,
            - BufferedReader in = new BufferedReader(new FileReader("foo.in"));
        - will buffer the input from the specified file. **Without buffering, each invocation of read() or readLine() could cause bytes to be read from the file, converted into characters, and then returned, which can be very inefficient**.
        - Programs that use DataInputStreams for textual input can be localized by replacing each DataInputStream with an appropriate BufferedReader. 
- 비교
    - [Difference between Scanner and BufferReader Class in Java](https://www.geeksforgeeks.org/difference-between-scanner-and-bufferreader-class-in-java/)
        - **BufferedReader is synchronous while Scanner is not**. BufferedReader should be used if we are working with multiple threads.
        - **BufferedReader has significantly larger buffer memory than Scanner**.
        - The Scanner has a little buffer (1KB char buffer) as opposed to the BufferedReader (8KB byte buffer), but it’s more than enough.
        - **BufferedReader is a bit faster as compared to scanner because scanner does parsing of input data and BufferedReader simply reads sequence of characters**.
    - [Scanner와 BufferedReader 차이](https://cocomo.tistory.com/507)
         ```sh 
        InputStreamReader는 입력을 character로 읽어들인다. 키보드로 입력하는 글자 한개에 해당된다고 할 수 있다. 하지만 한 글자가 아닌 줄단위의 문자열을 입력으로 받으려면 마찬가지로 불편하다. 그래서 생겨난 것이 BufferedReader이다.
        ```
    - [5 Difference between BufferedReader and Scanner class in Java - File Tutorial Example](https://www.java67.com/2016/06/5-difference-between-bufferedreader-and-scanner-in-java.html?m=1)
        1. **A scanner** is a much more powerful utility than BufferedReader. It can **parse the user input and read an int, short, byte, float, long and double apart from String**. On the other hand, BufferedReader can only read String in Java.
        2. BuffredReader has a significantly large buffer (8KB) than Scanner (1KB), which means if you are reading long String from a file, you should use BufferedReader but for short input and input other than String, you can use Scanner class.
        3. BufferedReader is older than Scanner. It's present in Java from JDK 1.1 onward but Scanner is only introduced in JDK 1.5 release.
        4. **Scanner uses regular expression to read and parse text input. It can accept custom delimiter and parse text into primitive data type** e.g. int, long, short, float or double using nextInt(), nextLong(), nextShort(), nextFloat(), and nextDouble() methods, while BufferedReader  can only read and store String using readLine() method.
        5. Another major difference between BufferedReader and Scanner class is that BufferedReader is synchronized while Scanner is not. This means, you **cannot share Scanner between multiple threads but you can share the BufferedReader object**.   
        **This synchronization also makes BufferedReader little bit slower in single thread environment as compared to Scanner, but the speed difference is compensated by Scanner's use of regex, which eventually makes BufferedReader faster for reading String**. 


- 관련 문제
  - [균형잡힌 세상](https://www.acmicpc.net/problem/4949)
  - [그대로 출력하기2](https://www.acmicpc.net/problem/11719)
