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
  
  * 速度控制函数
  <br>依照ledcWrite()函数相关功能进行编写
  
  * 代码样例
  ```
  void Motor_Speed(int motorID, int speed) 
  {  // 电机速度设置 // ID=1~4,speed=-255~255
  if (speed == 0) {
    ledcWrite(motorID * 2 - 2, 0);
    ledcWrite(motorID * 2 - 1, 0);
  } else if (speed > 0) {
    ledcWrite(motorID * 2 - 2, speed);
    ledcWrite(motorID * 2 - 1, 0);
  } else {
    ledcWrite(motorID * 2 - 2, 0);
    ledcWrite(motorID * 2 - 1, -speed);
  }
  }
  //其中motorID * 2 - 2对应的是PWM通道，设置为从0开始
  ```

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

## 预期实现成果展示
<video width="600" height="600" controls>
  <source src="../resource/img/up_motorcontrol.mp4" type="video/mp4">
</video>