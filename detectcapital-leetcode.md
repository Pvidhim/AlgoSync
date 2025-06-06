# Detect Capital - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Detect Capital - We define the usage of capitals in a word to be right when one of the following cases holds:

 * All letters in this word are capitals, like "USA".
 * All letters in this word are not capitals, like "leetcode".
 * Only the first letter in this word is capital, like "Google".

Given a string word, return true if the usage of capitals in it is right.
  
  ### Examples:
  ```
  Example 1:

Input: word = "USA"
Output: true


Example 2:

Input: word = "FlaG"
Output: false
  ```
  
  ### Constraints:
  
  Constraints:

 * 1 <= word.length <= 100
 * word consists of lowercase and uppercase English letters.
  
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

    bool detectCapitalUse(string word) {

        int flag = 0;

        int cnt = 0;

        for (int i = 0; i < word.size(); i++) {

            if ((int)word[i] >= 65 && (int)word[i] <= 90) {

                cnt = cnt + 1;

            }

        }

        if (cnt == word.size() || cnt == 0)

            return true;

        else {



            if (cnt == 1 && (int)word[0] >= 65 && (int)word[0] <= 90) {

                return true;

            } else {

                return false;

            }

        }

    }

};
  ```
  