# Best time to buy and Sell stock [link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

## Example 1:

- Input: prices = [7,1,5,3,6,4]
- Output: 5
- Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
**Note** that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

## Example 2:

- Input: prices = [7,6,4,3,1]
- Output: 0
- Explanation: In this case, no transactions are done and the max profit = 0.

**Constraints:**

- 1 <= prices.length <= 10^5
- 0 <= prices[i] <= 10^4

## Solution

```C++
// C++
  class Solution {
    public:
        int maxProfit(vector<int>& p) {
            if (p.empty()) return 0;
            int pmax=0, minnum = INT_MAX;
            for(int i=0;i<p.size();i++){
                minnum = min(minnum,p[i]);
                pmax = max(pmax,p[i]-minnum);
            }

            return pmax;
        } 
  };
```

```C++
// C++ Best Solution
    class Solution {
      public:
              Solution(){ios_base::sync_with_stdio(false);
              cin.tie(NULL);
              cout.tie(NULL);}

          int maxProfit(vector<int>& prices) {
              int n=prices.size();
              int ans =0, min_val = prices[0];
              for(int i=0; i<n; i++)
              {
                  if(min_val > prices[i])
                      min_val = prices[i];
                  else if(ans < prices[i] - min_val)
                      ans = prices[i] - min_val;
              }
              return ans;
          }
      };
```
```Java
    // JAVA
    class Solution {
        public int maxProfit(int[] prices) {
            int mini = Integer.MAX_VALUE;
            int p = 0;

            for(int i=0;i<prices.length;i++){
                mini = Math.min(mini,prices[i]);
                p = Math.max(p,prices[i]-mini);
            }

            return p;
        }
    }
```
