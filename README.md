# augment-code-z

自动化构建和修改 Augment VSCode 插件，提供三重增强注入功能。

## 🎯 功能特性

### 三重注入（Triple Injection）

1. **拦截器注入** (Interceptor)
   - 网络请求拦截（HTTP/HTTPS/Axios/Fetch/XMLHttpRequest）
   - Session ID 伪造
   - 硬件信息伪造
   - 防检测保护

2. **Token 登录增强** (Token Login Enhanced)
   - 🔐 Token 管理界面
   - 🚀 直接登录功能
   - 🔗 深链支持（autoAuth/push-login）
   - 📋 Webview 图形化登录
   - 💾 会话管理（查看/复制/更新 accessToken 和 tenantURL）
   - 🔄 自动更新余额 token

3. **余额显示增强** (Balance Enhanced)
   - 💰 状态栏实时显示余额
   - ⏱️ 自动刷新（可配置间隔 60-3600秒）
   - 📊 余额监控
   - ⚙️ 配置管理

## 🚀 工作原理

1. 从 VSCode 市场下载最新的官方 Augment 插件
2. 解压插件包
3. 执行三重注入：
   - **头部注入**：拦截器代码
   - **尾部注入**：Token 登录模块加载器
   - **尾部注入**：余额显示模块加载器
   - **尾部注入**：三重导出处理器
4. 复制模块文件到插件目录
5. 更新 package.json 添加命令和配置
6. 合并 README 文档
7. 重新打包为 .vsix 文件
8. 发布到 GitHub Releases（标签：augment-code-z-v{VERSION}）

## 📥 使用方法

### 安装插件

1. 从 [Releases](../../releases) 页面下载最新的 `augment-code-z-{VERSION}.vsix` 文件
2. 在 VSCode 中按 `Ctrl+Shift+P` 打开命令面板
3. 输入 `Extensions: Install from VSIX...`
4. 选择下载的 `.vsix` 文件

### 新增命令

#### Token 登录相关
- `Augment: Token Management` - Token 管理
- `Augment: Direct Login` - 直接登录

#### 余额显示相关
- `Augment Balance: Open Settings` - 打开余额设置
- `Augment Balance: Refresh Balance` - 刷新余额
- `Augment Balance: Toggle Display` - 切换显示/隐藏

### 配置项

```json
{
  "augmentBalance.token": "余额监控 token 或 View usage 链接",
  "augmentBalance.updateInterval": 600,  // 更新间隔（秒）
  "augmentBalance.enabled": true         // 是否启用
}
```

### 一键换号

使用配套工具 [zAugment](https://github.com/Zheng-up/zAugment) 实现一键换号和余额监控。

## 🔗 相关项目

- 原项目: [AugmentInjectoer_release](https://github.com/tanranv5/AugmentInjectoer_release)
- 配套工具: [zAugment](https://github.com/Zheng-up/zAugment)

## 🛠️ 技术栈

- **CI/CD**: GitHub Actions
- **语言**: Python 3, Shell
- **工具**: unzip, jq
- **打包**: ZIP (VSIX 格式)

## 📋 构建触发方式

1. **定时触发**：每 2 小时自动检查并构建新版本
2. **手动触发**：通过 GitHub Actions 手动运行
3. **版本检测**：如果版本已存在则跳过构建

## 📄 许可证

MIT