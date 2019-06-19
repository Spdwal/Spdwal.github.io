---
layout: post
title: "[Leetcode from zero to one] 1089"
category: 
tags: []
---

# 1089 - Duplicate Zeros

Given a fixed length array `arr` of integers, duplicate each occurrence of zero, shifting the remaining elements to the right.

Note that elements beyond the length of the original array are not written.

Do the above modifications to the input array **in place**, do not return anything from your function.

 

**Example 1:**

```
Input: [1,0,2,3,0,4,5,0]
Output: null
Explanation: After calling your function, the input array is modified to: [1,0,0,2,3,0,0,4]
```

**Example 2:**

```
Input: [1,2,3]
Output: null
Explanation: After calling your function, the input array is modified to: [1,2,3]
```

 

**Note:**

1. `1 <= arr.length <= 10000`
2. `0 <= arr[i] <= 9`

```c++
class Solution {
public:
    void duplicateZeros(vector<int>& arr) {
        int cnt = count(arr.begin(), arr.end(), 0);
        int sz = arr.size();
        int j = cnt + sz;
      	// 先将多出来的数据给舍去，直到j到了sz的范围之内。
        for(int i = sz - 1; i >= 0; --i){
            if(--j < sz){
                arr[j] = arr[i];
            }
          	// 如果 arr[i] != 0, 那么 && 后面的表达式不会计算，等于是此循环i， j 都往后走了一步。 否则 j 往后走两步。也就是空出来一个0的位置。
            if(arr[i] == 0 && --j < sz){
                arr[j] = 0;
            }
        }
    }
};
```

