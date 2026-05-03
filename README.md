# Media Agent Pro
[![Python version](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/)  
🚀 All-in-one Content Production Agent for Self-Media

> 基于大语言模型 (LLM) 的全栈自媒体内容生产工作站。  
> *A full-stack content production workstation based on LLM, supporting multi-platform publishing.*

---

## 目录 (Table of Contents)

- [核心特性 (Features)](#核心特性-features)
- [技术栈 (Tech Stack)](#技术栈-tech-stack)
- [快速开始 (Quick Start)](#快速开始-quick-start)
- [项目结构 (Project Structure)](#项目结构-project-structure)
- [核心工作流 (Workflow)](#核心工作流-workflow)
- [贡献 (Contributing)](#贡献-contributing)
- [License](#license)

---

## 核心特性 (Features)

- ⚡ **异步生成架构**：多线程后台生成，提升效率
- 🎨 **视觉集成**：集成 DALL-E 3 自动生成高审美封面
- 📱 **多平台适配**：支持公众号、小红书、短视频稿件自动转化
- 🗄️ **持久化管理**：内置 SQLite 数据库，历史可追溯和导出
- 📊 **响应式 UI**：基于 Tailwind CSS

---

## 技术栈 (Tech Stack)

- **Backend:** Python 3.9+ / Flask
- **AI Models:** OpenAI GPT-4o (text), DALL-E 3 (images)
- **Database:** SQLite
- **Frontend:** Tailwind CSS, JavaScript, Marked.js

---

## 快速开始 (Quick Start)

```bash
git clone https://github.com/aboluo12138/Media-Agent-Pro.git
cd Media-Agent-Pro
pip install flask openai python-docx
```

**设置 OpenAI API Key**

- Windows (PowerShell)
  ```powershell
  $env:OPENAI_API_KEY="sk-xxxx"
  ```
- Linux / macOS
  ```bash
  export OPENAI_API_KEY="sk-xxxx"
  ```

**启动服务**

```bash
python app.py
```

访问: [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## 项目结构 (Project Structure)

```plaintext
├── app.py                # Flask 主程序
├── media_agent.db        # SQLite 数据库（自动生成）
├── static/               # 静态资源
└── README.md             # 项目说明
```

---

## 核心工作流 (Workflow)

1. **任务分发 (Task Dispatching):** 用户提交主题，生成唯一 `task_id`
2. **内容规划 (Agent Planning):** 后台调用 GPT-4o 结构化生成内容（JSON）
3. **视觉创作 (Visual Design):** 调用 DALL-E 3 自动生成封面
4. **状态轮询 (Polling):** 前端每 3 秒查询任务状态
5. **内容交付:** 前端渲染 Markdown，可一键复制

---

## 贡献 (Contributing)

欢迎 issue 和 PR！请阅读 [CONTRIBUTING.md](CONTRIBUTING.md) 以了解更多。

---

## License

[MIT License](LICENSE)
