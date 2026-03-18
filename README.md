项目名称
基于C++11新特性重写muduo网络核心TcpServer

项目地址
https://github.com/wvr100/muduo-core-main.git

项目描述
模拟muduo网络库，使用C++11新特性实现非阻塞IO复用的高并发TCP服务器模型核心（TcpServer），包括以下模块：

Acceptor

EventThreadPool

Channel

Poller

EventLoop

Buffer

TcpConnection

Logger

实现要点
采用 non-blocking + IO-multiplexing + loop 的线程设计框架

线程模型为 one loop per thread 的多线程服务端网络编程模型

结合 Reactor模型 进行实现

完全使用 C++11 标准：

使用智能指针（unique_ptr、shared_ptr、weak_ptr）管理内存资源

使用原子操作（atomic）保护状态量

使用 unique_lock 替代 lock_guard

采用 eventfd 作为事件通知描述符，方便高效派发异步任务到其他线程执行
