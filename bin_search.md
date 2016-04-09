

```python
python 风格二分查找
```


```python
为啥 要用二分查找呢？ 自带list.index（）
    优势：内置方法
    劣势： 1.list.index(value)  value 没有在list内部 就会弹出的异常ValueError
          2.时间复杂度 O(n)  大数据列表，就发现搜索异常慢
        
优先方法：二分搜索

1.时间复杂度 O(lg(n))，规模逐次减半

Note：
    先决条件：列表顺序已经排好
```


```python
二分搜索的主要思想：
1.选取中间的数 如果中间的数等于 value 就跳出 并返回当前值
             如果中间的数大于 value 就在左边的规模里
             如果中间的数小于 value 就在右边的规模里
        
2.不管是在左边的规模还是右边的规模里，再按照 1 的方法执行
```


```python
L = [i for i in range(10)]
```


```python
def bin_search(L, value,low,high):
    if high < low:
        return -1
    mid = int((low + high) / 2) #python3 中两个整数相除是小数
    if L[mid] > value:
        return bin_search(L, value, low, mid-1)
    elif L[mid] < value:
        return bin_search(L, value, mid+1, high)
    else:
        return mid
```


```python
# 测试 4 号 数字
```


```python
print(bin_search(L,4,0,9))
```

    4



```python

```
