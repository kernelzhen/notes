**字符串是集合类型**
### 定义
``` python
In [2]: s = 'hello python'

In [3]: s = "hello python"

In [4]: s = '''hellp python'''

In [5]: s = """hello python"""
```
前两种完全一样，后两种完全一样

### 转义
``` python
In [8]: s = 'I like \npython'

In [10]: print(s)
I like
python

In [11]: path = 'C:\\windows\\nt\\system32'

In [12]: print(path)
C:\windows\nt\system32

In [13]: path = r'C:\windows\nt\system32' # 加r前缀代表此字符串是自然语言， 不用转义

In [14]: print(path)
C:\windows\nt\system32
```
### 下标操作
``` python
In [20]: s = "i'm python"

In [21]: s[3]
Out[21]: ' '

In [22]: s[4]
Out[22]: 'p'

In [23]: s[4] = 'c'  # 字符串是不可变的
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-23-4d21b9501525> in <module>()
----> 1 s[4] = 'c'

TypeError: 'str' object does not support item assignment

```
### 字符串是开迭代对象
``` python
In [24]: for c in s:
    ...:     print(c)
        ...:
        i
        '
        m
        
        p
        y
        t
        h
        o
        n'

In [25]: list(s)
Out[25]: ['i', "'", 'm', ' ', 'p', 'y', 't', 'h', 'o', 'n']
"'"]
```
### 字符串的操作
#### join
``` python
In [26]: lst = ['i', 'am', 'python']

In [28]: ' '.join(lst)
Out[28]: 'i am python'

In [29]: ','.join(lst)
Out[29]: 'i,am,python'
```
#### 分割
* split
* rsplit
* splitlines
* partition
* rpartition

*split*
``` python
In [30]: s = 'I love python'

In [31]: s.split()  # 默认使用空格分割
Out[31]: ['I', 'love', 'python']

In [32]: 'i    love python'.split()  #多个空格当成一个空格处理
Out[32]: ['i', 'love', 'python']

In [33]: 'i     love python'.split(' ') # 当指定以空格为分割时，每个空格都处理
Out[33]: ['i', '', '', '', '', 'love', 'python']

In [34]: 'i i i i i i i'.split(maxsplit=2) # split 从左往右分割字符串， maxsplit参数表示分割多少次， 默认值为-1 表示分割所有
Out[34]: ['i', 'i', 'i i i i i']
```

*rsplit*
rsplit是split从右往左的版本

``` python
In [37]: s = ''i am python
    ...: i love haha''
    
In [38]: s.splitlines()  #按行分割 并且返回结果不带换行符
Out[38]: ['i am python', 'i love haha']

In [39]: s.splitlines(True) #按行分割 并且返回结果带换行符
Out[39]: ['i am python\n', 'i love haha']'

```

