>Given an array of integers, return indices of the two numbers such that they add up to a specific target. 
You may assume that each input would have exactly one solution, and you may not use the same element twice.
>
> Given nums = [2, 7, 11, 15], target = 9,
>
> Example:
> Because nums[0] + nums[1] = 2 + 7 = 9,
> return [0, 1].

刷LeetCode首先要清楚题目给出的条件，这样我们才能在正确的假设下，写出正确的代码

上面的题目信息给出了两个关键点

1. 每次输入都是有一个解的，所以不存在没有解的情况
2. 同一元素不能使用两次

清楚题目条件，稍有基础同学都会想到使用嵌套的for循环就能解决问题，只不过时间复杂度为O(n^2),并不是优秀解法，代码如下：

```javascript
var twoSum = function(nums, target) {
    var length = nums.length
    for (var i = 0; i < length - 1; i++) {
        for (var j = i + 1; j < length; j++) {
            if (nums[i] + nums[j] === target) {
                return [i,j]
            }
        }
    }
}
```

暂时没有想到更加好的解法，想到好的解法会进行更新