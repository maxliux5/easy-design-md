---
name: easy-design-md
description: 当用户说"我要模仿 XXX"、"我想用 XXX 的设计风格"、"基于 XXX 设计系统"、"按照 Cal.com 的风格"、"参考 Stripe 设计"，或者"帮我做个页面"、"做个 landing page"、"做个官网"时触发。如果用户不确定想要哪个品牌，先帮助用户选择（智能推荐或展示 Demo），再下载对应的 DESIGN.md 文件。
---

# Design MD Importer

自动下载设计系统文件到指定目录。使用 [getdesign.md](https://getdesign.md) 服务获取 DESIGN.md 文件。

## 核心能力

当用户想要做页面时，**先展示 Demo 效果，让用户选择**，而不是直接下载。

## 支持的品牌

可用的设计系统包括：airbnb, airtable, apple, bmw, cal, claude, clay, clickhouse, cohere, coinbase, composio, cursor, elevenlabs, expo, ferrari, figma, framer, hashicorp, ibm, intercom, kraken, lamborghini, linear.app, lovable, minimax, mintlify, miro, mistral.ai, mongodb, notion, nvidia, ollama, opencode.ai, pinterest, posthog, raycast, renault, replicate, resend, revolut, runwayml, sanity, semrush, sentry, spacex, spotify, stripe, supabase, superhuman, tesla, together.ai, uber, vercel, voltagent, warp, webflow, wise, x.ai, zapier

## 推荐流程

当用户说"帮我做个页面"、"做个 landing page"等需求时：

### 第一步：展示 Demo

给用户一个交互式预览页面，让他**看到效果再选择**：

```
请访问交互式 Demo 预览：
https://easy-design-md.vercel.app/demo.html

在这个页面上，你可以：
1. 选择想做的页面类型（SaaS / 开发者文档 / 电商 / 品牌官网）
2. 看到推荐品牌的完整配色方案
3. 实时预览这些颜色在页面上的效果
4. 选定后告诉我你选择哪个品牌
```

### 第二步：用户选择品牌后，下载 DESIGN.md

```bash
# 下载到默认目录 ~/.design-md/{brand}/
npx getdesign@latest add {brand} --out ~/.design-md/{brand}
```

### 第三步：告知用户如何使用

"已为你下载 [品牌] 的 DESIGN.md 文件到 `~/.design-md/[品牌]/`"

"现在告诉我你想要什么样的页面，我会参考 DESIGN.md 来生成符合该设计风格的 UI。"

## 智能推荐分类

根据页面类型推荐：

| 页面类型 | 推荐品牌 | 推荐理由 |
|---------|---------|---------|
| SaaS 产品页 | Stripe, Linear, Vercel | 干净、专业、强调信任感 |
| 电商/电商详情 | Shopify, Apple | 清晰的信息层次、购买导向 |
| 开发者工具 | GitHub, Vercel, Railway | 技术文档、代码展示 |
| 文档/知识库 | Notion, Mintlify, Readme | 内容为主、清晰易读 |
| 创意/作品展示 | Dribbble, Behance, Framer | 视觉冲击、创意表达 |
| 移动端优先 | Apple, Superhuman | iOS 风格、简洁高效 |
| 企业/高端 | Stripe, Linear, Airbnb | 精致、高端感 |
| AI/科技感 | Claude, OpenAI, Together.ai | 前沿、科技感 |

## 品牌名称映射

用户可能使用不同的名称指代同一个品牌，需要标准化：

| 用户输入 | 实际品牌名 |
|---------|----------|
| Cal.com, cal.com, cal | cal |
| Linear, linear.app | linear.app |
| Vercel, vercel | vercel |
| Claude, claude | claude |
| ... | ... |

## 示例对话

**用户**: "我想做一个 SaaS 产品的官网"

**执行**:
1. 展示 Demo："在选择之前，你可以先看看效果：https://easy-design-md.vercel.app/demo.html"
2. 用户浏览后选择 Stripe
3. 下载 Stripe 的 DESIGN.md
4. 基于 Stripe 设计系统为用户生成页面

**用户**: "展示一些品牌让我看看"

**执行**:
1. 发送 Demo 链接给用户
2. 用户看完后选择 Airbnb
3. 下载 Airbnb 的 DESIGN.md

## 错误处理

- 如果品牌不存在，告知用户并列出最接近的可用品牌
- 如果 npx 下载失败，尝试备用方法或告知用户手动下载
- 如果指定目录不存在，自动创建

## 重要提示

- **永远先展示 Demo，再下载** - 让用户"看见再选择"
- 下载后告知用户："已为你下载 {品牌} 的 DESIGN.md 文件到 ~/.design-md/{品牌}/"
- 提醒用户："现在可以告诉我你想要什么样的页面，我会参考 DESIGN.md 来生成符合该设计风格的 UI"