# AI 科研绘图智能体 (AI Research Drawing Agent)

本项目是一个基于 AIMixhub 绘图大模型 API 的科研绘图智能体应用。

## 项目结构

- `index.html`: 应用主入口（包含前端界面与逻辑）
- `tju_white_padding.png`: 顶部 Logo 图片
- `Figure*.png`: 演示用占位图片

## 如何运行

由于浏览器安全策略限制（CORS），建议使用本地 HTTP 服务器运行，而不是直接双击打开 `index.html`。

### 方法 1: 使用 Python (推荐)

在终端中进入当前目录 (`AI_Draw`)，然后运行：

```bash
# Python 3
python3 -m http.server 8000
```

然后在浏览器访问: http://localhost:8000

### 方法 2: 使用 Node.js

如果你安装了 `http-server`:

```bash
npx http-server .
```

## 配置说明

1. 启动应用后，点击右上角的 **“设置”** 按钮。
2. 输入您的 **AIMixhub API Key**。
3. 选择绘图模型（推荐 DALL-E 3）。
4. 保存配置后即可开始使用。

## 功能特性

- **自然语言绘图**: 通过对话描述生成科研图像。
- **多场景演示**: 包含材料合成、微观结构、数据分析、多尺度模拟等演示场景。
- **智能体工作流**: 模拟“输入 -> 思考 -> 执行 -> 输出”的完整智能体过程。
