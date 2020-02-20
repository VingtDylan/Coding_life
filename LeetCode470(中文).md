## 470.用Rand7()实现Rand10():smiley:

[toc]

### 题目描述

已有方法 rand7 可生成 1 到 7 范围内的均匀随机整数，试写一个方法 rand10 生成 1 到 10 范围内的均匀随机整数。

不要使用系统的 Math.random() 方法。

示例:

> **输入: 1 **
>
> **输出: [7]**

> **输入: 2 **
>
> **输出: [8,4]**

>**输入: 3**
>
>**输出: [8,1,10]**

---

### 分析



### 示例代码

* #### XXXX(C++)

```c++
class Solution {
public:
    int rand10() {
        int n = (rand7() - 1) * 7 + rand7();
        return n < 40 ? n % 10 + 1 : rand10(); 
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

