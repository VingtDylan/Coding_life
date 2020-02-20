## 382.链表随机节点:smiley:

[toc]

### 题目描述

给定一个单链表，随机选择链表的一个节点，并返回相应的节点值。保证每个节点被选的概率一样。

进阶:
如果链表十分大且长度未知，如何解决这个问题？你能否使用常数级空间复杂度实现？

> **// 初始化一个单链表 [1,2,3].**
> **ListNode head = new ListNode(1);**
> **head.next = new ListNode(2);**
> **head.next.next = new ListNode(3);**
> **Solution solution = new Solution(head);**
> **// getRandom()方法应随机返回1,2,3中的一个，保证每个元素被返回的概率相等。**s**olution.getRandom();**

---

### 分析



### 示例代码

* #### XXXX(C++)

```c++
class Solution {
public:
    /** @param head The linked list's head.
        Note that the head is guaranteed to be not null, so it contains at least one node. */
    Solution(ListNode* head) {
        this->head = head;
    }
    
    /** Returns a random node's value. */
    int getRandom() {
        int res = head->val;
        int i = 2;
        ListNode* current = head->next;
        while(current){
            int j = rand() % i;
            if(j == 0 ) res = current->val;
            i++;
            current = current->next;
        }
        return res;
    }
private:
    ListNode* head;
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

