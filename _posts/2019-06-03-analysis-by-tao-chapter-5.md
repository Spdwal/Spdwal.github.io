---
layout: post
title: "Analysis by Tao Chapter 5"
category: 
tags: []
---

## 柯西序列

**5.1.1**

**证明：**

根据柯西序列的定义，设 $N \in \mathbb{N+}, j, k \geq N, d(a_j, a_k) \leq \varepsilon$ 现在取 $N = 1$ 那么可以将柯西数列划分为两个部分：

一个有限序列 $(a)_{n = 1}^{N}$ 此序列是有界的，不妨设他有上界 $x$ 。

一个无限序列 $(a)_{n = N}^{\infty}$ 是 $1-$ 稳定的。那么$ \forall n, n \geq N, d(a_N, a_n) \leq 1, a_n \leq a_N + 1$ 

那么这个序列 $\forall n \in N, a_n \leq max(x, a_N + 1)$ 它是有界的。得证。

下界同理。



