# Bulls and Cows
## 问题分析：
猜数字,利用哈希表法来解,用一个map来找cows降低时间复杂度
## 编程实现：
```C++
public class Solution {
    public String getHint(String secret, String guess) {
        int[] map=new int[10];
        int bulls=0,cows=0;
        for(int i=0;i<secret.length();i++)
        {
            int s=secret.charAt(i)-'0';
            int g=guess.charAt(i)-'0';
            if(s==g)
                bulls++;
            else 
            {
                if(map[s] < 0)
                    cows++;
                if(map[g] > 0)
                    cows++;
                map[s]++;
                map[g]--;
            }
        }
        return bulls+"A"+cows+"B";
    }
}
```
