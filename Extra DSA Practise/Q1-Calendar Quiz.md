# Calendar Quiz

Super Quiz Bee is a famous quiz Competition that tests sudent on a wide variety of academic subjects. This weeks's participants were kids of age 12 to 15 and quiz question is based on the Gregorian calendar.

In the first round of the competition, The Host of the event told the participants that it was monday on date 01/01/2001. Later he questioned each one of the participant what would be the day on the 1st January, giving them a particular year. Write a program to help the Host to validate the answers given by the participants.

## Input

The first line contains an integer that corresponds to a year.

## Output

Output the day on the 1st January of that given year.

## Example

- Input : 2001
- Output : Monday

## Solution

```C++
  // C++
  #include<bits/stdc++.h>
  using namespace std;
  
  int main(){
    int ref_year = 1900, year, diff, leap_year, non_leap_year, days, result;
    cin>>year;
    diff = year - 1 - ref_year;
    leap_year = diff/4;
    non_leap_year = diff - leap_year;
    days = leap_year*366 + non_leap_year*365 + 1;
    result = days%7;
    switch(result){
      case 0: cout<<"Monday"; break;
      case 1: cout<<"Tuesday"; break;
      case 2: cout<<"Wednesday"; break;
      case 3: cout<<"Thursday"; break;
      case 4: cout<<"Friday"; break;
      case 5: cout<<"Saturday"; break;
      case 6: cout<<"Sunday"; break;
    }
    return 0;
  }

```
