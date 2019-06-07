---
layout: post
title: "[Leetcode from zero to one] 1051"
category: 
tags: []
---

# 1051 - Height Checker

Students are asked to stand in non-decreasing order of heights for an annual photo.

Return the minimum number of students not standing in the right positions.  (This is the number of students that must move in order for all students to be standing in non-decreasing order of height.)

 

**Example 1:**

```
Input: [1,1,4,2,1,3]
Output: 3
Explanation: 
Students with heights 4, 3 and the last 1 are not standing in the right positions.
```

 

**Note:**

1. `1 <= heights.length <= 100`
2. `1 <= heights[i] <= 100`

题目有点懵逼，例子有点懵逼。

```c++
class Solution {
public:
    int heightChecker(vector<int>& heights) {
        vector<int> tmp (heights);
        sort(tmp.begin(), tmp.end());
        int res = 0;
        for(int i = 0; i < tmp.size(); ++ i){
            if(tmp[i] != heights[i]){
                res++;
            }
        }
        
        return res;
    }
};
```

