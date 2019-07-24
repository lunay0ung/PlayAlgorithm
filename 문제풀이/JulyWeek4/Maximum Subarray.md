
   
  - [문제](https://leetcode.com/problems/maximum-subarray/description/)
    - Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

    - Example 1:
      - Input: [-2,1,-3,4,-1,2,1,-5,4],
      - Output: 6
      - Explanation: [4,-1,2,1] has the largest sum = 6.

    
 - 풀이
 ```sh    
 
 ```
 
 - Result
   - Runtime:
   - Memory Usage:


 - 풀지 못함 
   - 참고: [Max Contiguous Subarray Sum - Cubic Time To Kadane's Algorithm ("Maximum Subarray" on LeetCode)](https://youtu.be/2MmGzdiKR9Y)
      - 풀이: [bephrem's github](https://github.com/bephrem1/backtobackswe/blob/master/Dynamic%20Programming%2C%20Recursion%2C%20%26%20Backtracking/maxContiguousSubarraySum.java)
   - [Dynamic programming](https://en.wikipedia.org/wiki/Dynamic_programming)
   - [Difference between Divide and Conquer Algo and Dynamic Programming](https://stackoverflow.com/questions/13538459/difference-between-divide-and-conquer-algo-and-dynamic-programming)
   - [Explanation on Integer.MAX_VALUE and Integer.MIN_VALUE to find min and max value in an array](https://stackoverflow.com/questions/30685641/explanation-on-integer-max-value-and-integer-min-value-to-find-min-and-max-value)
      ```sh
      ...if the first item in the array is larger than the rest, 
      then the largest item will always be Integer.MIN_VALUE because of the else-if statement.
      ```
      
      ```sh
      Instead of initializing the variables with arbitrary values (for example int smallest = 9999, largest = 0) 
      it is safer to initialize the variables with the largest and smallest values representable 
      by that number type (that is int smallest = Integer.MAX_VALUE, largest = Integer.MIN_VALUE).   
      Since your integer array cannot contain a value larger than Integer.MAX_VALUE and 
      smaller than Integer.MIN_VALUE your code works across all edge cases.
      ```
