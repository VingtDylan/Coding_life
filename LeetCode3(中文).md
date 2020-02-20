## 3.无重复字符的最长子串 :smiley:

[toc]

### 题目描述

给定一个字符串，请你找出其中不含有重复字符的 **最长子串** 的长度。 

示例 1:

> **输入: "abcabcbb"**
>
> **输出: 3**
>
> **解释: 因为无重复字符的最长子串是 "abc"，所以其长度为 3**

示例 2:

> **输入: "bbbbb"**
>
> **输出: 1**
>
> **解释: 因为无重复字符的最长子串是 "b"，所以其长度为 1**

示例 3:

> **输入: "pwwkew"**
>
> **输出: 3**
>
> **解释: 因为无重复字符的最长子串是 "wke"，所以其长度为 3。
>         请注意，你的答案必须是 子串 的长度，"pwke" 是一个子序列，不是子串。**

---

### 分析

hashmap建立字符与出现位置的映射。

### 示例代码

* #### hashmap建立字符与位置的映射(C++ v1)

```c++
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        unordered_map<int,int> m;
        int res = 0, left = -1;
        for(int i = 0; i < s.size(); i++){
            if(m.count(s[i]) && m[s[i]] > left){
                left = m[s[i]];
            }
            m[s[i]] = i;
            res = max(res, i - left);
        }
        return res;
    }
};
```

* #### vector (improved C++ v2)

```c++
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        vector<int> vec(128,-1);
        int res = 0, left = -1;
        for(int i = 0; i < s.size(); i++){
            left = max(left, vec[s[i]]);
            vec[s[i]] = i;
            res = max(res, i - left);
        }
        return res;
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

