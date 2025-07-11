# Implement Queue using Stacks - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Implement Queue using Stacks - Implement a first in first out (FIFO) queue using only two stacks. The implemented queue should support all the functions of a normal queue (push, peek, pop, and empty).

Implement the MyQueue class:

 * void push(int x) Pushes element x to the back of the queue.
 * int pop() Removes the element from the front of the queue and returns it.
 * int peek() Returns the element at the front of the queue.
 * boolean empty() Returns true if the queue is empty, false otherwise.

Notes:

 * You must use only standard operations of a stack, which means only push to top, peek/pop from top, size, and is empty operations are valid.
 * Depending on your language, the stack may not be supported natively. You may simulate a stack using a list or deque (double-ended queue) as long as you use only a stack's standard operations.
  
  ### Examples:
  ```
  Example 1:


Input
["MyQueue", "push", "push", "peek", "pop", "empty"]
[[], [1], [2], [], [], []]
Output
[null, null, null, 1, 1, false]

Explanation
MyQueue myQueue = new MyQueue();
myQueue.push(1); // queue is: [1]
myQueue.push(2); // queue is: [1, 2] (leftmost is front of the queue)
myQueue.peek(); // return 1
myQueue.pop(); // return 1, queue is [2]
myQueue.empty(); // return false
  ```
  
  ### Constraints:
  
  Constraints:

 * 1 <= x <= 9
 * At most 100 calls will be made to push, pop, peek, and empty.
 * All the calls to pop and peek are valid.

 

Follow-up: Can you implement the queue such that each operation is amortized [https://en.wikipedia.org/wiki/Amortized_analysis] O(1) time complexity? In other words, performing n operations will take overall O(n) time even if one of those operations may take longer.
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  C++  ```
  ```
  ["MyQueue","empty","push","push","empty","peek","push","push","peek","pop","empty","peek","pop","empty"]
[[],[],[1],[1],[],[],[5],[5],[],[],[],[],[],[]]
["MyQueue","push","pop","push","empty","push","pop","peek","push","empty","pop","pop","push","push","peek","empty","empty","empty","pop","pop","push","push","pop","empty","empty","pop","push","empty","push","pop","push","peek","empty","pop","peek","push","empty","push","empty","push","peek","pop","empty","empty","pop","push","pop","pop","empty","push","pop","push","push","empty","empty","empty","peek","peek","peek","empty","pop","empty","pop","push","empty","pop","pop","push","empty","push","pop","empty","pop","push","peek","pop","push","push","push","push","empty","pop","peek","pop","pop","push","peek","pop","pop","push","pop","push","peek","push","empty","push","empty","push","peek","pop","pop"]
[[],[7],[],[8],[],[4],[],[],[4],[],[],[],[5],[7],[],[],[],[],[],[],[9],[8],[],[],[],[],[9],[],[4],[],[5],[],[],[],[],[6],[],[7],[],[5],[],[],[],[],[],[5],[],[],[],[2],[],[7],[5],[],[],[],[],[],[],[],[],[],[],[2],[],[],[],[8],[],[2],[],[],[],[2],[],[],[1],[7],[9],[5],[],[],[],[],[],[8],[],[],[],[7],[],[6],[],[7],[],[4],[],[2],[],[],[]]
["MyQueue","push","push","push","push","push","peek","push","push","push","push","peek","pop","pop","pop","pop","peek","pop","pop","peek","pop"]
[[],[1],[4],[9],[2],[2],[],[1],[2],[7],[1],[],[],[],[],[],[],[],[],[],[]]
["MyQueue","push","push","push","push","push","push","push","push","push","push","peek","pop","pop","pop","pop","pop","pop","pop","peek","pop"]
[[],[5],[6],[7],[6],[1],[8],[2],[5],[4],[7],[],[],[],[],[],[],[],[],[],[]]
["MyQueue","push","push","push","push","push","push","push","push","push","push","peek","pop","pop","pop","pop","pop","pop","empty","peek","pop"]
[[],[4],[5],[6],[7],[8],[1],[1],[2],[3],[4],[],[],[],[],[],[],[],[],[],[]]
["MyQueue","empty","push","push","push","push","push","empty","push","push","push","peek","empty","peek","pop","pop","empty","pop","pop","peek","pop"]
[[],[],[1],[1],[1],[1],[1],[],[3],[4],[5],[],[],[],[],[],[],[],[],[],[]]
["MyQueue","push","pop","empty","push","pop","push","pop","push","peek","empty","pop","push","pop","push","peek","pop","empty","push","pop","push"]
[[],[1],[],[],[2],[],[3],[],[4],[],[],[],[5],[],[6],[],[],[],[7],[],[8]]
["MyQueue","push","push","peek","pop","push","empty","pop","pop","push","push","empty","push","empty","pop","pop","peek","peek","peek","empty","empty","push","pop","pop","push","peek","pop","push","empty","pop","push","empty","empty","pop","push","empty","pop","push","empty","pop","push","peek","push","empty","pop","empty","pop","push","pop","push","empty","pop","push","empty","pop","push","pop","push","peek","pop","push","empty","pop","push","pop","push","push","empty","push","push","pop","empty","pop","push","pop","peek","pop","pop","push","peek","peek","push","empty","push","push","empty","empty","peek","empty","push","pop","pop","pop","peek","empty","pop","push","peek","empty","empty","peek"]
[[],[9],[3],[],[],[5],[],[],[],[3],[8],[],[8],[],[],[],[],[],[],[],[],[4],[],[],[4],[],[],[8],[],[],[3],[],[],[],[4],[],[],[8],[],[],[2],[],[6],[],[],[],[],[1],[],[7],[],[],[8],[],[],[5],[],[6],[],[],[3],[],[],[9],[],[2],[6],[],[3],[5],[],[],[],[6],[],[],[],[],[9],[],[],[2],[],[3],[4],[],[],[],[],[3],[],[],[],[],[],[],[1],[],[],[],[]]
  ```
  