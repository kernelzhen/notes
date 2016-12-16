### re 正则

``` python
常用正则表达式符号
'.'     默认匹配除\n之外的任意一个字符，若指定flag DOTALL,则匹配任意字符，包括换行
'^'     匹配字符开头，若指定flags MULTILINE,这种也可以匹配上(r"^a","\nabc\neee",flags=re.MULTILINE)
'$'     匹配字符结尾，或e.search("foo$","bfoo\nsdfsf",flags=re.MULTILINE).group()也可以
'*'     匹配*号前的字符0次或多次，re.findall("ab*","cabb3abcbbac")  结果为['abb', 'ab', 'a']
'+'     匹配前一个字符1次或多次，re.findall("ab+","ab+cd+abb+bba") 结果['ab', 'abb']
'?'     匹配前一个字符1次或0次
'{m}'   匹配前一个字符m次
'{n,m}' 匹配前一个字符n到m次，re.findall("ab{1,3}","abb abc abbcbbb") 结果'abb', 'ab', 'abb']
'|'     匹配|左或|右的字符，re.search("abc|ABC","ABCBabcCD").group() 结果'ABC'
'(...)' 分组匹配，re.search("(abc){2}a(123|456)c", "abcabca456c").group() 结果 abcabca456c
 
 
'\A'    只从字符开头匹配，re.search("\Aabc","alexabc") 是匹配不到的
'\Z'    匹配字符结尾，同$
'\d'    匹配数字0-9
'\D'    匹配非数字
'\w'    匹配[A-Za-z0-9]
'\W'    匹配非[A-Za-z0-9]
's'     匹配空白字符、\t、\n、\r , re.search("\s+","ab\tc1\n3").group() 结果 '\t'

re.match() # 从头匹配
re.search() #匹配第一个
re.findall() #将匹配到的所有内容都放到一个list里面
```
* re.match()

``` python
        # 无分组
        r = re.match("h\w+", origin)
        print(r.group())     # 获取匹配到的所有结果
        print(r.groups())    # 获取模型中匹配到的分组结果
        print(r.groupdict()) # 获取模型中匹配到的分组结果

        # 有分组

        # 为何要有分组？提取匹配成功的指定内容（先匹配成功全部正则，再匹配成功的局部内容提取出来）

        r = re.match("h(\w+).*(?P<name>\d)$", origin)
        print(r.group())     # 获取匹配到的所有结果
        print(r.groups())    # 获取模型中匹配到的分组结果
        print(r.groupdict()) # 获取模型中匹配到的分组中所有执行了key的组
In [108]: origin = 'hello haha bcd alex 1ge haha acd 19'

In [104]: r = re.match("(?P<n1>h)(?P<n2>\w+)", origin)

In [105]: print(r.group())
hello

In [106]: print(r.groups())
('h', 'ello')

In [107]: print(r.groupdict())
{'n2': 'ello', 'n1': 'h'}
```