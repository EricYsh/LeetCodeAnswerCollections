# LeetCodeAnswerCollections

LeetCode题解精选代码收集 - Java版【持续更新中】

> 收集 LeetCode 刷题后的优质代码，附有思路，方便面试前复习回看
>
> 超链接指向 **LeetCode 中国**官网对应题目



## 22. generate-parentheses【[括号生成](https://leetcode-cn.com/problems/generate-parentheses/)】【中等】

这是一道递归题目，想法很重要，保证括号合法性是另一个要点

```java
		private List<String> result;

    public List<String> generateParenthesis(int n) {
        result = new ArrayList<String>();
        _generate(0, 0, n, "");
        return result;
    }

    private void _generate(int left, int right, int n, String s) {
        //terminator
        if (left == n && right == n) {
            result.add(s);
        }

        if (left < n)
            _generate(left + 1, right, n, s + "(");
        if (right < left)
            _generate(left, right + 1, n, s + ")");
    }
```



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

