---
layout: post
title: "[Leetcode from zero to one] 1053"
category: 
tags: []
---

# 1053 - Previous Permutation With One Swap

Given an array `A` of positive integers (not necessarily distinct), return the lexicographically largest permutation that is smaller than `A`, that can be **made with one swap** (A *swap* exchanges the positions of two numbers `A[i]` and `A[j]`).  If it cannot be done, then return the same array.

 

**Example 1:**

```
Input: [3,2,1]
Output: [3,1,2]
Explanation: Swapping 2 and 1.
```

**Example 2:**

```
Input: [1,1,5]
Output: [1,1,5]
Explanation: This is already the smallest permutation.
```

**Example 3:**

```
Input: [1,9,4,6,7]
Output: [1,7,4,6,9]
Explanation: Swapping 9 and 7.
```

**Example 4:**

```
Input: [3,1,1,3]
Output: [1,3,1,3]
Explanation: Swapping 1 and 3.
```

 

**Note:**

1. `1 <= A.length <= 10000`
2. `1 <= A[i] <= 10000`

刚开始一直看不懂题目，排列之间怎么做比较，后来问了一下群里的水友才看懂，下面举例子说明。

`[1,2,3]`的全排列是 `[3,2,1] [3,1,2] [1,2,3] [1,3,2] [2,1,3] [2,3,1]` 然后将他们按照字典序进行排列。

`[1,2,3] [1,3,2] [2,1,3] [2,3,1] [3,1,2] [3,2,1]` 排在前面的就是比较小的排列，排在后面的就是比较大的排列。

具体的做法就是从右边开始，先找第一个有上升趋势的数字，然后再次从后往前找，找到第一个比当前定的数字小的数字，当然也要考虑这个数字是不是有相同的数字，如果有，继续往左找然后两者交换。

```c++
class Solution {
public:
    vector<int> prevPermOpt1(vector<int>& A) {
        int n = A.size(), left = n - 2, right = n - 1;
        while (left >= 0  && A[left] <= A[left + 1]) left--;
        if (left < 0) return A;
        while (A[left] <= A[right]) right--;
        while (A[right - 1] == A[right]) right--;
        swap(A[left], A[right]);
        return A;
    }
};
```

