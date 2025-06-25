# Reverse Nodes in k-Group - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Reverse Nodes in k-Group - Given the head of a linked list, reverse the nodes of the list k at a time, and return the modified list.

k is a positive integer and is less than or equal to the length of the linked list. If the number of nodes is not a multiple of k then left-out nodes, in the end, should remain as it is.

You may not alter the values in the list's nodes, only nodes themselves may be changed.
  
  ### Examples:
  ```
  Example 1:

[https://assets.leetcode.com/uploads/2020/10/03/reverse_ex1.jpg]


Input: head = [1,2,3,4,5], k = 2
Output: [2,1,4,3,5]


Example 2:

[https://assets.leetcode.com/uploads/2020/10/03/reverse_ex2.jpg]


Input: head = [1,2,3,4,5], k = 3
Output: [3,2,1,4,5]
  ```
  
  ### Constraints:
  
  Constraints:

 * The number of nodes in the list is n.
 * 1 <= k <= n <= 5000
 * 0 <= Node.val <= 1000

 

Follow-up: Can you solve the problem in O(1) extra memory space?
  
  
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
    ListNode* reverseKGroup(ListNode* head, int k) {
        if (!head || !head->next || k <= 1)
            return head;

        // Dummy node to handle edge cases
        ListNode dummy(0);
        dummy.next = head;
        ListNode* prevGroupEnd = &dummy;

        while (true) {
            // Check if there's a complete group of size k
            ListNode* kth = prevGroupEnd;
            for (int i = 0; i < k && kth; ++i)
                kth = kth->next;
            if (!kth)
                break; // Not enough nodes for a complete group

            ListNode* groupStart = prevGroupEnd->next;
            ListNode* nextGroupStart = kth->next;

            // Reverse the group
            ListNode* prev = nextGroupStart;
            ListNode* curr = groupStart;
            while (curr != nextGroupStart) {
                ListNode* tmp = curr->next;
                curr->next = prev;
                prev = curr;
                curr = tmp;
            }

            // Connect the reversed group
            prevGroupEnd->next = kth;
            prevGroupEnd = groupStart;
        }

        return dummy.next;
    }
};
  ```
  