# Gas Station
## 问题分析：
N个加油站连成环状,给定gas和cost数组计算返回能够可以环绕这条回路的油站的索引
## 编程实现：
```C++
class Solution {
public:
    int canCompleteCircuit(vector<int> &gas, vector<int> &cost) {
        if(gas.size()== 0||cost.size()==0||gas.size()!=cost.size()) return -1;
        int total=0,sum=0,start=0;
        for(int i=0;i<gas.size();++i)
        {
            total+=(gas[i]-cost[i]);
            if(sum<0)
            {
                sum=(gas[i]-cost[i]);
                start=i;
            }
            else sum+=(gas[i]-cost[i]);
        }
        return total < 0 ? -1 : start; 
    }
};
```
