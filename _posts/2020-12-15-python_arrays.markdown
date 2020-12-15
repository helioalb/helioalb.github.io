---
layout: post
title:  "Python arrays"
date:   2020-12-15 05:45:03 -0300
categories: algorithm
---

## Defining an array

```python
array = [1, 2 , 3, 'test', True, False, 0.1]
```

## Accessing the first element

```python
array[0]

1
```

## Accessing the last element

```python
array[-1]

0.1
```

## Accessing the before last

```python
array[-2]
False
```

## Acessing a interval

Accessing from second until thirth elements

```python
array[1:3]

[2, 3]
```

## Accessing a invalid position

```python
array[130]

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```

## Length of an array

```python
len(array)

7
```

Is a good practise keep the same type for all elements of an array. For examplo

```python
numbers = [7, 6, 5, 4, 3, 2, 1]
```

## Sorting an array

```python
numbers.sort()

numbers
[1, 2, 3, 4, 5, 6, 7]
```

If you don't want change the original array, use the `sorded` function.

```python
numbers = [9, 8, 7, 6, 5, 4]

sorded(numbers)
[4, 5, 6, 7, 8, 9]

numbers
[9, 8, 7, 6, 5, 4]
```

## Adding at the first

You will use the `.insert` method. Note that this operation will shift all elements to the right. Avoid use it.

```python
numbers = [1, 2, 3]

numbers.insert(0, 999)

numbers
[999, 1, 2, 3]
```

## Adding at the end

It is the prefered way

```python
numbers = [1, 2, 3]
numbers.append(999)

numbers

[1, 2, 3, 999]
```

## Removing a item (by element)

```python
numbers = [1, 2, 3, 4, 999, 5, 6]

numbers.remove(999)

numbers
[1, 2, 3, 4, 5, 6]
```

## Removing a item (by position)

```python
numbers = [1, 2, 3, 4, 999, 5, 6]

del numbers[4]

numbers
[1, 2, 3, 4, 5, 6]
```


Note that all items at the right will be shifted to the left after this operation.

To improve performance you can change the value that you want to delete to `None`.

```python
numbers = [1, 2, 3, 4, 999, 5, 6]
numbers[4] = None

numbers
[1, 2, 3, 4, None, 5, 6]
```

## min and max

```python
numbers = [1, 2, 3, 4, 5, 6]

min(numbers)
1

max(numbers)
6
```

## Finding an element using the bisect lib

```python
import bisect

numbers = [9, 2, 6, 4, 3]
numbers.sort()

numbers
[2, 3, 4, 6, 9]

bisect.bisect(numbers, 6)
4
```

## Adding an element with bisect

```python
import bisect

numbers = [2, 3, 4, 6, 9]

bisect.insort(numbers, 888)

numbers

[2, 3, 4, 6, 9, 888]
```

## Range of items

```python
numbers = range(10)
numbers
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

## Two dimensions

```python
matrix = [[1,2], [3,4]]

matrix[0][0]
1
```

## Pointer to an array

```python
A = [1, 2, 3]
B = A
B[0] = 999

B
[999, 2, 3]

A
[999, 2, 3]
```

## Copy a list

```python
A = [1, 2, 3]
B = list(A)
B[0] = 999

B
[999, 2, 3]

A
[1, 2, 3]
```

## Copy

```python
import copy

A = [{'name': 'Helio', 'last_name': 'Albano'}]

B = copy.copy(A)

B[0]['last_name'] = 'Oliveira'

B

[{'last_name': 'Oliveira', 'name': 'Helio'}]

A
[{'last_name': 'Oliveira', 'name': 'Helio'}]
```

## Deepcopy

```python
import copy

A = [{'name': 'Helio', 'last_name': 'Albano'}]

B = copy.deepcopy(A)

B[0]['last_name'] = 'Oliveira'

B

[{'last_name': 'Oliveira', 'name': 'Helio'}]

A
[{'last_name': 'Albano', 'name': 'Helio'}]
```

## Inverting items

```python
a = [1, 2, 3, 4]

a[1], a[2] = a[2], a[1]

a

[1, 3, 2, 4]
```
