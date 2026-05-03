# ai_gongzhonghao_xiezuo_agent
一个本地部署自媒体内容生产 Agent
🚀 Media Agent Pro: 全媒体矩阵内容生产助手 (MVP)

Media Agent Pro 是一个基于大语言模型 (LLM) 的全栈自媒体内容生产工作站。它能够将一个模糊的“选题”转化为包含爆款标题矩阵、深度长文、多平台改编文案以及 AI 生成封面图的完整作品集。

✨ 核心特性

    ⚡ 异步生成架构：采用多线程处理。用户提交任务后无需守在网页前，AI 会在后台完成调研、撰写和绘图。

    🎨 视觉集成：集成 DALL-E 3，根据文章核心意境自动创作高审美自媒体封面图。

    📱 多平台适配：一套核心内容，自动分发为公众号长文（Markdown）、小红书爆款文案（含 Emoji）及短视频拍摄脚本。

    🗄️ 持久化管理：内置 SQLite 数据库，完整记录创作历史，随时回溯和导出。

    📊 响应式 UI：基于 Tailwind CSS 构建，支持历史记录侧边栏、实时状态轮询和一键复制功能。

🛠️ 技术栈

    后端: Python / Flask

    AI 大模型: OpenAI GPT-4o (文案) + DALL-E 3 (视觉)

    数据库: SQLite

    前端: Tailwind CSS / JavaScript / Marked.js (Markdown 渲染)

🚀 快速开始
1. 克隆项目
Bash

git clone https://github.com/aboluo12138/Media-Agent-Pro.git
cd media-agent-pro

2. 安装依赖

建议使用 Python 3.9+ 环境。
Bash

pip install flask openai python-docx

3. 配置环境变量

在你的终端或 .env 文件中设置 OpenAI API Key：
Bash

# Windows (PowerShell)
$env:OPENAI_API_KEY="sk-xxxx"

# Linux / Mac
export OPENAI_API_KEY="sk-xxxx"

4. 启动应用
Bash

python app.py

访问地址：[http://127.0.0.1:8000](http://127.0.0.1:8000)
📂 项目结构
Plaintext

├── app.py                # Flask 主程序（含 API 与 路由）
├── media_agent.db        # SQLite 数据库（启动后自动生成）
├── static/               # 静态资源文件 (可选)
└── README.md             # 项目说明文档

⚙️ 核心工作流说明

    任务分发 (Task Dispatching): 系统接收用户主题，生成一个唯一的 task_id 并立即返回给前端。

    内容规划 (Agent Planning): 后台线程调用 GPT-4o 进行结构化创作，产出 JSON 格式的多平台文案。

    视觉创作 (Visual Design): 根据文案中的 img_prompt 自动调用 DALL-E 3 接口生成配套封面。

    状态轮询 (Polling): 前端每隔 3 秒询问一次后端状态，直到生成任务标记为 completed。

    内容交付: 渲染 Markdown 效果，用户可通过一键复制按钮直接获取内容进行发布。
