# Valid Parentheses - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Valid Parentheses - Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

 1. Open brackets must be closed by the same type of brackets.
 2. Open brackets must be closed in the correct order.
 3. Every close bracket has a corresponding open bracket of the same type.
  
  ### Examples:
  ```
  Example 1:

Input: s = "()"

Output: true

Example 2:

Input: s = "()[]{}"

Output: true

Example 3:

Input: s = "(]"

Output: false

Example 4:

Input: s = "([])"

Output: true
  ```
  
  ### Constraints:
  
  Constraints:

 * 1 <= s.length <= 104
 * s consists of parentheses only '()[]{}'.
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  C++  ```
  ```
  class Solution {
public:
    bool isValid(string s) {
        stack<char> st;
        for ( char c : s){
            if ( c == '(' || c == '{' || c == '['){
                st.push(c);
            }else{
                if(st.empty() || (c == ')') && st.top() != '(' || (c == '}' && st.top() != '{') || (c == ']' && st.top() != '[')) {
                    return false ; }
                    st.pop();
            }} return st.empty();

    }
};
  ```
  