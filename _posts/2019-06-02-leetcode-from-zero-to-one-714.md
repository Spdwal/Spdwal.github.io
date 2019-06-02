---
layout: post
title: "[Leetcode from zero to one] 714"
category: 
tags: []
---

# 714 -  Best Time to Buy and Sell Stock with Transaction Fee

Your are given an array of integers `prices`, for which the `i`-th element is the price of a given stock on day `i`; and a non-negative integer `fee` representing a transaction fee.

You may complete as many transactions as you like, but you need to pay the transaction fee for each transaction. You may not buy more than 1 share of a stock at a time (ie. you must sell the stock share before you buy again.)

Return the maximum profit you can make.

**Example 1:**

```
Input: prices = [1, 3, 2, 8, 4, 9], fee = 2
Output: 8
Explanation: The maximum profit can be achieved by:
Buying at prices[0] = 1Selling at prices[3] = 8Buying at prices[4] = 4Selling at prices[5] = 9The total profit is ((8 - 1) - 2) + ((9 - 4) - 2) = 8.
```



**Note:**

`0 < prices.length <= 50000`.

`0 < prices[i] < 50000`.

`0 <= fee < 50000`.

最终还是要用动态规划来做。

```c++
class Solution {
public:
    int maxProfit(vector<int>& prices, int fee) {
        int sz = prices.size();
        if(sz < 2){
            return 0;
        }
        // 存储当前的资金，
        vector<int> hold(sz, 0);
      	// 存储利润
        vector<int> notHold(sz, 0);
        
      	// 由于没有初始资金，那么假设它买了第一波股票
        hold[0] = -prices[0];
        for(int i = 1; i < sz; i++){
          	// 获得当前资金最大值，主要是确定买入点。
          	// 如果i不是最合适的买入节点，那么会随着循环往后找最佳的节点。
            hold[i] = max(hold[i - 1], notHold[i - 1] - prices[i]);
          	// 确定卖出点，和利润。
          	// 同理
            notHold[i] = max(notHold[i - 1], hold[i - 1] + prices[i] - fee);
        }
        
        return notHold[sz - 1];
    }
};
```

这个题目感觉自己还是有点模糊，关于状态转移方程是在是总结不出来。