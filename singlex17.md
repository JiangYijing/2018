# Non-decreasing-array
## 问题分析：
非递减数列,最多有一次修改某个数字的机会是否能将数组变为非递减数组,关键寻找前后数与数的内在关系
## 编程实现：
```C++
class Solution {
public:
    bool checkPossibility(vector<int>& nums) {
        int cnt=1,n=nums.size();
        for(int i=1;i<n;++i)
        {
            if(nums[i]<nums[i-1])
            {
                if(cnt==0) return false;
                if(i==1||nums[i]>=nums[i-2]) nums[i-1]=nums[i];
                else nums[i]=nums[i-1];
                --cnt;
            } 
        }
        return true;
    }
};
```
