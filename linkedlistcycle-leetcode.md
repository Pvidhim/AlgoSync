# Linked List Cycle - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Linked List Cycle - Given head, the head of a linked list, determine if the linked list has a cycle in it.

There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.

Return true if there is a cycle in the linked list. Otherwise, return false.
  
  ### Examples:
  ```
  Example 1:

[https://assets.leetcode.com/uploads/2018/12/07/circularlinkedlist.png]


Input: head = [3,2,0,-4], pos = 1
Output: true
Explanation: There is a cycle in the linked list, where the tail connects to the 1st node (0-indexed).


Example 2:

[https://assets.leetcode.com/uploads/2018/12/07/circularlinkedlist_test2.png]


Input: head = [1,2], pos = 0
Output: true
Explanation: There is a cycle in the linked list, where the tail connects to the 0th node.


Example 3:

[https://assets.leetcode.com/uploads/2018/12/07/circularlinkedlist_test3.png]


Input: head = [1], pos = -1
Output: false
Explanation: There is no cycle in the linked list.
  ```
  
  ### Constraints:
  
  Constraints:

 * The number of the nodes in the list is in the range [0, 104].
 * -105 <= Node.val <= 105
 * pos is -1 or a valid index in the linked-list.

 

Follow up: Can you solve it using O(1) (i.e. constant) memory?
  
  
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
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    bool hasCycle(ListNode *head) {

        if( head == NULL || head->next == NULL ){
            return false;
        }
    unordered_set<ListNode*> st;
    while(head != NULL && st.find(head)==NULL) {
       st.insert(head);
       head = head->next;
    }
    if(head == NULL){
        return false;
    }
    else{
        return true;
    }
        
    }
};
  ```
  