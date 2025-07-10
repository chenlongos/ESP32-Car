# ESP32驱动轮子
## 硬件的连接
- 引脚连接参考
  * 电机1 PWM: GPIO27
  <br>电机1 DIR: GPIO13
  <br>电机2 PWM: GPIO4
  <br>电机2 DIR: GPIO2
  <br>电机3 PWM: GPIO17
  <br>电机3 DIR: GPIO12
  <br>电机4 PWM: GPIO15
  <br>电机4 DIR: GPIO14
## 相关函数的编写
- 电机控制函数
## 串口调试与烧录
- 一、调试方法
  * PlatformIO提供了方便的串口监视器：
  <br>点击底部状态栏"插头"图标
  <br>或命令面板输入"PlatformIO: Serial Monitor"
  <br>快捷键Ctrl+T Ctrl+X退出监视器
  * 可以在代码中添加Serial.println()函数增加调试信息
- 二、常见问题解决
  * 1.**上传失败**:
  <br>检查USB连接
  * 2.**库冲突**:
  <br>去除非必要的库，避免引起冲突
  * 3.**电机响应异常**：
  <br>检查电源是否充足
  <br>检查PWM频率和分辨率