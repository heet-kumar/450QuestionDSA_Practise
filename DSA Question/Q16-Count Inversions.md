# Count Inversions [link](https://practice.geeksforgeeks.org/problems/inversion-of-array-1587115620/1)

Given an array of integers. Find the Inversion Count in the array. 

Inversion Count: For an array, inversion count indicates how far (or close) the array is from being sorted. If array is already sorted then the inversion count is 0. If an array is sorted in the reverse order then the inversion count is the maximum. 
Formally, two elements a[i] and a[j] form an inversion if a[i] > a[j] and i < j .

## Example 1:

- Input: 
  - N = 5, 
  - arr[] = {2, 4, 1, 3, 5}
- Output: 3
- Explanation: The sequence 2, 4, 1, 3, 5 
has three inversions (2, 1), (4, 1), (4, 3).

## Example 2:

- Input: 
  - N = 5
  - arr[] = {2, 3, 4, 5, 6}
- Output: 0
- Explanation: As the sequence is already 
sorted so there is no inversion count.

## Example 3:

- Input: 
  - N = 3, 
  - arr[] = {10, 10, 10}
- Output: 0
- Explanation: As all the elements of array 
are same, so there is no inversion count.

## Your Task:
You don't need to read input or print anything. Your task is to complete the function inversionCount() which takes the array arr[] and the size of the array as inputs and returns the inversion count of the given array.

- Expected Time Complexity: O(NLogN).
- Expected Auxiliary Space: O(N).

**Constraints:**
- 1 ≤ N ≤ 5*10^5
- 1 ≤ arr[i] ≤ 10^18

## Solution

```C++
// C++
  class Solution{
    public:
      // arr[]: Input Array
      // N : Size of the Array arr[]
      // Function to count inversions in the array.

      typedef long long ll;
      long long ans = 0;
      void merge(ll arr[], ll low, ll mid, ll high)
      {
          ll n1 = mid-low+1;
          ll n2 = high-mid;
          ll left[n1], right[n2];

          for(int i=0;i<n1;i++)
             left[i] = arr[low+i];

          for(int i=0;i<n2;i++)
             right[i] = arr[mid+1+i];

          ll i=0,j=0,k=low;

          while(i<n1&&j<n2)
          {
              if(left[i]<=right[j])
                arr[k++] = left[i++];
              else
              {
                  ans+=(n1-i);
                  arr[k++] = right[j++];
              }
          }

          while(i<n1) arr[k++] = left[i++];
          while(j<n2) arr[k++] = right[j++];

      }
      void mergeSort(long long arr[], int low, int high)
      {
          if(low<high)
          {
              ll mid = low+(high-low)/2;
              mergeSort(arr,low,mid);
              mergeSort(arr,mid+1,high);
              merge(arr,low,mid,high);
          }
      }
      long long int inversionCount(long long arr[], long long N)
      {
          // Your Code Here
          mergeSort(arr,0,N-1);
          return ans;
      }

  };
  
```
