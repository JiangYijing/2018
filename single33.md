# 4Sum II
## 问题分析：
在四个数组中各取一个数字,使其和为0。
使用哈希表将时间复杂度缩小一倍,降到O(n2)
## 编程实现:
```C++
class Solution {
public:
    int fourSumCount(vector<int>& A, vector<int>& B, vector<int>& C, vector<int>& D) {
        int res=0;
        unordered_map<int, int> m;
        for(int i=0;i<A.size();++i)
        {
            for(int j=0;j<B.size();++j)
            {
                ++m[A[i]+B[j]];
            }
        }
        for(int i=0;i<C.size();++i)
        {
            for(int j=0; j<D.size();++j)
            {
                int target=-1*(C[i]+D[j]);
                res+=m[target];
            }
        }
        return res;
    }
};
```
