## 398.随机数索引 :smiley:

[toc]

### 题目描述

给定一个可能含有重复元素的整数数组，要求随机输出给定的数字的索引。 您可以假设给定的数字一定存在于数组中。 

示例:

> **int[] nums = new int[] {1,2,3,3,3};**
> **Solution solution = new Solution(nums);**
> **// pick(3) 应该返回索引 2,3 或者 4。每个索引的返回概率应该相等。**
> **solution.pick(3);**
> **// pick(1) 应该返回 0。因为只有nums[0]等于1。**
> **solution.pick(1);**

注意:
数组大小可能非常大。 使用太多额外空间的解决方案将不会通过测试。 

---

### 分析



### 示例代码

* #### XXXX(C++)

```c++
class Solution {
public:
    Solution(vector<int>& nums): vec(nums) {
        
    }
    
    int pick(int target) {
        int res = -1, count = 0;
        for(int i = 0; i < vec.size(); i++){
            if(vec[i] !=target)continue;
            count++;
            if(rand() % count == 0) res = i;
        }
        return res;
    }
private:
    vector<int> vec;
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

