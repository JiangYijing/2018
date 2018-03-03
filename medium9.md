# Combination Sum
## 问题分析：
求组合之和,需要另写一个递归函数,注意每次调用新的递归函数时,此时的target要减去当前数组的的数
## 编程实现：
```C++
class Solution {
public:
    vector<vector<int> > combinationSum(vector<int> &candidates, int target) {
        vector<vector<int> > res;
        vector<int> out;
        sort(candidates.begin(),candidates.end());
        combinationSumDFS(candidates,target,0,out,res);
        return res;
    }
    void combinationSumDFS(vector<int> &candidates, int target, int start, vector<int> &out, vector<vector<int> > &res) {
        if(target<0) return;
        else if(target==0) res.push_back(out);
        else 
        {
            for(int i=start;i<candidates.size();++i)
            {
                out.push_back(candidates[i]);
                combinationSumDFS(candidates,target-candidates[i],i,out,res);
                out.pop_back();
            }
        }
    }
};
```

# Combination Sum II
## 问题分析：
还是求组合之和,但是本题给定数组中的数字不能重复使用
## 编程实现：
```C++
class Solution {
public:
    vector<vector<int> > combinationSum2(vector<int> &num, int target) {
        vector<vector<int> > res;
        vector<int> out;
        sort(num.begin(), num.end());
        combinationSum2DFS(num, target, 0, out, res);
        return res;
    }
    void combinationSum2DFS(vector<int> &num, int target, int start, vector<int> &out, vector<vector<int> > &res) {
        if (target < 0) return;
        else if (target==0) res.push_back(out);
        else 
        {
            for(int i=start;i<num.size();++i)
            {
                if(i>start && num[i]==num[i-1) continue;
                out.push_back(num[i]);
                combinationSum2DFS(num,target-num[i],i+1,out,res);
                out.pop_back();
            }
        }
    }
};
```
