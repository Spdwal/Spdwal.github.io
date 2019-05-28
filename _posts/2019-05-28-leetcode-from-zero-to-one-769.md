---
layout: post
title: "[Leetcode from zero to one] 769"
category: 
tags: []
---

# 769 - Max Chunks To Make Sorted

Given an array `arr` that is a permutation of `[0, 1, ..., arr.length - 1]`, we split the array into some number of "chunks" (partitions), and individually sort each chunk.  After concatenating them, the result equals the sorted array.

What is the most number of chunks we could have made?

**Example 1:**

```
Input: arr = [4,3,2,1,0]
Output: 1
Explanation:
Splitting into two or more chunks will not return the required result.
For example, splitting into [4, 3], [2, 1, 0] will result in [3, 4, 0, 1, 2], which isn't sorted.
```

**Example 2:**

```
Input: arr = [1,0,2,3,4]
Output: 4
Explanation:
We can split into two chunks, such as [1, 0], [2, 3, 4].
However, splitting into [1, 0], [2], [3], [4] is the highest number of chunks possible.
```

**Note:**

- `arr` will have length in range `[1, 10]`.
- `arr[i]` will be a permutation of `[0, 1, ..., arr.length - 1]`.



这道题首先有一个要点，就是题目中明确表示了，它是有解的，离开了这个条件，解题的复杂度就要更上一层楼。

不然如果出现 [4,0,1,2,3]这样的数组，怎么样去分割他，都是无解的。

既然明确了这个条件，那么解题思路就是，如果在某个分割中，如果此分割中的最大值，等于数组的index，那么表示此分割已结束，res++；

 ```c++
class Solution {
public:
    int maxChunksToSorted(vector<int>& arr) {
        int res = 0;
        int max_i = 0;
        for(int i = 0; i < arr.size(); ++i){
            max_i = max(arr[i], max_i);
            if(max_i == i){
                res++;
            }
        }
        
        return res;
    }
};
 ```

