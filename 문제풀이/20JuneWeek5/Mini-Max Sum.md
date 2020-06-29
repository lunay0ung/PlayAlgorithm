
- [문제] (https://www.hackerrank.com/challenges/mini-max-sum/problem?h_r=next-challenge&h_v=zen)

- 결론: 다시 풀기 
  - ㅋㅋㅋ 아예 감도 안잡혀서 조금 생각하다가 바로 discussion으로 넘어감 ㅠㅋ 
  - 아래에 괜찮은 답변 있음 
  - 
  - 
  - 
   - 
 
 
 
 ------
 
 ```sh
 public static void main(String[] args) { Scanner in = new Scanner(System.in);

    long max, min, sum;
    sum = max = min = in.nextLong();

    for(int i=1; i<5;i++){
        long temp = in.nextLong();
        sum += temp;
        if(max>temp){
            if(min > temp) {
                min = temp;
            }
        } else {
            max = temp;
        }
    }

    System.out.print((sum -max) + " " + (sum - min));
}
 ```
