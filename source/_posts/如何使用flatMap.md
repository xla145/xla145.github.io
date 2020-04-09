---
title: 如何使用flatMap
date: 2019-03-15 09:52:57
tags:
- JAVA 8
---

### 使用场景

将多个集合的数据合并成一个集合数据

### 如何工作

通过下面的图，我们就很容易理解`flatmap`在`java8` 中是如何工作的

![](https://img.mupaie.com/20190304131022877.png)

使用红色标记的列表和绿色标记的列表，经过flatmap方法后在第二个管道中把把上述两个列表的数据合并成一个列表数据

###  例子

```java
List<List<Integer>> lists = new ArrayList<>();
List<Integer> list = new ArrayList<>();
list.add(4444);
list.add(33333);
list.add(444444);
lists.add(list);
lists.stream().flatMap(Collection::stream).forEach(System.out::println);
```
由于上述 lists.stream() 后返回的是stream<list<Integer>> 所以需要使用 `flatMap` 进行合并
### 总结

本文主要讲什么情况下使用 `flatmap`，然后解释一下 `flatmap`工作原理

参考文档
[How to use flatMap() in Java 8](http://www.java67.com/2016/03/how-to-use-flatmap-in-java-8-stream.html)
[Java 8 flatMap示例](https://www.mkyong.com/java8/java-8-flatmap-example/)

