# NODEJS

动态页面：访问的时候创建

静态页面：物理存在的网页文件

拓展JS在服务端的能力

### PHP vs Node.js

PHP类似脚本，在HTML中插入，是混合的模式。随时用，比较方便。但是不利于维护

JS 关注点分离的思想，类似于MVC构建弱耦合的系统

### Why Node.js

非阻塞IO

V8引擎

单线程实现多并发场景。回调机制

模块

多操作系统支持

支持同构的架构。不再区分前后端

### What is Node.js

不是语言，不是web框架

内核C++

最小开销处理上千的并发连接

### The Idea behind Node.js

对操作系统来说，创建进程是很昂贵的操作

进程数也是有限的

多进程逐渐转换为多线程，但是依然是有限的

最后考虑，IO复用，一个线程监控多个

Node.js单线程的方式，借助事件队列，实现高并发。异步，通过回调异步处理。单线程解决高并发IO。

以广度代替深度

IO密集型，而不是计算密集型，不适合太多CPU计算的任务

### 优势

#### 性能优势

现在语言的选择不再是页面的性能最大瓶颈

#### 实现成本

#### 调优成本

#### 学习成本

#### 模块数量多
