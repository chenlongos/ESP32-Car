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

* 代码样例
```
const char* webpage = "";//自己编写的网页
AsyncWebServer server(80);
const char* ssid = "Tsinghua-Dongsheng";
const char* password = "";
void notFound(AsyncWebServerRequest *request) {
    request->send(404, "text/plain", "Not found");
}
```

## 预期实现成果
<video width="600" height="600" controls>
  <source src="../resource/img/up_server.mp4" type="video/mp4">
</video>