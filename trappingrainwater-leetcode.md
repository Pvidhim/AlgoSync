# Trapping Rain Water - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Trapping Rain Water - Given n non-negative integers representing an elevation map where the width of each bar is 1, compute how much water it can trap after raining.
  
  ### Examples:
  ```
  Example 1:

[https://assets.leetcode.com/uploads/2018/10/22/rainwatertrap.png]


Input: height = [0,1,0,2,1,0,1,3,2,1,2,1]
Output: 6
Explanation: The above elevation map (black section) is represented by array [0,1,0,2,1,0,1,3,2,1,2,1]. In this case, 6 units of rain water (blue section) are being trapped.


Example 2:


Input: height = [4,2,0,3,2,5]
Output: 9
  ```
  
  ### Constraints:
  
  Constraints:

 * n == height.length
 * 1 <= n <= 2 * 104
 * 0 <= height[i] <= 105
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  C++  ```
  ```
  class Solution {
public:
    int trap(vector<int>& height) {
        int n = height.size(),water = 0 , leftmax = 0 , rightmax =0 , maxheight = height[0], index =0;
        //Max height finding 
        for(int i = 1 ; i<n ; i++)
        {
            if(maxheight<height[i])
            {
                maxheight = height[i];
                index = i; 
            }
        }
        //left max
        for(int i = 0 ; i<index ; i++)
        {
            if(leftmax>height[i])
            {
                water+= leftmax-height[i];
            }
            else leftmax = height[i];
        }
        //right max 
    for(int i = n-1 ; i>index; i--)
    {
        if(rightmax>height[i]) 
        water+= rightmax-height[i];
        else 
        rightmax = height[i];


    }
    return water;
    }
};
  ```
  