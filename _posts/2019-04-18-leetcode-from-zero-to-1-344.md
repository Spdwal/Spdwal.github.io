---
layout: post
title: "[Leetcode from zero to 1] 344"
category: 
tags: []
---

# 344 - Reverse String

Write a function that reverses a string. The input string is given as an array of characters `char[]`.

Do not allocate extra space for another array, you must do this by **modifying the input array in-place** with O(1) extra memory.

You may assume all the characters consist of [printable ascii characters](https://en.wikipedia.org/wiki/ASCII#Printable_characters).

```c++
class Solution {
public:
    void reverseString(vector<char>& s) {
        int j = s.size() - 1;
        for(int i = 0; i <= j; i++, j--){
            std::swap(s[i], s[j]);
        }
    }
};
```

本来想用递归来做，差点把我做傻逼了，其实就是一个很简单的翻转字符串。