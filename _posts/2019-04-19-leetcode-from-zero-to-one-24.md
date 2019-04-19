---
layout: post
title: "[Leetcode from zero to one] 24"
category: 
tags: []
---

# 24 - Swap Node Pairs

Given a linked list, swap every two adjacent nodes and return its head.

You may **not** modify the values in the list's nodes, only nodes itself may be changed.

**Example:**

```
Given 1->2->3->4, you should return the list as 2->1->4->3.
```

这道题最主要的坑第一是对链表的结构表述不够清楚，head到底是第一个节点还是指向第一个节点，第二就是故意加入了会导致段错误的数据，其他的来看，就是普通的链表翻转节点。

```c++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* swapNode(ListNode* PreNode){
        if(PreNode->next->next == NULL){
            return PreNode->next;
        }
      	// 很简单的翻转节点。
        ListNode* node = PreNode->next;
        PreNode->next = node->next;
        node->next = PreNode->next->next;
        PreNode->next->next = node;
      	// 返回下一对节点的之前那个节点。
        return node;
    }
    
    ListNode* swapPairs(ListNode* head) {
      	// 针对0个或者1个节点的特殊情况
        if(head == NULL || head->next == NULL){
            return head;
        }
      	// 因为头节点没有preNode，所以对头节点进行特殊处理。
        ListNode* PreNode = head;
        ListNode* headNext = head->next;
        head->next = headNext->next;
        headNext->next = head;
        head = headNext;
        PreNode = head->next;
      	// 依次翻转节点，
        while(PreNode->next != NULL){
            PreNode = swapNode(PreNode);
        }
        
        return head;
    }
};
```



