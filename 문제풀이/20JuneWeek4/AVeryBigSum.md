- [문제](https://www.hackerrank.com/challenges/a-very-big-sum/problem)

- 풀이
```sh
 // Complete the aVeryBigSum function below.
    static long aVeryBigSum(long[] ar) {
     
         long result = 0;
        for(long i : ar) {
          result += i;   
        }
        return result;
    }
```
