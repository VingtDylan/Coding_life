##  1.两数之和 :smile:

[toc]
### 题目描述

给定一个整数数组 `nums` 和一个目标值 `target`，请你在该数组中找出和为目标值的那 **两个** 整数，并返回他们的数组下标。 

你可以假设每种输入只会对应于一个答案。但是，你不能重复利用这个数组中同样的元素。

示例:

> **给定 nums=[2,7,11,15],target=9**
>
> **因为nums[0]+nums[1]=2+7=9**
>
> **所以返回[0,1]**

---

### 分析

HashMap常数级查找

### 示例代码

* #### 暴力搜索(看看热闹)(C++ v1)

```c++
class Solution {
public:
	vector<int> twoSum(vector>int& nums, int target){
        for(int i=0;i<nums.size();i++){
            for(int j=0;j<nums.size();j++){
                if(i==j)continue;
                if(nums[i]+nums[j]==target)return {i，j};
            }
        }
        return {};
    }    
};
```

* #### HashMap查找(C++ v2)

```c++
class Solution {
public:
	vector<int> twoSum(vector<int>& nums, int target){
        unordered_map mp;
        for(int i = 0;i < nums.size();i++){
            mp[nums[i]] = i;
        }
        for(int i = 0;i < nums.size();i++){
            if(count(target - mp[i]) != 0 && mp[target-nums[i]] != i)
                return {i,mp[nums[i]]};
        }
        return {};
    }    	
};
```

* #### Python(v1)

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        '''
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        '''
        for i in nums:
            j = target - i;
            start_index = nums.index(i);
            next_index = start_index+1;
            temp_nums = nums[next_index:]
            if j in temp_nums:
                return (nums.index(i),next_index+temp_nums.index(j))

```

* #### Python(v2)

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        '''
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        '''
        dict = {} 
        for i in range(len(nums)):
            if target - nums[i] not in dict:
                dict[nums[i]] = i;
            else:
                return [dict[target-nums[i]],i]
```

[^footnote]:快乐菜醒每一天!







