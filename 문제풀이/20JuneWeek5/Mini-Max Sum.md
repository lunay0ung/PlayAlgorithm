
- [문제](https://www.hackerrank.com/challenges/mini-max-sum/problem?h_r=next-challenge&h_v=zen)
  - Hints: Beware of integer overflow! Use 64-bit Integer.


- 결론: 다시 풀기 
  - ㅋㅋㅋ 아예 감도 안잡혀서 조금 생각하다가 바로 discussion으로 넘어감 ㅠㅋ 
  - 완벽하게 이해돼서 내 식대로 풀긴 했는데 아쉽다! for loop을 두번 돌리지 않아도 되었을 텐데~
  
  ```sh
  
    // Complete the miniMaxSum function below.
    static void miniMaxSum(int[] arr) {
        //정렬해서 앞의것 4개, 뒤의것 4개를 뽑아내면 됨
        Arrays.sort(arr);
        long mini = 0, max = 0;
        for (int i=0; i < arr.length-1; i++) {
            mini += arr[i];
        }
        for (int i=1; i < arr.length; i++) {
            max += arr[i];
        }
        System.out.print(mini+" "+max);

    }
  ```
  
  
  - 아래에 괜찮은 답변 있음 

  
 
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
