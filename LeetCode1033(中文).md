## 1033.移动石子直到连续 :smile:

[toc]

### 题目描述

三枚石子放置在数轴上，位置分别为 a，b，c。

每一回合，我们假设这三枚石子当前分别位于位置 x, y, z 且 x < y < z。从位置 x 或者是位置 z 拿起一枚石子，并将该石子移动到某一整数位置 k 处，其中 x < k < z 且 k != y。

当你无法进行任何移动时，即，这些石子的位置连续时，游戏结束。

要使游戏结束，你可以执行的最小和最大移动次数分别是多少？ 以长度为 2 的数组形式返回答案：answer = [minimum_moves, maximum_moves]

示例:

> **输入: a = 1,b = 2, c = 5**
>
> **输出:[1,2]**
>
> **解释:将石子从5移动到4再移动到3，或者我们可以直接将石子移动到3。**

>**输入: a = 4,b = 3, c = 2**
>
>**输出:[0,0]**
>
>**解释:我们无法进行任何移动。**


注意:

* `1 <= a <= 100`
* `1 <= b <= 100`
* `1 <= c <= 100`
* `a != b, b != c, c != a`

---

### 分析



### 示例代码

* #### XXXX(C++)

```c++
class Solution {
public:
    vector<int> numMovesStones(int a, int b, int c) {
        int minimal = min(min(a,b),c);
        int maximal = max(max(a,b),c);
        int medium = a + b + c - minimal - maximal;
        if(medium - minimal == 1 && maximal - medium == 1)
            return {0 , 0};
        if(medium - minimal <= 2 || maximal - medium <= 2)
            return {1 , maximal - minimal - 2};
        return {2 , maximal - minimal - 2};
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

