# Rotate List - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Rotate List - Given the head of a linked list, rotate the list to the right by k places.
  
  ### Examples:
  ```
  Example 1:

[https://assets.leetcode.com/uploads/2020/11/13/rotate1.jpg]


Input: head = [1,2,3,4,5], k = 2
Output: [4,5,1,2,3]


Example 2:

[https://assets.leetcode.com/uploads/2020/11/13/roate2.jpg]


Input: head = [0,1,2], k = 4
Output: [2,0,1]
  ```
  
  ### Constraints:
  
  Constraints:

 * The number of nodes in the list is in the range [0, 500].
 * -100 <= Node.val <= 100
 * 0 <= k <= 2 * 109
  
  
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
    ListNode* rotateRight(ListNode* head, int k) {
        if (!head || !head->next || k == 0) return head;

        // Count the number of nodes
        int cnt = 1;
        ListNode* tail = head;
        while (tail->next) {
            tail = tail->next;
            cnt++;
        }

        // Normalize k
        k = k % cnt;
        if (k == 0) return head;

        // Connect tail to head to make it circular
        tail->next = head;

        // Find new tail: (cnt - k) steps ahead
        ListNode* newTail = head;
        for (int i = 1; i < cnt - k; ++i) {
            newTail = newTail->next;
        }

        // Break the circle and get new head
        ListNode* newHead = newTail->next;
        newTail->next = nullptr;

        return newHead;
    }
};
  ```
  