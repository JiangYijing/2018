# Course Schedule
## 问题分析：
课程清单,在有向图中检测环,用两个端点表示一条边用边表示有向图
## 编程实现：
```C++
class Solution {
public:
    bool canFinish(int numCourses, vector<vector<int>>& prerequisites) {
        vector<vector<int> > graph(numCourses, vector<int>(0));
        vector<int> in(numCourses, 0);
        for (auto a : prerequisites) 
        {
            graph[a[1]].push_back(a[0]);
            ++in[a[0]];
        }
        queue<int> q;
        for(int i=0;i<numCourses;++i)
        {
            if(in[i]==0)
            q.push(i);
        }
        while(q.empty())
        {
            int t=q.front();
            q.pop();
            for(auto a : graph[t])
            {
                --in[a];
                if(in[a]==0) q.push(a);
            }
        }
        for(int i=0;i<numCourses;++i)
        {
            if(in[i]!=0)
            return false;
        }
        return true;
    }
};
```
