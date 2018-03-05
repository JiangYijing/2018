# Subsets
## 问题分析：
求集合中所有子集问题,要求子集中元素非递减序排列,所以需要将原数组排序,所以构造子集方法可以构造一个二叉树或从第二层开始迭代
## 编程实现：
```C++
class Solution {
public:
    vector<vector<int>> subsets(vector<int>& nums) {
        vector<vector<int>> res(1);
        sort(nums.begin(),nums.end());
        int i=0,j=0;
        for(i=0;i<nums.size();i++)
        {
            int resSize=res.size();
            for(j=0;j<resSize;j++)
            {
                res.push_back(res[j]);
                res.back().push_back(nums[i]);
            }
        }
        return res;        
    }
};
```
