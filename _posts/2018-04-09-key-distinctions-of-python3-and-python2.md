---
title: Python3.x 和 Python2.x 的主要区别
layout: post
date: 2018-04-09 +0800
categories: pyCoder之路
tag: [python2,python3]
---

* content
{:toc}




## 1.性能 
Py3.0 运行 pystone benchmark 的速度比 Py2.5 慢 30%。Guido 认为 Py3.0 有极大的优化空间，在字符串和整形操作上可以取得很好的优化结果。Py3.1 性能比 Py2.5 慢 15%，还有很大的提升空间。 

## 2.编码 
Py3.X源码文件默认使用 utf-8 编码，这就使得以下代码是合法的：

``` 
    >>> 中国 = 'china' 
    >>>print(中国) 
    china 
```

## 3. 语法 
1）去除了 <>，全部改用 != 

2）去除``，全部改用 repr() 

3）关键词加入 as 和 with，还有 True, False, None 

4）整型除法返回浮点数，要得到整型结果，请使用 // 

```
python 2.4.2以前

   10/3      结果为 3     

python 3.0

   10 / 3 结果为 3.3333333333333335

   10 // 3 结果为 3
```

5）加入 nonlocal 语句。使用 noclocal x 可以直接指派外围（非全局）变量 

6）去除 print 语句，加入 print() 函数实现相同的功能。同样的还有 exec 语句，已经改为 exec() 函数，例如： 
   
```
     2.X: print "The answer is", 2*2 
     3.X: print("The answer is", 2*2) 
     2.X: print x,                              # 使用逗号结尾禁止换行 
     3.X: print(x, end=" ")                     # 使用空格代替换行 
     2.X: print                                 # 输出新行 
     3.X: print()                               # 输出新行 
     2.X: print >>sys.stderr, "fatal error" 
     3.X: print("fatal error", file=sys.stderr) 
     2.X: print (x, y)                          # 输出repr((x, y)) 
     3.X: print((x, y))                         # 不同于print(x, y)!
     
``` 

7）改变了顺序操作符的行为，例如 x<y，当 x 和 y 类型不匹配时抛出 TypeError 而不是返回随即的 bool 值  

8）输入函数改变了，删除了raw\_input，用 input 代替，Python3 中 input 得到的为 str ；Python2 的 input 的到的为 int 型，Python2 的 raw\_input 得到的为 str 类型 

```
  Python 2
>>> my_input = input('enter a number: ')
enter a number: 123

>>> type(my_input)
<type 'int'>

>>> my_input = raw_input('enter a number: ')
enter a number: 123

>>> type(my_input)
<type 'str'>


Python 3
>>> my_input = input('enter a number: ')

enter a number: 123

>>> type(my_input)
<class 'str'>
```

9）去除元组参数解包。不能 def(a, (b, c)):pass 这样定义函数了 

10）新式的 8 进制字变量，相应地修改了 oct() 函数。 

```
   2.X的方式如下： 
     >>> 0666 
     438 
     >>> oct(438) 
     '0666' 
   3.X这样： 
     >>> 0666 
     SyntaxError: invalid token (<pyshell#63>, line 1) 
     >>> 0o666 
     438 
     >>> oct(438) 
     '0o666' 
```

11）增加了 2 进制字面量和 bin() 函数 
    >>> bin(438) 
    '0b110110110' 
    >>> _438 = '0b110110110' 
    >>> _438 
    '0b110110110' 
   
12）支持class decorator。用法与函数decorator一样： 

```
    >>> def foo(cls_a): 
          def print_func(self): 
             print('Hello, world!') 
          cls_a.print = print_func 
          return cls_a 
    >>> @foo 
    class C(object): 
      pass 
    >>> C().print() 
    Hello, world! 
    
```

## 4. 字符串和字节串 
1）现在字符串只有str一种类型，但它跟2.x版本的unicode几乎一样。


2）关于字节串，请参阅“数据类型”的第2条目 

3) 

## 5.数据类型 

1）Py3.X 去除了 long 类型，现在只有一种整型—— int ，但它的行为就像 2.X 版本的 long 

2）新增了 bytes 类型，对应于 2.X 版本的八位串，定义一个 bytes 字面量的方法如下： 

```
    >>> b = b'china' 
    >>> type(b) 
    <type 'bytes'> 
```

bytes序列，一但形成，其内容是不可变的 ( 字节数组是可变的 )

```
s="ABCD"
b=s.encode("gbk")
print b[0]       # 显示   65
b[0] = 66   # 执行该句，出现异常: 'bytes' object does not support item assignment

a = bytearray(   10 )
a[0] = 25    # 可以用赋值语句更改其元素，但所赋的值必须在 0 ~ 255 之间
```

str 对象和 bytes 对象可以使用 .encode() (str -> bytes) or .decode() (bytes -> str) 方法相互转化。 

```
    >>> s = b.decode() 
    >>> s 
    'china' 
    >>> b1 = s.encode() 
    >>> b1 
    b'china' 
```

由于在 python 3.0中字符串以 unicode 编码存储，当写入二进制文件时，字符串无法直接写入（或读取），必须以某种方式的编码为字节序列后，方可写入。



3）dict 的 .keys()、.items 和 .values() 方法返回迭代器，而之前的 iterkeys() 等函数都被废弃。同时去掉的还有 dict.has_key()，用 in 替代它 

## 6.面向对象 

1）引入抽象基类（Abstraact Base Classes，ABCs）。 

2）容器类和迭代器类被ABCs化，所以cellections模块里的类型比Py2.5多了很多。

``` 
    >>> import collections 
    >>> print('\n'.join(dir(collections))) 
    Callable 
    Container 
    Hashable 
    ItemsView 
    Iterable 
    Iterator 
    KeysView 
    Mapping 
    MappingView 
    MutableMapping 
    MutableSequence 
    MutableSet 
    NamedTuple 
    Sequence 
    Set 
    Sized 
    ValuesView 
    __all__ 
    __builtins__ 
    __doc__ 
    __file__ 
    __name__ 
    _abcoll 
    _itemgetter 
    _sys 
    defaultdict 
    deque 
```

另外，数值类型也被 ABCs 化。关于这两点，请参阅 PEP 3119和PEP 3141。 

3）迭代器的 next() 方法改名为\_\_next\_\_()，并增加内置函数 next()，用以调用迭代器的 \_\_next\_\_() 方法 

4）增加了 @abstractmethod 和 @abstractproperty 两个 decorator，编写抽象方法（属性）更加方便。 

## 7.异常 

1）所以异常都从 BaseException继承，并删除了StardardError 

2）去除了异常类的序列行为和.message属性 

3）用 raise Exception(args)代替 raise Exception, args语法 

4）捕获异常的语法改变，引入了as关键字来标识异常实例，在Py2.5中： 

```
    >>> try: 
    ...    raise NotImplementedError('Error') 
    ... except NotImplementedError, error:

    ...    print error.message 
    ... 
    Error
```
 
在Py3.0中： 

```
    >>> try: 
          raise NotImplementedError('Error') 
        except NotImplementedError as error: #注意这个 as 
          print(str(error)) 
    Error 
``` 


5）异常链，因为__context__在3.0a1版本中没有实现 

## 8.模块变动 

1）移除了cPickle模块，可以使用pickle模块代替。最终我们将会有一个透明高效的模块。 

2）移除了imageop模块 

3）移除了 audiodev, Bastion, bsddb185, exceptions, linuxaudiodev, md5, MimeWriter, mimify, popen2,  
rexec, sets, sha, stringold, strop, sunaudiodev, timing和xmllib模块 

4）移除了bsddb模块(单独发布，可以从http://www.jcea.es/programacion/pybsddb.htm获取) 

5）移除了new模块 

6）os.tmpnam()和os.tmpfile()函数被移动到tmpfile模块下 

7）tokenize模块现在使用bytes工作。主要的入口点不再是generate_tokens，而是 tokenize.tokenize() 

## 9.其它 
1）在 Python 3 中，range() 是像 xrange() 那样实现以至于一个专门的 xrange() 函数都不再存在（在 Python 3 中xrange() 会抛出命名异常）。
在 Python 2 中 xrange() 创建迭代对象的用法是非常流行的。比如： for 循环或者是列表/集合/字典推导式。这个表现十分像生成器（比如。“惰性求值”）。但是这个 xrange-iterable 是无穷的，意味着你可以无限遍历。由于它的惰性求值，如果你不得仅仅不遍历它一次，xrange() 函数 比 range() 更快（比如 for 循环）。尽管如此，对比迭代一次，不建议你重复迭代多次，因为生成器每次都从头开始。

2）bytes 对象不能 hash，也不支持 b.lower()、b.strip() 和 b.split() 方法，但对于后两者可以使用 b.strip(b’\n\t\r \f’) 和 b.split(b’ ‘) 来达到相同目的 

3）zip()、map() 和 filter() 都返回迭代器。而 apply()、callable()、coerce()、execfile()、reduce() 和 reload() 函数都被去除了。
现在可以使用 hasattr() 来替换 callable(). hasattr() 的语法如：

```
hasattr(string, '__name__')
```

4）string.letters 和相关的 .lowercase 和 .uppercase 被去除，请改用 string.ascii_letters 等 


5）如果 x < y 的不能比较，抛出 TypeError 异常。2.x版本是返回伪随机布尔值的 

6）__getslice__系列成员被废弃。a[i:j]根据上下文转换为
```
a.__getitem__(slice(I, j))或 __setitem__和 
__delitem__调用 
```

7）file 类被废弃，在Py2.5中： 

```
    >>> file 
    <type 'file'> 
```

在Py3.X中： 

```
    >>> file 
    Traceback (most recent call last): 
    File "<pyshell#120>", line 1, in <module> 
       file 
    NameError: name 'file' is not defined
    
```


## 参考
1. [ http://www.cnblogs.com/codingmylife/archive/2010/06/06/1752807.html
]( http://www.cnblogs.com/codingmylife/archive/2010/06/06/1752807.html)
2. [ https://www.cnblogs.com/hanggegege/p/5840005.html]( https://www.cnblogs.com/hanggegege/p/5840005.html)