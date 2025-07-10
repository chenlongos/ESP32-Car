# ESP32使能WiFi
## ESP32的WiFi板块函数的介绍
- 基础WiFi连接函数
  * 1.WiFi初始化与连接
  <br>(1)**WiFi.begin()​​ - 用于连接到指定的WiFi网络**
  <br>`WiFi.begin(ssid, password);  // 连接到指定SSID和密码的WiFi网络`
  <br>(2)**WiFi.status()​​ - 返回当前WiFi连接状态**
  <br>`wl_status_t status = WiFi.status();`
  <br>常见返回值：
  <br>WL_CONNECTED: 已连接(值为3)
  <br>WL_NO_SSID_AVAIL: 未找到指定网络(值为1)
  <br>WL_CONNECT_FAILED: 连接失败(值为4)
  <br>WL_IDLE_STATUS: WiFi处于空闲状态(值为0)
  <br>WL_DISCONNECTED: 未连接(值为6)
  * 2.网络信息获取
  <br>**WiFi.localIP()​​ - 获取ESP32在局域网中的IP地址**
  <br>`IPAddress ip = WiFi.localIP();`
  <br>`Serial.println(ip);  // 打印IP地址如"192.168.1.100"`
## WiFi板块基本代码架构
- 一、初始化
  * 配置模块的工作模式
  <br>`WiFi.mode(WIFI_STA);`
- 二、准备步骤
  * 指定需要连接的WiFi
  <br>`WiFi.begin(ssid, password);`
- 三、连接WiFi+打印ip地址
  ```
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  Serial.println("\nIP地址: " + WiFi.localIP().toString());


