# Highest Common Factor

Find the HCF(Highest Common Factor) of n number given in an integer array. Fill in the function HCF() and return the HCF.

## Example 1
- Input:
  - 3
  - {2,4,8}
- Output: 2
- Explaination: The common factor for 2,4,8 are 1 and 2. Hence the HCF is 2.

## Example 2
- Input:
  - 5
  - {10,15,20,35,70}
- Output: 5
- Expalination: The common factor for 10,15,20,35,70 are 1 and 5. Hence the HCF is 5.

## Input format:
- The size of array
- elements of the array

## Output format:
- Return the HCF of the given number

## Solution

```C++
  // C++ language used
  #include<bits/stdc++.h>
  using namespace std;
  
  int gcd(int a,int b){
    if(b==0) return a;
    else return gcd(b,a%b);
  }
  
  int main(){
    int n;
    cin>>n;
    int a[n];
    for(int i=0;i<n;i++) cin>>a[i];
    int t=a[0];
    for(int i=1;i<n;i++){
      t = gcd(a[i],t);
    }
    cout<<t;
    return 0;
  }
  
```
