Implement [pow(*x*, *n*)](http://www.cplusplus.com/reference/valarray/pow/), which calculates *x* raised to the power *n* (x^n).

**Example 1:**

```
Input: 2.00000, 10
Output: 1024.00000
```

**Example 2:**

```
Input: 2.10000, 3
Output: 9.26100
```

**Example 3:**

```
Input: 2.00000, -2
Output: 0.25000
Explanation: 2-2 = 1/22 = 1/4 = 0.25
```

**Note:**

- -100.0 < *x* < 100.0
- *n* is a 32-bit signed integer, within the range [−231, 231 − 1]

看到这道题有点被吓住了的感觉，脑海中没有什么思路。第一反应

- 也许需要位移运算
- 肯定不能暴力算出

想了一晚上，也没什么头绪，最后看了讨论中的一种解法，才知道原来是用递归。才发现很久不练习，大脑已经愚钝了。个人感觉递归的关键点就是要找到临界条件，保证执行栈都可以顺利推出。

```javascript
var myPow = function(x, n) {
    if (n === 0) {
        return 1
    }
    if (n < 0) {
        x = 1 / x;
        n = -n;
    }
    return n % 2 === 0 ? myPow(x * x, n / 2) : x * myPow(x, n - 1);

};
```

