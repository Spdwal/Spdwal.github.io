---
layout: post
title: "[Leetcode from zero to one] 78"
category: 
tags: []
---

# 78 - Subsets

Given a set of **distinct** integers, *nums*, return all possible subsets (the power set).

**Note:** The solution set must not contain duplicate subsets.

**Example:**

```
Input: nums = [1,2,3]
Output:
[
  [3],
  [1],
  [2],
  [1,2,3],
  [1,3],
  [2,3],
  [1,2],
  []
]
```

这道题看起来挺简单。。。写起来还真的有点难度。。

```c++
class Solution {
public:
    vector<vector<int>> subsets(vector<int>& nums) {
        vector<vector<int>> res{{}};
        
        for(auto num : nums){
            int n = res.size();
            for(int i = 0; i < n; ++i){
                res.push_back(res[i]);
                res.back().push_back(num);
            }
        }
        
        return res;
    }
};
```

首先构造数组res [[]]。

然后第一个循环运行时，n = 1, res = [[], []].back().push_back(1) = [[], [1]]

第二个循环运行时，n = 2, res = [[], [1]].push_back([1]) = [[], [1], [1]]

res = [[], [1], [1]].back().push_back(2) = [[], [1], [1,2]]

以此类推。