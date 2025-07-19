# Can Place Flowers - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Can Place Flowers - You have a long flowerbed in which some of the plots are planted, and some are not. However, flowers cannot be planted in adjacent plots.

Given an integer array flowerbed containing 0's and 1's, where 0 means empty and 1 means not empty, and an integer n, return true if n new flowers can be planted in the flowerbed without violating the no-adjacent-flowers rule and false otherwise.
  
  ### Examples:
  ```
  Example 1:

Input: flowerbed = [1,0,0,0,1], n = 1
Output: true


Example 2:

Input: flowerbed = [1,0,0,0,1], n = 2
Output: false
  ```
  
  ### Constraints:
  
  Constraints:

 * 1 <= flowerbed.length <= 2 * 104
 * flowerbed[i] is 0 or 1.
 * There are no two adjacent flowers in flowerbed.
 * 0 <= n <= flowerbed.length
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  C++  ```
  ```
  class Solution {
public:
    bool canPlaceFlowers(vector<int>& flowerbed, int n) {
        int num = flowerbed.size();
        if(num == 1 && flowerbed[0] == 0){
            return true;
        }
        if(num == 1 && flowerbed[0]==1 && n == 1){
            return false;
        }
        if(num == 1 && flowerbed[0]==1 && n == 0){
            return true;
        }
        int numzero = 0;
        if(flowerbed[0] == 0 && flowerbed[1] == 0 ){
            numzero++;
            flowerbed[0] = 1;
        }
        if(flowerbed[num-1] == 0 && flowerbed[num - 2]==0 && num!=2){
            numzero++;
            flowerbed[num-1] = 1;
        }
        for(int i = 1 ; i < num-1 ; i++){
            if(flowerbed[i]==0 && flowerbed[i-1]!=1 && flowerbed[i+1]!=1){
                numzero++;
                flowerbed[i] = 1;
            }
        }
        if(numzero >= n){
            return true;
        }
        else if ((numzero == n && n == 1) || n == 0){
            return true;
        }
        else{
            return false;
        }
        
    }
};
  ```
  