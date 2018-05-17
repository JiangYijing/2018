# Non-overlapping Intervals
## 问题分析：
非重叠空间,求需要至少移除多少个区间才能使剩下的区间没有重叠
## 编程实现：
```C++
class Solution {
public:
    int eraseOverlapIntervals(vector<Interval>& intervals) {
        int res=0,n=intervals.size(),last=0;
        sort(intervals.begin(),intervals.end(),[](Interval& a,Interval& b){return a.start<b.start;});
        for(int i=1;i<n;++i) {
            if(intervals[i].start<intervals[last].end)
            {
                ++res;
                if(intervals[i].end<intervals[last].end) 
                last = i;
            } 
            else
            {
                last=i;
            }
        }
        return res;
    }
};
```
