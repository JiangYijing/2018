#  Rotate Array
## 问题分析：
旋转数组,利用函数关系交换数字到新数组。
## 编程实现：
```C++
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        vector<int> t=nums;
        int i=0;
        for(i=0;i<nums.size();++ i)
        {
            nums[(i+k)%nums.size()]=t[i];
        }
    }
};
```

# Number of 1 Bits
## 问题分析：
判断整数中多少个1,既在n中又是1的数字个数。(主要先读懂理解题目含义,明白所给名词的意义)
## 编程实现：
```C++
class Solution {
public:
    int hammingWeight(uint32_t n) {
        int res = 0;
        int i=0;
        for(i=0;i<32;++i)
        {
            res+=(n&1);
            n=n>>1;
        }
        return res;
    }
};
```
