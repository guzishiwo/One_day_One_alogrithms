

```python
定义一个int型的一维数组，包含40个元素，用来存储每个学员的成绩，循环产生40个0~100之间的随机整数，
(1)将它们存储到一维数组中，然后统计成绩低于平均分的学员的人数，并输出出来。
(2)将这40个成绩按照从高到低的顺序输出出来。
```


```python
感悟：
    1.from __future__ import division 作用？
        导入python未来支持(精确除法)
    2.sorted 和 list.sort()的区别
        1.sorted(iterable, cmp=None, key=None, reverse=False) --> new sorted list
        2.L.sort(cmp=None, key=None, reverse=False) -- stable sort *IN PLACE*

```


```python
from __future__ import division
import random
```


```python
def make_score(num):
    return ([random.randint(0,100) for i in range(num)])
```


```python
def less_avg(score_list):
    avg_score = sum(score_list)/len(score_list)
    less_avg_list = [i for i in score_list if i < avg_score]
    return len(less_avg_list)
```


```python
if __name__ == '__main__':
    score_list = make_score(20)
    print('the number of less avg is ',less_avg(score_list))
    sorted(score,reverse=True)
```

    the number of less avg is  11
    [95, 95, 91, 84, 81, 81, 75, 70, 65, 56, 55, 51, 50, 48, 43, 36, 30, 30, 15, 1]

