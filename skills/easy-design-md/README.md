# Easy Design MD

Let AI help you choose the most suitable design system and download DESIGN.md files with one command.

## Slides Demo

![01 - Title](./01-title.png)
![02 - Before](./02-before.png)
![03 - Dual Track](./03-dual-track.png)
![04 - Smart Recommendation](./04-smart-rec.png)
![05 - Demo Preview](./05-demo.png)
![06 - Supported Brands](./06-brands.png)
![07 - Workflow](./07-workflow.png)
![08 - Directory Structure](./08-structure.png)
![09 - Installation](./09-install.png)
![10 - Get Started](./10-cta.png)

## Features

### Dual-Track Selection

When you want to mimic a brand's design, how do you know which one to choose?

**Option A: Smart Recommendation**
- Tell AI what type of page you want to build (SaaS, e-commerce, docs, etc.)
- AI recommends the most suitable design system based on page type

**Option B: Demo Preview**
- AI shows visual previews of several representative brands
- You choose the style you want after seeing the demos

### Smart Recommendation Categories

| Page Type | Recommended Brands |
|-----------|-------------------|
| SaaS Product Page | Stripe, Linear, Vercel |
| E-commerce Detail | Shopify, Apple |
| Developer Tools | GitHub, Vercel |
| Docs / Knowledge Base | Notion, Mintlify |
| Enterprise / Premium | Stripe, Airbnb |
| AI / Tech | Claude, OpenAI |
| Mobile-first | Apple, Superhuman |
| Creative Portfolio | Figma, Framer |

### 59+ Design Systems Supported

Stripe, Linear, Airbnb, Apple, Notion, Figma, Vercel, GitHub, Spotify, Cal.com, Claude, Cursor, Framer, Mistral, MongoDB, Notion, NVIDIA, OpenAI, Pinterest, PostHog, Raycast, Replicate, Resend, Runway, Sanity, Sentry, Spotify, Stripe, Supabase, Superhuman, Tesla, Together.ai, Uber, Vercel, Zapier and more.

## Installation

### Method 1: One-command Install (Recommended)

```bash
npx agent-skills-cli install https://github.com/maxliux5/easy-design-md
```

### Method 2: Manual Install

```bash
# Install to ~/.antigravity/skills/easy-design-md/
cp -r skills/easy-design-md ~/.antigravity/skills/
```

## Usage

After installation, just tell AI your needs:

```
User: "I want to build a SaaS product landing page"
AI: "For SaaS landing pages, I recommend Stripe or Linear. Stripe is clean and professional, Linear has a sleek dark theme. Which do you prefer?"

User: "Show me some brand demos"
AI: "Sure, here are previews of several representative brands..."
```

AI will guide you through the selection and automatically download the DESIGN.md file to `~/.design-md/{brand}/`.

## Directory Structure

```
~/.design-md/
├── cal/
│   └── DESIGN.md
├── stripe/
│   └── DESIGN.md
├── linear/
│   └── DESIGN.md
└── ...
```

## Workflow

1. **Express Your Need** - Tell AI what type of page you want to build
2. **Choose Method** - Smart recommendation or demo preview
3. **Confirm & Download** - AI downloads DESIGN.md after you select
4. **Start Designing** - Generate UI that matches the design system

## Tech Stack

- Claude Code Skill
- [getdesign.md](https://getdesign.md) - Design system file provider
