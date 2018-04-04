#  Median of Two Sorted Arrays
## 问题分析：
求两个有序数组中的中位数，并且指定时间复杂度,在两个单独的数组里使用二分法查找需要定义一个函数,并且要判断两个数组相加后的长度的奇偶性,分情况讨论,
奇数直接找中间,偶数找中间之和平均值 
## 编程实现：
```C++
class Solution {
public:
    double findMedianSortedArrays(vector<int>& nums1, vector<int>& nums2) {
        int total=nums1.size()+nums2.size();
        if(total%2==1)
        {
            return findKth(nums1,0,nums2,0,total/2+1);
        } 
        else
        {
            return(findKth(nums1,0,nums2,0,total / 2)+findKth(nums1,0,nums2,0,total/2+1))/2;
        }
    }
    double findKth(vector<int>&nums1,int i,vector<int>&nums2,int j,int k) {
        if(nums1.size()-i>nums2.size()-j) return findKth(nums2,j,nums1,i,k);
        if(nums1.size()==i) return nums2[j+k-1];
        if(k==1) return min(nums1[i],nums2[j]);
        int pa=min(i+k/2,int(nums1.size())),pb=j+k-pa+i;
        if(nums1[pa-1]<nums2[pb-1])  return findKth(nums1,pa,nums2,j,k-pa+i);
        else if(nums1[pa-1]>nums2[pb-1]) return findKth(nums1,i,nums2,pb,k-pb+j);
        else  return nums1[pa-1];
    }
};
```
