---
layout: post
title: "[Leetcode from zero to one] 1014"
category: 
tags: []
---

# 1014 - Best Sightseeing Pair

Given an array `A` of positive integers, `A[i]` represents the value of the `i`-th sightseeing spot, and two sightseeing spots `i` and `j` have distance `j - i` between them.

The *score* of a pair (`i < j`) of sightseeing spots is (`A[i] + A[j] + i - j)` : the sum of the values of the sightseeing spots, **minus** the distance between them.

Return the maximum score of a pair of sightseeing spots.

 

**Example 1:**

```
Input: [8,1,5,2,6]
Output: 11
Explanation: i = 0, j = 2, A[i] + A[j] + i - j = 8 + 5 + 0 - 2 = 11
```

 

**Note:**

1. `2 <= A.length <= 50000`
2. `1 <= A[i] <= 1000`

可以吧方程转换为 `(A[i] + i) + (A[j] - j)` 

注意此时索引要从1开始，因为`prev_index`已经是0了，不能重复计算这个。

```c++
class Solution {
public:
    int maxScoreSightseeingPair(vector<int>& A) {
        int res = 0;
        int prev_index = 0;
        for(int i = 1; i < A.size(); ++i){
            res = max(res, A[i] - i + A[prev_index] + prev_index);
            if(A[i] + i > A[prev_index] + prev_index){
                prev_index = i;
            }
        }
        return res;
    }
};
```

