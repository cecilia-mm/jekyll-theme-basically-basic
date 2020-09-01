---
layout: page
title: 还在为不会yml语言烦恼吗？点击这里，教你轻松学习yml！
excerpt_separator: "<!--more-->"
categories:
     - 学习笔记
---

<!--more-->

# YAML学习笔记

# 一、简介
##### 1.YAML是一个类似XML、JSON的标记性语言。YAML强调以数据为中心，并不是以标识语言为重点。因而YAML本身的定义比较简单，号称“一种人性化的数据格式语言”。
##### 2.与XML、JSON的比较：比json、xml等更适合做配置文件
***
# 二、设计目标
1. 容易阅读
2. 可用于不同程序间的数据交换
3. 适合描述程序所使用的数据结构，特别是脚本语言
4. 丰富的表达能力与可拓展性
5. 易于使用
---

# 三、基本语法：
1. 规则：
   - 大小写敏感
   - 使用缩进表示层级关系
   - 缩进是不允许使用Tab键，只允许使用空格
   - 所进的空格数目不重要，只要相同层级的元素左侧对齐即可

2. 支持的数据结构
   - 对象：键值对的集合，又称为映射（mapping）/哈希（hashes） / 字典（dictionary）
   - 数组：一组按次序排列的值，又称为序列（sequence）/列（list）
   - 字面量（数字、字符串、布尔值）：单个的、不可再分的值
3. 具体写法
- 字面量（数字、字符串、布尔值）
   - k: v :字面量直接写，字符串默认不用加上单引号或者双引号
   - 双引号：会转义特殊字符
   - 单引号：不会转义字符串里边的特殊字符；特殊字符会作为本身想表示的意思
   - 示例：
   ```
   name: zhangsan
   age: 20
   isBoss: false
   ```
- 数组
   - 多行写法使用- 值来表示数组中的一个元素，需要注意缩进；单使用[值，值] 来表示一个数组
   - 示例：
   ```
   #多行结构
   friends：
   - zhangsan
   - lisi
   - wangwu

   #单行结构
   friend:[zhangsan,lisi,wangwu]
   ```
- 对象
   - 多行写法：key：value的形式，使用多行写法需要注意缩进
   - 单行写法：使用{key:value}的形式书写
   - 示例：
   ```
   #多行结构
   friend:
   name:zhangsan
   age:20

   #单行结构
   friend:{name:zhangsan,age:20}
   ```
- .properties文件和.yml文件之间的不同

   - .properties文件中的写法(示例)：
   ```
   person.last-name=\u674E\u56DB
   person.age=12
   person.birth=2017/12/15
   person.boss=false
   person.maps.k1=v1
   person.maps.k2=14
   person.lists=a,b,c
   person.dog.name=dog
   person.dog.age=1
   ```
   - .yml文件中的写法(示例)：
   ```
   person：
  last-name: zhangsan
  age: 20
  birth: 2017/12/15
  boss: false
  maps:{key1:value1,key2:value2} 
  lists:[a,b,c]
  dog:
   name: dog
   age: 1
   ```

---

# 四、YAML 组织结构
##### YAML 文件可以由一或多个文档组成（也即相对独立的组织结构组成），文档间使用“---”（三个横线）在每文档开始作为分隔符。同时，文档也可以使用“...”（三个点号）作为结束符（可选）。

（注意：如果只是单个文档，分隔符“---”可省略。）


