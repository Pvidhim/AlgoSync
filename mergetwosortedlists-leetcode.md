# Merge Two Sorted Lists - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Merge Two Sorted Lists - You are given the heads of two sorted linked lists list1 and list2.

Merge the two lists into one sorted list. The list should be made by splicing together the nodes of the first two lists.

Return the head of the merged linked list.
  
  ### Examples:
  ```
  Example 1:

[https://assets.leetcode.com/uploads/2020/10/03/merge_ex1.jpg]


Input: list1 = [1,2,4], list2 = [1,3,4]
Output: [1,1,2,3,4,4]


Example 2:


Input: list1 = [], list2 = []
Output: []


Example 3:


Input: list1 = [], list2 = [0]
Output: [0]
  ```
  
  ### Constraints:
  
  Constraints:

 * The number of nodes in both lists is in the range [0, 50].
 * -100 <= Node.val <= 100
 * Both list1 and list2 are sorted in non-decreasing order.
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  C++  ```
  ```
  class Solution {
public:
    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
        ListNode* dummy = new ListNode(0);
        ListNode* cur = dummy;

        while (list1 && list2) {
            if (list1->val > list2->val) {
                cur->next = list2;
                list2 = list2->next;
            } else {
                cur->next = list1;
                list1 = list1->next;
            }
            cur = cur->next;
        }

        cur->next = list1 ? list1 : list2;

        ListNode* head = dummy->next;
        delete dummy;
        return head;        
    }
};
  ```
  