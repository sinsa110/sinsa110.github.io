---
layout: post
title:  字典树 Trie 结构介绍及其实现
date:   2018-01-04 01:08:00 +0800
categories: python
tag: Trie 树
---
* content
{:toc}


### 概念 {#concept}
Trie，又称前缀树或字典树，是一种有序树状的数据结构，用于保存关联数组，其中的键通常是字符串。

### 性质 {#xz}
1. 根节点不包含字符，除根节点外的每个节点只包含一个字符。
2. 从根节点到某一个节点，路径上经过的字符连接起来，为该节点对应的字符串。
3. 每个节点的所有子节点包含的字符串不相同。
4. 每个节点的所有子孙都有相同的前缀，也就是这个节点对应的字符串。

### 基本思想 {#sx}

#### 1、插入过程 {#cr}
这里以字母树为例，对于一个单词，从根开始，沿着单词的各个字母所对应的树中的节点分支向下走，直到单词遍历完，将最后的节点标记为红色，表示该单词已插入Trie树。

#### 2、查询过程 {#find}

同样的，从根开始按照单词的字母顺序向下遍历trie树，一旦发现某个节点标记不存在或者单词遍历完成而最后的节点未标记为红色，则表示该单词不存在，若最后的节点标记为红色，表示该单词存在。

### 应用 {#yy}
1. 关键词检索
2. 词频统计
3. 搜索提示
4. 作为辅助结构
5. ... ...



### 优缺点 {#yqd}
优点：时间复杂度小。它的插入和查询时间复杂度都为 O(k) ，其中 k 为 key 的长度，与 Trie 中保存了多少个元素无关。

缺点：空间消耗很高。

### 实现 {#sx}

#### python 版 {#python}

用嵌套字典来实现树结构

``` python
# !/usr/bin/env python
# -*- coding:utf-8 -*-
# create on 18/1/4
__author__ = 'yipu.si'
import sys
import json

import logging
from logging import info, error, warn

logging.basicConfig(level=logging.INFO, format='%(asctime)s - PID:%(process)d - %(levelname)s: %(message)s')

reload(sys)
sys.setdefaultencoding('utf-8')


class Trie:
    root = {}
    END = '/'
    info("define Trie")
    def add(self, word):
        node = self.root
        for c in word:
            node = node.setdefault(c, {})
        node[self.END] = None

    def add_word_list(self, words):
        info("add words")
        for word in words:
            self.add(word)
        info("added successfully")

    def find(self, word):
        node = self.root
        for c in word:
            if c not in node:
                return False
            node = node[c]
        return self.END in node

    def VPrint(self):
        print json.dumps(self.root, encoding='utf-8', ensure_ascii=False, indent=1)


if __name__ == '__main__':
    word = u"""一举,一举一动,一举成名,一举成名天下知,万能,万能胶"""
    li = word.split(",")
    trie = Trie()
    trie.add_word_list(li)
    trie.VPrint()
    print trie.find(u"一举一动")
    print trie.find("sinsaSi")



```




