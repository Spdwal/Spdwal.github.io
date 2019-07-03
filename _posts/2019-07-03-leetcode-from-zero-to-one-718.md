---
layout: post
title: "[Leetcode from zero to one] 718"
category: 
tags: []
---

# 718 - Maximum Length of Repeated Subarray

Given two integer arrays `A` and `B`, return the maximum length of an subarray that appears in both arrays.

**Example 1:**

```
Input:
A: [1,2,3,2,1]
B: [3,2,1,4,7]
Output: 3
Explanation: 
The repeated subarray with maximum length is [3, 2, 1].
```

 

**Note:**

1. 1 <= len(A), len(B) <= 1000
2. 0 <= A[i], B[i] < 100

一道普通的dp题，可以通过优化将空间复杂度简化到O(m)。

```c++
class Solution {
public:
    int findLength(vector<int>& A, vector<int>& B) {
        int m = A.size();
        int n = B.size();
        if(m == 0 || n == 0){
            return 0;
        }
        int res = 0;
        vector<int> dp(m + 1);
        for(int i = m - 1; i >= 0; --i){
            for(int j = 0; j < n; ++j){
                res = max(res, dp[j] = A[i] == B[j] ? 1 + dp[j + 1] : 0);
            }
        }
        
        return res;
    }
};
```

