---
name: easy-design-md
description: 当用户说"我要模仿 XXX"、"我想用 XXX 的设计风格"、"基于 XXX 设计系统"、"按照 Cal.com 的风格"、"参考 Stripe 设计"等时触发。如果用户不确定想要哪个品牌，先帮助用户选择（智能推荐或展示 Demo），再下载对应的 DESIGN.md 文件。
---

# Design MD Importer

自动下载设计系统文件到指定目录。使用 [getdesign.md](https://getdesign.md) 服务获取 DESIGN.md 文件。

## 支持的品牌

可用的设计系统包括：airbnb, airtable, apple, bmw, cal, claude, clay, clickhouse, cohere, coinbase, composio, cursor, elevenlabs, expo, ferrari, figma, framer, hashicorp, ibm, intercom, kraken, lamborghini, linear.app, lovable, minimax, mintlify, miro, mistral.ai, mongodb, notion, nvidia, ollama, opencode.ai, pinterest, posthog, raycast, renault, replicate, resend, revolut, runwayml, sanity, semrush, sentry, spacex, spotify, stripe, supabase, superhuman, tesla, together.ai, uber, vercel, voltagent, warp, webflow, wise, x.ai, zapier

## 双轨选择流程

当用户表达想要模仿某个品牌的设计时，先问用户想要哪种选择方式：

**选项 A: 智能推荐**
- 询问用户想做什么类型的页面
- 根据页面类型推荐最合适的品牌
- 用户确认后下载

**选项 B: 展示 Demo**
- 展示几个代表性品牌的视觉预览
- 用户看完后选择想要哪个
- 下载选中的品牌

## 默认下载目录

**默认保存到**: `~/.design-md/{brand}/DESIGN.md`

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

## 智能推荐流程

1. **询问需求**: "你想做什么类型的页面？（电商、SaaS 产品页、文档、博客、管理后台等）"
2. **分析关键词**: 从用户回答中提取页面类型关键词
3. **推荐**: "基于你的需求，我推荐 [品牌 A] / [品牌 B]，原因是..."
4. **确认下载**: 用户确认后执行下载命令

## 展示 Demo 流程

1. **选择代表性品牌**: 从列表中挑选 4-6 个有代表性的品牌展示
2. **生成预览**: 每个品牌展示：
   - 主题色彩（色板）
   - 字体风格
   - 排版特点
   - 一个简单的示例 UI 片段描述
3. **用户选择**: "看完后告诉我你想用哪个品牌的风格"
4. **下载**: 执行下载命令

## 下载命令

```bash
# 下载到默认目录 ~/.design-md/{brand}/
npx getdesign@latest add {brand} --out ~/.design-md/{brand}

# 下载到自定义目录
npx getdesign@latest add {brand} --out /path/to/designs/{brand}
```

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
1. 识别为 SaaS 产品页类型
2. 智能推荐："SaaS 官网的话，我推荐 Stripe 或 Linear，它们的设计干净专业，很适合 SaaS 产品"
3. 用户选择 Linear
4. 下载 Linear 的 DESIGN.md

**用户**: "展示一些品牌让我看看"

**执行**:
1. 选择代表性品牌：Stripe, Linear, Airbnb, Apple, Notion, Figma
2. 展示每个品牌的视觉特点
3. 用户选择 Airbnb
4. 下载 Airbnb 的 DESIGN.md

## 错误处理

- 如果品牌不存在，告知用户并列出最接近的可用品牌
- 如果 npx 下载失败，尝试备用方法或告知用户手动下载
- 如果指定目录不存在，自动创建

## 重要提示

- 下载后告知用户："已为你下载 {品牌} 的 DESIGN.md 文件到 ~/.design-md/{品牌}/"
- 提醒用户："现在可以告诉我你想要什么样的页面，我会参考 DESIGN.md 来生成符合该设计风格的 UI"
