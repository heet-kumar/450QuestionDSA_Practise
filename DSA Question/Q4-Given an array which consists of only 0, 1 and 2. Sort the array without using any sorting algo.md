# Given an array which consists of only 0, 1 and 2. Sort the array without using any sorting algorithm

Given an array of size N containing only 0s, 1s, and 2s; sort the array in ascending order.

### Example 1:

- Input: 
  - N = 5
  - arr[]= {0 2 1 2 0}
- Output:
  0 0 1 2 2
- Explanation:
0s 1s and 2s are segregated 
into ascending order.

### Example 2:

- Input: 
  - N = 3
  - arr[] = {0 1 0}
- Output:
0 0 1
- Explanation:
0s 1s and 2s are segregated 
into ascending order.

### **Your Task :**
You don't need to read input or print anything. Your task is to complete the function sort012() that takes an array arr and N as input parameters and sorts the array in-place.

- Expected Time Complexity: O(N)
- Expected Auxiliary Space: O(1)

### Constraints:
- 1 <= N <= 10^6
- 0 <= A[i] <= 2

## Solution :

```C++
// C++
class Solution{
  public:
  void sort012(int a[], int n)
  {
      // coode here 

      int cnt0=0,cnt1=0,cnt2=0;

      for(int i=0;i<n;i++){
          if(a[i]==0) cnt0++;
          else if(a[i]==1) cnt1++;
          else cnt2++;
      }
      int i=0;
      while(cnt0--){
          a[i++]=0;
      }
      while(cnt1--){
          a[i++]=1;
      }
      while(cnt2--){
          a[i++]=2;
      }
  }
};
```

```C++
// C++ -> Dutch National Flag Algorithm
void sort012(int a[], int n)
{
    int low = 0, mid = 0, high = n - 1;
    while (mid <= high)
    {
        if (a[mid] == 0)
        {
            swap(a[mid], a[low]);
            mid++;
            low++;
        }
        else if (a[mid] == 1)
            mid++;
        else
        {
            swap(a[mid], a[high]);
            high--;
        }
    }
}
```

```Java
// java
public static void sort012(int a[], int n)
    {
        // code here 
        int cnt0=0,cnt1=0,cnt2=0;
        
        for(int i=0;i<n;i++){
            if(a[i]==0) cnt0++;
            else if(a[i]==1) cnt1++;
            else cnt2++;
        }
        int i=0;
        while(cnt0>0){
            a[i++]=0;
            cnt0--;
        }
        while(cnt1>0){
            a[i++]=1;
            cnt1--;
        }
        while(cnt2>0){
            a[i++]=2;
            cnt2--;
        }
    }
```
