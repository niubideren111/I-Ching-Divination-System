# 🔮 I Ching Divination System | 周易易经占卜系统

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

访问在线演示站点，无需安装即可体验：



### 演示截图

<img width="2484" height="1353" alt="屏幕截图 2024-10-29 114634" src="https://github.com/user-attachments/assets/6b5a7fad-40c4-4407-9590-723ca32e5d75" />
<img width="2471" height="1381" alt="屏幕截图 2024-10-29 114624" src="https://github.com/user-attachments/assets/28e6c741-8b36-4422-9d45-1987a6ed7e7a" />
<img width="2540" height="1381" alt="屏幕截图 2024-10-29 114423" src="https://github.com/user-attachments/assets/274d3b6e-6e90-4862-8597-d2b2f7c457af" />
<img width="2539" height="1369" alt="屏幕截图 2025-04-18 194842" src="https://github.com/user-attachments/assets/b2650f4a-3650-441f-9f21-dd71c319deb3" />
<img width="2471" height="1285" alt="屏幕截图 2025-03-15 113242" src="https://github.com/user-attachments/assets/fea28aee-ac91-4280-bccc-5892c4236464" />
<img width="2522" height="1364" alt="屏幕截图 2024-10-29 115350" src="https://github.com/user-attachments/assets/ec45b7c4-9da8-4935-aa50-7b7a5414856c" />
<img width="2446" height="1292" alt="屏幕截图 2024-10-29 115251" src="https://github.com/user-attachments/assets/cc84bf8b-ce17-4124-957c-9ba05d3be8f4" />
<img width="2306" height="1369" alt="屏幕截图 2024-10-29 114720" src="https://github.com/user-attachments/assets/1c159bac-c008-4506-ae83-bc7967472654" />
<img width="2427" height="1398" alt="屏幕截图 2024-10-29 114655" src="https://github.com/user-attachments/assets/8694da88-63b7-42f3-a4e6-d379b2ff1572" />


## 📞 Contact | 联系方式 | 聯絡方式

* Telegram: @fox_lovemyself
* Email:zyue02561@gmail.com

💬 Fast response within 24h

---

---

## 🚀 快速开始

### 本地运行（5秒启动）

```bash
# 1. 克隆仓库
git clone https://github.com/niubideren111/I-Ching-Divination-System.git
cd I-Ching-Divination-System

# 2. 启动本地服务器（任选一种方式）

# 方式一：使用 Python（推荐）
python -m http.server 8080

# 方式二：使用 Node.js（需安装 npx）
npx serve .

# 方式三：使用 VS Code Live Server 插件

# 3. 打开浏览器访问
# http://localhost:8080
部署到 GitHub Pages（免费托管）
bash
# 1. 在仓库 Settings > Pages 中
#    - Source 选择 "main" 分支
#    - 文件夹选择 "/ (root)"
#    - 点击 Save

# 2. 等待1-2分钟，访问
#    https://your-username.github.io/I-Ching-Divination-System/
---

🧠 算法说明
1. 六爻起卦算法
javascript
// 示例：生成随机阴阳爻（49蓍草法简化版）
function generateLine() {
    // 随机生成老阴(6)、少阳(7)、少阴(8)、老阳(9)
    // 6和8为阴爻（--），7和9为阳爻（—）
    const result = [6, 7, 8, 9][Math.floor(Math.random() * 4)];
    return {
        type: result === 6 || result === 8 ? 'yin' : 'yang',
        changing: result === 6 || result === 9,  // 老阴老阳为动爻
        value: result
    };
}
2. 卦象转换算法
卦名	上卦	下卦	二进制编码
乾为天	乾☰	乾☰	111111
坤为地	坤☷	坤☷	000000
屯	坎☵	震☳	010001
3. 五行生克关系
text
相生：木 → 火 → 土 → 金 → 水 → 木
相克：木 → 土 → 水 → 火 → 金 → 木
4. 天干地支算法
十天干：甲、乙、丙、丁、戊、己、庚、辛、壬、癸

十二地支：子、丑、寅、卯、辰、巳、午、未、申、酉、戌、亥

六合：子丑合、寅亥合、卯戌合、辰酉合、巳申合、午未合

详细算法请参阅 docs/algorithms.md（待补充）

🔧 自定义扩展
添加新的起卦方式
在 common.js 中添加新函数：

javascript
// 自定义起卦方法
function customDivinationMethod() {
    // 实现您的起卦逻辑
    return hexagramResult;
}
集成 AI 助手（ChatGPT等）
javascript
// 使用 AI 进行占卜解读
async function aiInterpretation(hexagramData) {
    const response = await fetch('YOUR_API_ENDPOINT', {
        method: 'POST',
        body: JSON.stringify(hexagramData)
    });
    return await response.json();
}
---
---
### ❓ 常见问题
Q: 如何将 Excel/Word 数据转换为 JSON？
bash
# 使用 Python 转换
pip install pandas openpyxl
python scripts/convert_data.py
Q: 占卜结果是随机的吗？
A: 是的。按传统周易理论，起卦过程模拟随机性（如掷钱币、分蓍草），本项目使用加密安全的随机数生成器。

Q: 可以用于商业产品吗？
A: 本项目采用 MIT 许可证，允许商业使用。但请您遵守各地法律法规，不得用于欺诈或虚假宣传等违法行为。

Q: 如何贡献卦辞解释内容？
A: 欢迎完善 data/interpretations.json 文件，提交 Pull Request 即可。

🤝 贡献指南
欢迎贡献代码、完善文档或报告问题！

Fork 本仓库

创建特性分支 (git checkout -b feature/amazing-feature)

提交更改 (git commit -m 'feat: add some amazing feature')

推送到分支 (git push origin feature/amazing-feature)

创建 Pull Request

详细规范请参阅 CONTRIBUTING.md

⚠️ 免责声明
本项目基于传统文化研究目的开发：

🔮 占卜结果仅供娱乐和学术参考

📚 不应作为人生决策、投资、医疗或法律行为的依据

🌐 用户自行承担使用本项目的责任

🚫 禁止用于任何形式的诈骗、迷信宣传或非法活动

📜 许可证
本项目采用 MIT License 开源许可证。

🌟 Star History
如果这个项目对您有帮助，请点击右上角 ⭐ 支持一下！










