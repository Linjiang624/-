# 🎯 AI 求职助手（Job-Hunt AI Assistant）

> 一个面向零基础转行者的 AI 求职工具：**智能问答 + JD 解析 + 模拟面试**。
> 基于 DeepSeek 大模型，纯前端实现，零后端依赖。

## ✨ 功能

| 功能 | 说明 |
|------|------|
| 💬 **AI 求职问答** | 多轮对话，内置个人简历资料，回答贴合个人情况 |
| 📄 **JD 分析器** | 粘贴招聘 JD，AI 提取岗位职责 / 硬性要求 / 加分项 / 面试考点 |
| 🎤 **模拟面试** | 以 JD 为背景扮演面试官：逐题提问 → 追问细节 → 总结打分 |
| 🎨 **个人主页** | 三段式布局、技能卡片、每日名言、聊天气泡界面 |

## 🛠️ 技术栈

- **HTML / CSS**：语义化结构、flex 布局、盒子模型、响应式卡片
- **JavaScript**：DOM 操作、事件监听、async/await、fetch API
- **DeepSeek API**：`deepseek-chat` 模型、system/user/assistant 消息结构、上下文管理（多轮对话）
- **Git / GitHub**：版本管理、密钥隔离（.gitignore）

## 🚀 本地运行

```bash
# 1. 克隆仓库
git clone https://github.com/Linjiang624/-.git

# 2. 配置 API 密钥（注意：此文件已被 .gitignore 排除，不会入库）
#    在 portfolio-site/config.js 中填入你的 DeepSeek Key：
#    const DEEPSEEK_API_KEY = "sk-你的密钥";

# 3. 用浏览器打开 portfolio-site/index.html 即可
```

> 💡 推荐用 VS Code 的 Live Server 扩展打开（右键 → Open with Live Server）。

## 🔑 密钥安全说明

- API 密钥存放在 `config.js`，已被 `.gitignore` 排除，**不会上传到 GitHub**
- 泄露密钥请立即到 platform.deepseek.com 删除重建
- ⚠️ 注意：纯前端调用 API 仅适合学习/演示。生产环境应通过**后端代理**转发请求，避免密钥暴露在浏览器端

## 🧠 核心架构（AI 应用通用套路）

```
用户输入 → 拼上 system 提示词（人设 + 资料/JD）→ 发送给大模型 → 渲染回答
```

- **上下文管理**：`chatHistory` 数组保存全部对话，每次全量发送，实现多轮记忆
- **提示词切换**：换 system 提示词 = 换角色（助手 / JD 分析师 / 面试官）

## 📌 后续规划

- [ ] 简历文件上传解析（PDF/Word）
- [ ] 面试记录保存到本地（localStorage）
- [ ] 后端代理转发（生产级密钥安全）
- [ ] 移动端适配优化

---

*本项目是 90 天求职冲刺计划的一部分，由零基础学习者独立开发。*
