# Reverse Linked List - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Reverse Linked List - Given the head of a singly linked list, reverse the list, and return the reversed list.
  
  ### Examples:
  ```
  Example 1:

[https://assets.leetcode.com/uploads/2021/02/19/rev1ex1.jpg]


Input: head = [1,2,3,4,5]
Output: [5,4,3,2,1]


Example 2:

[https://assets.leetcode.com/uploads/2021/02/19/rev1ex2.jpg]


Input: head = [1,2]
Output: [2,1]


Example 3:


Input: head = []
Output: []
  ```
  
  ### Constraints:
  
  Constraints:

 * The number of nodes in the list is the range [0, 5000].
 * -5000 <= Node.val <= 5000

 

Follow up: A linked list can be reversed either iteratively or recursively. Could you implement both?
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  C++  ```
  ```
  /**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode* temp;
        temp = head;
        ListNode* prev = nullptr ;
        ListNode* front;
        while(temp!=NULL){
            front = temp->next;
            temp->next = prev;
            prev = temp;
            temp = front;
        }
        return prev;
    }
};
  ```
  