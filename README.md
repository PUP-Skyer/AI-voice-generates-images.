# 🎙️ 五哥生图 - 语音输入版 (WuGe Image Generation - Voice Edition)

![Version](https://img.shields.io/badge/version-1.2-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Voice](https://img.shields.io/badge/Voice-语音输入-red)

> 🎤 **为五哥生图添加语音输入功能** —— 用说话代替打字，让AI生图更便捷

---

## 📖 项目简介

本项目在 [五哥生图](https://api.wuyinkeji.com) 的基础上，创新性地集成了 **Web Speech API 语音识别技术**，为AI图片生成工具添加了语音输入功能。用户只需点击麦克风按钮，就能通过说话来输入图片描述词，无需手动打字，大幅提升了使用便捷性。

### 核心功能

- 🎤 **语音输入**：点击麦克风按钮，说话即可输入提示词（**原创功能**）
- 🖼️ **AI生图**：支持 GPT 和 NanoBanana Pro 两种生图模型（**基于五哥生图API**）
- 📝 **实时转写**：语音识别结果实时填充到输入框（**原创功能**）
- 🎨 **参考图支持**：支持URL和本地上传参考图（**基于五哥生图原代码**）
- 💾 **历史记录**：对话历史和图片画廊持久化存储（**基于五哥生图原代码**）

### ⚠️ 原创功能说明

本项目的**原创功能部分**包括：
1. **语音输入集成**：麦克风按钮UI + Web Speech API语音识别
2. **实时语音转写**：`interimResults`实现边说边显示
3. **追加输入模式**：保留已有文本，语音输入追加到后面
4. **录音状态动画**：CSS脉冲光晕 + 状态提示浮层
5. **智能错误处理**：6种错误场景的友好提示
6. **自动重启机制**：Chrome静默超时后自动恢复监听

### 📝 第三方代码来源

| 代码来源 | 说明 | 授权方式 |
|---------|------|---------|
| [五哥生图 v1.2](https://api.wuyinkeji.com) | 原始AI生图界面和API调用逻辑 | 五哥科技API服务，用于学习和比赛 |
| [Tailwind CSS](https://tailwindcss.com) | CSS样式框架 | CDN引入，MIT许可证 |
| [Web Speech API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API) | 浏览器原生语音识别API | 浏览器标准API |

---

## 🚀 快速开始

### 环境要求

- 现代浏览器（Chrome 60+、Edge 79+）
- 麦克风权限（用于语音识别）
- HTTP服务器（本地文件协议不支持语音API）

### 运行步骤

```bash
# 1. 克隆仓库
git clone https://github.com/PUP-Skyer/AI-voice-generates-images..git
cd AI-voice-generates-images.

# 2. 启动HTTP服务器（任选一种方式）
# 方式一：使用Python
python -m http.server 8080

# 方式二：使用Node.js
npx serve .

# 方式三：使用PHP
php -S localhost:8080
```

### 使用方式

1. 打开浏览器访问 `http://localhost:8080/五哥生图v1.2-语音版.html`
2. 点击左上角 ⚙️ 按钮设置API密钥
3. 点击底部 🎤 麦克风按钮开启语音输入
4. 对着麦克风说话，文字会实时填入输入框
5. 点击发送按钮生成图片

---

## 🎤 语音输入功能详解

### 技术实现

基于 **Web Speech API**（`SpeechRecognition` 接口），实现了：

| 特性 | 实现方式 |
|------|---------|
| 语音识别 | `SpeechRecognition` 连续识别模式 |
| 语言设置 | 中文（zh-CN） |
| 实时转写 | `interimResults = true`，边说边显示 |
| 追加模式 | 支持在已有文本基础上继续语音输入 |
| 自动重启 | Chrome静默超时后自动恢复监听 |
| 错误处理 | 网络/权限/设备等6种错误的友好提示 |

### 使用流程

```
点击🎤按钮 → 浏览器请求麦克风权限 → 开始监听
     ↓
说话 → 实时转写到输入框 → 再次点击🎤停止
     ↓
点击发送 → 调用五哥API生图 → 图片显示在画廊
```

### 浏览器兼容性

| 浏览器 | 支持情况 | 说明 |
|--------|---------|------|
| Chrome 60+ | ✅ 完全支持 | 推荐使用 |
| Edge 79+ | ✅ 完全支持 | 基于Chromium |
| Firefox | ⚠️ 部分支持 | 需要手动启用 |
| Safari | ❌ 不支持 | 未实现Web Speech API |

> ⚠️ **注意**：Web Speech API 依赖 Google 语音服务器，国内网络需要VPN才能使用语音识别功能。

---

## 📁 项目结构

```
AI-voice-generates-images.
├── README.md                          # 项目说明文档
├── LICENSE                            # MIT许可证
├── CONTRIBUTING.md                    # 贡献指南
├── .gitignore                         # Git忽略配置
├── src/
│   └── 五哥生图v1.2-语音版.html        # 主应用（语音增强版）
└── docs/
    ├── CHANGELOG.md                   # 更新日志
    └── DEMO_SCRIPT.md                 # 演示视频脚本
```

---

## 🏗️ 技术架构

```
┌─────────────────────────────────────────────────┐
│                  五哥生图 v1.2                     │
├─────────────────────────────────────────────────┤
│  原有功能：                                       │
│  ├── GPT生图（0.1元/张）                          │
│  ├── NanoBanana Pro（0.3元/张）                   │
│  ├── 参考图支持（URL + 本地上传）                   │
│  ├── 图片画廊 + 轻箱预览                          │
│  └── 对话历史管理                                │
├─────────────────────────────────────────────────┤
│  新增功能：语音输入                                │
│  ├── 🎤 麦克风按钮（CSS动画）                     │
│  ├── Web Speech API 集成                         │
│  ├── 实时语音转文字                               │
│  ├── 追加模式（保留已有文本）                      │
│  ├── 录音状态指示（脉冲动画）                      │
│  └── 错误处理（网络/权限/设备）                    │
└─────────────────────────────────────────────────┘
```

---

## 📋 API依赖

本项目调用以下外部API：

| API | 用途 | 说明 |
|-----|------|------|
| 五哥科技 API | AI图片生成 | 需要API密钥 |
| Web Speech API | 语音识别 | 浏览器原生API |

### 第三方库

| 库 | 版本 | 用途 | 许可证 |
|----|------|------|--------|
| Tailwind CSS | CDN | UI样式框架 | MIT |

---

## 🔍 创新特性

### 1. 语音输入集成

在原有五哥生图的输入栏中新增麦克风按钮，点击后启动Web Speech API进行语音识别。识别结果实时填充到textarea中，支持追加模式（在已有文本基础上继续输入）。

### 2. 录音状态动画

- **按钮状态**：录音时按钮变红 + 脉冲光晕动画
- **状态提示**：按钮上方显示"正在聆听..."浮层
- **停止动画**：点击停止后动画消失

### 3. 智能错误处理

针对6种错误场景提供友好提示：
- `network`：语音服务网络不可用（需VPN）
- `not-allowed`：麦克风权限被拒绝
- `no-speech`：未检测到语音
- `audio-capture`：未检测到麦克风设备
- `service-not-allowed`：语音服务不可用
- `aborted`：识别被中断

### 4. 自动重启机制

Chrome浏览器会在静默一段时间后自动停止语音识别。本项目实现了自动重启机制，在识别停止后自动恢复监听，确保持续可用。

---

## 🛠️ 开发指南

### 本地开发

```bash
# 1. 克隆仓库
git clone https://github.com/PUP-Skyer/AI-voice-generates-images..git

# 2. 启动本地服务器
python -m http.server 8080

# 3. 打开浏览器
open http://localhost:8080/五哥生图v1.2-语音版.html
```

### 代码修改

- 所有代码在 `src/五哥生图v1.2-语音版.html` 单文件中
- 语音输入功能在 `/* ===== 语音输入功能 ===== */` 注释块中
- 使用Tailwind CSS进行样式设计

### 测试语音功能

1. 使用Chrome浏览器打开页面
2. 确保可以访问Google服务（语音识别依赖）
3. 点击麦克风按钮，允许麦克风权限
4. 说话测试语音识别

---

## 📜 许可证

本项目采用 [MIT 许可证](LICENSE) 开源。

---

## 🙏 致谢

- [五哥生图](https://api.wuyinkeji.com) - AI图片生成API服务
- [Web Speech API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API) - 浏览器语音识别API
- [Tailwind CSS](https://tailwindcss.com) - 实用优先的CSS框架
- [HTML5 Canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) - 2D绘图API

---

## 📞 联系方式

- 项目主页：https://github.com/PUP-Skyer/AI-voice-generates-images.
- 问题反馈：https://github.com/PUP-Skyer/AI-voice-generates-images./issues
- 邮箱联系：puchengxi_2026@user.noreply.gitee.com

---

⭐ 如果这个项目对您有帮助，请给个Star支持一下！

---

## 🎬 演示视频

▶️ [AI语音生成图片演示视频](https://www.bilibili.com/video/BV1P6Jg6sE2w)
