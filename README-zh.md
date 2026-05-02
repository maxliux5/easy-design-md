# Easy Design MD

Design MD Importer 是一个让 AI 帮助用户快速获取设计系统的 Claude Code skill。用户告诉 AI 想模仿的品牌，AI 会自动下载对应的 `DESIGN.md` 文件。

## 核心功能

1. **智能推荐** - 根据页面类型（如 SaaS 官网、电商、博客等）推荐合适的设计系统
2. **双轨选择流程** - 用户可以明确选择品牌，或让 AI 智能推荐
3. **59+ 品牌支持** - 包括 Stripe、Linear、Airbnb、Apple、Notion、Figma、Vercel、GitHub、Spotify 等

## 工作流（四步）

1. 描述需求（"我要做一个 SaaS 官网"）
2. AI 智能推荐或用户选择品牌
3. 自动下载品牌的 DESIGN.md 文件
4. 基于设计系统进行开发

## 安装方式

```bash
npx agent-skills-cli install https://github.com/用户名/easy-design-md
```

## 预览

打开 `examples/presentation.html` 查看完整幻灯片介绍。