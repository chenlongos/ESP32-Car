# ESP32使用I/O接口
## 数字I/O的不同工作模式介绍
![ESP32管脚图](https://i-blog.csdnimg.cn/blog_migrate/b5e5d7d537c60a57956b11f2739ec9c2.png)
- 一、基本输入输出模式
  * 1.数字输入模式(INPUT)
  <br>用于读取外部数字信号状态(高/低电平)
  * 2.数字输出模式(OUTPUT)
  <br>控制引脚输出高/低电平
- 二、带内部电阻的输入模式
  * 1.**上拉输入模式(INPUT_PULLUP)**
  <br>**(1)功能**：
  <br>启用内部上拉电阻(约45kΩ)的输入模式
  <br>**(2)特点**：
  <br>引脚悬空时默认读取为高电平
  <br>适合连接接地式开关/按键
  <br>可节省外部上拉电阻
  * 2.**下拉输入模式(INPUT_PULLDOWN)**
  <br>**(1)功能**​​：
  <br>启用内部下拉电阻(约45kΩ)的输入模式
  <br>**(2)特点**​​：
  <br>引脚悬空时默认读取为低电平
  <br>适合连接接电源式开关/按键
  <br>可节省外部下拉电阻
## Arduino框架
- 一、必要头函数/库
  * 1.Arduino
  <br>核心库，包括GPIO基础函数
  * 2.LedConctroller
  <br>将控制GPIO的基础函数替换，如下
  ```
  //Aruino
  pinMode(pin, mode);  // 配置引脚为输入或输出模式
  digitalWrite(pin, value);  // 设置输出电平（HIGH/LOW）
  ```
  ```
  //LedController
  //介绍详见上一章
  ledcSetup(uint8_t chan, double freq, uint8_t bit_num);
  ledcAttachPin(uint8_t pin, uint8_t chan);
  edcWrite(uint8_t chan, uint32_t duty);
  ```
- 二、代码样例
```
#include <Arduino.h>
void Motor_Setup(int motorID, int pin1,
                 int pin2) {  // 电机初始化 ID=1~4 定义四组电机
  ledcSetup(motorID * 2 - 2, freq, resolution_bits);
  ledcAttachPin(pin1, motorID * 2 - 2);
  ledcSetup(motorID * 2 - 1, freq, resolution_bits);
  ledcAttachPin(pin2, motorID * 2 - 1);
}
void setup() {
  delay(500);
  Serial.begin(115200);
  
  Motor_Setup(1, 27, 13); // 设电机组标号和对应的引脚
  Motor_Setup(2, 4, 2);
  Motor_Setup(3, 17, 12);
  Motor_Setup(4, 15, 14);
}


void loop() {
  delay(1000);
}
```

