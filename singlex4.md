# Summary Ranges
## 问题分析:
有序数组总结区间,主要利用遍历找出连续的序列,每次检查下一个数是不是递增的
## 编程实现:
```C++
class Solution {
public:
    vector<string> summaryRanges(vector<int>& nums) {
        vector<string>res;
        int i=0,n=nums.size();
        while(i<n) 
        {
            int j=1;
            while(i+j<n&&nums[i+j]-nums[i]==j)
            ++j;
            res.push_back(j<=1?to_string(nums[i]) : to_string(nums[i])+"->"+to_string(nums[i+j-1]));
            i+=j;
        }
        return res;
    }
};
```
