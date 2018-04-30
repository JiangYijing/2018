# Search for a Range
## 问题分析:
给出数组有序条件,利用二分法解决
## 编程实现:
```C++
class Solution {
public:
    vector<int> searchRange(vector<int>& nums, int target) {
        int n=(int)nums.size();
        int pos=binarySearch(nums,0,n-1,target);
        vector<int> result;
        int low=-1;
        int high=-1;
        if(pos>=0)
        {
            low=pos;
            int l=low;
            while(l>=0) 
            {
                low=l;
                l=binarySearch(nums,0,low-1,target);
            }
            high=pos;
            int h=high;
            while(h>=0)
            {
                high=h;
                h=binarySearch(nums,high+1,n-1,target);
            }
        }
        result.push_back(low);
        result.push_back(high);
        return result;
    }
    private:
    int binarySearch(vector<int> nums, int low, int high, int target){
        while(low<=high)
        {
            int mid=low+(high-low)/2;
            if(nums[mid]==target)
            {
                return mid;
            }
            if(target>nums[mid])
            {
                low=mid+1;
            }
            if(target<nums[mid]) 
            {
                high=mid-1;
            }
        }
        return -1;
    }
};
```
