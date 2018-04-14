---
layout: post
title:  pandas dataframe 中的 explode 函数
date:   2018-04-13 01:08:00 +0800
categories: python 
tag: pandas;dataframe;explode
---
* content
{:toc}



> 在使用 pandas 进行数据分析的过程中，我们常常会遇到将一行数据展开成多行的需求，多么希望能有一个类似于 hive sql 中的 explode 函数。这个函数如下：
> 

## Code 

```
# !/usr/bin/env python
# -*- coding:utf-8 -*-
# create on 18/4/13
import pandas as pd


def dataframe_explode(dataframe, fieldname): 
    temp_fieldname = fieldname + '_made_tuple_' 
    dataframe[temp_fieldname] = dataframe[fieldname].apply(tuple)       
    list_of_dataframes = []
    for values in dataframe[temp_fieldname].unique().tolist(): 
        list_of_dataframes.append(pd.DataFrame({
            temp_fieldname: [values] * len(values), 
            fieldname: list(values), 
        }))
    dataframe = dataframe[list(set(dataframe.columns) - set([fieldname]))].merge(pd.concat(list_of_dataframes), how='left', on=temp_fieldname) 
    del dataframe[temp_fieldname]
    return dataframe


df = pd.DataFrame({'listcol':[[1,2,3],[4,5,6]], "aa": [222,333]})
df = dataframe_explode(df, "listcol")
``` 

## Description
将 dataframe 按照某一指定列进行展开，使得原来的每一行展开成一行或多行。( 注：该列可迭代， 例如list, tuple, set) 