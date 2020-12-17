---
layout: post
title:  "Python strings"
date:   2020-12-17 05:45:03 -0300
categories: algorithm
---

## Defining a string

```python
s = 'my first string'
```

## Repeting a string

```python
s = 'cuelhino, se eu fosse como tu, tirava a mao do bolso e enfiava a mao no ' * 3
s
'cuelhino, se eu fosse como tu, tirava a mao do bolso e enfiava a mao no cuelhino, se eu fosse como tu, tirava a mao do bolso e enfiava a mao no cuelhino, se eu fosse como tu, tirava a mao do bolso e enfiava a mao no '
```


## Replace

```python
'javascriptexample'.replace('javascript', 'python')
'pythonexample'
```

## To Lower

```python
'PYthon'.lower()
'python'
```

## To Upper

```python
'python'.upper()
'PYTHON'
```

## Starts with

```python
'pythonexample'.startswith('python')
True
```

```python
'pythonexample'.startswith('example')
False
```

## Ends with

```python
'pythonexample'.endswith('python')
False
```

```python
'pythonexample'.endswith('example')
True
```

## Split

```python
'Helio Albano de Oliveira'.split(' ')
['Helio', 'Albano', 'de', 'Oliveira']
```

```python
'test1, test2, test3'.split(',')
['test1', ' test2', ' test3']
```

## Remove spaces (left and right)

```python
'        Helio Albano de Oliveira       '.strip()
'Helio Albano de Oliveira'
```


## Remove spaces (only left)

```python
'        Helio Albano de Oliveira'.strip()
'Helio Albano de Oliveira'
```

## Remove spaces (only left)

```python
'        Helio Albano de Oliveira         '.lstrip()
'Helio Albano de Oliveira         '
```


## Remove spaces (only right)

```python
'        Helio Albano de Oliveira         '.rstrip()
'        Helio Albano de Oliveira'
```

## Title

```python
'helio albano'.title()
'Helio Albano'
```

## Substrings

```python
s = '0123456789'

s[0]
'0'

s[1]
'1'
```

```python
s = '0123456789'

s[0:5]
'01234'
```

## Invert string

```python
s[::-1]
'9876543210'
```
