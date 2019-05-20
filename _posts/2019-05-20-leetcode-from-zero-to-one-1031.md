---
layout: post
title: "[Leetcode from zero to one] 1031"
category: 
tags: []
---

# 1031 - Maximum Sum of Two Non-Overlapping Subarrays

Given an array `A` of non-negative integers, return the maximum sum of elements in two non-overlapping (contiguous) subarrays, which have lengths `L` and `M`.  (For clarification, the `L`-length subarray could occur before or after the `M`-length subarray.)

Formally, return the largest `V` for which `V = (A[i] + A[i+1] + ... + A[i+L-1]) + (A[j] + A[j+1] + ... + A[j+M-1])` and either:

- `0 <= i < i + L - 1 < j < j + M - 1 < A.length`, **or**
- `0 <= j < j + M - 1 < i < i + L - 1 < A.length`.

 



**Example 1:**

```
Input: A = [0,6,5,2,2,5,1,9,4], L = 1, M = 2
Output: 20
Explanation: One choice of subarrays is [9] with length 1, and [6,5] with length 2.
```

**Example 2:**

```
Input: A = [3,8,1,3,2,1,8,9,0], L = 3, M = 2
Output: 29
Explanation: One choice of subarrays is [3,8,1] with length 3, and [8,9] with length 2.
```

**Example 3:**

```
Input: A = [2,1,5,6,0,9,5,0,3,8], L = 4, M = 3
Output: 31
Explanation: One choice of subarrays is [5,6,0,9] with length 4, and [3,8] with length 3.
```

 

**Note:**

1. `L >= 1`
2. `M >= 1`
3. `L + M <= A.length <= 1000`
4. `0 <= A[i] <= 1000`

这道题写起来有点难。。。。看了解答看了挺久才懂的。具体的解答写在代码的注释里。

```c++
class Solution {
public:
    int maxSumTwoNoOverlap(vector<int>& A, int L, int M) {
      	// 将sum保存在数组里面。
        for (int i = 1; i < A.size(); ++i)
            A[i] += A[i - 1];
      	// 先将最左边的 L + M长度的数组元素和作为result。
      	// Lmax是最左边的L个元素的sum
      	// Mmax是最左边的M个元素的sum
        int res = A[L + M - 1], Lmax = A[L - 1], Mmax = A[M - 1];
      	// 对答案进行不停的更新，Lmax随着i往右走，不停的更新，同理Mmax
        for (int i = L + M; i < A.size(); ++i) {
            Lmax = max(Lmax, A[i - M] - A[i - L - M]);
            Mmax = max(Mmax, A[i - L] - A[i - L - M]);
          	// 感觉最最卧槽的一段，因为无论是Lmax还是Mmax都没有和i-M, i-L重合
          	// 想了很久也没想通，最后看出来了，Lmax, Mmax一直在更新，而[L],[M]也一直在跟新，而每次只取最大值。
            res = max(res, max(Lmax + A[i] - A[i - M], Mmax + A[i] - A[i - L]));
        }
        return res;
    }
};
```

