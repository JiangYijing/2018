# Merge Intervals
## 问题分析：
合并区间,先排序再合并,把第一个区间存入结果中,然后从第二个开始遍历区间.若结果中最后一个区间和遍历的当前区间无重叠则直接将当前区间存入结果中,有重叠就
将结果中最后一个区间的end值更新为结果中最后一个区间的end和当前end值之中的较大值继续遍历区间集
## 编程实现：
```C++
class Solution {
public:
    vector<Interval> merge(vector<Interval>& intervals) {
        if(intervals.empty()) return {};
        sort(intervals.begin(),intervals.end(),[](Interval &a,Interval&b) 
        {return a.start < b.start;});
        vector<Interval> res{intervals[0]};
        for(int i=1;i<intervals.size();++i) {
            if (res.back().end<intervals[i].start)
            {
                res.push_back(intervals[i]);
            } 
            else
            {
                res.back().end=max(res.back().end,intervals[i].end);
            }
        }   
        return res;
          }
          };
```
