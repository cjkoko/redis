# Linux版安装
#####  1. 下载获得redis-3.0.4.tar.gz后将它放在我们的linux目录/opt 
#####  2. /opt目录下。解压命令：tar -zxvf redis-3.0.4.tar.gz
#####  3. 解压完成后出现文件夹：redis-3.0.4,  进入目录：cd redis-3.0.4
#####  4. 在redis-3.0.4目录下执行mark命令
运行make命令时出现的错误解析：

1.安装gcc

    gcc是linux下的一个编译程序，是C程序的编译工具。

    GCC(GNU Compiler Collection) 是 GNU(GNU's Not Unix) 计划提供的编译器家族，

    它能够支持 C, C++, Objective-C, Fortran, Java 和 Ada 等等程序设计语言前端，

    同时能够运行在 x86, x86-64, IA-64, PowerPC, SPARC 和 Alpha 等等几乎目前所有的硬件平台上。

    鉴于这些特征，以及 GCC 编译代码的高效性，使得 GCC 成为绝大多数自由软件开发编译的首选工具。

    虽然对于程序员们来说，编译器只是一个工具，除了开发和维护人员，很少有人关注编译器的发展，

    但是 GCC 的影响力是如此之大，它的性能提升甚至有望改善所有的自由软件的运行效率，

    同时它的内部结构的变化也体现出现代编译器发展的新特征。

   <img src="https://i.loli.net/2020/01/09/bAfZ9WvXkDLc2rM.png" >

    a. 能上网：yum install gcc-c++

    b.不能上网：

2.二次make

3.Jemalloc/jemalloc.h:没有那个文件或目录

    运行make distclean之后再make

   <img src="https://i.loli.net/2020/01/09/zsAIbGT8U1Puyfc.png" >


4.Redis Test(可以不用执行)

   <img src="https://i.loli.net/2020/01/09/Ah2XBED1vKMQt7H.png" >

###### 下载TCL的网址：http://www.linuxfromscratch.org/blfs/view/cvs/general/tcl.html

###### 安装TCL：
  <img src="https://i.loli.net/2020/01/09/VYHuMOydK2Fogwm.png" >


#####  5. 如果make完成后继续执行make install

<img src="https://i.loli.net/2020/01/09/jfDSrWU1TGZ5dCV.png" >

#####  6. 查看默认安装目录usr/local/bin

<img src="https://i.loli.net/2020/01/09/vQJDLVUHOcTP1Xm.png" >

1. redis-benchmark:性能测试工具，可以在自己电脑运行，看看自己的电脑性能如何
2. redis-check-aof：修复有问题的aof文件
3. redis-check-dump：修复有问题的dump，rdb文件
4. redis-cli：客户端，操作入口
5. redis_sentinel:redis集群使用
6. redis_server:redis服务器启动命令

##### 7. 启动
1. 修改redis.conf文件将里面的daemonsize no改成yes，让服务在后台启动

2. 将默认的redis.conf拷贝到自己定义好的路径下做好备份
3. 启动

   <img src="https://i.loli.net/2020/01/09/Hpyug43mNRLFK76.png" >

4. 连通测试

   <img src="https://i.loli.net/2020/01/09/ogUil1ETk3PwcRO.png" >

5. /usr/local/bin目录下运行redis-server，运行拷贝出存放了自动义conf文件目录下的redis.conf文件

6. 永远的helloworld

    <img src="https://i.loli.net/2020/01/09/HSuExRJ7zrnFbqT.png" >

##### 8. 关闭
    
<img src="https://i.loli.net/2020/01/09/jKb4H2mfEqcshDk.png" >

1. 单实例关闭：redis-cli shutdown

2. 多实例关闭：指定端口关闭：redis-cli -p 6379 shutdown