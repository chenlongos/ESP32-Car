# 0.3 前置知识引导 

## 与Arduino开发相关的语法介绍
- 一、基础语法架构
  <br>`void setup() {
  // 初始化代码，只执行一次}`
  <br>`void loop() {
  // 主循环代码，重复执行}`
- 二、相关库中核心函数的介绍
  * **LedController**
  <br>(1)**ledcSetup() - PWM通道初始化**
  <br>`double ledcSetup(uint8_t chan, double freq, uint8_t bit_num)`
  <br>i.**功能**​​：配置指定LEDC通道的PWM信号参数
​​  <br>ii.**参数**​​：
  <br>chan：通道号(0-15，取决于ESP32型号)
  <br>freq：PWM频率(Hz)
  <br>bit_num：占空比分辨率(1-16位)
​​  <br>返回值​​：实际设置的频率值
​​  <br>iii.**说明**​​：必须先调用此函数初始化通道才能使用其他PWM功能
  <br>(2)**ledcAttachPin() - 引脚绑定**
  <br>`void ledcAttachPin(uint8_t pin, uint8_t chan)`
  <br>i.**功能**​​：将GPIO引脚绑定到指定的PWM通道
​​  <br>ii.**参数**​​：
  <br>pin：GPIO引脚号
  <br>chan：已初始化的PWM通道号
​​  <br>iii.**说明**​​：一个通道可绑定多个引脚，实现同步控制
  <br>(3)**ledcWrite() - 占空比设置**
  <br>`void ledcWrite(uint8_t chan, uint32_t duty)`
  <br>i.**功能**​​：设置指定通道的PWM占空比
​  <br>ii.**​参数**​​：
  <br>chan：PWM通道号
  <br>duty：占空比值(范围由分辨率决定)
​​  <br>iii.**说明**​​：这是最核心的PWM输出函数，用于实时调整输出强度

## PWM原理与占空比计算
- PWM基本原理
  * 1.**核心概念**
  <br>**脉冲信号**​​：由高电平和低电平交替组成的方波信号
​​  <br>**周期**(T)​：一个完整PWM波形的时间长度（单位：秒）
​​  <br>**频率**(f)​​：单位时间内周期数，f=1/T（单位：Hz）
​​  <br>**脉宽**(高电平时间)​​：一个周期内信号保持高电平的时间
​​  <br>**占空比**(D)：高电平时间与周期的比值，D = (高电平时间/T) × 100%
  * 2.**工作原理**
  <br>**PWM基于​​面积等效原理**​​：冲量（脉冲面积）相等而形状不同的窄脉冲加在具有惯性的环节上时，其效果基本相同。
  <br>通过改变占空比来调节平均输出电压：
  <br>占空比越大 → 平均电压越高
  <br>占空比越小 → 平均电压越低

