---
layout: post
title: "[Leetcode from zero to one] 999"
category: 
tags: []
---

# 999 - Available Captures for Rook

On an 8 x 8 chessboard, there is one white rook.  There also may be empty squares, white bishops, and black pawns.  These are given as characters 'R', '.', 'B', and 'p' respectively. Uppercase characters represent white pieces, and lowercase characters represent black pieces.

The rook moves as in the rules of Chess: it chooses one of four cardinal directions (north, east, west, and south), then moves in that direction until it chooses to stop, reaches the edge of the board, or captures an opposite colored pawn by moving to the same square it occupies.  Also, rooks cannot move into the same square as other friendly bishops.

Return the number of pawns the rook can capture in one move.



这个题目最大的坑，就是看不懂题目- -b。。。挺绕的，归根究底就是看在一步以内可以吃到几个棋子，而不是在一步内最多吃到多少个棋子。



```c++
class Solution {
public:
    int cap(vector<vector<char>>& b, int x, int y, int dx, int dy) {
        while (x >= 0 && x < b.size() && y >= 0 && y < b[x].size() && b[x][y] != 'B') {
            if (b[x][y] == 'p') return 1;
            x += dx, y += dy;
        }
    return 0;
    }
    int numRookCaptures(vector<vector<char>>& b) {
    for (auto i = 0; i < b.size(); ++i)
        for (auto j = 0; j < b[i].size(); ++j)
            if (b[i][j] == 'R') return cap(b,i,j,0,1)+cap(b,i,j,0,-1)+cap(b,i,j,1,0)+cap(b,i,j,-1,0);
        return 0;
    }
};
```

