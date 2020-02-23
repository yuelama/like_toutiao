# wmp-news

### Udacity 微信小程序纳米学位课程项目——震今新闻



#### 项目简介

本项目为Udacity微信小程序纳米学位课程项目--新闻应用。主要包括新闻列表页，新闻详情页和用户标签设置页。主要实现动态显示新闻列表，点击新闻跳转新闻详情浏览，获取用户授权设置新闻类型标签，通过野狗云进行用户信息及用户标签信息存储

#### 运行环境说明

由于本项目为学习项目，在微信小程序中直接获取用户信息`wx.getuserinfo`存在`https://api.weixin.qq.com
不在以下 request 合法域名列表中`中的问题，故在电脑模拟器运行时需勾选`不校验合法域名、
web-view（业务域名）、TLS 版本以及 HTTPS 证书`，在手机端需打开`调试模式`。后期将所有调用接口移至后台服务，
保证数据的安全性

#### 主要实现功能

- 小程序入口
  - 配置野狗云服务，实例化服务
  - 用户通过`wx.login`登录并获取用户openId
  - 根据openId获取野狗云中用户信息（所选择的标签）
  - 更新（update）野狗云中的当前用户信息
  - 设置（add）野狗云中的当前用户信息
- 新闻列表页
  - 根据用户信息动态设置显示的新闻类型
  - 调用API获取当前选中的新闻类型的新闻列表
  - 使用`swiper`组件显示3条新闻滚动播放
  - 点击新闻跳至`新闻详情页`
  - 点击`新闻类型设置`请求用户授权，授权成功后跳转至`标签设置页`
- 新闻详情页
  - 根据路由传递的新闻Id调用API获取新闻详情并渲染
  - 根据不同新闻内容显示不同格式
- 标签设置页
  - 获取已授权用户个人信息，显示用户头像和昵称
  - 从野狗云获取当前用户设置的标签
  - 点击标签修改用户设置的标签信息并同步至野狗云
  - 返回`新闻列表页`时可根据用户新设置的标签重新渲染新闻列表

界面截图

![tag-setting](./images/screenshot/news-list.png)
![tag-setting](./images/screenshot/news-detail.png)
![tag-setting](./images/screenshot/tag-setting.png)
