

```python
# 问题分析 
# 斐波那契数列 用 递归实现会产生大量的重复的子序列
# fib(3)= fib(2) + fib(1) = fib(1) + fib(0) + fib(1) 逐次递归
# 如何避免不算重复的子序列？
```


```python

memo = {0:0, 1:1}
def fib(n):
    if not n in memo:
        memo[n] = fib(n-1)+fib(n-2)
    return memo[n]
```


```python
[fib(i) for i in range(10)]
```




    [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]




```python
感悟： 
 1.字典也可以迭代
 2.字典迭代出的值是key
 3.取字典的值用dict[key]  记住key 应该被【】列表包围
 4.if not varible in memo：  if 不仅可以用 判断在里面 还以用来判断不在里面
```


```python
# 问题： 还有无其他解法

```


```python
def fib1(n):
    a, b = 0, 1
    for i in range(n):
        a, b = b, a+b
    return a
```


```python
感悟：
    1.原来的两个数字a,b，用新的两个数字去替换
    2.a <----b
    3.b <----a + b
    4.交换两个数字 a，b = b ，a
    5.返回值 <----- a
```


```python
[fib1(i) for i in range(10)]
```




    [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]




```python

```
