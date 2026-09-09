# Commdesk

**面向 Windows 的中文通信调试工作台。** 将串口、蓝牙、TCP / UDP 通信、命令管理与 Lua / C 脚本集成在一个紧凑的桌面界面中，适合嵌入式开发、设备联调与日常通信排查。

本仓库用于托管公开发行包和自动更新清单，不是源码仓库。

## 主要功能

- **多种连接方式**：串口、蓝牙客户端、TCP 客户端 / 服务端、UDP 客户端 / 服务端；支持 Windows 虚拟串口工具。
- **通信监视与记录**：文本与 HEX 收发、时间戳、方向筛选、搜索、暂停滚动、记录导出及本地 JSONL 原始数据记录。
- **命令目录管理**：按文件夹组织 TXT、HEX、Lua 和 C 命令，支持独立编辑窗口、语法高亮以及 Lua / C 本地代码格式化。
- **脚本与控件**：使用 Lua / C 编写调试流程和交互控件，支持先运行脚本、后连接设备。
- **便携工作目录**：程序、设置、命令与日志保存在同一目录树中，复制整个文件夹即可迁移。
- **双源签名更新**：在软件设置中检查更新，自动下载并校验更新包，再替换程序并重新启动。

## 下载与运行

- [Gitee 发行版（主源）](https://gitee.com/cauzyx/commdesk-releases/releases)
- [GitHub Releases（备用源）](https://github.com/cauzyx/commdesk-releases/releases)

在发行版页面下载 `Commdesk_<版本>_windows-x64.zip`，完整解压到可写目录，打开 `Commdesk.exe`。请保留同目录的运行时和工具文件，不要只复制主程序，也不要直接在压缩包中运行。

**运行环境：Windows 10 / 11 x64，以及 Microsoft Edge WebView2 Runtime。** 正常使用不需要安装 Node.js、Rust 或开发工具。

## 自动更新

**Gitee 为主源，GitHub 为备用源。** 软件先访问 Gitee；主源不可用时尝试 GitHub。两个平台托管相同的更新包和版本清单：

- Gitee：`master` 分支的 `latest.json`
- GitHub：`main` 分支的 `latest.json`

软件通过 SHA-256 与数字签名校验下载内容，更新时保留用户设置、现有命令及日志；安装或新版本启动失败时尝试恢复旧版。更新包与首次解压使用的便携包为同一文件。签名校验用于自动更新，不等同于 Windows 商业代码签名。

首次发行包与清单上传完成后，在线检查更新才会生效；后续版本继续通过上述双源分发。

## 使用说明

- 首次启动不会自动连接真实设备；连接前请核对通信参数。
- Lua / C 脚本以当前用户权限运行，只运行可信脚本。
- 虚拟串口驱动操作需要管理员授权；普通启动不会静默安装驱动。
- 串口、蓝牙及高吞吐表现取决于设备、驱动和环境；发送成功表示驱动接受数据，不等同于设备已执行命令。
- 更详细的操作说明、脚本 API 和版本说明随发行包提供。

## 反馈

反馈问题时请提供软件版本、Windows 版本、连接方式与复现步骤，并在上传日志前移除账号、密钥或设备私有数据。

- [Gitee Issues](https://gitee.com/cauzyx/commdesk-releases/issues)
- [GitHub Issues](https://github.com/cauzyx/commdesk-releases/issues)
