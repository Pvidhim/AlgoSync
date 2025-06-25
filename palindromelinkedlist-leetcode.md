# Palindrome Linked List - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Palindrome Linked List - Given the head of a singly linked list, return true if it is a palindrome or false otherwise.
  
  ### Examples:
  ```
  Example 1:

[https://assets.leetcode.com/uploads/2021/03/03/pal1linked-list.jpg]


Input: head = [1,2,2,1]
Output: true


Example 2:

[https://assets.leetcode.com/uploads/2021/03/03/pal2linked-list.jpg]


Input: head = [1,2]
Output: false
  ```
  
  ### Constraints:
  
  Constraints:

 * The number of nodes in the list is in the range [1, 105].
 * 0 <= Node.val <= 9

 

Follow up: Could you do it in O(n) time and O(1) space?
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  C++  ```
  ```
  class Solution {
public:
    bool isPalindrome(ListNode* head) {
        vector<int> arr;

        while (head != nullptr) {
            arr.push_back(head->val);
            head = head->next;
        }

        int left = 0;
        int right = arr.size() - 1;

        while (left < right) {
            if (arr[left] != arr[right]) {
                return false;
            }
            left++;
            right--;
        }

        return true;        
    }
};
  ```
  