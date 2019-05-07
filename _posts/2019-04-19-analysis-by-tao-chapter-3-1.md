---
 layout: post
title: "Analysis by Tao Chapter 3"
category: 
tags: []
---

<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>

# 习题

## 基础知识

**3.1.1** 证明集合的 “相等”的定义，是自反的、对称的、和可传递的。

**证明：**

自反性：

$\forall x \in X, x \in X, \therefore X = X$，自反性成立。

对成性：

$X = Y, \therefore \forall x \in X, x \in Y, \forall y \in Y, y \in X$，对称性成立。

可传递性：

$X = Y, Y = Z，\therefore \forall x \in X, x \in Y, \forall y \in Y, y \in Z$

$\therefore \forall x \in X, x \in Z, \therefore X =Z$，可传递性成立。

**3.1.2** 只利用定义 3.1.4、公理 3.1、公理 3.2 和公理3.3 证明集合 $\phi 、\{\phi\}、\{\{\phi\}\}、\{\phi, \{\phi\}\}$是互不相等的集合。

**证明：**
利用**公理 3.2** 与 **定义 3.1.4**

$\phi \in \{\phi\}, \phi \notin \phi, \therefore \{\phi\} \neq \phi$。

$\phi \in \{\phi, \{\phi\}\}, \phi \notin \phi, \therefore \phi \neq \{\phi, \{\phi\}\}$

$\{\phi\} \in \{\{\phi\}\}, \{\phi\} \notin \phi, \therefore \phi \neq \{\{\phi\}\}$

依次可得：

$\{\phi \} \neq \{\{\phi\}\}, \{\phi\} \neq \{\phi, \{\phi\}\}, \{\{\phi\}\} \neq \{\phi,\{\phi\}\}$。

因为 $\phi$ 也是一个对象，所以存在有 $\{\phi\}$ 这个集合。

依次使用 **公理 3.3**，证明以上集合都是有效集合，

**3.1.3** 证明求并运算是可交换的，并且证明 $A \cup A = A \cup \phi = \phi \cup A = A$。

**证明：**

并运算的交换律：

$x  \in A \cup B, x \in A$ 或者 $x \in B$，假设 $x \in A$，可得 $x \in B \cup A$，

假设 $x \in B$，可得 $x \in B \cup A$，所以可得

$\forall x \in A \cup B, x \in B \cup A, A \cup B = B \cup A$

$\forall x \in A \cup A，x  \in A \Rightarrow x \in A $ 或者 $x \in \phi$。

$\therefore A \cup \phi = A \cup A$，由之前可得并运算是可交换的，所以 $A \cup \phi = \phi \cup A$

$\forall x \in A \Rightarrow x \in A $ 或者 $x \in \phi \therefore A = A \cup \phi$。再由集合相等的传递性，即可得证。

**3.1.4** 证明 $A \subseteq B,B \subseteq A \Rightarrow A = B$，$A \subsetneq B, B \subsetneq C \Rightarrow A \subsetneq C$。

**证明：**

先证第一条。

$\because A \subseteq B \Rightarrow \forall x \in A, x \in B$

$B \subseteq A \Rightarrow \forall x \in B, x \in A$

根据**定义 3.1.4**，可得 $A = B$。

再证第二条。首先由 $A \neq B,B \neq C \Rightarrow A \neq C$

再 $A \subsetneq B \Rightarrow \forall x \in A, x \in B$

$B \subsetneq C \Rightarrow \forall y \in B, y\in C$

$\therefore \forall x \in A, x \in C \Rightarrow A \subset C$

又 $\because A \neq C \therefore A \subsetneq C$，得证。

**3.1.5** 设 $A$ 和 $B$ 是集合，证明命题 $A \subseteq B , A\cup B = B, A \cap B = A$ 在逻辑上是等价的。

**证明：**

先证命题1蕴含命题2：

$A \subseteq B \Rightarrow \forall x \in A , x \in B $

$\Rightarrow \forall x \in A \cup B \Rightarrow x \in A \vee x \in B \Rightarrow x \in B$ 

$\therefore A \subseteq B \Rightarrow A \cup B = B$  。

再证命题1蕴含命题3:

$A \subseteq B \Rightarrow \forall x \in A, x \in B \wedge x \in A \Rightarrow x \in A$

$\therefore A \subseteq B \Rightarrow A \cap B = A$

$\Rightarrow \forall x \in A \cap B \Rightarrow A \cap B = A$

再证命题2蕴含命题1:

$A \cup B = B \Rightarrow \forall x \in A \cup B, x \in B \Rightarrow$ A中所有的元素都在B中 $\Rightarrow A \subseteq  B$

再证命题2蕴含命题3:

$2 \Rightarrow 1 \Rightarrow 3$ 得证。

先证命题3蕴含命题1:

$A \cap B = A \Rightarrow \forall x \in A \cap B,x \in A$

可得 $A$ 中的所有的值，都既属于 $A$ 也属于 $B$ ，可得 $A \subseteq B$ 得证。

再证命题3蕴含命题2：

$3 \Rightarrow 1 \Rightarrow 2$ 得证。

**3.1.6** 证明集合构成布尔代数，设 $A、B、C$ 都是集合，令 $X$ 表示包含 $A、B、C$ 作为其子集的集合。

1. 我们有 $A \cup \phi = A$ 和 $A \cap \phi = \phi$。
2. 我们有 $A \cup X = X$ 和 $A \cap X = A$。
3. 我们有 $A \cap A = A$ 和 $A \cup A = A$。
4. 我们有 $A \cup B = B \cup A$ 和 $A \cap B = B \cap A$。
5. 我们有 $(A \cup B) \cup C = A \cup (B \cup C)$ 和 $(A \cap B) \cap C = A \cap (B \cap C)$。
6. 我们有 $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$ 和 $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$。
7. 我们有 $A \cup (X \setminus A) = X$ 和 $A \cap (X \setminus A) = \phi$。
8. 我们有 $X \setminus (A \cup B) = (X \setminus A) \cap (X \setminus B) $ 和 $X \setminus (A \cap B) = (X \setminus A) \cup (X \setminus B) $。

**证明：**

1. 由上题可得：$\phi \subseteq A \Rightarrow A \cup \phi = A, A \cap \phi = B$

2. 同上：$A \subseteq X \Rightarrow A \cap X = A, A \cup X = X$

3. 同上：$A \subseteq A \Rightarrow A \cap A = A, A \cup A = A$

4. **见 引理 3.1.3 证明**

5. **见 引理 3.1.3 证明**

6. 先证明 $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$

   $\forall x \in A \cap (B \cup C) \Rightarrow x \in A \wedge x \in (B \cup C)$

   可分成以下两种情况：

   1. $x \in A \wedge x \in B \Rightarrow x \in (A \cap B) \Rightarrow x \in (A \cap B) \cup (A \cap C)$
   2. $x \in A \wedge x \notin B \wedge x \in c \Rightarrow x \in (A \cap C) \Rightarrow x \in (A \cap B) \cup (A \cap C)$

   $\therefore \forall x \in A \cap (B \cup C) \Rightarrow x \in (A \cap B) \cup (A \cap C)$

   $\therefore A \cap (B \cup C) \subseteq (A \cap B) \cup (A\cap C)$

   $x \in (A \cap B) \Rightarrow x \in A \cap (B \cup C)$

   $x \in (A \cap C) \Rightarrow x \in A \cap (B \cup C)$

   $\therefore (A \cap B) \cup (A \cap C) \subseteq A \cap (B \cup C)$

   $\therefore (A \cap B) \cup (A \cap C) = A \cap (B \cup C)$  得证。

   再证明 $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$

   $\forall x \in A \cup (B \cap C) \Rightarrow x \in A \vee x \in (B \cap C)$

   也分为两种情况：

   1. $x \in A \Rightarrow  x \in (A \cap B) \wedge x \in (A \cap C) \Rightarrow x \in (A \cap B) \cup (A \cap C)$
   2. $x \in (B \cap C) \Rightarrow x \in B \wedge x \in C \Rightarrow x \in (A \cup B) \wedge x \in (A \cup C) \Rightarrow x \in (A \cup B) \cap (A \cup C)$

   $\therefore \forall x \in A \cup (B \cap C), x \in (A \cup B) \cap (A \cup C)$

   $\therefore A \cup (B \cap C) \subseteq (A \cup B) \cap (A \cup C)$

   $x \in (A \cup B) \cap (A \cup C)$  也分成两种情况讨论

   1. $x \in A \wedge x \notin (B \cup C)  \Rightarrow x \in A \cup (B \cap C)$
   2. $x \notin A \wedge x \in (B \cap C) \Rightarrow x \in A \cup (B \cap C)$

   $\therefore \forall x \in (A \cup B) \cap (A \cup C) \subseteq A \cup (B \cap C)$

   $\therefore A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$ 得证。

7. $\forall x \in (X \setminus A) \Rightarrow \forall x \in X \wedge x \notin A$

   $A \cup (X \setminus A) \Rightarrow \forall x \in A \vee \forall x \in (X \setminus A) $ 又 $\because A \subseteq X \Rightarrow \in X$

   $\therefore A \cup (X \setminus A) \in X$

   $\forall x \in X \Rightarrow x \in (X \setminus A) \Rightarrow x \in A \cup (X \setminus A)$

   $\therefore X \subseteq A \cup (X \setminus A)$

   $\therefore A \cup (X \setminus A) = X$ 

   $A \cap (X \setminus A) \Rightarrow \forall x \in A \wedge (x \in X \wedge x \notin A) \Rightarrow (x \in A \wedge x \notin A) \wedge x \in X$

   $x \in \phi \wedge x \in X \Rightarrow x \in \phi$

   $ A \cap (B \cup C) \subseteq \phi$

   $\phi \subseteq A \cap (B \cup C)$

   $A \cap (X \setminus A) = \phi$

8. 先证 $X \setminus (A \cup B) = (X \setminus A) \cap (X \setminus B)$

   $\forall x \in X \setminus (A \cup B) \Rightarrow x \notin (A \cup B)$

   $x \in X \setminus A \wedge x \in X \setminus B$

   $x \in (X \setminus A) \cap (x \setminus B)$

   $X \setminus (A \cup B) \subseteq (X \setminus A) \cup (X \setminus B)$

   $\forall x \in (X \setminus A) \cap (X \setminus B) \Rightarrow x \in X \wedge x \notin A \wedge x \notin B$

   $x \in X \setminus (A \cup B)$

   $(X \setminus A) \cap (X \setminus B) \subseteq X \setminus (A \cup B)$

   $\therefore (X \setminus A) \cap (X \setminus B) = X \setminus (A \cup B)$  得证。

   再证 $X \setminus (A \cap B) = (X \setminus A) \cup (X \setminus B)$

   $X \setminus (A \cap B) \Rightarrow \forall x \in X \wedge x \notin (A \cap B)$

   存在以下三种情况：
   
   1. $x \in X \setminus (A \cup B) \Rightarrow x \in X \setminus A \Rightarrow x \in (X \setminus A) \therefore x \in (X \setminus A) \cup (x \setminus B)$
   2. $x \in (A \setminus B) \because A \subseteq X \therefore x \in (X \setminus B) \therefore  x \in (X \setminus A) \cup (x \setminus B)$
   3. $x \in (B \setminus A) \because B \subseteq X \therefore x \in (X \setminus A) \therefore  x \in (X \setminus A) \cup (x \setminus B)$ 
   
   $\therefore X \setminus (A \cap B) \subseteq (X \setminus A) \cup (X \setminus B)$
   
   $(X \setminus A) \cup (X \setminus B) \Rightarrow \forall x \in (X \setminus A) \cup (X \setminus B) $
   
   当 $x \in (X \setminus A) \because (A \cap B) \subseteq A \therefore x\in X \setminus (A \cap B)$
   
   同理 $x \in (X \setminus B),x \in X \setminus (A \cap B)$
   
   $\therefore (X \setminus A) \cup (X \setminus B) \subseteq X \setminus (A \cap B)$
   
   $\therefore X \setminus (A \cap B) = (X \setminus A) \cup (X \setminus B)$ 得证。

**3.1.7** 设 $A、B、C$ 都是集合，证明 $A \cap B \subseteq A$ 和 $A \cap B \subseteq B$。更进一步的，证明 $C \subseteq A$ 且 $C \subseteq B$，当且仅当 $C \subseteq A \cap B$。类似的，证明 $A \subseteq A \cup B$ 和 $B \subseteq A \cup B$，且进一步证明 $A \subseteq C$ 且 $B \subseteq C$，当且仅当 $A \cup B \subseteq  C$

**证明：**

先证 $A \cap B \subseteq A$

$\forall x \in A \cap B \Rightarrow x \in A \wedge x \in B \Rightarrow x \in A \Rightarrow A \cap B \subseteq A$

同理可证 $A \cap B \subseteq B$

$C \subseteq A \wedge C \subseteq B \Rightarrow \forall x \in C, x \in A \wedge x \in B \Rightarrow x \in A \cap B$

$\therefore C \subseteq  A \cap B$

$C \subseteq A \cap B \Rightarrow \forall x \in C, x \in A \wedge x \in B \Rightarrow C \subseteq A \wedge C \subseteq B$ 

$\therefore C \subseteq A \wedge C \subseteq B \Leftrightarrow C \subseteq A \cap B$ 得证。

余下同理。

**3.1.8** 设 $A$  和 $B$ 是集合，证明**吸收率** $A \cap (A \cup B) = A$ 和 $A \cup (A \cap B) = A$。

**证明：**

$\forall x \in A \cup B \wedge x \in A \because A \subseteq A \cup B \therefore x \in A \therefore A \cap (A \cup B) \subseteq A$

$\forall x \in A, x \in A \wedge x \in (A \cup B) \therefore x \in A \cap (A \cup B)$

$\therefore A \cap (A \cup B) = A$

类似可证 $A \cup (A \cap B) = A$

**3.1.9** 令 $A、B、X$ 表示集合，并且他们满足 $A \cup B = X$ 和 $A \cap B = \phi$。证明：$ A = X \setminus B, B = X \setminus A$ 

**证明：**

$\forall x \in A , \because A \cup B \ X \therefore x \in A, \because A \cap B = \phi \therefore x \notin B $

$\therefore A \subseteq X \setminus B$

$\forall x \in X \setminus B \Rightarrow x \in X \wedge x \notin B$

$\because A \cup B = X, A \cap B = \phi \Rightarrow x \in A$

$X \setminus B \subseteq A \Rightarrow A = X \setminus B$  得证。

同理可证 $B = X \setminus A$

**3.1.10** 设 $A$ 和 $B$ 是集合，证明三个集合 $A \setminus B 、A \cap B 、B \setminus A$ 是不相交的，并且他们的并集是$A \cup B$

**证明：**

假设他们仨个集合是相交的。

假设$A \setminus B$ 与 $A \cap B$ 相交

那么$\exist x \in A \setminus B, x \in A \cap B, \therefore x \in B \wedge x \notin B$ 矛盾，所以这两个集合不相交。同理可证其他集合之间的关系。

令$ X = A \cup B \therefore \forall x \in X$ 可化为以下三种之一

1. $x \in A \wedge x \notin B \Rightarrow x \in A \setminus B$
2. $x \in B \wedge x \notin A \Rightarrow x \in B \setminus A$
3. $x \in A \wedge x \in B \Rightarrow x \in A \cap B$

得证。

**3.1.11** 证明替代公理能推导出分类公理。

**证明：**

替代公理为：

$z \in \{y: P(x, y), x \in A \} \Leftrightarrow x \in A, P(x, z)\ is \ true$

令 $Q(y) := P(x, y),  x = y$

$y \in \{x \in A: Q(x) \ is \ true \} \Leftrightarrow y \in A \wedge Q(y) \ is \ true$ 得证。



















 