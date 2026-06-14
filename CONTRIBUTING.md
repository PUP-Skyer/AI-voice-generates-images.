# 贡献指南 (Contributing Guide)

感谢您对 AI语音绘图助手 项目的关注！我们欢迎所有形式的贡献，包括代码、文档、问题报告和功能建议。

## 📋 目录

- [开发环境搭建](#开发环境搭建)
- [如何贡献](#如何贡献)
- [代码风格指南](#代码风格指南)
- [提交信息规范](#提交信息规范)
- [Pull Request 要求](#pull-request-要求)
- [问题报告](#问题报告)
- [功能建议](#功能建议)

---

## 开发环境搭建

### 1. 环境要求

- **操作系统**: Windows 10+, macOS 10.14+, 或 Linux
- **浏览器**: Google Chrome 60+ 或 Microsoft Edge 79+（用于测试语音功能）
- **开发工具**: 任何代码编辑器（推荐 VS Code）
- **Node.js**: v14+ （可选，用于本地开发服务器）

### 2. 安装步骤

```bash
# 1. Fork 项目仓库
# 在 GitHub 页面点击 "Fork" 按钮

# 2. 克隆您的 Fork 仓库
git clone https://github.com/your-username/voice-draw-repo.git
cd voice-draw-repo

# 3. 添加上游仓库
git remote add upstream https://github.com/original-owner/voice-draw-repo.git

# 4. 创建开发分支
git checkout -b feature/your-feature-name
```

### 3. 启动本地服务器

```bash
# 方法一：使用 Python
python -m http.server 8000

# 方法二：使用 Node.js
npx serve .

# 方法三：使用 VS Code Live Server 扩展
# 安装扩展后右键点击 index.html -> "Open with Live Server"
```

### 4. 访问应用

打开浏览器访问 `http://localhost:8000`

---

## 如何贡献

### 1. 报告问题 (Bug Report)

如果您发现了 Bug，请：

1. 在 [Issues 页面](https://github.com/yourusername/voice-draw-repo/issues) 搜索是否已有相同问题
2. 如果没有，创建新的 Issue，使用 Bug Report 模板
3. 提供详细的问题描述、复现步骤、期望行为和实际行为
4. 包含浏览器版本、操作系统等环境信息
5. 如果可能，提供截图或屏幕录制

### 2. 提交代码

1. 从 `main` 分支创建您的功能分支
2. 进行代码修改和测试
3. 确保代码符合项目规范
4. 提交 Pull Request

### 3. 改进文档

文档的改进同样重要，包括：
- 修复错别字和语法错误
- 添加使用示例
- 完善 API 文档
- 翻译文档

---

## 代码风格指南

### JavaScript 规范

```javascript
// 1. 使用 ES6+ 特性
const greeting = "Hello"; // 使用 const
let count = 0;            // 使用 let（避免 var）

// 2. 命名规范
// 变量和函数：camelCase
const maxRetries = 3;
function drawRectangle() {}

// 类名：PascalCase
class VoiceCommandEngine {}

// 常量：UPPER_SNAKE_CASE
const MAX_RETRY_COUNT = 3;

// 3. 缩进：2 个空格
if (condition) {
  doSomething();
}

// 4. 字符串：优先使用单引号
const message = 'Hello World';

// 5. 分号：始终使用分号
const value = 10;
```

### HTML/CSS 规范

```html
<!-- HTML -->
<!-- 使用语义化标签 -->
<div class="container">
  <header>...</header>
  <main>...</main>
</div>

<!-- 属性顺序 -->
<div id="app" class="main" data-name="voice-draw"></div>
```

```css
/* CSS */
/* 使用 Tailwind CSS 工具类 */
/* 自定义样式遵循 BEM 命名规范 */
.container {
  /* 属性按字母顺序排列 */
  background-color: white;
  color: black;
  font-size: 16px;
}
```

### 代码组织

```javascript
// 每个类/模块遵循以下结构：
/**
 * 类/模块描述
 * @author 作者名
 * @version 版本号
 */
class ClassName {
  // 1. 静态属性
  static instance = null;

  // 2. 构造函数
  constructor(options) {
    // 2.1 属性初始化
    this.property = options.property;
    
    // 2.2 方法调用
    this.init();
  }

  // 3. 静态方法
  static getInstance() {}

  // 4. 公共方法
  methodName() {}

  // 5. 私有方法（使用 # 前缀或约定）
  #privateMethod() {}

  // 6. getter/setter
  get value() {}
  set value(val) {}
}
```

---

## 提交信息规范

我们使用 [Conventional Commits](https://www.conventionalcommits.org/zh-hans/) 规范。

### 格式

```
<type>(<scope>): <subject>

<body>

<footer>
```

### 类型 (type)

| 类型 | 说明 | 示例 |
|------|------|------|
| `feat` | 新功能 | `feat(voice): 添加语音命令识别` |
| `fix` | 修复 Bug | `fix(canvas): 修复矩形绘制偏移问题` |
| `docs` | 文档更新 | `docs: 更新 README 使用说明` |
| `style` | 代码格式（不影响功能） | `style: 修复代码缩进` |
| `refactor` | 重构（非新功能、非修复） | `refactor(engine): 重构命令解析逻辑` |
| `perf` | 性能优化 | `perf(render): 优化 Canvas 渲染性能` |
| `test` | 测试相关 | `test: 添加语音引擎单元测试` |
| `chore` | 构建/工具链更新 | `chore: 更新 ESLint 配置` |
| `ci` | CI/CD 配置 | `ci: 添加 GitHub Actions` |

### 示例

```bash
# 简单提交
git commit -m "feat(voice): 添加语音实时预览功能"

# 详细提交
git commit -m "fix(canvas): 修复旋转角度计算错误

- 修复了顺时针旋转 90 度时的计算错误
- 添加了旋转角度的边界检查

Closes #123"
```

### 范围 (scope)

可选的范围包括：
- `voice` - 语音相关功能
- `canvas` - Canvas 绘制相关
- `engine` - 语音命令引擎
- `ui` - 用户界面
- `scene` - 场景绘画功能
- `docs` - 文档
- `test` - 测试

---

## Pull Request 要求

### 1. PR 标题

使用与提交信息相同的格式：

```
feat(voice): 添加语音命令识别功能
```

### 2. PR 描述模板

```markdown
## 📝 概述
<!-- 简要描述这个 PR 做了什么 -->

## 🎯 变更类型
- [ ] Bug 修复
- [ ] 新功能
- [ ] 重构
- [ ] 文档更新
- [ ] 其他

## 📋 详细描述
<!-- 详细描述变更内容 -->

## 🧪 测试情况
<!-- 描述如何测试这些更改 -->

### 测试步骤
1. 打开应用
2. 执行 XXX 操作
3. 验证 XXX 结果

### 测试环境
- 浏览器: Chrome 120.0
- 操作系统: Windows 11

## 📸 截图/录屏
<!-- 如果是 UI 变更，请提供截图 -->

## ✅ 检查清单
- [ ] 代码符合项目风格规范
- [ ] 已在目标浏览器中测试
- [ ] 语音功能正常工作
- [ ] 更新了相关文档
- [ ] 没有引入新的警告或错误

## 🔗 相关 Issue
<!-- 如果有相关的 Issue，在这里链接 -->
Closes #XXX
```

### 3. PR 注意事项

1. **每个 PR 只做一件事**
   - 保持 PR 的专注性和可审查性
   - 如果有多个修改，拆分为多个 PR

2. **保持提交历史清晰**
   - 使用有意义的提交信息
   - 避免无意义的提交（如 "fix typo"、"wip"）
   - 在提交前整理提交历史

3. **确保代码质量**
   - 移除所有 console.log 调试语句
   - 确保没有语法错误
   - 测试所有语音命令

4. **及时响应反馈**
   - 认真对待审查意见
   - 及时进行修改
   - 保持友好的沟通态度

---

## 问题报告

### Bug 报告模板

```markdown
## 🐛 Bug 描述
<!-- 清晰简洁地描述 bug -->

## 📝 复现步骤
1. 打开应用
2. 点击 '...'
3. 说出 '...'
4. 看到错误

## ✅ 期望行为
<!-- 描述期望发生的事情 -->

## ❌ 实际行为
<!-- 描述实际发生的事情 -->

## 📸 截图/录屏
<!-- 如果可能，请提供截图或录屏 -->

## 🖥️ 环境信息
- 操作系统: [例如 Windows 11, macOS 13]
- 浏览器: [例如 Chrome 120.0.6099.71]
- 麦克风: [例如 内置麦克风, USB 麦克风]

## 📝 附加信息
<!-- 任何其他有助于诊断问题的信息 -->
```

---

## 功能建议

### 功能请求模板

```markdown
## 🚀 功能描述
<!-- 清晰简洁地描述您想要的功能 -->

## 💡 动机/用例
<!-- 描述为什么需要这个功能，解决什么问题 -->

## 📝 详细描述
<!-- 详细描述功能应该如何工作 -->

## 🎨 设计建议
<!-- 如果有设计建议，请提供 -->

## 📊 优先级
- [ ] 必须有 (Must Have)
- [ ] 应该有 (Should Have)
- [ ] 可以有 (Could Have)
- [ ] 暂时不需要 (Won't Have)

## 📝 附加信息
<!-- 任何其他相关信息 -->
```

---

## 行为准则

### 我们的承诺

为了营造一个开放和友好的环境，我们作为贡献者和维护者承诺：参与本项目的每个人都能获得无骚扰的体验，无论其年龄、体型、残疾、民族、性别认同和表达、经验水平、国籍、个人形象、种族、宗教信仰或性取向如何。

### 我们的标准

有助于创造积极环境的行为包括：

- 使用友好和包容的语言
- 尊重不同的观点和经验
- 优雅地接受建设性的批评
- 关注对社区最有利的事情
- 对其他社区成员表示同理心

不可接受的行为包括：

- 使用性暗示的语言或图像，以及不受欢迎的性关注
- 恶意评论、人身攻击或政治攻击
- 公开或私下的骚扰
- 未经明确许可发布他人的私人信息
- 其他在专业环境中被合理认为不当的行为

---

## 许可证

通过贡献您的代码，您同意您的贡献将在 MIT 许可证下获得许可。

---

## 感谢

感谢您对 AI语音绘图助手 项目的贡献！您的帮助使这个项目变得更好。

如有任何问题，请随时通过 [Issues](https://github.com/yourusername/voice-draw-repo/issues) 与我们联系。