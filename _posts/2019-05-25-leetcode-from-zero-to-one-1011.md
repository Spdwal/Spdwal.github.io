---
layout: post
title: "[Leetcode from zero to one] 1011"
category: 
tags: []
---

# 1011 - Capacity To Ship Packages Within D Days

A conveyor belt has packages that must be shipped from one port to another within `D` days.

The `i`-th package on the conveyor belt has a weight of `weights[i]`.  Each day, we load the ship with packages on the conveyor belt (in the order given by `weights`). We may not load more weight than the maximum weight capacity of the ship.

Return the least weight capacity of the ship that will result in all the packages on the conveyor belt being shipped within `D` days.

 

**Example 1:**

```
Input: weights = [1,2,3,4,5,6,7,8,9,10], D = 5
Output: 15
Explanation: 
A ship capacity of 15 is the minimum to ship all the packages in 5 days like this:
1st day: 1, 2, 3, 4, 5
2nd day: 6, 7
3rd day: 8
4th day: 9
5th day: 10

Note that the cargo must be shipped in the order given, so using a ship of capacity 14 and splitting the packages into parts like (2, 3, 4, 5), (1, 6, 7), (8), (9), (10) is not allowed. 
```

**Example 2:**

```
Input: weights = [3,2,2,4,1,4], D = 3
Output: 6
Explanation: 
A ship capacity of 6 is the minimum to ship all the packages in 3 days like this:
1st day: 3, 2
2nd day: 2, 4
3rd day: 1, 4
```

**Example 3:**

```
Input: weights = [1,2,3,1,1], D = 4
Output: 3
Explanation: 
1st day: 1
2nd day: 2
3rd day: 3
4th day: 1, 1
```

 

**Note:**

1. `1 <= D <= weights.length <= 50000`
2. `1 <= weights[i] <= 500`

这道题归根究底还是用的暴力方法做的，只是用了二分搜索来稍微减少了一点时间复杂度。

最终的时间复杂度为 O(nlogn)

```c++
class Solution {
private:
  	// 计算在当前的cap下需要多少天才可以吧货物运完。
    int countDays(vector<int>& weight, int totalCap, int currentCap = 0, int res = 1){
        for(auto ws : weight){
            currentCap += ws;
            if(currentCap > totalCap){
                res++;
                currentCap = ws;
            }
        }
        return res;
    }
public:
    int shipWithinDays(vector<int>& weights, int D) {
      	// 最大值不会超过所有数字之和。
        int Max = accumulate(weights.begin(), weights.end(), 0);
      	// 最小值不会小于 Max/D 和 数组中所有数字中的最大者。
        int Min = max(Max / D, *max_element(weights.begin(), weights.end()));
        while(Min < Max){
            int Middle = (Max + Min) / 2;
          	// 如果计算出的日子数太少了的话，就表示Cap这个值偏大
            // 继续进行二分搜索
            if(countDays(weights, Middle) <= D){
                Max = Middle;
            }else{
                Min = Middle + 1;
            }
        }
        
        return Min;
    }

};
```

