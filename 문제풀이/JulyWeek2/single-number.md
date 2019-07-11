

Given a non-empty array of integers, every element appears twice except for one. Find that single one.

Note:

Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

Example 1:

Input: [2,2,1]
Output: 1
Example 2:

Input: [4,1,2,1,2]
Output: 4

--

class Solution {
    public int singleNumber(int[] nums) {
        
   	List<Integer> list = new ArrayList<Integer>();
		for(int i=0; i < nums.length; i++) {
			
			if(!list.contains(nums[i])) {
				list.add(nums[i]);
				
			}
			else {
				int value= nums[i];
				list.remove(Integer.valueOf(value)); //여기서 실수..
			}
		}
		//System.out.println("size: "+list.size());
		return list.get(0);

    }//singleNumber
}//class

Runtime: 110 ms, faster than 5.02% of Java online submissions for Single Number.
Memory Usage: 39 MB, less than 98.26% of Java online submissions for Single Number.

*원래 처음에 하려다 끝내 실패한 방법: 
https://leetcode.com/problems/single-number/discuss/43039/Java-use-HashMap
