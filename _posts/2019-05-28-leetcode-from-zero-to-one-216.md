---
layout: post
title: "[Leetcode from zero to one]  216"
category: 
tags: []
---

# 216 - Combination Sum III

Find all possible combinations of ***k*** numbers that add up to a number ***n***, given that only numbers from 1 to 9 can be used and each combination should be a unique set of numbers.

**Note:**

- All numbers will be positive integers.
- The solution set must not contain duplicate combinations.

**Example 1:**

```
Input: k = 3, n = 7
Output: [[1,2,4]]
```

**Example 2:**

```
Input: k = 3, n = 9
Output: [[1,2,6], [1,3,5], [2,3,4]]
```

其实这归根究底，是一个DFS问题。。

可以用递归来做：

```c++
class Solution {
public:
    void combinationSum(vector<vector<int>> &res, vector<int> sol, int k, int n){
      	// 如果数组大小合适，切刚好n == 0，res加入一个数组。
        if(sol.size() == k && n ==0){
            res.push_back(sol);
        }
        if(sol.size() < k){
          	// i 要大于 sol的最后一个值。
            for(int i = sol.empty() ? 1 : sol.back() + 1; i <= 9; ++i){
								// 错误。break
                if(n - i < 0){
                    break;
                }
                sol.push_back(i);
                combinationSum(res, sol, k, n - i);
                sol.pop_back();
            }
        }
    }
    vector<vector<int>> combinationSum3(int k, int n) {
        vector<vector<int>> res;
        vector<int> sol;
        combinationSum(res, sol, k, n);
        return res;
    }
};
```

