- [문제](https://www.hackerrank.com/challenges/birthday-cake-candles/problem?h_r=next-challenge&h_v=zen)

- 결과 -> 10점 받음 ㅋㅋㅋㅋ이게 좀 쉽기도 한데...그래도 좋당 
```sh
    // Complete the birthdayCakeCandles function below.
    //ar에서 가장 큰 숫자의 개수 구하기
    static int birthdayCakeCandles(int[] ar) {
        Arrays.sort(ar); //일단 정렬한다
        //가장 끝에 있는 원소를 꺼낸다
        int max = ar[ar.length-1];
        int candles = 0;
        for(int candle : ar) {
            System.out.println("candle: "+candle);
            if(candle == max) {
                candles ++;
            }
        }

        return candles;
    }
```
