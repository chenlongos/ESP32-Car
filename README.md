# ESP32-Car
ESP32小车开发指导书，本指导书仍在撰写中

## 写给后续编写人员：

如果需要加入视频文件，需要先对视频进行一下转码，因为在chrome浏览器下只能播放编码为h.264的视频，虽然视频文件都是.mp4文件，但内部编码方式可能不一样，因此为了保证所有浏览器都能播放，尽量还是对视频进行一次转码，下面介绍如何转码。  

### ffmpeg工具

ffmpeg是一个命令行工具，因此下载下来想要使用的话要么在下载文件夹内打开命令行，要么把下载路径加入环境变量Path中，这里放一下[ffmpeg下载官方](https://ffmpeg.org/)，下面的使用假定已经完成以上这些工作。  

```cmd
ffmpeg -i [待转码文件路径] -vcodec h264 [输出文件路径]
```

两个文件路径可以是相对路径也可以是绝对路径，但是印象中ffmpeg对文件路径的空格或者中文之类的有比较奇怪的要求，尽量还是不要在路径中有这些比较好。可以在一个比较安全的路劲下转完之后再复制到需要的路径下，下面举个例子：

```cmd
ffmpeg -i ./up_motorcontrol.mp4 -vcodec h264 ./output.mp4
```

- [前言](src/preface.md)

- [序章：环境配置与预备知识](src/chapter0/chapter_00.md)
  * [硬件平台介绍](src/chapter0/0_1_hardware_intro.md)
  * [开发环境准备](src/chapter0/0_2_dev_env.md)
  * [前置知识引导](src/chapter0/0_3_prerequisites.md)

- [第一章：ESP32小车基本控制](src/chapter1/chapter_01.md)
  * [硬件介绍](src/chapter1/1_1_hardware_intro.md)
  * [ESP32使用I/O接口](src/chapter1/1_2_io_control.md)
  * [ESP32驱动轮子](src/chapter1/1_3_motor_control.md)
  * [项目实践：ESP32驱动小车转向](src/chapter1/1_4_turn_around.md)

- [第二章：ESP32小车远程控制](src/chapter2/chapter_02.md)
  * [ESP32使能WiFi](src/chapter2/2_1_wifi_control.md)
  * [ESP32搭建网络服务](src/chapter2/2_2_establish_server.md)
  * [网页遥控小车前进](src/chapter2/2_3_web_control_car_advance.md)
  * [项目实践：网页控制小车](src/chapter2/2_4_web_control_car.md)

- [第三章：ESP32机械抓手基本控制](src/chapter3/chapter_03.md)
  * [ESP32使用PWM](src/chapter3/3_1_pwm_control.md)
  * [ESP32驱动舵机](src/chapter3/3_2_servo_control.md)
  * [项目实践：ESP32抓取网球](src/chapter3/3_3_catch_tennis.md)

- [第四章：YOLO模型训练及识别](src/chapter4/chapter_04.md)
  * [网球识别](src/chapter4/4_1_tennis_detect.md)
  * [ESP32小车识别](src/chapter4/4_2_car_detect.md)
  * [项目实践：网球和ESP32小车位置识别](src/chapter4/4_3_tennis_and_car_position_detect.md)

- [第五章：项目实践-边缘智能目标检测](src/chapter5/chapter_05.md)
  * [里程碑1：根据YOLO结果返回控制小车指令](src/chapter5/5_1_yolo_result_to_car_cmd.md)
  * [里程碑2：根据小车指令转向瞄准网球](src/chapter5/5_2_car_cmd_turn_to_tennis.md)
  * [里程碑3：根据小车指令靠近网球](src/chapter5/5_3_car_cmd_move_to_tennis.md)
  * [里程碑4：根据小车指令抓取网球](src/chapter5/5_4_car_cmd_catch_tennis.md)

- [第六章：项目实践-使用Rust库开发ESP32小车](src/chapter6/chapter_06.md)

- [第七章：项目实践-移植ArceOS Unikernel驱动小车](src/chapter7/chapter_07.md)

- [第八章：项目实践-基于视觉大模型捡网球](src/chapter8/chapter_08.md)

- [第九章：项目实践-通过语音交互实现捡万物](src/chapter9/chapter_09.md)

- [第十章：项目实践-通过语音交互实现分类存放](src/chapter10/chapter_10.md)