# ESP32使用PWM
## 使用PWM控制舵机的语法基本框架
- 一、初始化与绑定通道
  * 主要使用函数
  <br>`ledcSetup(PWM_CHANNEL, PWM_FREQ, PWM_RESOLUTION);`
  <br>`ledcAttachPin(SERVO_PIN, PWM_CHANNEL);`
- 二、编写控制舵机角度函数
  * 利用角度、脉宽、分辨率之间的关系编写
  * 使用`ledcWrite(PWM_CHANNEL, duty);`
  <br>进行输出
- 三、对多个电机进行控制，实现对抓手运动状态控制
  * 利用switch结构改写上述角度函数
  * 根据舵机实际情况，编写能实现抓手初始状态、抓物状态、缩回状态、释放状态等的各种函数