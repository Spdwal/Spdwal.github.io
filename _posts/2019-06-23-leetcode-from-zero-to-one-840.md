---
layout: post
title: "[Leetcode from zero to one] 840"
category: 
tags: []
---

# 840 - Magic Squares In Grid

A 3 x 3 magic square is a 3 x 3 grid filled with distinct numbers **from 1 to 9** such that each row, column, and both diagonals all have the same sum.

Given an `grid` of integers, how many 3 x 3 "magic square" subgrids are there?  (Each subgrid is contiguous).

 

**Example 1:**

```
Input: [[4,3,8,4],
        [9,5,1,9],
        [2,7,6,2]]
Output: 1
Explanation: 
The following subgrid is a 3 x 3 magic square:
438
951
276

while this one is not:
384
519
762

In total, there is only one magic square inside the given grid.
```

**Note:**

1. `1 <= grid.length <= 10`
2. `1 <= grid[0].length <= 10`
3. `0 <= grid[i][j] <= 15`



蠢办法，一个一个试就完了。

```c++
class Solution {
public:
    
    bool chk(vector<vector<int>>& grid, int m, int n) {
        
        if (m + 3 > grid.size())
            return false;
        
        if (n + 3 > grid[m].size())
            return false;
        
        vector<bool> v (10, false);
        
        for (int i = m; i < m + 3; i++) {
            for (int j = n; j < n + 3; j++) {
                v[grid[i][j]] = true;
            }
        }
        
        int sum = grid[m][n] + grid[m+1][n+1] + grid[m+2][n+2];
        
        if (sum != grid[m][n+2] + grid[m+1][n+1] + grid[m+2][n])
            return false;
        
        
        for (int i = m; i < m + 3; i++) {
            if (grid[i][n] + grid[i][n+1] + grid[i][n+2] != sum)
                return false;
        }
        
        for (int i = n; i < n + 3; i++) {
            if (grid[m][i] + grid[m+1][i] + grid[m+2][i] != sum)
                return false;
        }
        
        for (int i = 1; i <= 9; i++) {
            if (!v[i]) {
                return false;
            }
        }
        
        return true;
        
    } 
    
    int numMagicSquaresInside(vector<vector<int>>& grid) {
        
        int r = grid.size();
        int c = grid[0].size();
        
        int cnt = 0;
        
        for (int i = 0; i < r; i++) {
            for (int j = 0; j < c; j++) {
                if (chk(grid, i, j))
                    cnt++;
            }
        }
        
        return cnt;
    }
};
```

