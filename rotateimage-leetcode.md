# Rotate Image - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Rotate Image - You are given an n x n 2D matrix representing an image, rotate the image by 90 degrees (clockwise).

You have to rotate the image in-place [https://en.wikipedia.org/wiki/In-place_algorithm], which means you have to modify the input 2D matrix directly. DO NOT allocate another 2D matrix and do the rotation.
  
  ### Examples:
  ```
  Example 1:

[https://assets.leetcode.com/uploads/2020/08/28/mat1.jpg]


Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]
Output: [[7,4,1],[8,5,2],[9,6,3]]


Example 2:

[https://assets.leetcode.com/uploads/2020/08/28/mat2.jpg]


Input: matrix = [[5,1,9,11],[2,4,8,10],[13,3,6,7],[15,14,12,16]]
Output: [[15,13,2,5],[14,3,4,1],[12,6,8,9],[16,7,10,11]]
  ```
  
  ### Constraints:
  
  Constraints:

 * n == matrix.length == matrix[i].length
 * 1 <= n <= 20
 * -1000 <= matrix[i][j] <= 1000
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  C++  ```
  ```
  class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {
        for(int i = 0 ; i < matrix.size(); i++){
            for(int j = 0 ; j < i; j++){
                swap(matrix[i][j],matrix[j][i]);
            }
        }
        for(int i = 0 ; i < matrix.size();i++){
            reverse(matrix[i].begin(),matrix[i].end());
        }
        
    }
};
  ```
  