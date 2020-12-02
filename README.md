# LeetCodeAnswerCollections

LeetCode题解精选代码收集 - Java版

> 收集 LeetCode 刷题后的优质代码，附有思路，方便面试前复习回看
>
> 超链接指向LeetCode中国官网对应题目



## 70.climbing-stairs 【[爬楼梯](https://leetcode-cn.com/problems/climbing-stairs/)】【简单】

这道题直接递归会超时，这里引入动态规划的思想

```java
public int climbStairs(int n) {
  			
        if(n <= 2) return n;

        int x = 1;
        int y = 2;
        for(int z =3;z <= n; z++){
            int temp = x + y;
            x = y;
            y = temp;
        }
        return y;
    }
```

