# 高校教学资源服务网

高校教学资源服务网是基于微信小程序开发的一款App。
### ○ 更新记录
#### 2019.2.9
规划小程序的结构，修改课件图标

根目录下app.json更新，pages/music文件夹修改为pages/courseware文件夹，pages/welcome/welcom.js更新后运行成功，不报错。
出现github上的pages/music文件夹无法删除，本机文件已经改名为courseware，music文件夹是要删除的，查阅资料发现需要使用命令才能删除，问题尚未解决。


### ○ 项目介绍
高校教学资源服务网是基于微信小程序+ES6进行开发，能同时运行在Android、iOS环境下。涵盖了课件、微课、资源三个版块。
- 开屏引导图
    1. 调用微信wx.onAccelerometerChange重力感应设备API,实现水波荡漾。
    2. 调用wx.getUserInfo获取用户头像。
- 工具类
    1. 用Promise封装wx.request(),简化代码结构:
    2.  电影评分实现
