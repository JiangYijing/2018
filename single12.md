# Search a 2D Matrix
## 问题分析：
将2D矩阵转化成1行数组的对应表,利用二分查找在原矩阵中定位到所需要的值
## 编程实现：
```C++
public boolean searchMatrix(int[][] matrix, int target) {
         if(matrix.length==0||matrix[0].length==0||matrix==null)
              return false;
              
          int rows = matrix.length;
          int cols = matrix[0].length;
          
          int low = 0;
          int high = rows*cols-1;
         
         while(low<=high){
             int mid = (low+high)/2;
             int midValue = matrix[mid/cols][mid%cols];
             if(midValue == target)
                 return true;
             else if(midValue < target)
                 low = mid+1;
             else
                 high = mid-1;
         }
         return false;
     }
  ```   
