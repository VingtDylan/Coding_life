## 2.两数之和 :smiley:

[toc]

### 题目描述

给出两个 **非空** 的链表用来表示两个非负的整数。其中，它们各自的位数是按照 **逆序** 的方式存储的，并且它们的每个节点只能存储 **一位** 数字。 

如果，我们将这两个数相加起来，则会返回一个新的链表来表示它们的和。

您可以假设除了数字 0 之外，这两个数都不会以 0 开头。

示例:

> **输入: (2 -> 4 -> 3) + (5 -> 6 -> 4)**
>
> **输出: 7 -> 0 -> 8**
>
> **原因: 342 + 465 = 807**

---

### 分析

逐位相加，注意进位即可。

### 示例代码

* #### 注意一下carry位就好了(C++)

  借鉴网上的结点，防止输入都是空的情况。

```c++
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode* dummy = new ListNode(-1);
        ListNode* cur = dummy;
        int carry = 0;
        while(l1 != NULL||l2 != NULL){
            int a = (l1 != NULL) ? l1->val : 0;
            int b = (l2 != NULL) ? l2->val : 0;
            int sum = a + b + carry;
            cur->next = new ListNode(sum % 10);
            carry = sum / 10;
            cur = cur->next;
            l1 = (l1 != NULL) ? l1->next : NULL;
            l2 = (l2 != NULL) ? l2->next : NULL;
        }
        cur->next = carry ? new ListNode(1) : NULL;
        return dummy->next;
    }
};
```

* #### XXXX(Python v1)

```python
class Solution(object,...):
    def XXXX(self,...):
        '''
        :type ...
        :rtype: ...
        ...
        '''
```

* #### continued



[^footnote]: 快乐菜醒每一天!