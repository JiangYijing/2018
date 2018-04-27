#   Number of Boomerangs 
## 问题分析:
回旋镖的数量的计算,本题定义了一种类似回旋镖形状的三元组结构,并要求第一个点和第二个点之间的距离跟第一个点和第三个点之间的距离相等,提供n个点,找出回旋镖的个数
## 编程实现:
```C++
class Solution {
public:
    int numberOfBoomerangs(vector<pair<int, int>>& points) {
        int res=0;
        for(int i=0;i<points.size();++i) 
        {
            unordered_map<int, int> m;
            for(int j=0;j<points.size();++j)
            {
                int a=points[i].first-points[j].first;
                int b=points[i].second-points[j].second;
                ++m[a*a+b*b];
            }
            for(auto it=m.begin();it!=m.end();++it) 
            {
                res+=it->second*(it->second-1);
            }
        }
        return res;
    }
};
```
