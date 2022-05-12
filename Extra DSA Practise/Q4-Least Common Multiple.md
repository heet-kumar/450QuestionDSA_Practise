# Least Common Multiple

Find the LCM of the given two integers. Fill in the function that takes as inputs two integers and return the LCM.

## Example 1 :
- Input:
  - 2
  - 3
- Output: 6
- Explaination: The LCM of 2 and 3 is 6.

## Example 2:
- Input:
  - 5
  - 65
- Output: 65
- Explaination: The LCM of 5 and 65 is 65.

## Input format:
- First Integer
- Second Integer

## Output format:
- Return the LCM of the two number

**Code Constraints :**
- 1 <= input1 <= 10^9
- 1 <= input2 <= 10^9

## Solution :

```C++
  // Code in C++ language
  #include<bits/stdc++.h>
  using namespace std;
  
  int gcd(int a,int b){
    if(b==0)return a;
    return gcd(b,a%b);
  }
  
  int lcm(int a,int b){
    return (a / gcd(a,b)) * b;
  }
  
  int main(){
    int a,b;
    cin>>a>>b;
    cout<<lcm(a,b);
    return 0;
  }
  
```
