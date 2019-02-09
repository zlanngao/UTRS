# 高校教学资源服务网

高校教学资源服务网是基于微信小程序开发的一款App。

###  项目介绍
狗蛋TV是基于微信小程序+ES6进行开发，能同时运行在Android、iOS环境下。涵盖了音乐、短视频、影评三个版块。
- 开屏引导图
    1. 调用微信wx.onAccelerometerChange重力感应设备API,实现水波荡漾。
    2. 调用wx.getUserInfo获取用户头像。
- 工具类
    1. 用Promise封装wx.request(),简化代码结构:
    
```
const $get = (url, data) => {
  return new Promise((resolve, reject) => {
    wx.request({
      url,
      data,
      header: { 'Content-Type': 'json' },
      success: resolve,
      fail: reject
    })
  })
}
```

  2.  电影评分实现

```
const convertToStarsArray = (average) => {
  const LENGTH = 5;
  const CLS_ON = 'on'; // 全星
  const CLS_HALF = 'half'; // 半星
  const CLS_OFF = 'off'; // 无星
  let result = [];
  let score = Math.round(average) / 2;
  let hasDecimal = score % 1 !== 0
  let integer = Math.floor(score)
  for (let i = 0; i < integer; i++) {
    result.push(CLS_ON)
  }
  if (hasDecimal) {
    result.push(CLS_HALF)
  }
  while (result.length < LENGTH) {
    result.push(CLS_OFF)
  }
  return result;
}
```
    
- 小程序内部组件实现上拉刷新，下拉加载
```
    方法一：scroll-view 组件
    方法二：onPullDownRefresh和onReachBottom方法实现小程序下拉加载和上拉刷新
```

- 阅读模块

    1.  [微信小程序使用wxParse解析html](https://github.com/icindy/wxParse)
    ```
    项目中遇到在微信小程序里需要显示音乐文章的内容，文章内容是通过接口读取的服
    务器中的富文本内容，是html格式的，小程序默认是不支持html格式的内容显示的，
    那我们需要显示html内容的时候，就可以通过wxParse来实现。
    ```
### 项目安装
```
    git clone git@github.com:lishuaixingNewBee/gordanTv.git
```

### 目录结构
------
```shell
|--- utils & Public Function              通用函数
|--- components & components Public View  components和template模板
|--- images & Img Resources               图片资源
|--- pages & View Dir                     页面
```
### ○ 更新记录
#### 2019.2.9
规划小程序的结构，修改课件图标

根目录下app.json更新，music文件夹修改为courseware文件夹，更新后运行成功，不报错。
