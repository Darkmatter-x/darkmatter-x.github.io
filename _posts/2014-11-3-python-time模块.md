---
title: Python Time 模块
layout: post
category : python
tagline: "不积跬步，无以至千里；不积小流，无以成江海。"
tags : [python]
---
- time.time **获取当前时间的[时间戳](http://zh.wikipedia.org/zh-cn/%E6%99%82%E9%96%93%E6%88%B3)**  
```python
    time.time()  #1415022953.471965
```  
- time.strftime() **格式化输出**  
```python
 	time.strftime('%Y-%m-%d %H:%M:%S')  #'2014-11-03 21:57:06'	
```
- time.clock() **返回程序运行时间**  
```python
	time.clock() #0.193492
```
- time.localtime() **将时间戳转换成UTC时区(当前时区)struct_time**  
```python
	time.localtime()
    
    #time.struct_time(tm_year=2014, tm_mon=11, tm_mday=3, tm_hour=22, tm_min=25, tm_sec=18, tm_wday=0, tm_yday=307, tm_isdst=0)
```
- time.gmtime() **将时间戳转换成UTC时区（0时区) struct_time**
```python
	time.gmtime(1415022953.471965)
    
	##time.struct_time(tm_year=2014, tm_mon=11, tm_mday=3, tm_hour=13, tm_min=55, tm_sec=53, tm_wday=0, tm_yday=307, tm_isdst=0)
```
- time.mktime() **将struct_time 转换成时间戳**
```python
	time.mktime(time.gmtime()) #1414995746.0
```
- time.strptime() **将时间字符串转换成struct_time**
```python
	time.strptime('3/Nov/2014:22:33:29', '%d/%b/%Y:%X')
    
    #time.struct_time(tm_year=2014, tm_mon=11, tm_mday=3, tm_hour=22, tm_min=33, tm_sec=29, tm_wday=0, tm_yday=307, tm_isdst=-1)
```