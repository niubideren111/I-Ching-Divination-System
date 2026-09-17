# 周易源码｜八字排盘、五行、紫微斗数、易经、奇门遁甲、七政四余|I Ching Divination System 

> 中文简体 · 中文繁體 · English 多语言产品与源码资料

[简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [English](README.en.md) · [产品页面](https://niubideren111.github.io/I-Ching-Divination-System/zh-cn/)

以八字排盘网页为入口的周易开发资料，包含 JavaScript 公共函数、时区处理和截图导出文件。项目还展示大六壬、流年、七政四余等页面截图，便于了解排盘类产品的界面组织。

**周易源码 · 八字排盘源码 · 易经源码 · JavaScript排盘**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow.svg)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Online Demo](https://img.shields.io/badge/demo-online-brightgreen.svg)](https://your-github-username.github.io/I-Ching-Divination-System)

> 一个基于传统周易文化的开源占卜系统 | An open-source I Ching divination system based on traditional Zhouyi culture

**[在线演示 | Online Demo](https://your-github-username.github.io/I-Ching-Divination-System)** | **[快速开始](#-快速开始)** | **[算法说明](#-算法说明)**

---

## 📑 目录

- [简介](#-简介)
- [功能特性](#-功能特性)
- [在线演示](#-在线演示)
- [快速开始](#-快速开始)
- [项目结构](#-项目结构)
- [算法说明](#-算法说明)
- [自定义扩展](#-自定义扩展)
- [常见问题](#-常见问题)
- [贡献指南](#-贡献指南)
- [免责声明](#-免责声明)
- [许可证](#-许可证)

---

## 📖 简介

本项目是一个基于**周易（易经）** 传统文化的开源占卜系统，实现了六爻起卦、变卦分析、阴阳五行等核心算法。项目旨在：

- 📚 为传统文化爱好者提供学习工具
- 🔬 探索古典哲学与现代编程的结合
- 🧪 为学术研究提供可验证的算法实现

> 🎯 **项目定位**：开源研究项目，仅供学习交流和文化传播使用。

---

## ✨ 功能特性

| 模块 | 功能说明 |
|------|----------|
| 🔮 **六爻起卦** | 支持传统蓍草法、金钱卦等多种起卦方式 |
| 🔄 **变卦分析** | 自动计算动爻、变卦及本卦、互卦、变卦关系 |
| ☯ **阴阳五行** | 集成天干地支、五行生克、刑冲合害分析 |
| 🌐 **网页界面** | 纯前端实现，无需后端服务器即可运行 |
| 📱 **响应式设计** | 支持PC端和移动端访问 |
| 🧠 **AI扩展接口** | 预留与LLM（ChatGPT等）集成的API结构 |

---

## 🌐 在线演示

访问在线index.html演示站点或联系Tg：@fox_lovemyself，无需安装即可体验：



### 演示截图

![周易八字排盘与干支信息页面](docs/assets/seo/i-ching-divination-system-01.jpg)
![大六壬排盘表格页面](docs/assets/seo/i-ching-divination-system-02.jpg)
![流年信息与排盘数据列表](docs/assets/seo/i-ching-divination-system-03.jpg)
![八字排盘信息汇总页面](docs/assets/seo/i-ching-divination-system-04.jpg)


## 公开源码与资料

| 文件 | 说明 |
|---|---|
| [index.html](index.html) | 原有八字排盘网页 |
| [common.js](common.js) | 公共 JavaScript 文件 |
| [timezone.js](timezone.js) | 时区处理资料 |
| [canvas2image.js](canvas2image.js) | 画布图片导出文件 |
| [五行数值328.xlsx](%E4%BA%94%E8%A1%8C%E6%95%B0%E5%80%BC328.xlsx) | 五行数值表 |
| [docs/algorithm_api.md](docs/algorithm_api.md) | 已有算法接口文档 |


## 相关项目

- [Chess-and-Card-Game-Product-Design-Copy](https://github.com/niubideren111/Chess-and-Card-Game-Product-Design-Copy)

## 项目咨询

- Telegram：[fox_lovemyself](https://t.me/fox_lovemyself)
- GitHub：[周易八字排盘源码](https://github.com/niubideren111/I-Ching-Divination-System)





---
### ❓ 常见问题
Q: 占卜结果是随机的吗？
A: 是的。按传统周易理论，起卦过程模拟随机性（如掷钱币、分蓍草），本项目使用加密安全的随机数生成器。

Q: 可以用于商业产品吗？
A: 本项目采用 MIT 许可证，允许商业使用。但请您遵守各地法律法规，不得用于欺诈或虚假宣传等违法行为。

Q: 如何贡献卦辞解释内容？
A: 欢迎完善 data/interpretations.json 文件，提交 Pull Request 即可。

### 🤝 贡献指南
欢迎贡献代码、完善文档或报告问题！

Fork 本仓库

创建特性分支 (git checkout -b feature/amazing-feature)

提交更改 (git commit -m 'feat: add some amazing feature')

推送到分支 (git push origin feature/amazing-feature)

创建 Pull Request

详细规范请参阅 CONTRIBUTING.md

### ⚠️ 免责声明
本项目基于传统文化研究目的开发：

🔮 占卜结果仅供娱乐和学术参考

📚 不应作为人生决策、投资、医疗或法律行为的依据

🌐 用户自行承担使用本项目的责任

🚫 禁止用于任何形式的诈骗、迷信宣传或非法活动

### 📜 许可证
本项目采用 MIT License 开源许可证。

### 🌟 Star History
如果这个项目对您有帮助，请点击右上角 ⭐ 支持一下！










