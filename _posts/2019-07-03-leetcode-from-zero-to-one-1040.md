---
layout: post
title: "[Leetcode from zero to one] 1040"
category: 
tags: []
---

# 1040 - Moving Stones Until Consecutive II

On an **infinite** number line, the position of the i-th stone is given by `stones[i]`.  Call a stone an *endpoint stone* if it has the smallest or largest position.

Each turn, you pick up an endpoint stone and move it to an unoccupied position so that it is no longer an endpoint stone.

In particular, if the stones are at say, `stones = [1,2,5]`, you **cannot** move the endpoint stone at position 5, since moving it to any position (such as 0, or 3) will still keep that stone as an endpoint stone.

The game ends when you cannot make any more moves, ie. the stones are in consecutive positions.

When the game ends, what is the minimum and maximum number of moves that you could have made?  Return the answer as an length 2 array: `answer = [minimum_moves, maximum_moves]`

 

**Example 1:**

```
Input: [7,4,9]
Output: [1,2]
Explanation: 
We can move 4 -> 8 for one move to finish the game.
Or, we can move 9 -> 5, 4 -> 6 for two moves to finish the game.
```

**Example 2:**

```
Input: [6,5,4,3,10]
Output: [2,3]
We can move 3 -> 8 then 10 -> 7 to finish the game.
Or, we can move 3 -> 7, 4 -> 8, 5 -> 9 to finish the game.
Notice we cannot move 10 -> 2 to finish the game, because that would be an illegal move.
```

**Example 3:**

```
Input: [100,101,104,102,103]
Output: [0,0]
```

 

**Note:**

1. `3 <= stones.length <= 10^4`
2. `1 <= stones[i] <= 10^9`
3. `stones[i]` have distinct values.



这道题目是真的挺难的，看答案都看的懵逼了，很久都反应不过来到底是为了啥。

这道题将它分成两个部分来看，一个部分是求最大移动次数，一个部分是求最小移动次数。

最大移动次数，是我们尝试将石头全部移动到最右边或者最左边，然后在这两个次数中取最大即可。

以移动到最右边为例。首先因为不能从endpoint移动到 endpoint 来刷次数，那么stones[0] 到 

最左端的时候每次移动1次，直到移动到`stone[n - 1] - n + 1`

总共的移动次数就是`stones[n - 1] - n + 1 - (stones[1]) + 1`

此处的最后一个+1为 `stones[0] -> stones[1] + 1` 位置时的移动次数。

至于low的话，就是一个稍微简单一点的滑动窗口。可以看代码来了解。

```c++
class Solution {
public:
    vector<int> numMovesStonesII(vector<int>& stones) {
        sort(stones.begin(), stones.end());
        int i = 0;
        int n = stones.size();
        int low = n;
      	// 边界条件，节省运行时间用。
        if(n < 3 || stones[n-1]-stones[0] == n-1){
            return {0, 0};
        }
        // 求出最大的移动次数。
        int high = max(stones[n - 1] - stones[1] - n + 2, stones[n - 2] - stones[0] - n + 2);
        for(int j = 0; j < n; ++j){
            while(stones[j] - stones[i] >= n) ++i;
            if (j - i + 1 == n - 1 && stones[j] - stones[i] == n - 2)
                low = min(low, 2);
            else
                low = min(low, n - (j - i + 1));
        }
        
        return {low, high};
    }
};
```

