# 飞腾派驱动开发指导书

- [前言](preface.md)

- [序章：环境配置与预备知识](chapter_00.md)
  * [* 硬件平台介绍](0_1_hardware_intro.md)
  * [* 开发环境准备](0_2_dev_env.md)
  * [前置知识引导](0_3_prerequisites.md)

- [第一章：ESP32小车基本控制](chapter_01.md)
  * [硬件介绍](1_1_hardware_intro.md)
  * [ESP32使用I/O接口](1_2_io_control.md)
  * [ESP32驱动轮子](1_3_motor_control.md)
  * [项目实践：ESP32驱动小车转向](1_4_turn_around.md)

- [第二章：ESP32小车远程控制](chapter_02.md)
  * [ESP32使能WiFi](2_1_wifi_control.md)
  * [ESP32搭建网络服务](2_2_establish_server.md)
  * [网页遥控小车前进](2_3_web_control_car_advance.md)
  * [项目实践：网页控制小车](2_4_web_control_car.md)

- [第三章：ESP32机械抓手基本控制](chapter_03.md)
  * [ESP32使用PWM](3_1_pwm_control.md)
  * [ESP32驱动舵机](3_2_servo_control.md)
  * [项目实践：ESP32抓取网球](3_3_catch_tennis.md)

- [第四章：YOLO模型训练及识别](chapter_04.md)
  * [网球识别](4_1_tennis_detect.md)
  * [ESP32小车识别](4_2_car_detect.md)
  * [项目实践：网球和ESP32小车位置识别](4_3_tennis_and_car_position_detect.md)

- [第五章：项目实践-边缘智能目标检测](chapter_05.md)
  * [里程碑1：根据YOLO结果返回控制小车指令](5_1_yolo_result_to_car_cmd.md)
  * [里程碑2：根据小车指令转向瞄准网球](5_2_car_cmd_turn_to_tennis.md)
  * [里程碑3：根据小车指令靠近网球](5_3_car_cmd_move_to_tennis.md)
  * [里程碑4：根据小车指令抓取网球](5_4_car_cmd_catch_tennis.md)

- [第六章：项目实践-使用Rust库开发ESP32小车](chapter_06.md)

- [第七章：项目实践-移植ArceOS Unikernel驱动小车](chapter_07.md)

- [第八章：项目实践-基于视觉大模型捡网球](chapter_08.md)

- [第九章：项目实践-通过语音交互实现捡万物](chapter_09.md)

- [第十章：项目实践-通过语音交互实现分类存放](chapter_10.md)