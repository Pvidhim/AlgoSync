# Create Hello World Function - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Create Hello World Function - Write a function createHelloWorld. It should return a new function that always returns "Hello World".
  
  ### Examples:
  ```
  Example 1:


Input: args = []
Output: "Hello World"
Explanation:
const f = createHelloWorld();
f(); // "Hello World"

The function returned by createHelloWorld should always return "Hello World".


Example 2:


Input: args = [{},null,42]
Output: "Hello World"
Explanation:
const f = createHelloWorld();
f({}, null, 42); // "Hello World"

Any arguments could be passed to the function but it should still always return "Hello World".
  ```
  
  ### Constraints:
  
  Constraints:

 * 0 <= args.length <= 10
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  JavaScript  ```
  ```
  function f(a, b) {
    const sum = a + b;
    return sum;
}
console.log(f(3, 4)); // 7
  ```
  