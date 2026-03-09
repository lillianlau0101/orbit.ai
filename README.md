<div align="center">

# 🪐 orbit.ai

**A satellite for your mental space.**
*你内心世界的守望星*

[![GitHub Stars](https://img.shields.io/github/stars/lillianlau0101/orbit.ai?style=flat-square)](https://github.com/lillianlau0101/orbit.ai/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/lillianlau0101/orbit.ai?style=flat-square)](https://github.com/lillianlau0101/orbit.ai/network)
[![GitHub Issues](https://img.shields.io/github/issues/lillianlau0101/orbit.ai?style=flat-square)](https://github.com/lillianlau0101/orbit.ai/issues)
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](LICENSE)
[![Version](https://img.shields.io/badge/version-v1.0.0-green.svg?style=flat-square)](https://github.com/lillianlau0101/orbit.ai)

[English](#-overview) | [中文文档](#-项目概述)

</div>

---

## ✨ Overview

Most diary apps ask you to write. orbit.ai asks you to *feel*.

orbit.ai is a gentle, AI-powered emotional diary companion built on WeChat Mini Program. Instead of a blank page, you get a warm conversation with **LingLing** — an empathic AI companion who listens, reflects, and helps you understand the emotional patterns beneath your everyday life.

> You just write what's on your mind.  
> orbit.ai returns: a mood score, key life insights, and a beautiful card summarizing what really happened today.

---

## ✨ 项目概述

大多数日记 App 要你写字，orbit.ai 要你感受。

orbit.ai 是一款基于微信小程序的治愈系 AI 情绪日记伴侣，以腾讯混元大模型为核心驱动。你不需要面对一张空白页，而是与温柔的 AI 伙伴**灵灵**展开一场真实的对话——她倾听你、陪伴你，并帮你看见日常生活背后隐藏的情绪规律。

> 你只需要：用自然语言写下今天的心情与故事  
> orbit.ai 将返回：情绪评分、核心事件洞察，以及一张记录你今天的精美卡片

---

## 🌟 Features / 核心功能

### 💬 Empathic Conversation / 共情对话
Talk to **LingLing**, your AI companion, in natural language. No templates, no prompts — just honest conversation.  
与 AI 伙伴**灵灵**自然对话，没有模板、没有格式要求，只需真实倾诉。

### 📊 Mood Mapping / 情绪量化
Every diary entry is automatically scored on an emotional valence scale (1–10), turning abstract feelings into trackable data.  
每篇日记自动生成情绪评分（1–10），将模糊的感受转化为可追踪的数据。

### 🃏 Insight Card / 洞察卡片
Structural extraction of key events, decisions, and emotional triggers — distilled into a beautifully designed daily card.  
自动提取核心事件、重要决定与情绪触发点，生成精美的每日洞察卡片。

### 📈 Life Patterns / 生命轨迹（Roadmap）
Over time, orbit.ai maps your emotional journey — helping you spot recurring patterns and understand yourself more deeply.  
随着时间积累，orbit.ai 绘制你的情绪旅程，帮助你发现生命中的规律与成长轨迹。

---

## 🏗️ Architecture / 技术架构

| Layer | Technology |
|-------|-----------|
| **Frontend** | WeChat Native Mini Program Framework |
| **AI Brain** | Tencent Hunyuan-pro LLM |
| **Backend** | WeChat CloudBase (Cloud Functions) |
| **Design Language** | Warm Beige Minimalism |

---

## 🚀 Quick Start / 快速开始

### Prerequisites / 前置要求

| Tool | Version | Notes |
|------|---------|-------|
| **WeChat DevTools** | Latest | [Download / 下载](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html) |
| **WeChat CloudBase** | — | Enabled in your Mini Program console |
| **Tencent Hunyuan API** | — | [Apply for access / 申请](https://cloud.tencent.com/product/hunyuan) |

### 1. Clone the repo / 克隆项目

```bash
git clone https://github.com/lillianlau0101/orbit.ai.git
cd orbit.ai
```

### 2. Configure environment / 配置环境

Open `miniprogram/app.js` and replace the CloudBase environment ID:

```js
// app.js
const env = 'YOUR_CLOUDBASE_ENV_ID'; // 替换为你的 CloudBase 环境 ID
```

### 3. Deploy Cloud Functions / 部署云函数

In WeChat DevTools, right-click each folder under `/cloudfunctions` and select **"Upload and Deploy"**:

```
cloudfunctions/
├── hunyuan/        # LLM conversation handler / 对话处理
├── moodAnalysis/   # Mood scoring / 情绪评分
└── insightCard/    # Insight extraction / 洞察提取
```

### 4. Run locally / 本地运行

Open the project root in **WeChat DevTools** → Select `miniprogram/` as the project directory → Click **Compile**.

---

## 📁 Project Structure / 项目结构

```
orbit.ai/
├── miniprogram/        # WeChat Mini Program frontend
│   ├── pages/          # All pages (home, diary, insights...)
│   ├── components/     # Reusable UI components
│   └── app.js          # App entry & config
├── cloudfunctions/     # Backend cloud functions
│   └── hunyuan/        # Hunyuan LLM integration
├── newversion/         # Next version dev branch
├── roadmap/            # Feature roadmap & planning
└── tasks/              # Development task tracker
```

---

## 🗺️ Roadmap / 未来规划

- [x] Real-time empathic conversation with LingLing / 灵灵实时对话
- [x] Mood scoring (1–10) / 情绪量化评分
- [x] Daily insight card generation / 每日洞察卡片
- [ ] Weekly / monthly emotional trend charts / 周月情绪趋势图
- [ ] Voice diary input / 语音日记输入
- [ ] Export diary as PDF / 导出 PDF 日记本
- [ ] Multi-language support / 多语言支持

---

## 🤝 Contributing / 参与贡献

orbit.ai is open source and welcomes contributions. If you have ideas for improving the emotional companion experience, feel free to open an issue or pull request.

orbit.ai 完全开源，欢迎贡献代码与想法。如果你有关于情感陪伴体验的改进建议，欢迎提 issue 或 PR。

1. Fork the repo
2. Create your feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add: your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 📄 License

MIT © [Lillian Lau](https://github.com/lillianlau0101)

---

<div align="center">

**Made with 💛 for quieter minds.**
*为那些需要被温柔接住的情绪而生。*

⭐ If orbit.ai resonates with you, a star means the world — it helps more people find this little companion.  
⭐ 如果 orbit.ai 触动了你，点个 Star 吧——它能帮助更多人找到这个小小的陪伴。

</div>
