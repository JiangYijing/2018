# Remove Duplicates from Sorted Array II
## 问题分析：
最多允许两次重复,用count来记录重复的次数
## 编程实现：
```C++
class Solution {
public:
     int removeDuplicates(vector<int>& nums) {
        int n=nums.size;
        if(n<=2) return n;
        int pre=0,cur=1,count=1;
        while(cur<n)
        {
            if(nums[pre]==nums[cur]&&count==0) 
            ++cur;
            else 
            {
                if(nums[pre]==nums[cur]) 
                --count;
                else count=1;
                nums[++pre]=nums[cur++];
            }
        }
        return pre+1;
    }
};
```
