# 🎙️ AI语音绘图助手 (AI Voice Drawing Assistant)

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![AI](https://img.shields.io/badge/AI-语音交互-purple)
![Canvas](https://img.shields.io/badge/Canvas-2D绘图-orange)

> 🌟 **用语音指挥AI，让想象力在画布上自由绽放** —— 全球首个支持实时语音预览的智能绘图系统

## 📖 项目简介

AI语音绘图助手是一款革命性的语音控制绘图工具，彻底改变了传统的绘图交互方式。用户只需通过简单的语音指令，就能在Canvas画布上实时绘制各种图形，实现"边说边画"的神奇体验。项目包含两个核心产品：纯语音控制的AI绘图工具和生图工具的语音增强版本。

本项目创新性地集成了Web Speech API、HTML5 Canvas 2D API和智能语音识别技术，构建了一套完整的语音绘图指令系统。支持43种语音指令，涵盖从基础图形绘制到复杂场景创作的全方位需求。无论是初学者还是专业设计师，都能通过自然语言与画布进行流畅交互，让创意表达变得更加直观和高效。

项目采用模块化架构设计，包含14个独立的JavaScript模块，遵循命令模式和适配器模式，确保系统的可扩展性和可维护性。整个应用打包为单个HTML文件，使用Tailwind CSS实现现代化UI，无需任何构建工具即可直接运行。

## 🚀 核心创新点

| 创新特性 | 描述 |
|---------|------|
| 🎤 **实时语音预览 (边说边画)** | 独创的语音实时预览技术，在语音识别过程中就能看到绘制效果，无需等待识别完成 |
| 🎭 **AI场景自动绘画** | 输入"画日落"等场景描述，AI自动生成10步绘画序列，将复杂场景分解为简单步骤 |
| 🧑‍🏫 **语音引导教程** | AI教师模式，通过语音一步步教你绘画，提供实时指导和反馈 |
| 🖱️ **语音对象编辑** | 支持通过语音选择、移动、缩放、删除画布上的对象，实现完全语音化操作 |
| 🎨 **智能语音指令引擎** | 43种语音指令的智能解析系统，支持自然语言理解，自动匹配绘制参数 |

## ✨ 功能特性

### 基础绘图功能
- 🖌️ 基础图形绘制（矩形、圆形、三角形、直线、曲线等）
- 🎨 颜色和填充设置（支持语音切换颜色、透明度）
- 📐 线条样式调整（宽度、虚线、实线）
- ✏️ 自由绘图模式（语音控制画笔大小）
- 📝 文字添加和编辑

### 智能语音功能
- 🗣️ 43种语音指令支持
- 🔄 实时语音预览（边说边画）
- 🤖 AI场景自动绘画（"画一幅星空"）
- 🎓 语音引导教程（"教我画笑脸"）
- 🎯 语音对象编辑（选择、移动、缩放、删除）
- 🔊 语音反馈和提示

### 辅助功能
- 📁 作品保存和导出（PNG、JSON）
- 🔄 撤销/重做操作
- 📊 绘制历史记录
- 🖼️ 图片缓存（IndexedDB）
- 💾 状态持久化（localStorage）

## 🌐 在线演示

🔗 **[立即体验 AI语音绘图助手](https://your-demo-url.com)**

> 💡 提示：请使用支持Web Speech API的浏览器（Chrome、Edge）获得最佳体验

## 🚀 快速开始

### 环境要求
- 现代浏览器（Chrome 60+、Edge 79+）
- 麦克风权限（用于语音识别）
- HTTP服务器（本地文件协议不支持语音API）

### 运行步骤

```bash
# 1. 克隆仓库
git clone https://github.com/PUP-Skyer/AI-voice-generates-images..git
cd voice-draw-repo

# 2. 启动HTTP服务器（任选一种）
# 方法一：Python
python -m http.server 8000

# 方法二：Node.js
npx serve .

# 方法三：VS Code Live Server扩展

# 3. 打开浏览器访问
# http://localhost:8000
```

### 直接使用
1. 将 `index.html` 文件放入任意HTTP服务器目录
2. 使用浏览器打开页面
3. 授予麦克风权限
4. 开始语音绘图！

## 📋 语音指令列表

### 基础绘图指令
| 指令 | 示例 | 说明 |
|------|------|------|
| `画矩形` | "画一个矩形" | 绘制矩形 |
| `画圆形` | "画圆形" | 绘制圆形 |
| `画三角形` | "画三角形" | 绘制三角形 |
| `画直线` | "画直线" | 绘制直线 |
| `画曲线` | "画曲线" | 绘制曲线 |
| `画线` | "画一条线" | 绘制直线段 |
| `画点` | "画点" | 绘制点 |

### 参数控制指令
| 指令 | 示例 | 说明 |
|------|------|------|
| `设置颜色` | "设置颜色为红色" | 设置图形颜色 |
| `设置大小` | "设置大小为100" | 设置图形尺寸 |
| `设置位置` | "设置位置100 200" | 设置绘制位置 |
| `设置旋转` | "设置旋转45度" | 设置旋转角度 |
| `设置透明度` | "设置透明度50%" | 设置透明度 |
| `设置线宽` | "设置线宽3" | 设置线条宽度 |
| `设置线型` | "设置虚线" | 设置线条样式 |

### 对象操作指令
| 指令 | 示例 | 说明 |
|------|------|------|
| `选择对象` | "选择矩形" | 选择画布对象 |
| `移动对象` | "向右移动100" | 移动选中对象 |
| `缩放对象` | "放大两倍" | 缩放选中对象 |
| `删除对象` | "删除矩形" | 删除选中对象 |
| `旋转对象` | "旋转90度" | 旋转选中对象 |
| `复制对象` | "复制" | 复制选中对象 |

### 智能绘画指令
| 指令 | 示例 | 说明 |
|------|------|------|
| `画场景` | "画一幅日落" | AI自动绘制场景 |
| `教我画` | "教我画笑脸" | 语音引导教程 |
| `填充颜色` | "填充蓝色" | 填充图形颜色 |

### 系统控制指令
| 指令 | 示例 | 说明 |
|------|------|------|
| `清空画布` | "清空画布" | 清空所有内容 |
| `撤销` | "撤销" | 撤销上一步操作 |
| `重做` | "重做" | 重做撤销的操作 |
| `保存作品` | "保存作品" | 保存当前作品 |
| `导出图片` | "导出图片" | 导出为PNG格式 |
| `放大画布` | "放大" | 放大画布视图 |
| `缩小画布` | "缩小" | 缩小画布视图 |

## 🏗️ 技术架构

```
┌─────────────────────────────────────────────────────────────┐
│                     用户语音输入                              │
└─────────────────┬───────────────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────────────┐
│              Web Speech API (SpeechRecognition)              │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │  语音识别    │  │  语音合成    │  │  实时预览    │        │
│  │  (Recognition)│  │ (Synthesis) │  │ (Preview)   │        │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
└─────────────────┬───────────────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────────────┐
│              语音命令引擎 (VoiceCommandEngine)                │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │  命令解析    │  │  参数提取    │  │  指令匹配    │        │
│  │  (Parser)   │  │ (Extractor) │  │ (Matcher)   │        │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
└─────────────────┬───────────────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────────────┐
│              绘制执行层 (Drawing Execution)                   │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │  基础图形    │  │  场景绘画    │  │  对象管理    │        │
│  │ (Shapes)    │  │ (Scene)     │  │ (Objects)   │        │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
└─────────────────┬───────────────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────────────┐
│              HTML5 Canvas 2D 渲染引擎                        │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │  图形绘制    │  │  状态管理    │  │  事件处理    │        │
│  │ (Rendering) │  │ (State)     │  │ (Events)    │        │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
└─────────────────┬───────────────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────────────┐
│              数据持久化层 (Data Persistence)                  │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │  IndexedDB  │  │ localStorage│  │   导出功能    │        │
│  │  (图片缓存)  │  │  (状态保存)  │  │ (PNG/JSON)  │        │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
└─────────────────────────────────────────────────────────────┘
```

## 📁 项目结构

```
voice-draw-repo/
├── README.md                # 项目说明文档
├── index.html              # 主应用文件（单HTML文件）
├── LICENSE                 # MIT许可证
├── CONTRIBUTING.md         # 贡献指南
├── .gitignore              # Git忽略配置
├── docs/                   # 文档目录
│   ├── DESIGN.md           # 设计文档
│   ├── DEMO_SCRIPT.md      # 演示脚本
│   └── CHANGELOG.md        # 更新日志
└── assets/                 # 资源文件（如需要）
```

## 🔍 创新特性详解

### 1. 实时语音预览技术（边说边画）
传统语音绘图工具需要等待语音完全识别后才能看到效果，用户体验差。本项目独创的实时预览技术，在语音识别过程中就开始分析文本，实时更新画布内容。用户每说出一个词，都能立即看到绘制效果，实现真正的"边说边画"。

### 2. AI场景自动绘画
通过自然语言描述场景（如"画一幅日落"），AI会自动将复杂场景分解为10个简单的绘画步骤，生成智能绘画序列。每一步都包含具体的图形参数和绘制顺序，让普通用户也能创作出专业级的作品。

### 3. 语音引导教程系统
AI教师模式通过语音一步步指导用户绘画，提供实时反馈和鼓励。系统会根据用户的绘画进度调整教学节奏，确保每个人都能学会复杂的绘图技巧。

### 4. 语音对象编辑
支持通过语音对画布上的对象进行精确操作，包括选择特定对象、移动到指定位置、缩放到特定比例、旋转到指定角度等。完全语音化的操作流程，让双手离开鼠标也能完成精细编辑。

### 5. 模块化语音指令引擎
采用命令模式设计的语音指令引擎，支持43种指令的智能解析。系统能够理解自然语言的多种表达方式，自动提取参数，适应不同的说话习惯。

## 🌐 浏览器兼容性

| 浏览器 | 版本 | 语音识别 | 语音合成 | Canvas | 状态 |
|--------|------|----------|----------|--------|------|
| Google Chrome | 60+ | ✅ 完整支持 | ✅ 完整支持 | ✅ 完整支持 | 🟢 推荐 |
| Microsoft Edge | 79+ | ✅ 完整支持 | ✅ 完整支持 | ✅ 完整支持 | 🟢 推荐 |
| Safari | 14.1+ | ⚠️ 部分支持 | ✅ 完整支持 | ✅ 完整支持 | 🟡 可用 |
| Firefox | 50+ | ❌ 不支持 | ⚠️ 部分支持 | ✅ 完整支持 | 🔴 有限 |
| Opera | 47+ | ✅ 完整支持 | ✅ 完整支持 | ✅ 完整支持 | 🟢 可用 |

> ⚠️ **注意**：Web Speech API在Chrome和Edge中支持最完善，推荐使用这两个浏览器获得最佳体验。

## 🛠️ 开发指南

### 开发环境搭建
```bash
# 1. 安装Node.js（可选，用于本地服务器）
# 从 https://nodejs.org 下载安装

# 2. 安装代码编辑器（推荐VS Code）
# 安装Live Server扩展用于实时预览

# 3. 克隆项目
git clone https://github.com/PUP-Skyer/AI-voice-generates-images..git
cd voice-draw-repo

# 4. 启动开发服务器
# 使用VS Code Live Server
# 或使用命令行：npx serve .
```

### 代码结构说明
- `index.html` - 包含所有HTML、CSS和JavaScript代码的单文件应用
- 使用Tailwind CSS进行样式设计
- 模块化JavaScript类设计，易于维护和扩展

### 开发建议
1. 修改前请先阅读设计文档 (`docs/DESIGN.md`)
2. 保持单文件架构，所有代码在 `index.html` 中
3. 遵循现有的代码风格和注释规范
4. 新增语音指令需要在命令注册表中添加映射
5. 测试时确保使用支持Web Speech API的浏览器

## 📜 许可证

本项目采用 [MIT 许可证](LICENSE) 开源。

```
MIT License

Copyright (c) 2026 AI Voice Drawing Assistant

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 🙏 致谢

- **Web Speech API** - 提供语音识别和合成的浏览器原生API
- **HTML5 Canvas** - 强大的2D绘图API
- **Tailwind CSS** - 实用优先的CSS框架
- **IndexedDB** - 客户端数据存储解决方案
- **开源社区** - 感谢所有贡献者和反馈者

## 📞 联系方式

- 项目主页：https://github.com/PUP-Skyer/AI-voice-generates-images.
- 问题反馈：https://github.com/PUP-Skyer/AI-voice-generates-images./issues
- 邮箱联系：puchengxi_2026@user.noreply.gitee.com

---

<p align="center">
  <strong>🌟 如果这个项目对您有帮助，请给个Star支持一下！</strong>
</p>
<p align="center">
  <sub>Made with ❤️ by AI Voice Drawing Assistant Team</sub>
</p>