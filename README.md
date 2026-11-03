# Windows Application Archive

社区维护的 Windows 应用归档与 Linux ARM64 应用元数据索引，用于软件保存、兼容性研究和自动化获取。

本仓库不是所收录软件原开发商或发行商的官方仓库。应用名称和商标归各自权利人所有。

## 内容

- Releases：完整的 Windows 应用或经授权可再分发的 Linux ARM64 安装包
- `apps/*.json`：应用版本、文件名、大小、架构与摘要元数据
- `routes.json`：面向受支持客户端的结构化路由指导与安装建议；不包含任意命令、URL 或产品专用提示词
- `schema/*.json`：应用归档和路由指导的元数据格式定义

归档文件会记录准确大小和 SHA-256，以便下载后检查文件完整性。兼容性、许可证和使用条件以对应应用及其运行环境为准。

## 路由指导

`routes.json` 使用版本化结构描述精确应用名、用户意图、目标平台和受控结果。当前支持：

- `install_catalog_application`：把目标切换到 `applications.json` 中可解析的应用名称，再执行原安装校验。
- `open_android_app_search`：提示用户打开指定 Android 应用并搜索目标；客户端只生成受控打开动作。
- `plain_guidance`：展示长度受限的普通文字步骤。

路由文本不得包含 Markdown 链接、URL、Claw 协议、Shell、HTML 或工具调用。产品内置的专用路由优先于本文件；本仓库当前不配置 Steam 路由。
