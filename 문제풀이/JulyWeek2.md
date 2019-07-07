
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
        
         int[] indeces = new int[2] ;

         for(int startNum=0; startNum < nums.length; startNum++) {
                for(int nextNum = startNum+1; nextNum < nums.length; nextNum++) {

                  if(nums[startNum] + nums[nextNum] == target) {
                     indeces[0] = startNum;
                     indeces[1] = nextNum;
                     break;
                  }
            }//for
         }//for
         return indeces;
       }
    }
    ```
