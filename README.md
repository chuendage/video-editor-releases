# 字幕工坊 Windows 测试版

当前内测版本：**0.3.0 Pre-release**。此仓库提供公开下载，无需 GitHub 登录，适用于 Windows 10/11 x64。

| 下载 | 用法 | 大小 |
| --- | --- | --- |
| [安装包（推荐）](https://github.com/chuendage/video-editor-releases/releases/download/beta-v0.3.0/VideoWorkflow-0.3.0-setup.exe) | 双击安装，按向导完成后从快捷方式启动 | 657 MiB |
| [便携版 ZIP](https://github.com/chuendage/video-editor-releases/releases/download/beta-v0.3.0/VideoWorkflow-0.3.0-windows-x64-portable.zip) | 完整解压后双击 `VideoWorkflow.exe`，保留整个目录 | 761 MiB |

两种包都包含 Python 运行时、Faster-Whisper small 多语言模型和 FFmpeg，无需安装 Python，首次本地识别无需联网下载模型。默认本地设备为 CPU/int8。`update.zip` 和 `version.json` 供软件升级器使用，首次安装无需单独下载。

## 开始使用

1. 安装并启动“字幕工坊”，在“软件更新”确认版本为 **0.3.0**。
2. 在“字幕识别”选择视频或音频，运行识别后查看、保存生成的 SRT。默认顺序为必剪 B → 剪映 J → 本地 Faster-Whisper；在“识别与草稿设置”调整开关和顺序。云端会上传所选音频，J 的第三方签名服务器只接收请求元数据；离线使用可只启用本地 ASR。
3. 内测人员进入“软件更新”，选择“测试通道”并保存；启动检查可以关闭，也可手动检查更新。
4. 已安装 0.2.0 的员工可先备份安装目录的 `userdata/`，切换到测试通道后检查更新、下载并安装。软件校验更新签名与 SHA-256 后安装、重启；新版启动失败时自动恢复上一版本。

应用默认“正式通道”。本次仅更新测试通道，正式通道暂时没有版本；暂不可用的更新提示不影响字幕识别。

更新基础地址已内置：

```text
https://github.com/chuendage/video-editor-releases/releases/download
```

[0.3.0 安装验证步骤与发布记录](https://github.com/chuendage/video-editor-releases/releases/tag/beta-v0.3.0) · [测试通道](https://github.com/chuendage/video-editor-releases/releases/tag/beta) · [旧版 0.2.0](https://github.com/chuendage/video-editor-releases/releases/tag/beta-v0.2.0)

## 本次范围与验证

本版新增云端优先 ASR、降级原因记录、识别设置和含循环 BGM 的剪映草稿生成。BGM 从 0 覆盖全片，默认 −18 dB，首版不做旁白避让。五步任务创建和执行继续使用 CLI，在线纠错、翻译和配音需配置相应服务；完成任务后可从桌面任务详情生成草稿。完整桌面批处理、四家 TTS、视频滤镜和自动导出待后续版本。

已在 GitHub Windows runner 完成 **136 项测试（0 失败、0 跳过）**、成包真实 B 云端识别、离线识别与降级、草稿/BGM 生成、安装卸载和升级回滚。升级检查使用构造的基线，不代表员工 0.2.0 安装的原位升级已实测。

J 的第三方签名服务在构建机返回 **HTTP 403**，尚无 J 真实转写成功证据；遇此情况自动降级本地，也可关闭 J。员工 Windows 10/11、实际剪映打开/播放和 NVIDIA/CUDA 仍需真机验收。内部包暂未配置 Windows 代码签名。

员工设置和字幕存放于安装目录的 `userdata/`，卸载保留此目录。便携版移动或备份时请保留整个目录。反馈时记录软件版本、Windows/剪映版本、实际 ASR 提供商、错误码和操作步骤。
