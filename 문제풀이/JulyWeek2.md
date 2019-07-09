
 - 문제
   - Given an array of integers, return indices of the two numbers such that they add up to a specific target.
 You may assume that each input would have exactly one solution, and you may not use the same element twice.

    - Example:
    Given nums = [2, 7, 11, 15], target = 9,
    Because nums[0] + nums[1] = 2 + 7 = 9,
    return [0, 1].

 - 풀이
    - Java 
    ```sh
    class Solution {
        public int[] twoSum(int[] nums, int target) {
        
         int[] indices = new int[2] ;

         for(int startNum=0; startNum < nums.length; startNum++) {
                for(int nextNum = startNum+1; nextNum < nums.length; nextNum++) {

                  if(nums[startNum] + nums[nextNum] == target) {
                     indices[0] = startNum;
                     indices[1] = nextNum;
                     break;
                  }
            }//for
         }//for
         return indices;
       }
    }
    ```
   - Result
     - Runtime: 25 ms, faster than 25.52% of Java online submissions for Two Sum.
     - Memory Usage: 37.4 MB, less than 99.54% of Java online submissions for Two Sum.

   - Kotlin
    ```sh
    class Solution {
       fun twoSum(nums: IntArray, target: Int): IntArray {
                val indices = IntArray(2) //인덱스를 담을 배열의 크기는 2

                //nums 배열에 담긴 숫자들을 인덱스 0번부터 차례로 꺼내서 바로 다음 인덱스의 숫자와 더하고,
                //둘의 합이 target과 같으면 해당 숫자들의 인덱스를 indeces배열에 넣은 후 리턴한다
             outerLoop@ for(startNum in 0 until nums.size) {
                      for(nextNum in 1 until nums.size) {
                        if(startNum != nextNum && nums[startNum] + nums[nextNum] == target) {
                            indices[0] = startNum
                            indices[1] = nextNum
                            break@outerLoop 
                        }
                    }
                }

               return indices           

        }
    }
    ```
    - Result
      - Runtime: 348 ms, faster than 11.67% of Kotlin online submissions for Two Sum.
      - Memory Usage: 35.2 MB, less than 100.00% of Kotlin online submissions for Two Sum.
   
    
    - 참고
      - [Returns and Jumps](https://kotlinlang.org/docs/reference/returns.html#returns-and-jumps)
        - Any expression in Kotlin may be marked with a label. Labels have the form of an identifier followed by the @ sign, for example: abc@, fooBar@ are valid labels (see the grammar). To label an expression, we just put a label in front of it
        -  A break qualified with a label jumps to the execution point right after the loop marked with that label. A continue         proceeds to the next iteration of that loop.
      
           - return: By default returns from the nearest enclosing function or anonymous function.
           - break: Terminates the nearest enclosing loop.
           - continue: Proceeds to the next step of the nearest enclosing loop.
