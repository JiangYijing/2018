# Assign Cookies
## 问题分析：
分点心 ~~(点心?什么点心?什么馅?)~~ 对于小朋友和饼干的匹配问题,问饼干能最多满足几个小朋友,考察贪婪算法  
由于每个小朋友需要的饼干数不同,所以需要数组排序使需要饼干数由小到大排列,然后再遍历饼干数组看是否满足,利用计数器记录满足的小朋友数量
## 编程实现：
```C++
class Solution {
public:
    int findContentChildren(vector<int>& g, vector<int>& s) {
         int res=0,p=0;
         sort(g.begin(),g.end());
         sort(s.begin(),s.end());
         for(int i=0;i<s.size();++i)
         {
             if(s[i]>=g[p])
             {
                 ++res;
                 ++p;
                 if(p>=g.size())
                 break;
             }
         }
         return res;
    }
};
```
