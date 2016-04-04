

```python
问题
定义一个int型的一维数组，包含10个元素，分别赋值为1~10， 然后将数组中的元素都向前移一个位置，

即，a[0]=a[1],a[1]=a[2],…最后一个元素的值是原来第一个元素的值，然后输出这个数组。
```


```python
L = [i for i in range(1,11)]
a = L.pop(0)
L.append(a)
print(L)
```

    [2, 3, 4, 5, 6, 7, 8, 9, 10, 1]



```python
反思：
    array.pop([i])
    1.Removes the item with the index i from the array and returns it. 
    2.The optional argument defaults to -1, so that by default the last item is removed and returned.
    3.在python环境下，列表重头删除。元素各个位置发生变化
```


```python

```


```python

```
