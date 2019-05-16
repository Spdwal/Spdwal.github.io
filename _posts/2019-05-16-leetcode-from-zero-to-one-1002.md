---
layout: post
title: "[Leetcode from zero to one] 1002"
category: 
tags: []
---

# 1002 - Find Common Characters

Given an array `A` of strings made only from lowercase letters, return a list of all characters that show up in all strings within the list **(including duplicates)**.  For example, if a character occurs 3 times in all strings but not 4 times, you need to include that character three times in the final answer.

You may return the answer in any order.

 

**Example 1:**

```
Input: ["bella","label","roller"]
Output: ["e","l","l"]
```

**Example 2:**

```
Input: ["cool","lock","cook"]
Output: ["c","o"]
```

 

**Note:**

1. `1 <= A.length <= 100`
2. `1 <= A[i].length <= 100`
3. `A[i][j]` is a lowercase letter

本来想用暴力解法，但是用脑子一想就觉得会超时，看过discuss之后，发现是利用一个临时变量来存储每一个字母的数量，然后依次取两辆字符串之间的最小值，只要不为0，就表示它在多个字符串中出现过。

```c++
class Solution {
public:
    vector<string> commonChars(vector<string>& A) {
        vector<int> count(26, INT_MAX);
        for(auto str : A){
            vector<int> countTemp(26, 0);
            for(auto ch : str){
                countTemp[ch - 'a']++;
            }
            for(int i = 0; i < 26; ++i){
                count[i] = min(count[i], countTemp[i]);
            }
        }
        
        vector<string> ret;
        for(int i = 0; i < 26; ++i){
            for(int j = 0; j < count[i]; ++j){
                ret.push_back(string(1, i + 'a'));
            }
        }
        
        return ret;
    }
};
```

