---
layout: post
title: "[Leetcode from zero to one] 621"
category: 
tags: []
---

# 621 - Task Scheduler

Given a char array representing tasks CPU need to do. It contains capital letters A to Z where different letters represent different tasks. Tasks could be done without original order. Each task could be done in one interval. For each interval, CPU could finish one task or just be idle.

However, there is a non-negative cooling interval **n** that means between two **same tasks**, there must be at least n intervals that CPU are doing different tasks or just be idle.

You need to return the **least** number of intervals the CPU will take to finish all the given tasks.

 

**Example:**

```
Input: tasks = ["A","A","A","B","B","B"], n = 2
Output: 8
Explanation: A -> B -> idle -> A -> B -> idle -> A -> B.
```

 

**Note:**

1. The number of tasks is in the range [1, 10000].
2. The integer n is in the range [0, 100].

- 首先计算每个元素的出现次数。
- 设E的最大频率为M
- 我们可以安排E的第一次M-1次发生，每次E之后将在E的连续时间表之间至少有N个CPU周期
- 调度M-1次出现后的总CPU周期E =（M-1）*（N + 1）// 1来自E本身的CPU周期
- 现在安排最后一轮任务。我们将需要最后一次出现E的至少1个CPU周期。如果有多个具有频率M的任务，则它们都需要1个以上的周期。
- 运行频率字典，对于频率== M的每个元素，将1个周期添加到结果中。
- 如果我们有比上面计算的最大插槽数更多的任务，我们将返回任务数组的长度，因为我们至少需要那么多CPU周期。

```c++
class Solution {
public:
    int leastInterval(vector<char>& tasks, int n) {
        unordered_map<char, int> imap;
        int cnt = 0;
        for(auto ele : tasks){
            imap[ele]++;
            cnt = max(cnt, imap[ele]);
        }
        
        int res = (n + 1) * (cnt - 1);
        
        for(auto ele : imap){
            if(ele.second == cnt){
                res++;
            }
        }
        
        return max((int)tasks.size(), res);
    }
};
```

