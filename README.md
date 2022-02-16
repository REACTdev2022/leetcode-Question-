# leetcode-Question-
Data structure and 

ARRAYS QUESTION:->
TWO SUM:->https://leetcode.com/problems/two-sum/description/
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

Example:1

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].

Example:2
Input: nums = [3,2,4], target = 6
Output: [1,2]

Thought Process:->
Brute Force
Use every element as an anchor and search its right element
    The time complexity is O(n^2) = (n - 1) + (n - 2) + ... + 1
    The space complexity is O(1)
Optimal (Hash Map)
  Leverage the power of hashmap and store the number and its index in the map
  When the map contain target - curNum, we know the search is complete
    The time complexity is O(n)
    The space complexity is O(n)
    
    ```class Solution {
    public int[] twoSum(int[] nums, int target) {
        if (nums == null) return null;
        int[] result = new int[2];
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            if (map.containsKey(target - nums[i])) {
                result[0] = map.get(target - nums[i]);
                result[1] = i;
                return result;
            }
            map.put(nums[i], i);
        }
        return result;
    }
}


```
