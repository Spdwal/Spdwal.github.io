---
layout: post
title: "[Leetcode from zero to one] 217"
category: 
tags: []
---

# 217 - Contains Duplicate

Given an array of integers, find if the array contains any duplicates.

Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

**Example 1:**

```
Input: [1,2,3,1]
Output: true
```

**Example 2:**

```
Input: [1,2,3,4]
Output: false
```

**Example 3:**

```
Input: [1,1,1,3,3,4,3,2,4,2]
Output: true
```

```c++
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        unordered_map<int, bool> imap;
        for(auto num : nums){
            if(imap.find(num) != imap.end()){
                return true;
            }else{
                imap[num] = true;
            }
        }
        return false;
    }
};
```

很简单，用map就能做，但是空间复杂度略高。

可以使用sort来做。

```c++
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        for (int i=0; i<int(nums.size())-1; i++) {
            if (nums[i]==nums[i+1])
                return true;
        }
        return false;    
    }
};
```

诡异的是，它的时间复杂度甚至比之前用unordered_map还好。。。

还有一个1line的解答。

```c++
class Solution {
  public:
    bool containsDuplicate(vector<int>& nums) {
        return set<int>(nums.begin(), nums.end()).size() < nums.size();
    }
};
```

