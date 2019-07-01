---
layout: post
title: "[Leetcode from zero to one] 64"
category: 
tags: []
---

# 64 - Minimum Path Sum

Given a *m* x *n* grid filled with non-negative numbers, find a path from top left to bottom right which *minimizes* the sum of all numbers along its path.

**Note:** You can only move either down or right at any point in time.

**Example:**

```
Input:
[
  [1,3,1],
  [1,5,1],
  [4,2,1]
]
Output: 7
Explanation: Because the path 1→3→1→1→1 minimizes the sum.
```

很简单的动态规划，由于输入不是const的，甚至可以直接用数组本身作为dp数组。

```c++
class Solution {
public:
    int minPathSum(vector<vector<int>>& grid) {
        int m = grid.size();
        int n = grid[0].size();
        for(int i = 0; i < m; ++i){
            for(int j = 0; j < n; ++j){
                if(i == 0 && j != 0){
                    grid[i][j] += grid[i][j - 1];
                }else if(i != 0 && j == 0){
                    grid[i][j] += grid[i - 1][j];
                }else if(i == 0 && j == 0){
                    continue;
                }else{
                    grid[i][j] += min(grid[i - 1][j], grid[i][j - 1]);
                }
            }
        }
        
        return grid[m - 1][n - 1];
    }
};
```

