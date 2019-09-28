## 1、Bio、Nio、Aio
- bio 同步阻塞
- nio 同步非阻塞
- aio 异步
## 2、Linux网络编程5中i/o模型(了解)
- 阻塞IO
- 非阻塞IO
- IO复用
- 信息驱动
- 异步IO
## 3、Netty概念
- 异步事件驱动框架
- 自带编解码器解决了拆包和粘包问题
- 精心设计的Reactor线程模型支持高并发海量连接
## 4、同步、异步和阻塞、非阻塞
- **同步阻塞：** <br/>      A调用B，A要一直等待B结果返回才能继续后续操作，这就是同步阻塞
- **同步非阻塞：**  <br/> A调用B，A不等待B返回结果，继续后续操作。然后A间歇询问B结果，这就是同步非阻塞
- **异步：**  <br/>A调用B，A不等待B返回结果，继续后续操作。等待B完成后，主动将结果告诉A，这就是异步

注：只有同步才有阻塞和非阻塞；异步没有

## 5、Netty核心组件
- **channel：** <br/>      全双工(读写)，常见的有FileChannel、SocketChannel、ServerSocketChannel
- **Buffer：**  <br/> 
mark、position、limit、capacity
- **Selector：**  <br/>将channel注册到Selector上
- **unsafe：**  <br/>操作底层，如硬件
## 6、Reactor模型
- **Acceptor：** <br/>
接受客户端连接，简历对应的Handler，并向Reactor注册次Handler
- **Handler：** <br/>
和客户端通讯的实体
- **Reactor：** <br/>
IO时间派发者
## 7、Netty中两个EventLoopGroup作用
- **BossGroup：** <br/>
用于服务端接受客户端的连接
- **WorkerGroup：** <br/>
用于进行socketChannel的网络读写
## 8、粘包拆包
由于tcp底层并不了解上层业务数据的含义，所以一个完整的包可能被tcp拆分成多个包进行发送，也可能把多个小的包封装成一个大的数据包发送，这就是拆包和粘包

