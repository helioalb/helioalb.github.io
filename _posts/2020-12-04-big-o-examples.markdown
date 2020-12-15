---
layout: post
title:  "Big O examples"
date:   2020-12-04 05:45:03 -0300
categories: algorithm
---

## O(n)

```python
def find_sum(items):
    sum = 0

    for item in items
        sum += item

    return sum
```

```python
def find_max(items):
    max = 0

    for item in items:
        if item > max:
          max = item

    return max
```

## O(1)

doesn't exist any iteraction

```python
def hello_world():
    print('hello world')
```

```python
def return_the_same(n):
    return n
```

```python
def first(items):
    return items[0]
```

```python
def increase_queue():
    the_queue = queue.Queue()
    the_queue.put(2)
```

## O(n<sup>2</sup>)

```python
def find_common_elements(items1, items2):
    result = []

    for item1 in items1:
        for item2 in items2:
            if item1 == item2:
                result.append(item1)

    return result
```

## O(2<sup>n</sup>)

solve with **2** sub-problems

```python
def fibonacci(num):
    if num <= 1:
        return num

    return fibonacci(n - 2) + fibonacci(n - 1)
```

## O(n!)

```python
def factorial(n):
    for x in xrange(n):
        print x
        factorial(n - 1)
```

![Big O complexity chart](/images/big-o-complexity-chart.png)
