# Find minimum and maximum element in an array

Given an array A of size N of integers. Your task is to find the minimum and maximum elements in the array.

 

Example 1:

- Input:
  1. N = 6
  2. A[] = {3, 2, 1, 56, 10000, 167}
- Output:
min = 1, max =  10000
 

Example 2:

- Input:
  1. N = 5
  2. A[]  = {1, 345, 234, 21, 56789}
- Output:
min = 1, max = 56789
 

Your Task:  
You don't need to read input or print anything. Your task is to complete the function getMinMax() which takes the array A[] and its size N as inputs and returns the minimum and maximum element of the array.

 

- Expected Time Complexity: O(N)
- Expected Auxiliary Space: O(1)

 

Constraints:
- 1 <= N <= 10^5
- 1 <= Ai <= 10^12

## Solution :

```C++

// c++

pair<long long, long long> getMinMax(long long a[], int n) {
    long long mini = INT_MAX;
    long long maxi = INT_MIN;
    
    for(auto i=0;i<n;i++){
        mini = min(mini,a[i]);
        maxi = max(maxi,a[i]);
    }
    
    return {mini,maxi};
}
```

```Java

//Java
//User function Template for Java

/*
 class pair  
{  
    long first, second;  
    public pair(long first, long second)  
    {  
        this.first = first;  
        this.second = second;  
    }  
} */

class Compute 
{
    static pair getMinMax(long a[], long n)  
    {
        //Write your code here
        long mini = Integer.MAX_VALUE;
        long maxi = Integer.MIN_VALUE;
        
        for(long i:a){
            mini = Math.min(mini,i);
            maxi = Math.max(maxi,i);
        }
        
        pair p = new pair(mini,maxi);
        
        return p;
    }
}

```
