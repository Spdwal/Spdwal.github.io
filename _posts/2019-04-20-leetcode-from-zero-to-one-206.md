---
layout: post
title: "[Leetcode from zero to one] 206"
category: 
tags: []
---

# 206 - Reverse Linked List

Reverse a singly linked list.

**Example:**

```
Input: 1->2->3->4->5->NULL
Output: 5->4->3->2->1->NULL
```

**Follow up:**

A linked list can be reversed either iteratively or recursively. Could you implement both?

写了20多分钟。。。。感觉自己真的渣化了。。。

以下为非递归版本。

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
    ListNode* reverseList(ListNode* head) {
        if(head == NULL || head->next == NULL){
            return head;
        }
        // 三个节点保存住状态
        ListNode* preTemp = head;
        ListNode* temp = preTemp->next;
        ListNode* tempNext = temp->next;
        
        
        while(temp != NULL){
            
            tempNext = temp->next;
            // 中间节点指向之前的节点
            temp->next = preTemp;
            // 前继节点往后走
            preTemp = temp;
            // 当前节点往后走
            temp = tempNext;
        }
        
        head->next = NULL;
        return preTemp;
    }
};
```

