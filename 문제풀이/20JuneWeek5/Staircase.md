
- [문제](https://www.hackerrank.com/challenges/staircase/problem)
  - *지난 주에 못 풀고 다시 풀어보는 문제
  
- 결과: 지난 주엔 아예 못풀었지만 이번엔 그래도..어느 정도는 ㅋㅋ 내 힘으로 풂. 근데 너무 복잡하게 풀었다. 
```sh
  // Complete the staircase function below.
    static void staircase(int n) {
     int count = 0;

        for(int i = 0; i < n; i++ ){
            for (int a = n-i-1; a > 0; a --) {
                System.out.print(" ");
                //System.out.println(">>>> count: "+count);
            }
            count ++;
            for(int b = n-count; b < n; b ++ ){
                System.out.print("#");
            }
            System.out.println("");
        }
    }

```
  
  
