# find duplicate in an array of N+1 Integers
# Find the Duplicate Number

Given an array of integers nums containing n + 1 integers where each integer is in the range [1, n] inclusive.

There is only one repeated number in nums, return this repeated number.

You must solve the problem without modifying the array nums and uses only constant extra space.

## Example 1:

- Input: nums = [1,3,4,2,2]
- Output: 2

## Example 2:

- Input: nums = [3,1,3,4,2]
- Output: 3

## Constraints:

- 1 <= n <= 10^5
- nums.length == n + 1
- 1 <= nums[i] <= n
- All the integers in nums appear only once except for precisely one integer which appears two or more times.

## Solution

```C++
  // C++ but space complexity is O(N)
  class Solution {
    public:
        int findDuplicate(vector<int>& nums) {
            set<int> s;
            int len = nums.size(),temp,i;
            for(i=0;i<len;i++){
                temp = s.size();
                s.insert(nums[i]);

                if(s.size() == temp) 
                {
                    break;
                }  
            }
            return nums[i]; 
        }
    };
```
