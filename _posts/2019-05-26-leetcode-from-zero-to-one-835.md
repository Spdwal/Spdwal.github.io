---
layout: post
title: "[Leetcode from zero to one] 835"
category: 
tags: []
---

# 835 - Image Overlap

Two images `A` and `B` are given, represented as binary, square matrices of the same size.  (A binary matrix has only 0s and 1s as values.)

We translate one image however we choose (sliding it left, right, up, or down any number of units), and place it on top of the other image.  After, the *overlap* of this translation is the number of positions that have a 1 in both images.

(Note also that a translation does **not** include any kind of rotation.)

What is the largest possible overlap?

**Example 1:**

```
Input: A = [[1,1,0],
            [0,1,0],
            [0,1,0]]
       B = [[0,0,0],
            [0,1,1],
            [0,0,1]]
Output: 3
Explanation: We slide A to right by 1 unit and down by 1 unit.
```

**Notes:** 

1. `1 <= A.length = A[0].length = B.length = B[0].length <= 30`
2. `0 <= A[i][j], B[i][j] <= 1`

这道题目有点难度- -b。。。抄的discuss然后看懂的。

```c++
class Solution {
public:
    int largestOverlap(vector<vector<int>>& A, vector<vector<int>>& B) {
        vector<int> LA, LB;
        int N = A.size();
        unordered_map<int, int> count;
      	// 这里使用100来做基数，例如A[5][14] 便是 LA 中的0514值
        // 此处便是存储在那个位置它的值为1。
        for (int i = 0; i < N * N; ++i) if (A[i / N][i % N] == 1) LA.push_back(i / N * 100 + i % N);
        for (int i = 0; i < N * N; ++i) if (B[i / N][i % N] == 1) LB.push_back(i / N * 100 + i % N);
      	// 计算出移动某个数值的时候，有多少个重合的地方。
        for (int i: LA) for (int j: LB) count[i - j]++;
        int res = 0;
      	// 找到重合中的最大值。
        for (auto it: count) res = max(res, it.second);
        return res;
    }
};
```

