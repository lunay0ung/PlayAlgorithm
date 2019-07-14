 - 문제
   - Write a function that reverses a string. The input string is given as an array of characters char[].
   Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.
   You may assume all the characters consist of printable ascii characters.

    - Example 1:
    Input: ["h","e","l","l","o"]
    Output: ["o","l","l","e","h"]
    Example 2:

    - Example 2:
    Input: ["H","a","n","n","a","h"]
    Output: ["h","a","n","n","a","H"]
    
 - 풀이
 ```sh    
 class Solution {
    public void reverseString(char[] s) {       
       HashMap<Integer, Character> map = new HashMap<>();
       for(int i=0; i<s.length; i++) {
        int j = i+1;
          map.put(i, s[s.length-j]);  	 
       }//for

       for(int k=0; k< s.length; k++) {
         s[k] = map.get(k);
       }
    }//reverseString
 }
 ```
 
 - Result
   - Runtime: 7 ms, faster than 5.46% of Java online submissions for Reverse String.
   - Memory Usage: 44.9 MB, less than 99.07% of Java online submissions for Reverse String.
