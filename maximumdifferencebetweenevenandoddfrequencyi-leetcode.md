# Maximum Difference Between Even and Odd Frequency I - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Maximum Difference Between Even and Odd Frequency I - You are given a string s consisting of lowercase English letters.

Your task is to find the maximum difference diff = freq(a1) - freq(a2) between the frequency of characters a1 and a2 in the string such that:

 * a1 has an odd frequency in the string.
 * a2 has an even frequency in the string.

Return this maximum difference.
  
  ### Examples:
  ```
  Example 1:

Input: s = "aaaaabbc"

Output: 3

Explanation:

 * The character 'a' has an odd frequency of 5, and 'b' has an even frequency of 2.
 * The maximum difference is 5 - 2 = 3.

Example 2:

Input: s = "abcabcab"

Output: 1

Explanation:

 * The character 'a' has an odd frequency of 3, and 'c' has an even frequency of 2.
 * The maximum difference is 3 - 2 = 1.
  ```
  
  ### Constraints:
  
  Constraints:

 * 3 <= s.length <= 100
 * s consists only of lowercase English letters.
 * s contains at least one character with an odd frequency and one with an even frequency.
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  C++  ```
  ```
  #include <iostream>
#include <map>
using namespace std;

class Solution {
public:
    int maxDifference(string s) {
        map<char, int> mp;
        int maxodd = 0, maxeven = 0, mineven = INT_MAX; 

        
        for (char c : s) {
            mp[c]++;
        }

        
        for (auto &entry : mp) {
            int freq = entry.second;

            if (freq % 2 == 0) { 
                maxeven = max(maxeven, freq);
                mineven = min(mineven, freq);
            } else {
                maxodd = max(maxodd, freq);
            }
        }

        
        
            return maxodd - mineven;
        
    }
};
  ```
  