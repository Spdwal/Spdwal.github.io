---
layout: post
title: "[Leetcode from zero to one] 39"
category: 
tags: []
---

# 39 - Combination Sum

Given a **set** of candidate numbers (`candidates`) **(without duplicates)** and a target number (`target`), find all unique combinations in `candidates` where the candidate numbers sums to `target`.

The **same** repeated number may be chosen from `candidates` unlimited number of times.

**Note:**

- All numbers (including `target`) will be positive integers.
- The solution set must not contain duplicate combinations.

**Example 1:**

```
Input: candidates = [2,3,6,7], target = 7,
A solution set is:
[
  [7],
  [2,2,3]
]
```

**Example 2:**

```
Input: candidates = [2,3,5], target = 8,
A solution set is:
[
  [2,2,2,2],
  [2,3,3],
  [3,5]
]
```

使用递归来做，之前做过一道差不多的，算是经典题型了。

```c++
class Solution {
public:
    vector<vector<int>> combinationSum(vector<int>& candidates, int target) {
        sort(candidates.begin(), candidates.end());
        vector<vector<int>> res;
        vector<int> row;
        combinationSum(candidates, row, res, target, 0);
        return res;
    }
private:
    void combinationSum(vector<int> &candidates, vector<int> &row, vector<vector<int>> &res, int target, int begin){
        if(target == 0){
            res.push_back(row);
            return;
        }
        for(int i = begin; i < candidates.size() && target >= candidates[i]; ++i){
            row.push_back(candidates[i]);
            combinationSum(candidates, row, res, target - candidates[i], i);
            row.pop_back();
        }
    }
};
```

