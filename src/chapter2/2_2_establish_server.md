# ESP32搭建网络服务
## 网页搭建简单介绍
- ESP32可以搭建简单的Web服务器，通过浏览器访问ESP32的IP地址即可获取响应
## 网页搭建基本代码架构
- HTML页面嵌入方式
  <br>直接字符串嵌入​​：适合简单页面
  <br>`const char index_html[]PROGMEM=R"rawliteral(<html><body><h1>ESP32 Control Panel</h1><button onclick="fetch('/led?state=1')">Turn ON</button></body></html>)rawliteral";`