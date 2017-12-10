[TOC]

# 修订历史

* 2017-07-25初稿

# 概述

技术面试需要准备的内容，分为以下部分
- 算法基础
- 系统理论
- 应用实践

算法基础，包括常用的算法，数据结构，要求能够讲清楚常见算法流程，应用场景，复杂度分析，具备手写能力。数据结构要求掌握常见数据结构的内部结构分析，应用场景，变种分析。对于主力语言要求具备内置数据结构的深入理解。

系统理论主要指计算机领域的理论掌握水平，考察解决问题的深度与广度。主要包括编译原理，操作系统，网络协议，数据库原理和分布式理论等，需要具备常见理论概念的理解能力，应用场景识别能力，尽可能的深入理论细节。

应用实践包括熟悉主力语言，开源/商业项目实际经验，问题解决经验，场景分析，主要考察解决实际问题的经验和能力，是否具备缜密，全面的系统性分析能力，是否有对未知领域的探讨分析思路。

总体来说，前面2个方面虽然都是理论知识，但侧重点不一样，一个关注编码能力，一个关注平台知识。而第3方面是综合应用的能力。

# 算法基础篇

## 通用数据结构

数据结构，关键是理解结构的关系，它包括逻辑结构和存储结构两个方面。 

### 数据的逻辑结构

指对数据及其关系的抽象逻辑描述，与机器实现无关。根据定义的关系不同，数据的逻辑结构分为四种： 
- 集合结构。数据元素之间未定义任何关系的松散集合。
- 线性结构。数据元素之间定义了次序关系的集合（全序集合），描述的是1对1关系。 
- 树形结构。数据元素之间定义了层次关系的集合（偏序集合），描述的是1对多关系。
- 图状结构。数据元素之间定义了网状关系的集合，描述的是多对多关系。  

### 数据的存储结构

指数据结构在计算机存储器中的具体实现。存储结构与孤立的数据元素表示形式不同，数据结构中的数据元素不但要表示其本身的实际内容，还要表示清楚数据元素之间的逻辑结构。 

常见的存储结构有： 

- 顺序存储结构：特点是借助于数据元素的相对存储位置来表示数据元素之间的逻辑结构；
- 链式存储结构：特点是借助于指示数据元素地址的指针表示数据元素之间的逻辑结构。
- 散列存储结构：顺序+算列。
- 索引存储结构：顺序+索引。

## 常见数据结构

### 数组与链表

特性 | 数组 | 链表
---|---|---
内存分配 | 固定长度、静态分配 | 动态分配
存储方式 | 顺序存储 | 随机存储
特点 | 存储效率高，定位方便 | 形式多样，便于扩展

链表常见的有多种形式，包括单向链表，双向链表，环形链表。常见操作有构造链表，插入，删除，查找等，这一块需要熟悉。

推荐学习: 
- http://coolshell.cn/articles/8990.html
- 如何判断链表出现循环？如何找到开始循环的位置？

### 栈与队列

特性 | 栈 | 队列
---|---|---
约束 | 先进后出FILO | 先进先出FIFO
基本操作 | 入栈，出栈 | 入队，出队
复杂度 | O(1) | O(1)
存储方式 | 常见是数组(约束容量)，有栈顶指针 | 常见有环形数组，有头尾指针

推荐学习
- 计算机编程中，方法调用中栈的作用？了解尾递归的特性？
- 数值运算表达式的计算中栈的作用？
- 生产者消费者中的队列缓冲？

### 优先级与堆

优先级队列不同于普通队列，它有一个排序规则，只有优先级最高的元素才能首先出队。这个排序要求决定了它的存储结构不同于普通队列，通常是采用堆这种数据结构实现的。另外，这里的堆不是内存分配中的堆。

根据排序顺序的不同，堆通常有最小堆，最大堆，但实质上是没有什么区别的。以下以最大堆为例。

堆在存储结构上是一个数组，但逻辑结构是一颗满二叉树，根节点保存最大的元素，每个节点都比它的子节点要大。常见操作有获取最大元素，添加一个新元素，这些操作的算法复杂度都是O(logN)。每次操作要需要额外工作来达到新的平衡。

推荐学习
- 优先级队列的实现
- 在一个大集合中找到最大的n个数
- 给出一个整型数组和一个滑动窗口，求滑动窗口从左到右，每次窗口中中位数组成的数组

### 树

树的基本概念有根节点，父节点，子节点，高度等，常见的树有二叉查找树，平衡二叉树，红黑树，B-树，B+树，字典树(trie),后缀树，广义后缀树
http://m.blog.csdn.net/article/details?id=7324935

掌握基本的递归操作方式，例如树的遍历，计算树的高度。掌握比较高级的结构，如b树(索引常见结构)，红黑树(各项操作比较平衡，TreeMap的实现)

### 散列表，集合

key value结构的数据结构，表示两个对象的关联关系。常见的存储结构有数组方式和链表方式，通常查找，插入，删除的效率可以达到O(1),但如果存在严重冲突的时候，最坏效率会达到O(N)。

集合是散列表的一种特例，它关注的是元素的唯一性和快速查找，插入和删除，可以用散列表的key来做到。

推荐学习
- http://coolshell.cn/articles/6424.html

## 通用基本算法

查找和排序是两种最基本的算法。

### 查找算法

顺序查找，两分查找

针对一个列表的查找，朴素算法就是顺序查找，如果原始数据是已经排序的，则可以考虑两分查找。

推荐学习

- 如何在两个已经排序的数组中找到中位数？
- 如何在一个已排序的数组中找到最接近的数？

### 排序算法

| 排序方法     | 平均情况       | 最好情况 | 最坏情况 | 辅助空间     | 稳定性 |
|--------------|----------------|----------|----------|--------------|--------|
| 冒泡排序     | O(n2)          | O(n)     | O(n2)    | O(1)         | 稳定   |
| 简单选择排序 | O(n2)          | O(n2)    | O(n2)    | O(1)         | 稳定   |
| 直接插入排序 | O(n2)          | O(n)     | O(n2)    | O(1)         | 稳定   |
| 希尔排序     | O(nlogn)~O(n2) | O(n1.3)  | O(n2)    | O(1)         | 不稳定 |
| 堆排序       | O(nlogn)       | O(nlogn) | O(nlogn) | O(1)         | 不稳定 |
| 归并排序     | O(nlogn)       | O(nlogn) | O(nlogn) | O(n)         | 稳定   |
| 快速排序     | O(nlogn)       | O(nlogn) | O(n2)    | O(logn)~O(n) | 不稳定 |
| 基数排序     | O(d*(n+r)) | O(d*(n+r))d是位数，r是基数 | O(d*(n+r)) | O(n+r) | 稳定 |

基本原则:少量数据应该考虑简单的冒泡，选择等算法，大量数据应该考虑快速等较复杂算法，海量数据要结合外排序进行选择。有特定格式的数据考虑用桶等O(n)算法。

## 算法设计思路

- 穷举 对可能的情况一一验证
- 分治 把一个大问题分解成较小规模的问题
- 贪心 优先考虑当前已知环境下的最优选择
- 动态规划 根据状态转移方程进行最优决策的方法
- 回朔法 穷举的基础上加上剪枝

## 算法训练

- leetcode算法
- 知名公司的面试题(参考九章算法，牛客网)

# 系统理论篇

## 编译原理

- 了解编译原理中词法分析，语法分析，语义分析，中间代码生成等基本概念
- 掌握简单的词法分析，语法分析的实现过程，例如正则表达式

## 操作系统

TODO
- 进程管理
- 内存管理
- 存储管理
- 输入输出
- 调度与并发

## 计算机网络

### osi7层，tcp/ip4层的概念

![OSI七层模型](http://hi.csdn.net/attachment/201201/5/0_1325744597WM32.gif)

### ip协议

TODO
掌握常见路由算法

### tcp，udp协议

TODO
主要掌握tcp协议，包括建立连接，关闭连接的过程，了解tcp状态机变化

### http协议,ftp协议

TODO
http协议掌握细节

ftp协议需要掌握主动，被动模式的工作原理，交互流程及适用场景。是否主动看是否由服务端去连接客户端的。
- 主动模式，客户端通知服务端数据传输端口，服务端通过20端口连接客户端，适用于需要穿透防火墙，无法连接内网客户端的情况。
- 被动模式，服务端开启高段端口，通知客户端来连接，适用于客户端位于内网，无法穿透防火墙高端端口的情况。

## 数据库

* 掌握表、索引、视图、存储过程、触发器等常见概念，掌握常用SQL语法，如DDL、DML、DCL常见语句的写法，掌握数据库设计基本范式。
* 深入理解索引原理，掌握常见的B+树索引结构。掌握io,cpu和network的调优等基础及相互关系，掌握逻辑读，物理读，多块读，随机读和顺序读等io相关概念。深入理解SQL操作中数据的访问路径（全表扫描，索引唯一扫描，索引范围扫描，索引全扫描，索引快速全扫描，索引跳跃扫描），连接方式(嵌套循环连接、排序合并连接、哈希连接)和连接顺序等关键特性和适用场景，掌握索引设计的一般原则，能够分析SQL执行计划并制定优化方案。
- 掌握数据库结构体系
- SQL语句分析优化
- 事务管理

## 架构设计

- 理解集群，负载均衡，分布式等基本概念
- ACID(原子性，一致性，隔离性，持久性),CAP(一致性，可用性，分区容忍性),BASE(基本可用，软状态，最终一致性)理论

TODO
### pasox,zab一致性算法
TODO
### 布隆过滤器
TODO
### 主从架构
TODO
### mapreduce,bigtable,gfs
TODO
### 分布式会话存储
TODO
### 微服务架构
TODO
### 安全设计
TODO

### 一致性Hash

针对一组数据映射到一组服务器的场景，在调整服务器数量的时候，最大化单调性(尽量多的数据映射的服务器不变)和平衡性(数据平均到各服务器)的问题。

普通取模算法平衡性好，但主要缺点在于单调性不好，服务器变动的时候，数据映射几乎都变了。

- 一致性Hash算法采用环形结构，环上某段范围属于某个服务器，根据数据落在环上的点来确定服务器归属。服务器变动只会影响一部分数据，有利于单调性。
- 通过引入虚拟节点，使得少量服务器分散到环上的各个区域，有利于平衡性。

推荐学习
- https://my.oschina.net/hosee/blog/663070

### 分布式锁定

- 基于数据库行锁、表锁、乐观锁等机制
- 基于缓存的原子操作，例如redis的setnx命令
- 基于zookeeper的分布式锁

推荐学习
- https://my.oschina.net/hosee/blog/686161
 
### 分布式缓存

缓存设计考虑
- 理解缓存的应用场景-读多写少,重要指标是缓存命中率(缓存命中请求数/缓存请求数)，指标越高越好，通常要求大于95%
- 缓存穿透，策略就是没有也写入缓存，过期时间较短。另外就是采用布隆过滤器。
- 缓存失效雪崩，大量同时失效，策略就是分析用户行为，让失效比较分布。还有就是继续使用旧数据，但是异步更新数据，并通过队列等结构限制并发更新数量，这是针对采用旧数据也影响不大的情况。

缓存应用设计
- 考虑序列化的方式，涉及对象大小和性能
- 缓存对象大小要控制好，避免缓存单一超大对象
- 统一缓存对象key的写可能存在更新丢失或脏数据
- 缓存数据可能会因为空间问题被淘汰，要时刻检测是否为空。容量规划。
- 缓存哪些对象，缓存到哪里要规划，避免重复存储，大对象存储。隔离影响。
- 建议使用本地静态变量代替缓存对配置数据进行存储。本地要有一套缓存

缓存更新策略主要有四种：
- Cache aside 先保存再过期(应用方负责)
- Read through读操作时更新(缓存负责)
- Write through写操作时更新(缓存负责)
- Write behind caching只更新缓存

推荐学习
- http://coolshell.cn/articles/17416.html

# 应用实践篇

## 基本工具

- 版本管理工具svn、git
- 构建工具ant、maven、gradle

## 敏捷实践工具

实践 | 要点 | 工具
---|---|---
站立晨会|昨天进度，今天计划，困难和分享，约束时间|
showcase|召集需求干系人，状态的每次变更|
结对编程|相互交换角色|
代码评审|关注架构守护，不适宜揪代码规范细节|
持续集成|红灯停，绿灯行，黄灯等一等|cruisecontrol,jenkins
自动化测试|尽量自动化|selenium
回顾会议|关注做得不好的和改进意见|
静态检查|尽早使用,集成到CI|Findbugs、XLint

## 通用框架类

TODO
### spring 涉及ioc,aop

![Spring](http://docs.spring.io/spring/docs/current/spring-framework-reference/htmlsingle/images/spring-overview.png.pagespeed.ce.XVe1noRCMt.png)
### struts等mvc框架
### ibatis,hibernate等orm框架
### quartz定时调度
### log4j等日志框架
 
slf4j适配
![slf4j日志门面](https://www.slf4j.org/images/concrete-bindings.png)

log4j适配
![log4j2](http://img.blog.csdn.net/20150325191622288)

掌握日志api的常见用法，规范化日志输出，日志收集与分析。推荐学习[日志最佳实践](https://zhuanlan.zhihu.com/p/273634849)

### netty网络框架

![架构图](http://netty.io/images/components.png)

推荐学习
- [Java NIO通信框架在电信领域的实践](http://www.infoq.com/cn/articles/practice-of-java-nio-communication-framework)
- [Netty系列之Netty高性能之道](http://www.infoq.com/cn/articles/netty-high-performance)
- [Netty系列之Netty 服务端创建](http://www.infoq.com/cn/articles/netty-server-create)
- [Netty版本升级血泪史之线程篇](http://www.infoq.com/cn/articles/netty-version-upgrade-history-thread-part)
- [Netty案例集锦之多线程篇（续）](http://www.infoq.com/cn/articles/the-multithreading-of-netty-cases-part02)
- [Netty系列之Netty并发编程分析](http://www.infoq.com/cn/articles/netty-concurrent-programming-analysis)
- [Netty系列之Netty编解码框架分析](http://www.infoq.com/cn/articles/netty-codec-framework-analyse)
- [Netty系列之Netty百万级推送服务设计要点](http://www.infoq.com/cn/articles/netty-million-level-push-service-design-points)
- [Netty优雅退出机制和原理](http://www.infoq.com/cn/articles/netty-elegant-exit-mechanism-and-principles)

## java语言基础
- 面向对象特征,包括封装，继承，多态
- 原生类型与包装类型，原生类型是其他结构的基础，识别两者在内存上的区别，开封箱特性，了解包装类型的实现，如特定整型对象的缓存。
- 匿名类、内部类、静态内部类，了解他们之间的区别，还有编译后的实际结构(如何转换为普通类)。
- 可变长参数与数组参数，了解可变长参数在编译层面的实现，了解存在重载情况下可能的混淆问题。
- 内部变量初始化、构造方法、静态变量初始化、静态块、及存在继承关系时的执行顺序，原则:父类优先，静态常量优于静态块
- equals,hashcode用途，实现原则，hashcoe要实现简单，和equals保持一致，equals要确保自反性，对称性，传递性，一致性。了解hashcode和equals的应用场景。
- 对象的强、软、弱和虚引用,了解各种引用的区别及应用场景 http://www.importnew.com/20468.html
- 常见集合类的特性，应该能够在实际作用中灵活使用，掌握区别及实现原理，列表(ArrayList Vector LinkedList Queue Stack Deque PriorityQueue),散列(HashMap LinkedHashMap TreeMap IdentityHashMap EnumMap WeakHashMap HashTable SortedMap),集合(HashSet TreeSet EnumSet) 需要整理一个特性比较的表格 待整理
- 多线程基础 java线程模型，线程生命周期，sleep,wait,notify,notifyall,join等线程通信机制。理解同步，原子性，可见性，CAS无锁机制等概念，了解常见锁类型。
- 并发工具类，掌握常见并发工具类的特性，使用场景，使用方法。了解相关的实现原理。主要包括Executor,Atomic类，ConcurrentHashMap,CopyOnWriteArrayList,BlockingQueue,Latch,Barrier,Condition,Lock等等
- 擦除型泛型，上限，下限，掌握泛型的作用，如何保持旧代码兼容
- String、StringBuffer和StringBuilder类的应用场景，区别
- 正则表达式,掌握常见正则表达式写法，了解正则表达式实现
- Checked异常和Runtime异常体系,异常的性能，实践中异常的设计与统一处理，包括安全性设计
- 字符，字节，io流，掌握java流设计体系，字符编码相关知识点，编码转换特性
- 序列化，序列化应用场景，性能，安全性方面
- java8最新特性 http://m.open-open.com/m/lib/view/1403232177575.html#methodReferences

## jvm基础

TODO
- 对象内存占用大小
- 内存分布结构
- 垃圾回收算法
- 常见调优参数，策略
- vm辅助工具使用

推荐学习
- [从 Java 代码到 Java 堆](https://www.ibm.com/developerworks/cn/java/j-codetoheap/index.html) 
- [Java的内存泄漏](https://www.ibm.com/developerworks/cn/java/l-JavaMemoryLeak/)
- [JVM 垃圾回收器工作原理及使用实例介绍](https://www.ibm.com/developerworks/cn/java/j-lo-JVMGarbageCollection/index.html)
- [Java的内存泄漏](https://www.ibm.com/developerworks/cn/java/l-JavaMemoryLeak/)
- [JVM 优化经验总结](https://www.ibm.com/developerworks/cn/java/j-lo-jvm-optimize-experience/index.html)
- [Java 应用性能调优实践](https://www.ibm.com/developerworks/cn/java/j-lo-performance-tuning-practice/index.html)
- [常用 Java Profiling 工具的分析与比较](https://www.ibm.com/developerworks/cn/java/j-lo-profiling/index.html)

## 系统维护

TODO 
linux系统操作

熟悉常见命令的使用

- 基本操作(用户，文件管理，权限控制)
- 运行状态(磁盘空间，cpu，内存，网络，进程，io)
- 编译运行(环境参数，编译运行，调试定位)
- 工具使用( find awk sed)
