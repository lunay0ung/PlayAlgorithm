
- 코딩테스트
  - 답을 모르겠음
  
  ```sh
  package Test;

import java.lang.reflect.Array;
import java.util.ArrayList;
import java.util.List;

public class PaperStrip {
    public static int minPieces(int[] original, int[] desired) {
        //만약 원소를 비교했을 때 같으면, 그 뒤의 원소까지 비교를 해
            // 같아
        //      -> 그럼 4, 3, 2와 2, 4, 3의 비교지
                    //4와 2를 비교했는데  --달라, 그럼 j를 늘려서 비교해. 같아? -? i도 늘리고 j도 늘려
            // 달라 -> i는


        //1,4,3,2  1,2,4,3
        int count = 0;
        outerloop:
        for(int i = 0; i < original.length; i ++ ){
            for(int j=0; j< desired.length; j++) {
                if(original[i] == desired[i]) {
                    i++;
                    j++;
                }
                else {
                    count++;
                    j++;
                    break;
                }
            }
        }
        return count;

     /*   ArrayList<Integer> list = new ArrayList<>();
        int count = 0;
        for(int i = 0; i < original.length; i ++ ){
            for(int j=i; j< desired.length; j++) {
                if(original[i] == desired[j]) {
                    list.add(original[i]);
                }
                else {
                    count ++;
                    break;
                }
                break;
            }
        }
        return count;


      */
        //throw new UnsupportedOperationException("Waiting to be implemented.");
    }


    public static void main(String[] args) {
        int[] original = new int[] { 1, 4, 3, 2 };
        int[] desired = new int[] { 1, 2, 4, 3 };
        System.out.println(PaperStrip.minPieces(original, desired));
    }
}
  ```
