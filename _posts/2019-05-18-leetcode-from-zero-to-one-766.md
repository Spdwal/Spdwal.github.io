---
layout: post
title: "[Leetcode from zero to one] 766"
category: 
tags: []
---

# 766 - Toeplitz Matrix

A matrix is *Toeplitz* if every diagonal from top-left to bottom-right has the same element.

Now given an `M x N` matrix, return `True` if and only if the matrix is *Toeplitz*.
 

**Example 1:**

```
Input:
matrix = [
  [1,2,3,4],
  [5,1,2,3],
  [9,5,1,2]
]
Output: True
Explanation:
In the above grid, the diagonals are:
"[9]", "[5, 5]", "[1, 1, 1]", "[2, 2, 2]", "[3, 3]", "[4]".
In each diagonal all elements are the same, so the answer is True.
```

**Example 2:**

```
Input:
matrix = [
  [1,2],
  [2,2]
]
Output: False
Explanation:
The diagonal "[1, 2]" has different elements.
```



思路很简单，一个一个比较即可，注意边界问题。

```c++
class Solution {
public:
    bool isToeplitzMatrix(vector<vector<int>>& matrix) {
        int rowSize = matrix.size();
        int colSize = matrix[0].size();
        
        for(int row = 0; row < rowSize - 1; row++){
            for(int col = 0; col < colSize - 1; col++){
                if(matrix[row][col] != matrix[row+1][col+1]){
                    return false;
                }
            }
        }
        
        return true;
    }
};
```



