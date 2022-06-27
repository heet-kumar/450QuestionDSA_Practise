# Running Sum of 1d Array [Link](https://leetcode.com/problems/running-sum-of-1d-array/)

Given an array nums. We define a running sum of an array as runningSum[i] = sum(nums[0]…nums[i]).

Return the running sum of nums.

## Example 1:

- Input: nums = [1,2,3,4]
- Output: [1,3,6,10]
- Explanation: Running sum is obtained as follows: [1, 1+2, 1+2+3, 1+2+3+4].

## Example 2:

- Input: nums = [1,1,1,1,1]
- Output: [1,2,3,4,5]
- Explanation: Running sum is obtained as follows: [1, 1+1, 1+1+1, 1+1+1+1, 1+1+1+1+1].

## Example 3:

- Input: nums = [3,1,2,10,1]
- Output: [3,4,6,16,17]

**Constraints:**

- 1 <= nums.length <= 1000
- -10^6 <= nums[i] <= 10^6

# Solution

```C++
// Solution in C++ with recursion
  class Solution {
  public:
      vector<int> running(vector<int> v,int pos,int len,vector<int> &a,int sum){
          if(pos==len) return a;
          sum+=v[pos];
          a.push_back(sum);
          return running(v,pos+1,len,a,sum);
      }
      vector<int> runningSum(vector<int>& v) {
          int n = v.size();
          vector<int> a;
          running(v,0,n,a,0);
          return a;
      }
  }
```

```C++
// solution in C++ without recursion
  class Solution{
    public:
        vector<int> runningSum(vector<int> &v){
          int n = v.size();
          vector<int> a;
          a.push_back(v[0]);
          for(int i=1;i<n;i++){
              a.push_back(a[i-1]+v[i]);
          }
          return a;
        }
  }

```
