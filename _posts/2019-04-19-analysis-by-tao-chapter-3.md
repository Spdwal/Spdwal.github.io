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



## 罗素悖论（选学）

**3.2.1** 证明：我们假设万有分类公理为真，那么它能推出公理3.2，公理3.3，公理3.4，公理3.5，和公理3.6。

**证明：**

此题归根究底就是构建各种各样的$P(x)$。

由万有分类公理推断出空集：

$P(x) := \{x : \nexists  x \}$ 可得空集。

万有分类公理推断出单元素与双元素集。

单元素集：

$P(x) := \{x: $ 存在且只存在只存在唯一的一个 $x\}$

双元素集：

$P(x) := \{x: $ 存在且只存在两个不相等的 $x\}$

万有分类公理推出两合集的并集

$P(x) := \{x: x \in A \vee x \in B\}$

万有分类公理推出分类公理：

$P(x) := \{x : x \in A\}$

万有分类公理推出替代公理

$P(y) := \{y: x \in A, Q(x, y) \ is \ true \}$

万有分类公理推出无穷大：

$P(x) := \{x: P(0) \ is \ true, when \ P(x) \ is \ true , P(x++) \ is \ true \}$



**3.2.2** 利用正则性公理和单元素集公理证明：如果 $A$ 是一个集合，那么 $A \notin A$ 。进一步证明：如果 $A$ 和 $B$ 是两个集合，那么要么 $A \notin B$ 要么 $B \notin A$ 

**证明：**

先证第一个命题：

假设存在集合 $A$ 使得 $A \in A$

假设 $A$ 是一个原始集合，则命题显然为假，接下来证明为非原始集合的情况。

考虑单元素集 $\{A\}$ ，$A$ 与 $\{A\}$ ，$A \in \{A\} \wedge A \cap A \neq \phi$

与正则性矛盾，所以假设为False，得证。

再证第二个命题，假设 $A \neq B, A \in B \wedge B \in A$

假设一个集合 $\{A, B\} , A \in \{A, B\}, \because B \notin B \therefore B \cap \{A, B\} = {A}$

同理：$A \cap \{A, B\}  = \{B\}$，所以这个集合中的两个元素都与它相交，与正则性矛盾，得证。



**3.2.3** 在假定集合论和其他公理成立的前提下，验证万有分类公理与这样一个公理是等价的：该公理假定存在一个由一切集合所构成的万有集合$\Omega$ ，换言之，如果公理为真，那么就存在一个万有集合，繁殖如果存在一个万有集合，那么公理就为真。

**证明：**

$y \in \{x: \forall x P(x) \ is \ true \}$ 即是用公理推出万有集合。

对于万有集合的每一个元素，都可以依赖于$P$,所以存在任意x，都保证万有分类公理成立。



## 函数

**3.3.1** 证明定义3.3.7中"相等"的定义是自反的、对称的、和可传递的。同时证明替换性质：如果 $f$，$\tilde{f}: X \rightarrow Y$ 和 $g$，$\tilde{g} : Y \rightarrow Z$ 是满足 $f = \tilde{f}$ 和 $g = \tilde{g}$ 的函数，那么 $g \circ f = \tilde{g} \circ \tilde{f}$

**证明：**

自反性：

当$x \in X, f(x) = f(x) \wedge f: X \rightarrow Y, f: X \rightarrow Y$ 

显然也相等。

对称性：

$\forall x \in X, f(x) = g(x) \Rightarrow \forall x \in X, g(x) = f(x)$

$\therefore g = f$

可传递性：

$ \forall x \in X, f(x) = g(x), g(x) = h(x) \therefore f(x) = h(x)$得证。

替换性质：

$\because f(x) = \tilde{f}(x),g(x) = \tilde{g}(x) $

$\therefore g(f(x)) = g(\tilde{f}(x)),\therefore g(f(x)) = \tilde{g}(\tilde{f}(x))$ 得证。



**3.3.2** 设 $f: X \rightarrow Y$ 和 $g: Y \rightarrow Z$ 是函数。证明：如果 $f$ 和 $g$ 都是单射，那么 $g \circ f$ 也是单射；类似的，证明：如果 $f$ 和 $g$ 都是满射，那么 $g \circ f$ 也是满射。

**证明：**

先证单射：

当 $x_1, x_2 \in X, x_1 \neq x_2, f(x_1), f(x_2) \in Y,f(x_1) \neq f(x_2) \therefore g(f(x_1)) \neq g(f(x_2))$

所以 $g \circ f$ 也是单射的。

再证满射：

$\because f, g$ 都是满射的。 $\therefore \forall z \in Z$ 则 $z$ 通过 $g$ 对 $Y$ 中某一个元素起作用

又 $f$ 是满射的，所以 $\forall y \in Y$ $y$ 通过 $f$ 对 $X$ 中某一个元素起作用

$\therefore \forall z \in Z$ 都可以通过 $f \circ g$ 对 $X$ 上某个元素起作用。所以 $f \circ g$ 是满射的。



**3.3.3** 何时空函数是单射？满射？双射？

**解：**

空函数都是单射 
如果值域是空，则为满射 
如果值域为空，则为双射



**3.3.4** 在这一节中我们给出一些有关复合的消去律。设 $ f: X \rightarrow Y、\tilde{f}(x): X \rightarrow Y、g : Y \rightarrow Z$  和 $\tilde{g}: Y \rightarrow Z$ 都是函数。证明：如果 $g \circ f = g \circ \tilde{f}$ 并且 $g$ 是单射，那么 $f = \tilde{f}$ 。如果 $g$ 不是单射，那么上面的结论是否依然成立？证明：如果 $g \circ f = \tilde{g} \circ f$ 并且 $f$ 是满射、那么 $g = \tilde{g}$ 。如果 $f$ 不是满射，那么上述结论是否成立。

**证明：**

单射：

$\because g$  是单射，$\therefore y_1,y_2 \in Y, y_1 \neq y2, g(y_1) \neq g(y_2)$ 

$\therefore g \circ f = g \circ \tilde{f} \Rightarrow f = \tilde{f}$ 得证。

如果$g$ 不是单射，那么上面的结论不一定成立。

满射：

假设 $g \neq \tilde{g}, \because \forall y \in Y, \exists x \in X $ 

令 $x_1 = x_2 \Rightarrow y_1 = y_2, y_1, y_2 \in Y \therefore g(x) = \tilde{g}(x) $  得证。



**3.3.5** 设 $f: X \rightarrow Y$ 和 $g: Y \rightarrow Z$ 都是函数，证明：如果 $g \circ f$ 是单射，则 $f$ 一定是单射，$g$ 是否也一定是单射？如果 $g \circ f$ 为满射，则 $g$ 一定为满射。$f$ 是否也必须为满射？

**证明：**

单射：

如果 $f$ 不为单射，那么 $x_1 \neq x_2,  f(x_1) = f(x_2) \Rightarrow g(f(x_1)) = g(f(x_2))$ 与 $g \circ f$ 也为单射矛盾。

所以 $f$ 一定为单射。

接下来证明 $g$ 也为单射：

若 $g$ 不为单射，$g(y_1) = g (y_2), y_1 \neq y_2$ 

又 $f$ 为单射，$\therefore y_1 \neq y_2 \Rightarrow x_1 \neq x_2$ 与题设矛盾，得证。

满射：

假设 $g$ 不为满射，那么存在$z \in Z$ ，$z$ 对 $Y$ 中所有元素都形不成映射，也就是不存在$f(x)$ 得证。

$f$ 不一定为满射：

存在有 $y \in Y \wedge f(x) != y \wedge g \circ f $ 为满射。

在此情况下 $y_1 \in Y_1, g(y_1) = z, z \in Z, Y_1 \subset Y$  即可得到这个结论。



**3.3.6** 令 $f : X \rightarrow Y$ 是一个双射函数，并且 $f^{-1} : Y \rightarrow X$ 是 $f$ 的逆。证明下面的消去律：对任意的 $x \in X$ 有 $f^{-1}(f(x)) \ x$ ，对任意的 $y \in Y$ 有 $f(f^{-1}(x)) = y$ 。推导 $f^{-1}$ 也是可逆的，并且它的逆就是 $f$ (于是有$(f^{-1})^{-1} = f$) 。

**证明：**

由于 $f$ 是双射函数，对于 $\forall x \in X$ 存在唯一一个 $y$ ,使得 $ f(x) = y， f^{-1}(y) = x$。

$\therefore f^{-1}(f(x)) =x$，得证。

同理可以证明 $f(f^{-1}(x)) = y$

取 $\forall y \in Y, f^{-1}(y) = x \Rightarrow (f^{-1})^{-1}(x) = y = f(x)$ 得证。



**3.3.7** 设$f: X \rightarrow Y$ 和 $g : Y \rightarrow X$  都是函数，证明：如果 $f$ 和 $g$ 都是双射，那么 $g \circ f$ 也是双射，并且有 $(g \circ f)^{-1} = f^{-1} \circ g^{-1}$。

**证明：**

由3.3.6可得，若$f,g$ 都是单射，那么$g \circ f$ 也是单射。

若 $f, g$ 都是满射，那么 $g \circ f$ 也是满射。

所以第一问得证。

双射映射为 $X \rightarrow Y \rightarrow Z$ ，由于他们为双射，所以 $(g \circ f)^{-1} : Z \rightarrow X$ 

$(g \circ f)^{-1}(z) = x$

$g^{-1}(z) = y, f^{-1}(y) = z \Rightarrow f^{-1}(g^{-1}(z)) = x$

得证。



**3.3.8**  如果 $X$ 是 $Y$ 的一个子集，令 $\imath_{X \rightarrow Y} : X \rightarrow Y$ 表示从 $X$ 到 $Y$ 的包含映射，该映射被定义为：对任意的 $x \in X$ 有 $x \mapsto x$，即对任意的 $x \in X$ 有 $\imath_{X \rightarrow Y}(x) := x$。特别的，映射 $\imath_{ X \rightarrow X}$ 被称为$X$ 上的恒等映射。

1. 证明：如果 $X \subseteq Y \subseteq Z$，那么 $\imath_{Y \rightarrow Z} \circ \imath_{X \rightarrow Y} = \imath_{X \rightarrow Z}$。
2. 证明：如果 $f: A \rightarrow B$ 是任意一个函数，那么 $f = f \circ \imath_{A \rightarrow A} = \imath_{B \rightarrow B} \circ f$。
3. 证明：如果 $f: A \rightarrow B$ 是一个双射函数，那么 $f \circ f^{-1} = \imath_{B \rightarrow B}$ 并且 $f^{-1} \circ f = \imath_{A \rightarrow A}$。
4. 证明：如果 $X$ 和 $Y$ 是不相交的集合，并且 $f: X \rightarrow Z$ 和 $g: Y \rightarrow Z$ 都是函数，那么存在唯一的函数 $h : X \cup Y \rightarrow Z$ 使得 $h \circ \imath_{X \rightarrow X \cup Y}  = f$ 并且 $h \circ \imath_{Y \rightarrow X \cup Y} = g$。

**证明：**

1. $\imath_{X \rightarrow Y}(x) := x, \because Y \subseteq Z, \therefore \imath_{Y \rightarrow Z}(x) := x$

   $\because X \subseteq Z \therefore \imath_{X \rightarrow Z} := x$ 得证。

2. 定义域都为 $A$ ，值域都为 $B$

   对于$x \in A$ ，$f \circ \imath_{A \rightarrow A}(X) = f(\imath_{A \rightarrow A}(x)) = f(x)$ 得证。

   对于$x \in A$，$\imath_{B \rightarrow B}(f(x)) = y = f(x) $ 得证。

3. 利用3.3.6，得证。

4. 对于$x \in X, h(x) = f(x), if \ x \in Y, h(x) = g(x) $证明：$h \circ \imath_{X \cup Y} = f$ 

   定义域都为$X$，值域都为 $Z$ ，对于任意 $x \in X$

   $h \circ \imath_{X \rightarrow X \cup Y}(x) = z = f(x)$ 得证。

   同理可以证明第二个结论。



## 象和逆象

**3.4.1** 设 $f : X \rightarrow Y$  是一个双射函数，并且 $f^{-1} : Y \rightarrow X$ 是它的逆，设 $V$ 是 $X$ 的任意一个子集。证明：$V$  在 $f^{-1}$ 下的前象与 $V$ 在 $f$ 上的逆象是同一个集合，从而吧这两个集合都用 $f^{-1}(V)$ 来表示不会造成任何不兼容的情况。

**证明：**

前象：

$V$ 在 $f^{-1}$ 下的前象：$f^{-1}(V) := \{f^{-1}(x): x \in V\}$

V 在 $f$ 下的逆象: $ \{x \in X : f(x) \in V\}$

又因为 $f$ 是一个双射函数。

利用替换公理，

逆象：$P(x, y), x \in X, y \in V, P(x, y) \ is \ true$

前象：$Q(x, y), y \in V, Q(x, y) \ is \ true$ 

因为 $f$ 是一个双射函数，所以每一个 $y \in V$   必然有一个 $x \in X$  所以两个定义实际上是等价的，得证。



**3.4.2** 令 $f: X \rightarrow Y$ 表示从集合$X$ 到集合 $Y$ 的函数，$S$ 是 $X$ 的一个子集，$U$ 是 $Y$ 的一个子集。一般情况下，$f^{-1}(f(S))$ 与 $S$ 有什么关系？$f(f^{-1}(U))$ 与 $U$ 又有什么关系

**证明：**

设 $f(S) = U = \{f(x): x \in S\}$

$f^{-1}(f(S)) = f^{-1}(U) = \{x \in X: f(x) \in U\}$

$\forall x \in S, f(x) \in U, \wedge x \in S, x \in X$

$S \subseteq f^{-1}(f(S))$ 



设 $f^{-1}(U) = S = \{x \in X: f(x) \in U\}$

$\forall x \in S, x \in X, f(x) \in U$

$f(f^{-1}(U)) = \{f(x): x \in S\}$

$\forall y \in f(f^{-1}(U)), y \in (f(s): x \in S)$	

已知 $\forall x \in S, f(x) \in U$

$y \in U$

$f(f^{-1}(U)) \subseteq U$



**3.4.3**  设 $A$ 和 $B$ 是集合 $X$ 的两个子集，且 $f: X \rightarrow Y$ 是一个函数。证明：$f(A \cap B) \subseteq f(A) \cap f(B), f(A) \setminus f(B) \subseteq f(A \setminus B), f(A \cup B) = f(A) \cup f(B)$ 。对于前两个结论，$\subseteq$ 可以被加强为 $=$ 吗？

**证明：**

1. $f(A \cap B) \subseteq f(A)$

   $f(A \cap B) \subseteq f(B)$

   $\therefore f(A \cap B) \subseteq f(A) \cap f(B)$

2. $f(A) \setminus f(B) = \{y \in f(A) : y \notin f(B)\}$

   $\forall y_0 \in f(A) \setminus f(B)$ 都存在一个对应的$ x_0 \in A , y_0 = f(x_0)$

   同时 $x_0 \notin B$ 否则 $f(x_0) \in f(B)$ 矛盾。

   所以 $y_0 \in \{f(x): x \in A \setminus B\} = f(A \setminus B) $

   $\therefore f(A) \setminus f(B) \subseteq f(A \setminus B)$

3. $\forall y \in f(A \cup B)$ 都存在一个对应的 $x \in A \cup B, f(x) = y$

   $\therefore x \in A \vee x \in B, y \in f(A) \vee y \in f(B)$

   $y \in f(A) \cup f(B)$

   $f(A \cup B) \subseteq f(A) \cup f(B)$

   $\forall y \in f(A) \cup f(B) \Rightarrow y \in f(A) \vee y \in f(B)$

   同之前的证明：

   $x \in A \cup B, y \in f(A \cup B)$

   $f(A) \cup f(B) \subseteq f(A \cup B)$

   $f(A) \cup f(B) = f(A \cup B)$

4. 不可能，除非 $f$ 是一个双射。



**3.4.4** 设 $f: X \rightarrow Y$ 是从一个集合 $X$ 到另一个集合 $Y$ 的函数，并且令 $U, V$ 为 $Y$ 的子集。证明：$f^{-1}(U \cup V) = f^{-1}(U) \cup f^{-1}(V), f^{-1}(U \cap V) = f^{-1}(U) \cap f^{-1}(V), f^{-1}(U \setminus V) = f^{-1}(U) \setminus f^{-1}(V)$。

**证明：**

1. $f^{-1}(U \cup V) = \{x \in X: f(x) \in U \cup V\}$

   $\forall x_0 \in f^{-1}(U \cup V), f(x) \in U \cup V \Rightarrow f(x) \in U \vee f(x) \in V$

   $x \in f^{-1}(U) \vee x \in f^{-1}(V) \Rightarrow x \in f^{-1}(U) \cup f^{-1}(V)$

   $f^{-1}(U \cup V) \subseteq f^{-1}(U) \cup f^{-1}(V)$

   $\forall x \in f^{-1}(U) \cup f^{-1}(V) \Rightarrow x \in f^{-1}(U) \vee f^{-1}(V)$

   $f(x) \in U \vee f(x) \in V \Rightarrow f(x) \in U \cup V$

   $f^{-1}(U) \cup f^{-1}(V) \subseteq f^{-1}(U \cup V)$

   得证。

2. $\forall x \in f^{-1}(U \cap V) \Rightarrow f(x) \in U \cap V$

   $f(x) \in U \wedge f(x) \in V$

   $x \in f^{-1}(U) \wedge x \in f^{-1}(V)$

   $x \in f^{-1}(U) \cap f^{-1}(V)$

   $f^{-1}(U \cap V) \subseteq f^{-1}(U) \cap f^{-1}(V)$

   $\forall x \in f^{-1}(U) \cap f^{-1}(V)$

   $x \in f^{-1}(U) \wedge f^{-1}(V)$

   $f(x) \in U \wedge f(x) \in V \Rightarrow f(x) \in U \cap V$

   $x \in f^{-1}(U \cap V) \Rightarrow f^{-1}(U) \cap f^{-1}(V) \subseteq f^{-1}(U \cap V)$ 

   得证。

3. $\forall x \in f^{-1}(U \setminus V) \Rightarrow f(x) \in U \setminus V$

   $f(x) \in U \wedge f(x) \notin V$

   $x \in f^{-1}(U) \wedge x \notin f^{-1}(V) $

   $x \in f^{-1}(U) \setminus f^{-1}(V)$

   $f^{-1}(U \setminus V) \subseteq f^{-1}(U) \setminus f^{-1}(V)$

   $\forall x \in f^{-1}(U) \setminus f^{-1}(V)$

   $x \in f^{-1}(U) \wedge x \notin f^{-1}(V)$

   $f(x) \in U \wedge f(x) \notin  V$

   $f(x) \in U \setminus V$

   $x \in f^{-1}(U \setminus V)$

   $f^{-1}(U) \setminus f^{-1}(V) \subseteq f^{-1}(U \setminus V)$

   得证。

   **注意：** 3.4.3和3.4.4之间的最大的区别是，一个y可能对应多个x，所以不一定可以反推。



**3.3.5** 设 $f: X \rightarrow Y$ 是从一个集合 $X$ 到另一个集合 $Y$ 的函数，证明：$f(f^{-1}(S)) = S$ 对每一个 $S \subseteq Y$ 均成立的充要条件是 $f$ 是满射。证明：$f^{-1}(f(S)) = S$ 对每一个 $S \subseteq X$ 均成立的条件是  $f$ 是单射。

**证明：**

1. 先证充分性：

   假设 $f$ 不是满射，也就是至少存在一个 $y_0 \in Y, \forall x \in X, f(x) \neq y_0$，若 $y_0 \in S$,则显然假设不成立，得证。

   再证必要性：

   $f$ 是满射，设 $U = f^{-1}(S) = \{x \in X : f(x) \in S\}, f(U) = \{f(x): x \in U\}$

   $f(U) \subseteq S$，因为 $f$ 是满射，所以对任意的 $y_0 \in S$ 都能找到一个$x_0 \in X$ 满足 $f(x_0) = y_0$

   由 $U$ 的定义可知，$x_0 \in U \therefore y_o \in f(U)$

   $\therefore S \subseteq f(f^{-1}(S))$ 

   得证。

2. 假设 $f$  不是单射，那么存在有 $x_1, x_2, f(x_1) = f(x_2)$

   $x_1 \in S, x_2 \notin S, f(x_1) = y_1, f^{-1}(y_1) \neq S$。所以假设不成立，得证。



**3.3.6** 证明：$X$ 是一个集合，那么 $\{Y: Y $ 是 $X$ 的一个子集$\}$ 是一个集合。

**证明：** 

由已知的：$Y \subseteq X$ ,假设 $X = \phi \Rightarrow Y = \phi$

$U = $$\{Y: Y $ 是 $X$ 的一个子集$\} = \{\phi\}$ 

成立。

设 $X_n$ 中有 $n$ 个元素，$U_n$ 为一个集合

当 $X_{n+1}$ 中有 $n + 1$ 个元素时，$U_{n+1}$ 至少包含 $U_n$ 中的所有元素。也为集合。得证。



**3.3.7** 设 $X$ 和 $Y$ 是集合。对于任意一个函数 $f: X' \rightarrow Y'$，如果它满足定义域 $X'$ 是 $X$ 的子集，并且 $Y'$ 是 $Y$ 的子集，那么就称 $f$ 是从集合 $X$ 到 $Y$ 的偏函数。证明：从 $X$ 到 $Y $ 的全体偏函数本身成为一个集合。

**证明：**

根据3.4.6，所有的 $X$ 的子集构成一个集合 $A$ ,所有 $Y$ 的子集构成一个集合 $B$ ，对于 $A$ 中任意一个元素 $x$，$B$ 中任意一个元素 $y$，$x$ 和 $y$ 都是集合。根据幂集公理，$x$ 和 $y$ 为元素的集合也可以组成集合，记为 $D$ 。这样，对于 $D$ 中某个元素，即某个确定的 $x$ 和 $y$ 利用替换公理可以将其替换成 $C$ 中的元素，再对 $D$ 运用并集公理，得到的函数就是偏函数的集合。



**3.4.8** 证明两集合并集公理可以从公理3.1，3.3和3.11推出。

**证明：**

考虑两个集合 $ A, B$ 根据双元素公理，存在集合 $S = \{A, B\}$，对S使用并公理：

$x \in \bigcup S = x \in A \vee x \in B$

这就是两合集并集公理。



**3.4.9** 证明：如果 $\beta$ 和 $\beta'$ 是集合 $I$ 中的两个元素，并且对每一个 $\alpha \in I$，我们指定一个集合 $A_{\alpha}$，那么

​    $ \{x \in A_\beta: $ 对任意的$ \alpha \in I, x \in A_\alpha\}$

$= \{x \in A_{\beta'}:$ 对任意的$ \alpha \in I , x \in A_\alpha\}$

从而式3.3中给出的 $$\bigcap\limits_{\alpha \in I} A_\alpha$$ 的定义不依赖于 $\beta$，这也解释了为什么式3.4为真。

**证明：**

如果要等号两边成立，则需要：

$\{x \in A_\beta \cap A_{\beta'}: $ 对于一切 $\alpha \in I, x \in A_\alpha\}$

对于式3.4显然成立。



**3.4.10**  设 $I$ 和 $J$ 是两个集合，并对任意的 $\alpha \in I \cup J$，$A_\alpha$ 表示一个集合。证明：$(\bigcup\limits_{\alpha \in I}A_\alpha) \cup (\bigcup\limits_{\alpha \in J}A_\alpha) = \bigcup\limits_{\alpha \in I \cup J}A_\alpha$。如果 $J$ 和 $I$ 都是非空的，证明：$(\bigcap\limits_{\alpha \in I}A_\alpha) \cap (\bigcap\limits_{\alpha \in J}A_\alpha) = \bigcap\limits_{\alpha \in I \cup J} A_\alpha$。

**证明：**

$\forall y \in (\bigcup\limits_{\alpha \in I}A_\alpha) \cup (\bigcup\limits_{\alpha \in J}A_\alpha) $

存在 $\alpha \in I$ 使得 $y \in A_\alpha$ 或者 存在 $\alpha \in J$ 使得 $y \in A_\alpha$

存在 $\alpha \in I \cup J$ 使得 $y \in A_\alpha$

$\bigcup\limits_{\alpha \in I \cup J}A_\alpha$ 得证。

接下来证第二问。

$(\bigcap\limits_{\alpha \in I}A_\alpha) \cap (\bigcap\limits_{\alpha \in J}A_\alpha) $

对任意的 $\alpha \in I, y \in A_\alpha$  且对任意的 $\alpha \in J, y \in A_\alpha$

对任意的 $\alpha \in I \cup J$ 都有 $y \in A_\alpha$ 得证。



**3.4.11** 设 $X$ 是一个集合，$I$ 是一个非空集合，并且对任意的 $\alpha \in I$，$A_\alpha$ 是 $X$ 的子集，证明：$ X \setminus \bigcup\limits_{\alpha \in I} A_\alpha = \bigcap\limits_{\alpha \in I}(X \setminus A_\alpha)$ 和 $X \setminus \bigcap\limits_{\alpha \in I}A_\alpha = \bigcup\limits_{\alpha \in I}(X \setminus A_\alpha)$

**证明：**

1. $y \in X \wedge \forall \alpha \in I, y \notin A_\alpha$

   $\forall \alpha \in I, y \in X \wedge y \notin A_\alpha$

   等式左右两边相等。

2. $y \in X \setminus \forall \alpha \in I, y \in A_\alpha$

   $y \in X \wedge \exists \alpha \in I, y \notin A_\alpha$

   左右两边相等，得证。

   

























 