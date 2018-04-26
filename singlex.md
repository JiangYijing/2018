# Move Zeroes
## 问题分析:
移动0,将一个给定数组中所有的0都移到后面同时把非零数前移,要求不能改变非零数的相对应的位置关系,而且不能拷贝额外的数组
## 编程实现:
```C++
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        for(int i=0,j=0;i<nums.size();++i)
        {
            if(nums[i])
            {
                swap(nums[i],nums[j++]);
            }
        }
    }
};
```
