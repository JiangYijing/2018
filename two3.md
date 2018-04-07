# Happy Number
## 问题分析：
将一个数按照个,十,百,千位来分解,然后求他们的平方的和,得到结果后重复这个过程,若最后结果为1则该数字为happ number,返回true,否则返回false
## 编程实现：
```C++
class Solution {
public:
    bool isHappy(int n) {
        set<int> s;
        while(n!=1)
        {
            int t=0;
            while(n)
            {
                t+=(n%10)*(n%10);
                n/=10;
            }
            n=t;
            if(s.count(n)) break;
            else s.insert(n);
        }
        return n==1;
    }
};
```

# Find Minimum in Rotated Sorted Array
## 问题分析：
寻找旋转有序数组的最小值,由于空间复杂度问题,选择使用二分法
## 编程实现：
```C++
class Solution {
public:
    int findMin(vector<int> &num) {
        int left=0,right=num.size()-1;
        if(num[left]>num[right]) 
        {
            while (left != (right - 1)) 
            {
                int mid=(left+right)/2;
                if(num[left]<num[mid]) left=mid;
                else right=mid;
            }
            return min(num[left],num[right]);
        }
        return num[0];
    }
};
```
