# WeChatHook

## 简介

### 最新版已适配4.1.8
### 最新版已适配4.1.8
### 最新版已适配4.1.8
### 支持视频号直链下载
WeChatHook 是一个功能强大的 Python 微信机器人框架，基于 DLL 注入技术构建，支持丰富的接口和高扩展性。通过多线程消息处理，它能够高效应对大量消息，极大地提升你的开发效率。无论是处理复杂任务还是实现个性化需求！最新版已适配4.1.1

支持的接口
1. 检查登录状态
2. 获取用户信息
3. 发送文本消息
4. CDN发送文本消息
5. CDN发送图片
6. 发送图片消息
7. 发送文件消息
8. 发送表情消息
9. 发送小程序消息
10. 发送名片
11. 发送语音
12. 发送小程序
13. 发送位置
14. 发送音乐卡片
15. 发送链接卡片
16. 扫一扫
17. 小程序code
18. hook日志
19. pb数据
20. 转让群主
21. 发送群@消息
22. 发送xml消息
23. 发送链接卡片消息
24. 发送引用消息
25. 发送拍一拍消息
26. 发送视频消息
27. 获取联系人列表
28. 获取联系人详情
29. 创建群聊
30. 退出群聊
31. 获取群详情
32. 获取群成员列表
33. 添加群成员
34. 删除群成员
35. 邀请群成员
36. 转发任意消息
37. 合并转发
38. 设置朋友权限
39. 获取朋友圈首页
40. 获取朋友圈下一页
41. 朋友圈点赞
42. 朋友圈评论
43. 发送朋友圈
44. 网络查询微信号
45. 僵尸粉检测（方法一）
46. 僵尸粉检测（方法二）
47. 添加企业微信好友
48. 拉人进群40内以内
49. 邀请进群40人以上
50. 修改群聊备注
51. 设置群公告
52. 撤回消息
53. 添加好友分享的名片
54. 自动通过好友
55. 转发公众号消息
56. 转发公众号消息通过消息ID
57. 解码图片
58. 获取语音通过消息ID
59. 图片文本识别
60. 获取数据库句柄
61. 执行SQL命令
62. 获取公众号文章
63. 获取本地消息ID
64. 获取a8key
65. 获取企业群
66. 拉黑
67. 取消拉黑
68. 获取a8key裙邀请
69. 获取a8key公众号
70. 扫一扫获取V3
71. 接收转账
72. 退还转账
73. 获取收款码
74. 修改签名
75. 小程序云函数
76. 获取CDN信息
77. 修改微信号
78. 删除聊天记录
79. 微信设置
80. wxid取昵称
81. 扫一扫获取企业微信url
82. 添加好友

## 微信版本下载
- [WeChatSetup3.9.5.81.exe](https://github.com/tom-snow/wechat-windows-versions/releases/download/v3.9.5.81/WeChatSetup-3.9.5.81.exe)

## 安装

```bash
pip install wxhook
```

## 使用示例（技术Q:1332356386）

```python
# import os
# os.environ["WXHOOK_LOG_LEVEL"] = "INFO" # 修改日志输出级别
# os.environ["WXHOOK_LOG_FORMAT"] = "<green>{time:YYYY-MM-DD HH:mm:ss}</green> | <level>{message}</level>" # 修改日志输出格式
from wxhook import Bot
from wxhook import events
from wxhook.model import Event


def on_login(bot: Bot, event: Event):
    print("登录成功之后会触发这个函数")


def on_start(bot: Bot):
    print("微信客户端打开之后会触发这个函数")


def on_stop(bot: Bot):
    print("关闭微信客户端之前会触发这个函数")


def on_before_message(bot: Bot, event: Event):
    print("消息事件处理之前")


def on_after_message(bot: Bot, event: Event):
    print("消息事件处理之后")


bot = Bot(
    # faked_version="3.9.10.19", # 解除微信低版本限制
    on_login=on_login,
    on_start=on_start,
    on_stop=on_stop,
    on_before_message=on_before_message,
    on_after_message=on_after_message
)


# 消息回调地址
# bot.set_webhook_url("http://127.0.0.1:8000")

@bot.handle(events.TEXT_MESSAGE)
def on_message(bot: Bot, event: Event):
    bot.send_text("filehelper", "hello world!")


bot.run()
```
技术Q:1332356386
