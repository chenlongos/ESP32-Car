# 0.2 开发环境准备

## 0.2.1 运行环境

基础运行环境可以参考如下网址 使用VSCode+PlatformIO插件搭建开发环境：
https://blog.csdn.net/msdcp/article/details/127033151
https://blog.csdn.net/jiladahe1997/article/details/108270620
## 0.2.2 相关库的下载与介绍


- 一、ESPAsyncWebServer
  * ESPAsyncWebServer是PlatformIO环境下ESP32开发中极为重要的异步Web服务器库，它为物联网设备提供了高性能的网络通信能力。
  * 1.异步网络架构:
  <br>非阻塞式处理​​：采用事件驱动模型，服务器在处理请求时不会阻塞其他连接，能够同时处理多个客户端请求，显著提高吞吐量;
  <br>高效资源利用​​：在等待I/O操作(如文件读取、传感器数据采集)时，可以继续处理其他任务，减少CPU闲置时间;
  <br>实时响应机制​​：基于回调函数的事件处理方式，确保对客户端请求的快速响应，特别适合实时数据推送场景.
  * 2.协议支持能力:
  <br>支持GET、POST、PUT、DELETE、PATCH、HEAD和OPTIONS等HTTP方法
- 二、LedController
  * LEDController库是ESP32平台上用于控制LED和生成PWM信号的重要工具库，本项目中主要使用的是LEDController库中与PWM相关的核心函数（详见后续语法介绍）。
- 三、ESP32Servo
  * ESP32Servo库是专为ESP32系列微控制器设计的舵机控制库，它提供了简单易用的接口来控制标准舵机。具体包括基础控制功能，对多个舵机独立管理控制；运动控制功能，控制舵机角度、平滑运动等；状态查询功能，获取当前位置以及PWM通道查询等。
