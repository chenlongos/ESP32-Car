# ESP32驱动舵机

## 舵机信号脉宽映射与角度控制

- 一、舵机控制原理

以下是所使用舵机的PWM脉宽范围
![PWM脉宽范围](https://i-blog.csdnimg.cn/blog_migrate/3839b394f9183896344d5e36e68762a5.png#pic_center "PWM脉宽范围")

- 二、角度、分辨率、脉宽的转换公式

* 1.分辨率与脉宽的转换公式：
  <br>`duty = (pulseWidth / 20000) × (2^duty_max - 1)`
  <br>例如，分辨率为16位，0.5ms脉冲宽度对应的duty值即为(500/20000)×65535=1638

* 2.角度和脉宽的转换公式：
  <br>`angle = (pulseWidth_us - 500) × (180 / (2500 - 500))`

* 由上述两个公式即可推导出角度和分辨率之间的关系

- 三、代码样例
```
void setAngle(int servoNum, int angle) {
  angle = constrain(angle, 0, 180); // 限制角度范围
  float pulseWidth = 500 + angle * (2000.0 / 180.0); // 精确到11.111μs/°// 绝对值映射
  uint32_t duty = (uint32_t)((pulseWidth / 20000.0) * 65535 + 0.5); // 四舍五入
  ledcWrite(servoNum, duty);
}