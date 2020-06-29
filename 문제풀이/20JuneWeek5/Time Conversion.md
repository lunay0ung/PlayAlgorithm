- [문제](https://www.hackerrank.com/challenges/time-conversion/problem?h_r=next-challenge&h_v=zen)

- 결과 
  - 처음엔 AM을 고려하지 못했고,
  - 그 다음엔 테스트 케이스 10개 중에 1개가 틀렸는데 뭔지 모르겠음...
```sh
  static String timeConversion(String str) {
        //s를 :기준으로 나눠서 갖고있자
        String s = str.replaceAll(":","");
        String hour = s.substring(0, 2);
        String minute = s.substring(2, 4);
        String second = s.substring(4, s.length()-2);
        if(str.contains("PM")) {
            int hh = Integer.parseInt(hour)+12;
            hour = String.valueOf(hh);
        }
      if(str.contains("AM") && hour.equals("12")) {
            hour = "00";
        }
        return hour+":"+minute+":"+second;

    }
```


----------
  - 참고할 만한 답변,,,
```sh
public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    String in = sc.next();
    char[] inChar = in.toCharArray();
    char[] out = Arrays.copyOfRange(inChar, 0, 8);
    if(inChar[8] == 'A' && in.substring(0,2).equals("12")) {
        out[0] = '0';
        out[1] = '0';
    }
    else if(inChar[8] =='P' && !in.substring(0,2).equals("12")) {
        String s = "" + (Integer.parseInt(in.substring(0,2)) + 12);
        char[] f = s.toCharArray();
        out[0] = f[0];
        out[1] = f[1];
    }
    System.out.println(out);
}
```
