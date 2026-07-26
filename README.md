<div align="center">

# 网腾无限AI - 楹联创作与对仗押韵专家

**一个基于 Vue 3 + Vite + Vanilla CSS 构建的极简 AI 微应用，具备深色玻璃拟态自适应交互与微信端 H5 体验**

Vue 3 · TypeScript · Vite · Vanilla CSS · 开源协议 MIT

[![GitHub stars](https://img.shields.io/github/stars/WT-Agent/ai-duilian?style=social)](https://github.com/WT-Agent/ai-duilian)
[![GitHub license](https://img.shields.io/github/license/WT-Agent/ai-duilian)](https://github.com/WT-Agent/ai-duilian/blob/main/LICENSE)

[在线演示](#在线演示) · [快速启动](#快速启动) · [参与贡献](#参与贡献) · [支持一下](#支持一下)

</div>

## 关于我们

团队成员均来自 C9 等顶尖学府，在字节、腾讯、阿里的工程师组成，全职创业研发开源 AI 应用产品，让所有人感受 AI 的魅力。

本项目是网腾无限 AI 微应用的标准开发模版，内置了毛玻璃深色主题样式系统、移动端与 PC 端自适应响应式框架、API 中转代理配置与流量裂变逻辑。

**我们不搞概念，不卖课，只写能跑起来的代码。**

欢迎 Star、Fork、提 Issue，一起让这个项目变得更好用。

核心特性：
- **极简自适应交互**：提供毛玻璃质感的深色玻璃拟态自适应 Web 界面，高度适配移动端 H5 微信浏览器与 PC 体验。
- **一键零成本部署**：纯静态前端结构，支持零成本部署于 Vercel、GitHub Pages 或 CDN/OSS 静态托管服务。
- **安全开发代理**：本地开发支持使用个人 API 密钥发起代理请求，密钥由 Vite 服务器中转，无需担心前端泄露。
- **裂变解锁与留存**：内置微信朋友圈扫码分享拦截与额度重置机制，提升流量转化与留存。

## 4 大核心功能模块

1. **上联与下联精妙创作**：根据用户提供的楹联主题、联语字数（五言/七言/九言/长联）与诗韵风格（典雅/气势/清丽/喜庆），精工撰写上下联并标注清晰断句。
2. **横批拟定与主题蕴意**：拟定 4 字或 6 字凝练横批，深度阐释楹联背后的传统文化寓意、时代情怀与吉祥祝福。
3. **平仄对仗与韵律规则校验**：基于平水韵与律诗规则，逐字进行平仄标注与词性对仗分析，严格校验上仄下平收尾法则。
4. **典故出处与适用场景赏析**：剖析联语引用的经典诗词成语典故，提供最佳悬挂、张贴或赠送场景实用指导。

## 5 大 AI 评估指标

1. **平仄对仗 (`tonalAntithesis`)**：评估上下联字数相符、词性相对、平仄相间及上仄下平收尾规则的严密程度。
2. **语义和谐 (`semanticHarmony`)**：评估上下联动静呼应、立意融通及整体主题意境的和谐美感。
3. **修辞典雅 (`rhetoricalElegance`)**：评估文彩修辞、对仗用词选字及格调辞藻的典雅华贵程度。
4. **韵律节奏 (`rhymeRhythm`)**：评估诵读节奏感、语音韵律流畅度与断句押韵效果。
5. **文化底蕴 (`culturalHeritage`)**：评估典故成语引用的精准度与传统楹联文化内涵传承深度。

## 快速启动

### 1. 克隆项目
```bash
git clone https://github.com/WT-Agent/ai-duilian.git
cd ai-duilian
```

### 2. 安装依赖
项目强制使用 pnpm 作为包管理器：
```bash
pnpm install
```

### 3. 配置本地开发环境变量
复制并修改环境变量配置文件：
```bash
cp .env.example .env
```
根据微应用的功能类型，在 `.env` 中配置您的开发者密钥：
- `DEEPSEEK_API_KEY`: 您的 DeepSeek 开发者 API 密钥（用于文本生成任务）
- `DASHSCOPE_API_KEY`: 您的通义千问/通义万相开发者 API 密钥（用于多模态与生图任务）

### 4. 启动本地开发服务
```bash
pnpm dev
```
启动成功后在浏览器访问控制台输出的地址即可。

### 5. 生产构建打包
```bash
pnpm build
```
打包后生成的 `dist` 目录即为纯静态网页资源，可直接上传部署。

## 脚手架集成说明

本模板由私有总控仓库 `ai.wuxian.xyz` 中的 `@wuxian/cli` 脚手架统一管理，支持以下批量运维操作：

### 初始化或更新单个子项目

```bash
node bin/cli.js ai-duilian
```

脚手架将自动：
1. 读取子仓库的 `README.md` 首行作为 Prompt 主题。
2. 注入 Vue 3 静态页面结构及标准配置文件。
3. 保留原有的 `.git` 配置与 `README.md`，不覆盖个性化内容。

### 批量同步所有子项目

```bash
node bin/cli.js all
```

将模板的最新变更（如 SSO 逻辑、额度控制）一键同步至全部 31 个子项目。

### Agent 配置维护接口

```bash
# 读取子项目配置
node bin/cli.js get ai-duilian

# 写入/更新配置（支持热更新 prompt、model、title、temperature 等）
node bin/cli.js set ai-duilian prompt "你是一位精通中华楹联传统文化、平水韵与诗词韵律学的高级楹联大师兼文学顾问..."
node bin/cli.js set ai-duilian model deepseek-chat
```

## 联系方式

- GitHub Issues: [提交反馈](https://github.com/WT-Agent/ai-duilian/issues)
- 邮箱: us@wuxian.xyz

## 打赏支持

如果本项目对您有帮助，欢迎请作者喝杯咖啡。您的支持是持续维护与更新的动力。

<div align="center">

**微信支付** | **支付宝**
:---:|:---:
<img src="https://ai.wuxian.xyz/assets/tenpay.png" width="200" alt="微信支付"> | <img src="https://ai.wuxian.xyz/assets/alipay.png" width="200" alt="支付宝">

</div>

## 版权与许可

本项目基于 MIT License 开源协议。

Copyright (c) 2026. All rights reserved.
