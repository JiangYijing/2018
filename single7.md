# Max Points on a Line
## 问题分析：
给二维点求共点线的个数,利用公式y=ax+b利用赋值斜率来代表直线计算个数
## 编程实现：
```C++
/**
 * Definition for a point.
 * struct Point {
 *     int x;
 *     int y;
 *     Point() : x(0), y(0) {}
 *     Point(int a, int b) : x(a), y(b) {}
 * };
 */
class Solution {
public:
    int maxPoints(vector<Point>& points) {
        int res=0;
        for(int i=0;i<points.size();++i)
        {
            unordered_map<float,int> m;
            int duplicate=1;
            for(int j=i+1;j<points.size();++j) {
                if(points[i].x= points[j].x && points[i].y==points[j].y)
                {
                    ++duplicate;
                } 
                else if(points[i].x==points[j].x)
                {
                    ++m[INT_MAX];
                } 
                else 
                {
                    float slope=(float)(points[j].y-points[i].y)/(points[j].x-points[i].x);
                    ++m[slope];
                }
            }
            res=max(res, duplicate);
            for(auto it=m.begin();it!=m.end(); ++it) 
            {
                res=max(res,it->second+duplicate);
            }
        }
        return res;
    }
};
```
