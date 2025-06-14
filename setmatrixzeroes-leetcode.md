# Set Matrix Zeroes - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Set Matrix Zeroes - Given an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's.

You must do it in place [https://en.wikipedia.org/wiki/In-place_algorithm].
  
  ### Examples:
  ```
  Example 1:

[https://assets.leetcode.com/uploads/2020/08/17/mat1.jpg]


Input: matrix = [[1,1,1],[1,0,1],[1,1,1]]
Output: [[1,0,1],[0,0,0],[1,0,1]]


Example 2:

[https://assets.leetcode.com/uploads/2020/08/17/mat2.jpg]


Input: matrix = [[0,1,2,0],[3,4,5,2],[1,3,1,5]]
Output: [[0,0,0,0],[0,4,5,0],[0,3,1,0]]
  ```
  
  ### Constraints:
  
  Constraints:

 * m == matrix.length
 * n == matrix[0].length
 * 1 <= m, n <= 200
 * -231 <= matrix[i][j] <= 231 - 1

 

Follow up:

 * A straightforward solution using O(mn) space is probably a bad idea.
 * A simple improvement uses O(m + n) space, but still not the best solution.
 * Could you devise a constant space solution?
  
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

    void setZeroes(vector<vector<int>>& matrix) {

        int n = matrix.size();

        int m = matrix[0].size();

        vector<bool> rows(n, false), cols(m, false);

        for( int i = 0 ; i < n ; i++){

            for( int j = 0 ; j < m ; j++){

                if(matrix[i][j] == 0 ){

                    rows[i] = true;

                    cols[j] = true;

                }

            }

        }

for (int i = 0; i < n; i++) {

        for (int j = 0; j < m; j++) {

            if (rows[i] || cols[j])

                matrix[i][j] = 0;

        }

    }

    }

};
  ```
  

 

  #### approach 2: 

  ```  

 class Solution {

public:

    void setZeroes(vector<vector<int>>& matrix) {

        int n = matrix.size();

        int m = matrix[0].size();

        vector<bool> rows(n, false), cols(m, false);

        for( int i = 0 ; i < n ; i++){

            for( int j = 0 ; j < m ; j++){

                if(matrix[i][j] == 0 ){

                    rows[i] = true;

                    cols[j] = true;

                }

            }

        }

for (int i = 0; i < n; i++) {

        for (int j = 0; j < m; j++) {

            if (rows[i] || cols[j])

                matrix[i][j] = 0;

        }

    }

    }

}; 

 ``` 