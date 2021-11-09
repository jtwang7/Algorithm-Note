[50. Pow(x,n)](https://leetcode-cn.com/problems/powx-n/description/)

# 题解
Tag: 递归、二分

## 思路
推荐题解：
* [分治+递归 简洁明了](https://leetcode-cn.com/problems/powx-n/solution/fen-zhi-di-gui-jian-ji-ming-liao-by-wo-huan-neng-c/)
* [带数学公式，清晰好懂。递归和迭代都可以](https://leetcode-cn.com/problems/powx-n/solution/dai-shu-xue-gong-shi-qing-xi-hao-dong-di-gui-he-di/)

## 代码
```js
/**
 * @param {number} x
 * @param {number} n
 * @return {number}
 */
var myPow = function (x, n) {
  if (n === 0) return 1; // 递归终止条件

  // 处理幂小于 0 的情况
  if (n < 0) {
    return 1 / myPow(x, -n);
  }

  // 处理幂为奇数的情况
  if (n % 2) {
    return x * myPow(x, n - 1)
  }

  // 幂为偶数时，可以递归二分幂指数
  return myPow(x * x, n / 2);
};
```