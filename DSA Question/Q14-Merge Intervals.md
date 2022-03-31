# Merge Intervals [link](https://leetcode.com/problems/merge-intervals/)

Given an array of intervals where intervals[i] = [start[i], end[i]], merge all overlapping intervals, and return an array of the non-overlapping intervals that cover all the intervals in the input.

## Example 1:

- Input: intervals = [[1,3],[2,6],[8,10],[15,18]]
- Output: [[1,6],[8,10],[15,18]]
- Explanation: Since intervals [1,3] and [2,6] overlaps, merge them into [1,6].

## Example 2:

- Input: intervals = [[1,4],[4,5]]
- Output: [[1,5]]
- Explanation: Intervals [1,4] and [4,5] are considered overlapping.

**Constraints:**
- 1 <= intervals.length <= 10^4
- intervals[i].length == 2
- 0 <= starti <= endi <= 10^4

## Solution 

```C++
// C++
class Solution {
    public:
        vector<vector<int>> merge(vector<vector<int>>& it) {
            int top = 0;
            vector<vector<int>> v;
            int n = it.size();
            sort(it.begin(),it.end());
            vector<int> t;
            t.push_back(it[0][0]);
            t.push_back(it[0][1]);
            v.push_back(t);

            for(int i=1;i<n;i++){
                if(it[i][0]<=v[top][1]){
                    (v[top][1]>it[i][1])? v[top][1] = v[top][1]:v[top][1] = it[i][1];
                    (v[top][0]>it[i][0])? v[top][0]=it[i][0]:v[top][0]=v[top][0];
                }else{
                    top++;
                    t.clear();
                    t.push_back(it[i][0]);
                    t.push_back(it[i][1]);
                    v.push_back(t);
                }
            }
            return v;
        }
};
```