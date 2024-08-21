# WeChatHook

## 简介

WeChatHook 是一个功能强大的 Python 微信机器人框架，基于 DLL 注入技术构建，支持丰富的接口和高扩展性。通过多线程消息处理，它能够高效应对大量消息，极大地提升你的开发效率。无论是处理复杂任务还是实现个性化需求。

支持的接口
1. 检查登录状态
2. 获取用户信息
3. 发送文本消息
4. CDN发送文本消息
5. 发送图片消息
6. 发送文件消息
7. 发送表情消息
8. 发送小程序消息
9. 发送名片
10. 发送群@消息
11. 发送xml消息
12. 发送链接卡片消息
13. 发送引用消息
14. 发送拍一拍消息
15. 发送视频消息
16. 获取联系人列表
17. 获取联系人详情
18. 创建群聊
19. 退出群聊
20. 获取群详情
21. 获取群成员列表
22. 添加群成员
23. 删除群成员
24. 邀请群成员
25. 转发消息
26. 合并转发
27. 设置朋友权限
28. 获取朋友圈首页
29. 获取朋友圈下一页
30. 朋友圈点赞
31. 朋友圈评论
32. 下载附件
33. 网络查询微信号
34. 僵尸粉检测
35. 添加企业微信好友
36. 拉人进群40内以内
37. 邀请进群40人以上
38. 修改群聊备注
39. 设置群公告
40. 撤回消息
41. 添加好友分享的名片
42. 自动通过好友
43. 转发公众号消息
44. 转发公众号消息通过消息ID
45. 解码图片
46. 获取语音通过消息ID
47. 图片文本识别
48. 获取数据库句柄
49. 执行SQL命令
50. 获取公众号文章
51. 获取本地消息ID
52. 获取a8key
53. 获取企业群

## 微信版本下载
- [WeChatSetup3.9.5.81.exe](http://oss.zuoyu.top/WeChatSetup-3.9.5.81.exe)

## 安装

```bash
pip install wxhook
```

## 使用示例（技术微信:tts1837）

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
技术微信:tts1837
