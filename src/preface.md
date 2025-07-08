# 前言 

## 目录
- [前言](preface.md)

- [序章：环境配置与预备知识](chapter0/chapter_00.md)
  * [硬件平台介绍](chapter0/0_1_hardware_intro.md)
  * [开发环境准备](chapter0/0_2_dev_env.md)
  * [前置知识引导](chapter0/0_3_prerequisites.md)

- [第一章：ESP32小车基本控制](chapter1/chapter_01.md)
  * [硬件介绍](chapter1/1_1_hardware_intro.md)
  * [ESP32使用I/O接口](chapter1/1_2_io_control.md)
  * [ESP32驱动轮子](chapter1/1_3_motor_control.md)
  * [项目实践：ESP32驱动小车转向](chapter1/1_4_turn_around.md)

- [第二章：ESP32小车远程控制](chapter2/chapter_02.md)
  * [ESP32使能WiFi](chapter2/2_1_wifi_control.md)
  * [ESP32搭建网络服务](chapter2/2_2_establish_server.md)
  * [网页遥控小车前进](chapter2/2_3_web_control_car_advance.md)
  * [项目实践：网页控制小车](chapter2/2_4_web_control_car.md)

- [第三章：ESP32机械抓手基本控制](chapter3/chapter_03.md)
  * [ESP32使用PWM](chapter3/3_1_pwm_control.md)
  * [ESP32驱动舵机](chapter3/3_2_servo_control.md)
  * [项目实践：ESP32抓取网球](chapter3/3_3_catch_tennis.md)

- [第四章：YOLO模型训练及识别](chapter4/chapter_04.md)
  * [网球识别](chapter4/4_1_tennis_detect.md)
  * [ESP32小车识别](chapter4/4_2_car_detect.md)
  * [项目实践：网球和ESP32小车位置识别](chapter4/4_3_tennis_and_car_position_detect.md)

- [第五章：项目实践-边缘智能目标检测](chapter5/chapter_05.md)
  * [里程碑1：根据YOLO结果返回控制小车指令](chapter5/5_1_yolo_result_to_car_cmd.md)
  * [里程碑2：根据小车指令转向瞄准网球](chapter5/5_2_car_cmd_turn_to_tennis.md)
  * [里程碑3：根据小车指令靠近网球](chapter5/5_3_car_cmd_move_to_tennis.md)
  * [里程碑4：根据小车指令抓取网球](chapter5/5_4_car_cmd_catch_tennis.md)

- [第六章：项目实践-使用Rust库开发ESP32小车](chapter6/chapter_06.md)

- [第七章：项目实践-移植ArceOS Unikernel驱动小车](chapter7/chapter_07.md)

- [第八章：项目实践-基于视觉大模型捡网球](chapter8/chapter_08.md)

- [第九章：项目实践-通过语音交互实现捡万物](chapter9/chapter_09.md)

- [第十章：项目实践-通过语音交互实现分类存放](chapter10/chapter_10.md)

## 项目简介

本实践指南将带领您从零开始构建一个基于ESP32的智能网球捡拾小车系统。通过本项目的完整学习路径，您将掌握嵌入式开发、物联网通信、计算机视觉和智能控制等多项前沿技术。（编写中）

## 学习路径

### 基础准备
- **环境配置**：硬件平台介绍与开发环境搭建
- **预备知识**：嵌入式开发基础与ESP32编程入门

### 核心技能培养
1. **基础控制**  
   - ESP32 GPIO控制与电机驱动
   - 实现小车基本运动控制

2. **物联网应用**  
   - WiFi通信与网络服务搭建
   - 网页远程控制实现

3. **机械控制**  
   - PWM技术与舵机控制
   - 机械抓手精准控制

4. **计算机视觉**  
   - YOLO模型训练与部署
   - 目标检测与位置识别

### 进阶项目实践
- **边缘智能系统**：实现自动网球检测与抓取全流程
- **Rust开发实践**：使用Rust进行嵌入式开发
- **Unikernel探索**：移植ArceOS驱动系统
- **AI增强**：视觉大模型与语音交互应用

## 技术亮点

- 从硬件驱动到智能算法的完整开发链条
- 物联网与边缘计算的深度融合
- 传统嵌入式开发与现代AI技术的结合
- 多种编程范式与实践(Rust/Unikernel)

## 适合读者

- 嵌入式开发爱好者
- 物联网应用开发者
- 计算机视觉实践者
- 希望提升完整项目开发能力的学习者

> 通过本项目的阶梯式实践，您将获得从硬件控制到智能识别算法的全栈开发能力，掌握现代嵌入式智能系统的开发方法。