# Greatest English Letter in Upper and Lower Case [Link](https://leetcode.com/problems/greatest-english-letter-in-upper-and-lower-case/)

Given a string of English letters s, return the greatest English letter which occurs as both a lowercase and uppercase letter in s. The returned letter should be in uppercase. If no such letter exists, return an empty string.

An English letter b is greater than another letter a if b appears after a in the English alphabet.

## Example 1:

- **Input:** s = "lEeTcOdE"
- **Output:** "E"
- **Explanation:**
The letter 'E' is the only letter to appear in both lower and upper case.

## Example 2:

- **Input:** s = "arRAzFif"
- **Output:** "R"
- **Explanation:**
The letter 'R' is the greatest letter to appear in both lower and upper case.
**Note** that 'A' and 'F' also appear in both lower and upper case, but 'R' is greater than 'F' or 'A'.

## Example 3:

- **Input:** s = "AbCdEfGhIjK"
- **Output:** ""
- **Explanation:**
There is no letter that appears in both lower and upper case.

**Constraints:**

- 1 <= s.length <= 1000
- s consists of lowercase and uppercase English letters.


## Solution

```C++
// Solution in C++

class Solution {
public:
    string greatestLetter(string s) {
        int len = s.size();
        unordered_map<char,int> m;
        for(int i=0;i<len;i++){
            m[s[i]]++;
        }
        string ans ="";
        sort(s.begin(),s.end());
        for(int i=0;i<len;i++){
            char l = tolower(s[i]);
            char u = toupper(s[i]);
            if(m[l]&&m[u]) ans=u;
        }
        return ans; 
    }
};

```
```C++
// Solution in C++ time is reduced

class Solution {
    public:
        string greatestLetter(string s) {
            for(char ch='z';ch>='a';ch--){
                char ch2=ch-32;
                bool f1=false,f2=false;
                for(char ch3:s){
                    if(ch3==ch) f2=true;
                    if(ch3==ch2) f1=true;
                }
                if(f1 && f2) return string(1,ch2);
            }
            return "";
        }
};
