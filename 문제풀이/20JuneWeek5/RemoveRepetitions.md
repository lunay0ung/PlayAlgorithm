
- 코딩테스트
  - 처음에 문제를 잘못 이해해서 시간을 날림. 답 모름.
  
  ```sh
  //중복된 캐릭터 없애기
public class RemoveRepetitions {
    public static String transform(String input) {
        //연속된 문자열 중 중복된 것만 제거해야 함
        String ourString = "";
        for (int i=1; i<input.length() ; i++){
            int j = i+1;
            if(input.charAt(i)!=input.charAt(j)){
                ourString +=input.charAt(i);
            }
        }
        return ourString;
    }

    public static void main(String[] args) {
        System.out.println(RemoveRepetitions.transform("abbcbbb"));
    }
}
  ```
