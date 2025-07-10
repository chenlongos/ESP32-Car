# 网页遥控小车前进
## 控制运动板块与WiFi、网页搭建等板块的结合
* 使用AsyncWebServer中on函数接收网页相关指令
* 这里使用的是GET请求
  ```
  server.on("/led", HTTP_GET, [](AsyncWebServerRequest *request){
  String state = request->getParam("state")->value();
  digitalWrite(LED_PIN, state.toInt());
  request->send(200);});
* 通过以下方法对应控制运动相关函数：
  <br>`request->getParam("state")->value()`