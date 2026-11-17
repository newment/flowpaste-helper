# FlowPaste Helper

[FlowPaste](https://flowpaste.app) 剪贴板管理器的自动粘贴助手。

## 为什么需要 Helper？

Mac App Store 沙盒限制（Guideline 2.4.5）禁止应用模拟键盘按键。FlowPaste 主应用（App Store 版）只能将内容写回剪贴板，无法替你按下 ⌘V。FlowPaste Helper 是一个独立的 macOS 后台代理，通过系统「辅助功能」权限完成这最后一步。

## 安装

1. 下载 `FlowPaste-Helper-x.x.x.zip`
2. 解压后将 FlowPaste Helper.app 拖入应用程序文件夹
3. 打开 FlowPaste Helper，授予辅助功能权限
4. 在 FlowPaste 设置中启用「自动粘贴」

## 工作原理

```
用户按 Enter 选中条目
    ↓
FlowPaste（沙盒应用）写回剪贴板
    ↓
FlowPaste 发送分布式通知信号
    ↓
FlowPaste Helper（非沙盒）收到信号
    ↓
Helper 向前台应用投递 ⌘V 键盘事件
    ↓
目标应用粘贴内容
```

## 安全

- 仅监听一个通知名称，仅执行一个动作
- 不读取屏幕、不监控键盘、不上传数据
- 代码开源，可自行审计

## 卸载

删除应用程序中的 FlowPaste Helper 即可，登录项自动移除。

## License

MIT
