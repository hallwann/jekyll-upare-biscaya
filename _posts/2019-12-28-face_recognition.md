---
author: upare
title: 人脸识别管理系统
thumbnail:
  - /assets/projects/face_recognition/images/index.jpg
  - /assets/projects/face_recognition/images/template.jpg
category:
  - project
tag:
  - enterprise
  - ai
  - php
description: 该系统包括：识别前端设备（含显示器、摄像头、RS485、NFC读卡器、补光灯、POE供电模块等）；人脸注册系统（含图片注册、视频注册）；人脸信息管理系统（含用户管理、人脸信息管理、设备管理、设备授权）；API管理系统（含用户注册、人脸注册、人脸信息获取接口）。
---
**发布时间**: 2019-12-28 | **交付方式**: server+client+devices | **服务方式**: 线下  
**升级方式**: 定制 | **售后周期**: 360天

该系统包括：识别前端设备（含显示器、摄像头、RS485、NFC读卡器、补光灯、POE供电模块等）；人脸注册系统（含图片注册、视频注册）；人脸信息管理系统（含用户管理、人脸信息管理、设备管理、设备授权）；API管理系统（含用户注册、人脸注册、人脸信息获取接口）。

 模式可选择在线实时识别或离线识别，需要对前端设备进行定制，前端可对门禁、闸机等设备进行控制，后端进行数据处理和信息推送。

单机版识别套件可以通过左图中的设备完成人脸的注册、识别和数据回传功能，体积小巧，功耗低，适合桌面级别的人脸应用场景。

服务器版包括完整的用户管理、人脸管理单元，系统提供标准的b/s架构API接口（RESTFUL）使得二次开发更容易，对各种前端设备和语言兼容性极好，灵活部署，最多支持65536个设备在线。

- 完整的使用说明
- 协助部署该项目
- 完整的知识产权保护和转移手续
- 客户可根据需要定制页面和功能
- 有限的售后服务
- 第三方接入文档

Developing documents

Title:Face recognition system documents  
website: http://www.upare.com  
Author: Hallwann  
Email: webmaster@howwant.com  
  
Codes:  
 0:Success  
 1:Unknown error  
 2:invalid parameter  
 3:Engine unsuppored  
 4:Memery error  
 5:Bad state  
 6:User cancled  
 7:Expired  
 8:Pause  
 9:Buffer Overflow  
 10:Buffer Underflow  
 11:Disk space low  
 12:Compoent not exsit  
 13:Member global data not exist  
 28672:SDK error  
 28673:Invalid APPID  
 28674:Invalid DETECTKEY   
 28675:APPID &amp; DETECTKEY do not match  
 28676:Invalid SDKKey   
 28677:System version unsupported  
 28678:Licence expired  
 69632:PhotoStyling error  
 69633:Invalid engine handle  
 69634:Invalid memery manager handle  
 69635:Invalid device id  
 69636:Deivce id unsupported  
 69637:Invalid model handle  
 69638:Invalid model size  
 69639:Invalid image handle  
 69640:Image format unsupported  
 69641:Invalid image parameters  
 69642:Image size too large  
 69643:CPU unsupport AVX2  
 73728:Face recognition base error  
 73729:Invalid memory infomation  
 73730:Invalid face recognition image information  
 73731:Invalid face information  
 73732:No GPU avilable  
 73733:Feature level mismatched  
 9001:Device permission denied  
 9002:You need post parameters  
 9003:Serial number or device name post error  
 9004:Device name and the serial number mismatched  
 9005:Incomplete parameters submitted  
 9006:No faces detected  
 9007:Internal function submission error  
 9111:The image can to be coverted to BGR24  
 9112:The image can to be coverted to NV21  
 9113:Fail to read file  
 9114:Memery error  
 9115:Function parameter acquisition error  
 9116:Fail to initialize face detector engine  
 9117:Fail to initialize face feature engine  
 9118:Fail to initialize face age engine  
 9119:Fail to initialize face gender engine  
 9120:Fail to initialize face match engine  
 9121:Static face detected Error  
 9122:Static feature caught Error  
 9123:Static age estimated Error  
 9124:Static gender estimated Error  
 9125:Static face matched Error  
   
  
APIS:  
  
 API:/faces/api/token  
 Flag:token  
 Method:post  
 Usage:Post devices names and serial numbers to get the current token  
 parameters:   
 (string)deviceName  
 (string)sn  
 return:(json){"flag":"token","code":0,"token":"1f3568b85a11dbc4ae0eddf2b6c88c237fbb2d37"}  
 remarks:Every time you post to server need to get a new token  
  
 API:/faces/api/faceDetect  
 Flag:facedetect  
 Method:post  
 Usage:Get the face and its coordinates &amp; angle in the photos you posted  
 parameters:   
 (string)token  
 (file)image  
 return:(json){"flag":"facedetect","code":0,"faces":1,"faceContent":\[{"id":0,"left":132,"top":702,"right":876,"bottom":1446,"angle":1}\]}  
 remarks:angle=1: 0 degree; angle=2: 90 degree; angle=3: 90 degree; angle=4: 180 degree; angle=5: 30 degree; angle=6: 60 degree; angle=7: 120 degree; angle=8: 150 degree; angle=9: 210 degree; angle=10: 240 degree; angle=11: 300 degree; angle=12: 330 degree  
  
 API:/faces/api/faceAge  
 Flag:faceage  
 Method:post  
 Usage:Estimate age by face in image  
 parameters:   
 (string)token  
 (file)image  
 (int)left  
 (int)top  
 (int)right  
 (int)bottom  
 return:(json){"flag":"faceage","code":0,"age":22}  
  
 API:/faces/api/faceGender  
 Flag:facegender  
 Method:post  
 Usage:Estimate gender by face in image  
 parameters:   
 (string)token  
 (file)image  
 (int)left  
 (int)top  
 (int)right  
 (int)bottom  
 return:(json){"flag":"facegender","code":0,"gender":0}  
 remarks:gender 0=male,gender 1=female, gender -1=unknow  
  
 API:/faces/api/faceFeature  
 Flag:facefeature  
 Method:post  
 Usage:Get the picture's faces feature data(base64)  
 parameters:   
 (string)token  
 (file)image  
 (int)left  
 (int)top  
 (int)right  
 (int)bottom  
 return:(json){"flag":"facefeature","code":0,"feature":"ry6D1Oh5CldK2naH2v8","featureSize":123}  
  
 API:/faces/api/faceRecognize  
 Flag:facerecognize  
 Method:post  
 Usage:Matching two features(base64)' data to obtain confidence  
 parameters:   
 (string)token  
 (string)pending  
 (string)original  
 return:(json){"flag":"facerecognize","code":0,"score":0.848038}  
 remarks:Confidence level &gt;=0.6:match,else not match  
  
 API:/faces/api/getDbs  
 Flag:getDbs  
 Method:post  
 Usage:Get array of current device's faces database  
 parameters:   
 (string)deviceName  
 (string)deviceSN  
 (string)token  
 return:(json){'Flag':'getdbs','code':'codes','message':'messages',names:\[{'name':'name1','username':'username1','faceData':'facedata1','picUrl','picurl1'},{'name':'name2','username':'username2','faceData':'facedata2','picUrl','picurl2'},...\]}  
  
 API:/faces/api/regFace  
 Flag:regFace  
 Method:post  
 Usage:Put the uploaded picture's characteristic points in to datebase (For Mobile phone applications)  
 parameters:   
 (string)deviceName  
 (string)deviceSN  
 (string)username(unique)  
 (string)faceName  
 (string)picBase64(base64)  
 (string)faceData(base64):The face's characteristic points to base64 type  
 return:(json){"flag":"regFace","code":0}  
  
 API:/faces/api/clinetFeedback  
 Flag:clinetfeedback  
 Method:post  
 Usage:Clients/devices upload the recognized face inforamtion to the server  
 parameters:   
 (string)deviceName  
 (string)deviceSN  
 (string)faceName  
   
 return:(json){"flag":"clinetfeedback","code":0}  
  
 API:/faces/api/clinetWebResult  
 Flag:clinetwebresult  
 Method:post  
 Usage:Get clients/devices recognzition results  
 parameters:   
 (string)deviceName  
 (string)deviceSN  
   
 return:(json){"flag":"clinetwebresult","code":0,"faceName":"admin","time":1550563890}

  