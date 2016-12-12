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
