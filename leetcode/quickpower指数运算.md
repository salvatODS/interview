#### 快速指数运算

怎样算一个大的指数操作？（e.g. 2的200万次方）

详细题解见leetcode50题

简单来说，就是通过数学公式
```
x^n  = (x^2)^(n/2)
```

设指数为n，则能够通过递归在log n 的时间复杂度下解决

```
double dfs(double x, int n) {
if (n % 2) {  // odd power, times an extra x
    return dfs(x*x, n/2) * x;
} else {  // even power
    return dfs(x*x, n/2);
}
}
```