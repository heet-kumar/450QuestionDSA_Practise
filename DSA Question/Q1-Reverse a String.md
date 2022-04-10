# Reverse a String [link](https://practice.geeksforgeeks.org/problems/reverse-a-string/1)

You are given a string s. You need to reverse the string.

Example 1:

- Input:Geeks
- Output: skeeG

Example 2:

- Input: for
- Output: rof

Your Task:

You only need to complete the function reverseWord() that takes s as parameter and returns the reversed string.

- Expected Time Complexity: O(|S|).
- Expected Auxiliary Space: O(1).

Constraints:
1 <= |s| <= 10000


Solution:

```C++
string reverseWord(string str){
    
  //Your code here
  int l=0;
  int r=str.size() - 1;
  while(l<r){
      char temp = str[l];
      str[l] = str[r];
      str[r] = temp;
      
      l++;
      r--;
  }
  
  return str;
}
```
