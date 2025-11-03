# Augment Code Z - 三重增强注入版

本增强版在官方 Augment 扩展基础上进行**三重注入**（拦截器 + Token 登录增强 + 余额增强），提供更灵活的网络拦截、认证管理和余额监控体验。

## 🎯 三重注入功能

### 1. 拦截器注入 (Interceptor)
- 🛡️ 拦截网络 API 请求，防止账号被检测
- 🔐 Session ID 伪造
- 💻 硬件信息伪造
- 🚫 防封号保护

### 2. Token 登录增强 (Token Login Enhanced)
- 🔑 **Token Management** - Token 管理界面
- 🚀 **Direct Login** - 直接登录功能
- 🔗 支持推送深链 `autoAuth/push-login`，自动解析 tenantURL/accessToken/Portal
- 📋 提供 Webview 表单登录
- 💾 查看/复制/更新当前会话信息（accessToken、tenantURL）
- 🔄 自动更新余额监控 token

### 3. 余额显示增强 (Balance Enhanced)
- 💰 在 VS Code 状态栏实时显示账户余额
- ⏱️ 支持自动刷新（可配置间隔 60-3600 秒）
- 📊 从"查看用量/Portal"链接中提取 token
- ⚙️ 可配置显示/隐藏开关

## 📋 新增命令

### Token 登录相关
- `Augment: Token Management` - 打开 Token 管理界面
- `Augment: Direct Login` - 直接登录

### 余额显示相关
- `Augment Balance: Open Settings` - 打开余额设置
- `Augment Balance: Refresh Balance` - 手动刷新余额
- `Augment Balance: Toggle Display` - 切换显示/隐藏

## ⚙️ 配置项

```json
{
  "augmentBalance.token": "余额监控 token 或 View usage 链接",
  "augmentBalance.updateInterval": 600,  // 更新间隔（秒，范围：60-3600）
  "augmentBalance.enabled": true         // 是否启用余额显示
}
```

## 🔗 配套工具

- **一键换号工具**: [zAugment](https://github.com/Zheng-up/zAugment)
  - 实现一键换号
  - 更新余额监控 token
  - 推送登录到 VS Code

---

