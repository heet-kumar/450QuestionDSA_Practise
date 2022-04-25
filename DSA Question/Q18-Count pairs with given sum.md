# find all pairs on integer array whose sum is equal to given number [link](https://practice.geeksforgeeks.org/problems/count-pairs-with-given-sum5022/1)
# Count pairs with given sum

Given an array of N integers, and an integer K, find the number of pairs of elements in the array whose sum is equal to K.

## Example 1:

- Input:
  - N = 4, K = 6
  - arr[] = {1, 5, 7, 1}
- Output: 2
- Explanation: 
arr[0] + arr[1] = 1 + 5 = 6 
and arr[1] + arr[3] = 5 + 1 = 6.

## Example 2:

- Input:
  - N = 4, K = 2
  - arr[] = {1, 1, 1, 1}
- Output: 6
- Explanation: 
Each 1 will produce sum 2 with any 1.

## Your Task:
You don't need to read input or print anything. Your task is to complete the function getPairsCount() which takes arr[], n and k as input parameters and returns the number of pairs that have sum K.

- Expected Time Complexity: O(N)
- Expected Auxiliary Space: O(N)

**Constraints:**
- 1 <= N <= 10^5
- 1 <= K <= 10^8
- 1 <= Arr[i] <= 10^6

## Solution

```C++
  // C++ solution
  // only 180 test case passed out off 253
  
  class Solution{   
    public:
        int cnt = 0;

        void validpair(int a[],int n,int k,int pos){

            if(pos==n) return;
            else{
                for(int i=pos+1;i<n;i++){
                    if(a[pos]+a[i] == k) cnt++;
                }

                validpair(a,n,k,pos+1);
            }
        }

        int getPairsCount(int arr[], int n, int k) {
            // code here
            validpair(arr,n,k,0);
            return cnt;
        }
    };
  
  
```
