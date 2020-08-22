---
title: Python数据类型
date: 2020-08-22 10:24:33
tags: Python
categories: Python
thumbnail: /img/Python/1.jpg
---
找补找补
<!-- more -->

# Int
`Python`作为动态语言可以直接定义*variable*,Python中万物都是**variable**

``` python
a = 10
b = 3.14
c = 999999999999999
```

# String
`sting` ---> 字符串,在python中有多种方式声名字符串
+ ' ' 单引号
+ " " 双引号
+ ''' ''' 三个引号开始,三个引号结束,表示多行内容
+ r ' '  引号前面加`r`表示引号里面的内容不转义

> `\` 转义字符
``` python
word = 'hello world'
name = "Ben"
date = "2020\"7.16"
print(date)

line = '''line1
line2
line3
'''
print(line)

example = 'hello \n world'
print(example)
```

字符串可以进行编码,解码操作
- encode() Text ---> bytes
- decode() bytes ---> Text

# Bool
布尔值 True False 真假
+ or 只要一个为True就为真
+ and 必须所有的条件都为True才为真,否则为False
+ not 取反

``` python
print(True or False) # False
print(True and False) # False
print(not 9>3) # False
```

# None
`None`是个特殊的`空值`,**它并不是0**

# List
`列表`一种有序集合,可随时添加删除角色

``` python
teacher = ['John','Ben',1000]
print(teacher)
print(len(teacher))

# list第一位的索引是`0`,`-1`是倒数第一位
word = ['today','job','sister'] 
print(word[0]) # today
print(word[2]) # sister
print(word[-1]) # sister
prin(word([-3])) # today

# append()将数据追加到末尾
app = ['douyin','kuaisho']
app.append('huoshan')
print(app)

# insert()将数据添加到对应元素
app.insert(0,'weishi') 
print(app)

# pop()删除对应元素
math = [100,1000,200,20000]
math.pop(0)
print(math)

# 替换指定元素
L = ['gun','sos','beach']
L[2] = 'fuck'
print(L)

# 二维数组
p = ['asp','php']
s = ['python','java',p,'scheme']
print(len(s))
print(s[2][1]) # php

# 多维数组修改元素
eg = ['hello','hoi',[1,2],3]
eg[2].insert(0,'good')
print(eg)
```

# Tuple
`元组` tuple只能读取不能修改

``` python
exam = ('math','english')
print(exam[0])

# 定义一个空tuple
d = ()

# 定义一个元素的tuple
t = (1,) # `()`是小括号,为了不产生歧义一个元素的tuple后必须加上`,`
```


# Dict
`字典` 一个Key对应一个Value

``` python
# dict.['Key']
dictionary = {'America':'fuck you','China':'very good','age':18}

# 判断Key是否在dict里 ---> Key in dict
print('America' in dictionary)

# 删除一个key 
dictionary.pop('age')
print(dictionary)
```

# Set
`集合`

``` python
s = set([1,2,3])
print(type(s))
print(s)

# add() 追加元素到末尾,重复添加元素不变
s.add(4)
print(s)
s.add(4)
print(s)

# remove() 删除一个元素
s.remove(4)
print(s)
```

# End
- [x] int 十进制整数
- [x] string 字符串:单引号,双引号,`'''` `'''`
- [x] list 多个数据类型的列表:`append()`追加一个元素 `insert()`指定索引位置添加元素 `pop()`删除一个元素
- [x] tuple `元组`,定义一个元素的tuple要在后面加上`,`
- [x] dict `字典`:`pop()`删除一个Key
- [x] set `集合`
