---
layout: post
title: "[Leetcode from zero to one] 1010"
category: 
tags: []
---

# 1010 - Pairs of Songs With Total Durations Divisible by 60

In a list of songs, the `i`-th song has a duration of `time[i]` seconds. 

Return the number of pairs of songs for which their total duration in seconds is divisible by `60`.  Formally, we want the number of indices `i < j` with `(time[i] + time[j]) % 60 == 0`.

 

**Example 1:**

```
Input: [30,20,150,100,40]
Output: 3
Explanation: Three pairs have a total duration divisible by 60:
(time[0] = 30, time[2] = 150): total duration 180
(time[1] = 20, time[3] = 100): total duration 120
(time[1] = 20, time[4] = 40): total duration 60
```

**Example 2:**

```
Input: [60,60,60]
Output: 3
Explanation: All three pairs have a total duration of 120, which is divisible by 60.
```

 

**Note:**

1. `1 <= time.length <= 60000`
2. `1 <= time[i] <= 500`

不会做，看的答案，太巧妙了。

利用m数组来存储 n % 60 的数量。

然后每次读取一个数字的时候，就会在相应的数组位置上count++。

```c++
class Solution {
public:
    int numPairsDivisibleBy60(vector<int>& time, int res = 0) {
        vector<int> m(60);
        for (auto t : time) {
            res += m[(60 - t % 60) % 60];
            ++m[t % 60];
        }
        return res;
    }
};
```

