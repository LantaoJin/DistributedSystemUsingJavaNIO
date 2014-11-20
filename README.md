手把手教你使用JavaNIO构建Actor模式的高性能分布式系统
=============================

>要写好一个分布式系统往往是一件比较复杂的事情，特别是使用`Java`、`C++`这类不具有并发原语的非函数式编程语言，不仅需要考虑各个线程之间的同步和并发，还要考虑进程以及节点之间的通信和协作。单就通信框架这一层（如RPC调用）就有许多坑等着猿猿们来跳，如果再考虑系统在高并发情况下的响应时间和性能等，又会使系统设计变得复杂。好在我们无需从零开始，业界存在着许多开源的优秀的`分布式系统组件`（如RPC框架、序列化框架等等），这类组件封装了网络通信协议、序列化等底层处理，但要写出一个高性能的分布式系统仍然不容易。本教程将`手把手`的教你如何使用`JavaNIO`来写一个高性能的分布式系统，我们的系统使用`Actor`这种模式，使得其具有很好的扩展性，也便于理解。  

##一、预备知识
####JavaNIO  
JavaNIO网上已有许多不错的文章和教程供开发者学习，如[Java NIO Tutorial](http://tutorials.jenkov.com/java-nio/index.html)，[Getting started with new I/O](http://www.ibm.com/developerworks/java/tutorials/j-nio/j-nio.html)等等，详细内容本文不再累述，这里只简要总结一下。  
普通IO，也叫BIO、Blocking IO，数据在客户和服务器之间交换是阻塞式的，数据通过TCP协议从一端发送到另一端，无论是发送的一端还是接受的一端，在没有数据准备好的时候是处于一种等待状态的，该状态会block住该线程直到有数据后继续传输。  
NIO，也叫New IO、Non-Blocking IO，顾名思义是非阻塞式的，它不再将实际收发数据的客户端和服务端线程一对一绑定在一起，而是增加了一个事件管理线程，通过该事件管理线程来监听网络上数据是否已经准备好，然后告知相应的客户端或服务端的收发线程，可以来读写数据了。更进一步的，该事件管理线程及为我们常说的`reactor`。  
NIO的写法相对固定，服务端和客户端代码看起来类似，我们很容易写出一个简单的CS模型，具体写法会在后面章节详细介绍。要弄懂NIO首先要先理解Selector，Channel，SelectedKey和Buffer之间的关系：  
* Selector和Channel的关系  

* SelectedKey和Channel的关系  

* Channel和Buffer的关系  

####Actor模式
##二、最简单的Server和Client
##三、读写分离的Server&Client
##四、纯粹的Actor处理机
##五、Connection封装
##六、不同场景下的优化
##七、NIO常见的坑

