## 1. Two Sum (Easy)

[Leetcode link](https://leetcode.com/problems/two-sum/)

### 1.1 Description

Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

You may assume that each input would have **_exactly one solution_**, and you may not use the same element twice.

You can return the answer in any order.

Example 1:

    Input: nums = [2,7,11,15], target = 9
    Output: [0,1]
    Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

Example 2:

    Input: nums = [3,2,4], target = 6
    Output: [1,2]

Example 3:

    Input: nums = [3,3], target = 6
    Output: [0,1]

### 1.2 Solution

#### Solution 1. Brute Force

Java:

    public class Solution {
        public int[] twoSum(int[] nums, int target) {

            for(int i=0; i<nums.length; i++) {
                for(int j=i+1; j<nums.length; j++) {
                    if(nums[i]+nums[j] == target) {
                        return new int[] {i, j};
                    }
                }
            }
            // No answer
            return new int[] {};
        }
    }

Time complexity: O(n^2)
Space complexity: O(1)

#### Solution 2. Using Hashmap

##### What is Hashmap?

Java:

    public class Solution {
        public int[] twoSum(int[] nums, int target) {
            HashMap<Integer,Integer> indexMap = new HashMap<Integer,Integer>();
            for(int i = 0; i < nums.length; i++){
                Integer requiredNum = (Integer)(target - nums[i]);
                if(indexMap.containsKey(requiredNum)){
                    return new int[] {indexMap.get(requiredNum), i};
                }
                indexMap.put(nums[i], i);
            }
            // No answer
            return new int[] {};
        }
    }

Time complexity: O(n)
Space complexity: O(n)
