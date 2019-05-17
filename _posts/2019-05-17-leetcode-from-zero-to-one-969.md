---
layout: post
title: "[Leetcode from zero to one] 969"
category: 
tags: []
---

# 969 - Pancake Sorting

Given an array `A`, we can perform a *pancake flip*: We choose some positive integer `**k** <= A.length`, then reverse the order of the first **k** elements of `A`.  We want to perform zero or more pancake flips (doing them one after another in succession) to sort the array `A`.

Return the k-values corresponding to a sequence of pancake flips that sort `A`.  Any valid answer that sorts the array within `10 * A.length` flips will be judged as correct.

 

**Example 1:**

```
Input: [3,2,4,1]
Output: [4,2,4,3]
Explanation: 
We perform 4 pancake flips, with k values 4, 2, 4, and 3.
Starting state: A = [3, 2, 4, 1]
After 1st flip (k=4): A = [1, 4, 2, 3]
After 2nd flip (k=2): A = [4, 1, 2, 3]
After 3rd flip (k=4): A = [3, 2, 1, 4]
After 4th flip (k=3): A = [1, 2, 3, 4], which is sorted. 
```

**Example 2:**

```
Input: [1,2,3]
Output: []
Explanation: The input is already sorted, so there is no need to flip anything.
Note that other answers, such as [3, 3], would also be accepted.
```

 

**Note:**

1. `1 <= A.length <= 100`
2. `A[i]` is a permutation of `[1, 2, ..., A.length]`

这个煎饼排序，有一个要求就是本身是一个不重合的自然数的集合，要不然所需要的时间复杂度要再上一个数量级。

原理就是先找到[0…k]范围内最大的数字的位置 i ，然后将[0…i]翻转，此时最大的数字在A[0]处，然后再翻转[0…k],此时最大的数字就在了A[k]处，然后k—,重复以上步骤。

```c++
class Solution {
public:
    vector<int> pancakeSort(vector<int>& A) {
        vector<int> ret;
        int j;
        for(int i = A.size(); i > 0; i--){
            for(j = 0; A[j] != i; j++);
            reverse(A.begin(), A.begin() + j + 1);
            ret.push_back(j + 1);
            reverse(A.begin(), A.begin() + i);
            ret.push_back(i);
        }
        
        return ret;
    }
};
```

