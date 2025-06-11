# Two Sum - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Two Sum - Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.
  
  ### Examples:
  ```
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
  ```
  
  ### Constraints:
  
  Constraints:

 * 2 <= nums.length <= 104
 * -109 <= nums[i] <= 109
 * -109 <= target <= 109
 * Only one valid answer exists.

 

Follow-up: Can you come up with an algorithm that is less than O(n2) time complexity?
  
  ### Solution Language:
  ```
  Choose a type
  ```
  
  ### Approach:
  ---

  #### approach 1:
  ```
  class Solution {

public:

    vector<int> twoSum(vector<int>& nums, int target) {

        unordered_map<int,int> mpp;

        int n = nums.size();

        for ( int i = 0 ; i < n ; i++){

            int num = nums[i];

            int moreNeeded = target - num;

            if (mpp.find(moreNeeded) != mpp.end()) {

                return {mpp[moreNeeded], i};

            }

            mpp[num] = i;

        }

    return { -1, -1};

        }

};
  ```
  

 
  #### approach 2: 

 ``` Python3``` 
  ```  

 class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        n = len(nums)
        for i in range(n - 1):
            for j in range(i + 1, n):
                if nums[i] + nums[j] == target:
                    return [i, j]
        return []  # No solution found 

 ``` 


 
  #### approach 3: 

 ``` C++``` 
  ```  

 class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        n = len(nums)
        for i in range(n - 1):
            for j in range(i + 1, n):
                if nums[i] + nums[j] == target:
                    return [i, j]
        return []  # No solution found 

 ``` 
