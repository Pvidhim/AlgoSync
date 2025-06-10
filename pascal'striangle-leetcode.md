# Pascal's Triangle - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Pascal's Triangle - Given an integer numRows, return the first numRows of Pascal's triangle.

In Pascal's triangle, each number is the sum of the two numbers directly above it as shown:

[https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif]
  
  ### Examples:
  ```
  Example 1:

Input: numRows = 5
Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]


Example 2:

Input: numRows = 1
Output: [[1]]
  ```
  
  ### Constraints:
  
  Constraints:

 * 1 <= numRows <= 30
  
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

    vector<vector<int>> generate(int numRows) {

        vector<vector<int>> ans(numRows); 

        

        for (int i = 0; i < numRows; i++) {

            ans[i].resize(i + 1); 

            ans[i][0] = ans[i][i] = 1; 

            

            for (int j = 1; j < i; j++) {

                ans[i][j] = ans[i-1][j-1] + ans[i-1][j]; // Pascal's Triangle rule

            }

        }

        return ans;

    }

};
  ```
  

 

  #### approach 2: 

  ```  

 class Solution {

public:

    vector<vector<int>> generate(int numRows) {

        vector<vector<int>> result;

        for (int i = 0; i < numRows; i++) {

            vector<int> row(i + 1, 1);

            for (int j = 1; j < i; j++) {

                row[j] = result[i - 1][j - 1] + result[i - 1][j];

            }

            result.push_back(row);

        }

        return result;

    }

};

 

 ``` 

 

  #### approach 3: 

  ```  

 class Solution {

public:

    vector<vector<int>> generate(int numRows) {

        vector<vector<int>> result;

        for (int i = 0; i < numRows; i++) {

            vector<int> row(i + 1, 1);

            for (int j = 1; j < i; j++) {

                row[j] = result[i - 1][j - 1] + result[i - 1][j];

            }

            result.push_back(row);

        }

        return result;

    }

};

 

 ``` 