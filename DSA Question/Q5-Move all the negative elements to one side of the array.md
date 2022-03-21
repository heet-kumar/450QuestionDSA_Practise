# Move all the negative elements to one side of the array 

move all the negative elements of the array at the end of the array

### Example 1:

- Input:
  - N = 8
  - arr[] = {1, -1, 3, 2, -7, -5, 11, 6 }
- Output:
1 6 3 2 11 -5 -7 -1 

### Example 2:

- Input:
  - N = 8
  - arr[] = {-5, 7, -3, -4, 9, 10, -1, 11}
- Output:
11 7 10 9 -4 -3 -1 -5 

### Complexity:
- Time Complexity : O(N)
- Space Complexity : O(1)

## Solution :

```C++
// C++
#include <iostream>
using namespace std;

int main() {
    
    int n;
    cin>>n;
    
    int arr[n];
    for(int i=0;i<n;i++){
        cin>>arr[i];
    }
    
    int l = 0;
    int r = n-1;
    while(l<r){
        while(arr[l]>0) l++;
        while(arr[r]<0) r--;

        if(l<r){
            int t = arr[l];
            arr[l] = arr[r];
            arr[r] = t;
        }
    }
        
    for(int i=0;i<n;i++){
        cout<<arr[i]<<" ";
    }
    
	return 0;
}
```
