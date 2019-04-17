---
layout: post
title: "Analysis by Tao Chapter 2"
category: 
tags: []
---

## 习题

**2.2.1**证明加法是可结合的，对任意三个自然数 $a、b、c$，有 $(a + b) + c = a + (b + c)$成立。

__证明：__

​	先令$c = 0$，可得 $(a + b) + 0 = a + b$，$a + (b + 0) = a + b$，显然成立。

​	现假设 $(a + b) + c = a + (b + c)$，现讨论$c++$。

​	由**引理2.3.3**，可得 $ (a + b) + c++ = ((a + b) + c)++ $

​	由**引理2.2.3**，可得 $a + (b + (c++)) = a + ((b + c)++) = (a + (b + c))++$

​	由本题假设 $(a + b) + c = a + (b + c )$

​	显然得证。

​	即可归纳得得出$(a + b) + c = a + (b + c )$



**2.2.2** 证明令 $a$ 为一个正自然数，哪么恰存在一个一个自然数 $b$ 使得 $b++ = a$。

__证明：__

​	假设不存在一个自然数或者同时存在多个自然数 $ b$ 使得 $b++ = a$

​	首先假设不存在一个自然数 $b$ 使得 $b++ = a$。

   	因为 $a$ 是一个正自然数，所以 $a \neq 0$，根据自然数的定义可知：$a$若不为$0$一定为某个数的后继。命题不成立。

​	接下来假设存在不同的自然数$b、 c$，使得$b++ = a$且$c++ = a$。

​	由**公理 2.4**可得 $b = c$。与命题矛盾，所以得证。



__2.2.3__ 证明自然数的序的基本性质：令 $a、b、c$ 为任意自然数，那么：

1. 序是自反的：$a \geqslant a$。
2. 序是可传递的：如果 $a \geqslant b$ 并且 $b \geqslant c$，那么 $a \geqslant c$。
3. 序是反对称的：如果 $a \geqslant b$ 并且 $b \geqslant a$，那么 $a = b$。
4. 加法保持序不变：$a \geqslant b$，当且仅当$a + c \geqslant b + c$。
5. $a < b$，当且仅当 $a++ \leqslant b$。
6. $a < b$，当且仅当存在正自然数 $d$ 使得 $b = a + d$。

__证明：__

1. 令自然数 $m = 0$，可得 $a + m = a$，所以 $a \geqslant a$。

2. $ \because a \geqslant b, b \geqslant c, \therefore \exists m, n, \in \mathbb{N}, a  + m = b, b + n = c$

   $c = b + n = a + m + n, l := m + n, c = a + l$

   $\because m, n \in \mathbb{N},  l = m + n, \therefore l \in \mathbb{N}$

   $\because a + l = c, l \in \mathbb{N}, \therefore a \geqslant c$。得证

3. $\because a \geqslant b, b \geqslant a, \therefore \exists m,n \in \mathbb{N}, a + m = b, b + n = a$

   $\therefore a + m + n = a, \therefore m + n = 0$

   $\because m + n = 0, m, n \in \mathbb{N}, \therefore m = 0, n = 0$

   $\therefore a + 0 = b, \therefore a = b$

4. $\because a \geqslant b, \therefore a + m = b, m \in \mathbb{N}$

   $\because a + m = b, c \in \mathbb{N}, \therefore a + m + c = b + c \therefore a + c + m = b + c$

   $\because a + c + m = b + c, m \in \mathbb{N}, \therefore a + c \geqslant b + c$

5. 先证 $a < b \to a++ \leqslant b$

   $\because a < b \therefore a + m = b, m \in \mathbb{N} $

   令 $m := n + 1 ,n \in \mathbb{N},$，可得 $a + n + 1 = b, \because n++ \in \mathbb{N}$

   $a + 1 + n = b, (a++) + n = b, n \in \mathbb{N}, \therefore a++ < b$

   当 $n = 0$ 时，$a ++ = b,\therefore a++ \leqslant b$

   再证 $a++  \leqslant b \to a < b$

   $\because a ++ \leqslant b, \therefore (a++) + n = b, n \in \mathbb{N}$

   $a + (n++) = b, n \in \mathbb{N}, (n++) \in \mathbb{N}, \therefore a \leqslant  b$  

   又$\because n \in \mathbb{N}, \therefore n++ \neq 0, \therefore a + (n++) \neq b, \therefore a \leqslant b$ 得证。

6. 先证 $a < b \to \exists d \in \mathbb{N}^+, b = a + d$

   由$a < b$ 的定义，显然可得。

   再证 $\exists d \in \mathbb{N}^+, b = a + d \to a < b$

   $ b = a + d，d \in \mathbb{N}^+, \therefore b \neq a \therefore a < b$。得证。

__2.2.4__ 证明在命题__2.2.13__中注明了（为什么？）的三个命题。

1. 对所有$b$，均有$0 \leqslant b$
2. 如果$a > b$，那么有$a++ > b$
3. 如果$a = b$，那么$a++ > b $

__证明：__

1. 由定义可得：$b + 0 = b$，又$\because b \in \mathbb{N} \therefore 0 \leqslant b$ 得证。

2. $\because a > b, \therefore  a = b + n, n \in \mathbb{N}, \therefore a ++ = (b + n)++$

   $a ++ = b + (n++), \because n \in \mathbb{N}, \therefore (n++) \in \mathbb{N}, \therefore a++ > b$ 得证。

3. $\because a = b, \therefore a++ = b + 1, \because 1 \in \mathbb{N},  \therefore a++ > b$

__2.2.5__ 证明强归纳法原理：令 $m_0$ 表示一个自然数，$P(m)$ 表示与任意自然数 $m$ 有关的性质。假设对任意满足 $m \geqslant m_0$ 的自然数 $m$，均有如下内容成立：若 $P(m')$ 对任意满足 $m_0 \leqslant m' < m$ 的自然数 $m'$ 均为真，那么 $P(m)$ 也为真。（特别地，这意味着 $P(m_0)$ 为真，因为当 $ m = m_0$ 时，前提中的 $m'$ 取值为空。）于是我们能断定，对于任意满足 $m \geqslant m_0$ 的自然数 $m$，$P(m)$ 为真。

__证明：__

定义：$Q(m) := \{ (m \leqslant m' < m) \Longrightarrow  P(m') \}, S(m) := \{Q(m) \Longrightarrow P(m)\}$

只要证 $S(m)$ 为真时，$ P(m)$ 为真即可。

$(m \geqslant m_0) \Leftrightarrow (\exists n\in \mathbb{N}, m = m_0 + n)$

记 $Q'(n) := Q(m_0 + n) = Q(m)$，则$ Q'(0) = Q(m_0)$为空，为真。

假设 $Q'(n)$ 成立，也就是 $Q(m_0 + n) := \{(m_0 \leqslant m' < m_0 + n) \Longrightarrow P(m')\}$ 为真。

为使 $S(m_0 + n)$ 为真，须证明$P(m_0 + n)$ 必然为真。

也即是需证明 $\{(m_0 \leqslant m' \leqslant m_0 + n) \Longrightarrow P(m')\}$ 成立。

这与 $Q'(n + 1) = Q(m_0 + n + 1) = \{(m_0 \leqslant m' < m_0 + n + 1) \Longrightarrow P(m')\}$ 等价。

首先 $Q'(0)$ 成立，然后由定义可知，$Q'(n - 2)$ 成立，$Q'(n - 1)$ 成立，所以 $Q'(n)$成立，

$\therefore$ 对每个自然数$n$，$Q'(n)$ 都成立，即$Q(m)$ 成立。

为使$S(m)$ 为真，$P(m)$ 必定成立，命题得证。

__PS：该题的思路即是将强数学归纳法转换成普通的数学归纳法，利用 $Q'(n)$ 进行变形。__

__2.2.6__ 令 $n$ 表示一个自然数，令 $P(m)$ 是关于自然数的一个性质并且满足：只要$P(m++)$ 为真，$P(m)$ 就为真。假设 $ P(n)$也为真，证明：$P(m)$ 对满足 $m \leqslant n$ 的自然数 $m$ 均为真，这就称为逆向归纳法原理。

__证明：__

$Q(a) := \{\forall n \in \mathbb{N}, m \leqslant n, m + a = n, a \in \mathbb{N} \Longrightarrow P(m)\}$

当 $a = 0$ 时，$ m = n, P(n) \Longrightarrow Q(0)$

设 $Q(a)$ 成立，需证 $Q(a++)$ 成立。

$\because m + a = n$，设 $,b++ = m,b + (a++) = n$

$\because P(m) \therefore P(b++) \therefore P(b)$成立，

$\therefore Q(a++)$成立，由数学归纳法得证$P(m)$对满足 $m \leqslant n$ 的自然数 $ m​$ 均为真。

