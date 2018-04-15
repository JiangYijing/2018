# Top K Frequent Elements
## 问题分析：
选出数组中出现次数最多的k个元素,考虑用哈希表来做,建立数字和其出现次数的映射,然后再按照出现次数进行排序
## 编程实现：
```C++
class Solution {
public:
    vector<int> topKFrequent(vector<int>& nums, int k) {
        unordered_map<int, int> m;
        priority_queue<pair<int, int>> q;
        vector<int> res;
        for(auto a:nums) ++m[a];
        for(auto it:m) q.push({it.second,it.first});
        for(int i=0;i<k;++i) 
        {
            res.push_back(q.top().second);q.pop();
        }
        return res;
    }
};
```
