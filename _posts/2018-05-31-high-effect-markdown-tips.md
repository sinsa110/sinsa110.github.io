---
title: "[ 高效能系列 ] 易读易写的书写语言 Markdown"
layout: post
date: '2018-05-31 12:08:00 +0800'
categories: 高效能系列
tag: Markdown
---

* content
{:toc}


> 上一篇文章介绍了《如何绘制流程图》，在这篇文章，将介绍两个方面内容：
> 
> 1. Markdown 基本符号；
> 2. 一些编辑技巧工具。
> 


## 一、基本符号
### 1. 标题

语法：`	# + 空格 + 标题内容`

示例：

```
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题

一级标题
======
二级标题
-----
```

效果：

![image](https://user-images.githubusercontent.com/13688310/40984681-0ad3b3e2-6915-11e8-87ae-9bb39299c30b.png)



### 2. 换行

语法：`行末加两个空格和一个换行` 或在换行处插入`<br>`

示例：

```
未换行
的效果

已换行  
的效果

已换行<br>的效果

```
效果：

![image](https://user-images.githubusercontent.com/13688310/40984823-5949acde-6915-11e8-94a4-101e4884b4b3.png)

### 3. 分段

语法：段落间空一行 或在分段处插入`<br></br>`

示例：

```
未分段
的效果

已分段

的效果

已分段<br></br>的效果

```

效果：

![image](https://user-images.githubusercontent.com/13688310/40985017-bbfecdf0-6915-11e8-8499-3ad86e0e8e6d.png)


### 4. 加粗、斜体、删除线、底纹

语法：`**加粗**` `*斜体*` `~~删除线~~` （⚠️ 注意：符号和文字间没有空格）

示例：

```
**加粗**

*斜体*

~~删除线~~

` 底纹 `

```

效果：

![image](https://user-images.githubusercontent.com/13688310/40985265-574c8374-6916-11e8-9a0d-e56c9cb109d0.png)


### 5. 列表

语法：无序列表直接在文字前加 「 - 」 或者 「 * 」或者 「 + 」 即可，有序列表则直接在文字前加 「1.」「2.」「3.」 。在 「 * 」「 - 」「 + 」「1.」「2.」「3.」等前加两个空格键或者一个 tab 键就可以产生一个子列表。

	⚠️ 注意

		1. 符号要和文字之间加上一个字符的空格；
		
		3. 同一级的有序列表中的序号是连续的数字，它们与编号符号无关。

		   

示例：

```
#### 有序列表

1. text 1
2. text 2
  3. subtext 1
  4. subtext 2
5. text 3
6. text 4 

#### 无序列表

- text 1
- text 2
  - subtext 1
  - subtext 2
- text 3
- text 4 

```

效果：

![image](https://user-images.githubusercontent.com/13688310/40985361-83f177a4-6916-11e8-827d-605262b4531d.png)


### 6. 引用

语法：在文本内容之前加 「 > 」 即可将文本变成引用文本。「 >> 」 表示引用里面再套一层引用，依次类推。

	⚠️ 注意
	
		1. 如果 > 和 >> 嵌套使用的话，从 >> 退到 > 时，必须之间要加一个空格或者 > 作为过渡，否则默认为下一行和上一行是同一级别的引用。
		
		2. 引用标记里可以使用其他标记，如：有序列表或无序列表标记，代码标记等。

示例：

```
> 书山有路勤为径，学海无崖苦作舟
> 书山有路勤为径，学海无崖苦作舟
>> 书山有路勤为径，学海无崖苦作舟

>> 书山有路勤为径，学海无崖苦作舟
>>> 书山有路勤为径，学海无崖苦作舟
>>>> 书山有路勤为径，学海无崖苦作舟
>>>>> 书山有路勤为径，学海无崖苦作舟
>>>>>> 书山有路勤为径，学海无崖苦作舟
>>>>>>> 书山有路勤为径，学海无崖苦作舟

```

效果：

![image](https://user-images.githubusercontent.com/13688310/40985470-c6567e82-6916-11e8-94f5-af1f7da4afa1.png)


### 7. 图片和链接

语法：`![图片描述](图片的地址或存储路径)` `[文本内容](链接的地址)`

示例：

```
#### 博客链接
[my blog](https://sinsa110.github.io/)

#### 绘制流程图基本技巧中的图片
![决策流程图](https://user-images.githubusercontent.com/13688310/40121933-3aed351e-5955-11e8-99b9-96f742e6acf6.png)
```

效果：

![image](https://user-images.githubusercontent.com/13688310/40985557-fa21b948-6916-11e8-8a3c-984e68cb3702.png)


### 8. 表格

语法:

```
表头|表头|表头
---|:--:|---:
内容|内容|内容
内容|内容|内容

第二行分割表头和内容。
- 有一个就行，为了对齐，多加了几个
文字默认居左
-两边加：表示文字居中
-右边加：表示文字居右

```
⚠️ 注：原生的语法两边都要用 | 包起来。此处省略




 示例 & 效果：

![image](https://user-images.githubusercontent.com/13688310/41035258-aec6c030-69be-11e8-990f-0bf8f0a23360.png)


### 9. 脚注

语法：脚注总是成对出现的，「 [^1] 」作为标记，可以点击跳至末尾注解。「 [^1]: 」填写注解，不论写在什么位置，都会出现在文章的末尾。

示例：

```
### 脚注

标记[^1]
[^1]: 注解

```

效果：

![image](https://user-images.githubusercontent.com/13688310/41041273-325dedda-69d1-11e8-99bc-4d39db1e1d5f.png)




## 二、技巧 & 工具

### 1. 表格内容填充工具 [Tables Generator](https://www.tablesgenerator.com/markdown_tables)

Tables Generator 是一个可以在线快速生成 Text、Markdown 格式等多种格式表格的工具，支持在表格中填充数据，保证排版整齐，而且支持将Excel等的表格转化为markdown的格式，生成复制以后即可使用。

示例：

![markdown_table_new](https://user-images.githubusercontent.com/13688310/41035800-632b91b2-69c0-11e8-8abd-c7ecb102b553.gif)






## 参考资料
1. [http://www.markdown.cn](http://www.markdown.cn)
2. [https://blog.csdn.net/witnessai1/article/details/52551362](https://blog.csdn.net/witnessai1/article/details/52551362)
3. [https://segmentfault.com/markdown](https://segmentfault.com/markdown)

