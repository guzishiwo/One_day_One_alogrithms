

```python
# 采用的思想（Divide-and-ConquerMethod）
# 1.把一个问题分解成若干具有同样的性质的子问题
# 2.递归的解决同样的问题
# 3.然后把若干问题的解合并变成问题的解。
# 一：分解问题
# 1.由三个对象组成，1.左子区域 < 2.pivot（轴点）<3.右子区域
# 二：求解
# 2.通过递归调用，求解左半部分，和右半部分。
# 三：合并
# 本身就是已经排号的序列，无需合并
```


```python
#第一版  python 快速排序算法
def quick_sort(L):
    left = []
    right = []
    pivotList = []
    if len(L) <= 1:
        return L
    else:
        pivot = L[0]
        for i in L:
            if i < pivot :
                left.append(i)
            elif i > pivot :
                right.append(i)
            else:
                pivotList.append(i)
        left = quick_sort(left)
        right = quick_sort(right)
        
        return left + pivotList + right
                                                                                                                                                
```


```python
L = [8, 10, 9, 6, 4, 16, 5, 13, 26, 18, 2, 45, 34, 23, 1, 7, 3]
```


```python
#快速排序后
print(quick_sort(L))
```

    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 13, 16, 18, 23, 26, 34, 45]



```python
# 排序优化版
def qsort(list):
    if not list:
        return []
    else:
        pivot = list[0]
        less = [x for x in list     if x <  pivot]
        more = [x for x in list[1:] if x >= pivot]
        return qsort(less) + [pivot] + qsort(more)
# 感悟：
# 1. 判断是否为列表 直接写 if not list
# 2. more  中 永远放到 pivot 右边 所以重 list【1：】开始切片
# 3.整数不能和列表相加
```


```python
L = [5,3,1,2]
print(qsort(L))
```

    [1, 2, 3, 5]



```python
#一句话函数版快排
def qsort2(L):
    return (qsort([y for y in L[1:] if y <  L[0]]) + L[:1] + qsort([y for y in L[1:] if y >= L[0]])) if len(L) > 1 else L
# 感悟 
# 1.[] if Before else after  if 前还可以是列表推导式 
# 2. 取基数时 L[:1]  你不知道具体位置 而是知道第一个数字
```


```python
print(qsort2(L))
```

    [1, 2, 3, 5]



```python

```
