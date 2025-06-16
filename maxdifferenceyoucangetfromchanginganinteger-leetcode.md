# Max Difference You Can Get From Changing an Integer - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Max Difference You Can Get From Changing an Integer - You are given an integer num. You will apply the following steps to num two separate times:

 * Pick a digit x (0 <= x <= 9).
 * Pick another digit y (0 <= y <= 9). Note y can be equal to x.
 * Replace all the occurrences of x in the decimal representation of num by y.

Let a and b be the two results from applying the operation to num independently.

Return the max difference between a and b.

Note that neither a nor b may have any leading zeros, and must not be 0.
  
  ### Examples:
  ```
  Example 1:


Input: num = 555
Output: 888
Explanation: The first time pick x = 5 and y = 9 and store the new integer in a.
The second time pick x = 5 and y = 1 and store the new integer in b.
We have now a = 999 and b = 111 and max difference = 888


Example 2:


Input: num = 9
Output: 8
Explanation: The first time pick x = 9 and y = 9 and store the new integer in a.
The second time pick x = 9 and y = 1 and store the new integer in b.
We have now a = 9 and b = 1 and max difference = 8
  ```
  
  ### Constraints:
  
  Constraints:

 * 1 <= num <= 108
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  C++  ```
  ```
  class Solution {
public:
    int maxDiff(int num) {
        string num1 = to_string(num);
        string num2 = num1;
        string maxi;
        string mini;
        char maxdigi = '0';
        char minidigi = '0';
        for(int i = 0 ; i < num1.size(); i++){
            if(num1[i] != '9'){
                maxdigi = num1[i];
                break;
            }
        }
        for(int i = 0 ; i < num1.size(); i++){
            if(num1[i] == maxdigi){
                num1[i] = '9';
            }
        }
        maxi = num1;
        int pos;

        for(int i =0; i < num2.size() ; i++){
            if(num2[i] != '1' && num2[i] != '0'){
                minidigi = num2[i];
                pos=i;
                break;
            }
        }
        if(pos == 0){
        for(int i = 0 ; i < num2.size(); i++){
            if(num2[i] == minidigi){
                num2[i] = '1';
            }

        }
        }
        else{
            for(int i = 0 ; i < num2.size(); i++){
            if(num2[i] == minidigi){
                num2[i] = '0';
            }

        }
        }
        mini = num2;

        int diff = stoi(maxi) - stoi(mini);
        return diff;

        
    }
};
  ```
  