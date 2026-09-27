# 字幕工坊 Windows 测试版

当前内测版本：**0.2.0**。此仓库提供公开下载，无需 GitHub 登录。

| 下载 | 用法 | 大小 |
| --- | --- | --- |
| [安装包](https://github.com/chuendage/video-editor-releases/releases/download/beta-v0.2.0/VideoWorkflow-0.2.0-setup.exe) | 双击安装，按向导完成后从快捷方式启动 | 645 MiB |
| [便携版 ZIP](https://github.com/chuendage/video-editor-releases/releases/download/beta-v0.2.0/VideoWorkflow-0.2.0-windows-x64-portable.zip) | 完整解压后双击 `VideoWorkflow.exe`，保留整个目录 | 744 MiB |

两种包都包含 Python 运行时、Faster-Whisper small 多语言模型和 FFmpeg，无需安装 Python，首次本地识别无需联网下载模型。默认使用 CPU/int8。

## 开始使用

1. 选择安装包或便携版，启动“字幕工坊”。
2. 在“本地字幕识别”选择视频或音频，运行识别后查看、保存生成的 SRT。
3. 内测人员进入“软件更新”，选择“测试通道”并保存；启动检查可以关闭，也可手动检查更新。
4. 出现新版时点击下载并安装。软件校验更新签名与 SHA-256 后安装、重启；新版启动失败时自动恢复上一版本。

应用默认“正式通道”。本次仅发布测试通道，正式通道暂时没有版本；暂不可用的更新提示不影响本地字幕识别。

更新基础地址已内置：

```text
https://github.com/chuendage/video-editor-releases/releases/download
```

[测试通道](https://github.com/chuendage/video-editor-releases/releases/tag/beta) · [0.2.0 固定发行记录](https://github.com/chuendage/video-editor-releases/releases/tag/beta-v0.2.0)

## 本次范围与验证

本版提供本地字幕识别、任务查看、环境诊断和在线升级；原有五步 CLI 保留，在线纠错、翻译和配音需要另行配置服务。完整桌面批处理、剪映草稿和自动导出留待后续版本。

已在 GitHub Windows runner 完成 101 项测试、成包真实离线识别、安装卸载，以及正常升级和损坏 EXE 回滚检查。仍需员工 Windows 10/11 实机内测；NVIDIA/CUDA 尚未实机验收。内部包暂未配置 Windows 代码签名。

员工设置和字幕存放于安装目录的 `userdata/`，卸载保留此目录。便携版移动或备份时请保留整个目录。
