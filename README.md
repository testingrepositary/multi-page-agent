# Multi Page Agent

> **This is our fork of [alibaba/page-agent](https://github.com/alibaba/page-agent).** We're extending it to support multi-page workflows.

---

## 🗂️ How This Repo Is Set Up

### Branches (what you see on GitHub)

| Branch | What it is |
|--------|-----------|
| **`main`** | Our branch. All our new features and changes go here. |
| **`alibaba-original`** | A clean, untouched copy of alibaba's code. Just for reference. |

### Remotes (hidden connections — you won't see these on GitHub)

Remotes are like saved bookmarks on your computer that point to GitHub repos. They let git know where to push and pull code.

| Remote | Points to | What it's for |
|--------|-----------|---------------|
| **`origin`** | Our fork (`testingrepositary/multi-page-agent`) | Where we push our work |
| **`upstream`** | Alibaba's repo (`alibaba/page-agent`) | Where we pull their updates from |

### Setting up on a new machine

When you clone this repo on a different computer, `origin` is set up automatically but `upstream` is not (remotes are local to each machine). Run this once after cloning:

```bash
git remote add upstream https://github.com/alibaba/page-agent.git
```

### How to get alibaba's latest updates

Their updates don't come in automatically. When you want them, ask an agent to run:

```bash
git fetch upstream        # Download their latest code (doesn't change your files)
git merge upstream/main   # Merge their changes into your branch
```

If both sides edited the same lines, there'll be a **conflict** — the agent will help you sort it out.

---

## Original README below

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://img.alicdn.com/imgextra/i4/O1CN01qKig1P1FnhpFKNdi6_!!6000000000532-2-tps-1280-256.png">
  <img alt="Page Agent Banner" src="https://img.alicdn.com/imgextra/i1/O1CN01NCMKXj1Gn4tkFTsxf_!!6000000000666-2-tps-1280-256.png">
</picture>

[![License: MIT](https://img.shields.io/badge/License-MIT-auto.svg)](https://opensource.org/licenses/MIT) [![TypeScript](https://img.shields.io/badge/%3C%2F%3E-TypeScript-%230074c1.svg)](http://www.typescriptlang.org/) [![Bundle Size](https://img.shields.io/bundlephobia/minzip/page-agent)](https://bundlephobia.com/package/page-agent) [![Downloads](https://img.shields.io/npm/dt/page-agent.svg)](https://www.npmjs.com/package/page-agent) [![GitHub stars](https://img.shields.io/github/stars/alibaba/page-agent.svg)](https://github.com/alibaba/page-agent)

The GUI Agent Living in Your Webpage. Control web interfaces with natural language.

🌐 **English** | [中文](./docs/README-zh.md)

<a href="https://alibaba.github.io/page-agent/" target="_blank"><b>🚀 Demo</b></a> | <a href="https://alibaba.github.io/page-agent/docs/introduction/overview" target="_blank"><b>📖 Docs</b></a> | <a href="https://news.ycombinator.com/item?id=47264138" target="_blank"><b>📢 HN Discussion</b></a> | <a href="https://x.com/simonluvramen" target="_blank"><b>𝕏 Follow on X</b></a>

<video id="demo-video" src="https://github.com/user-attachments/assets/a1f2eae2-13fb-4aae-98cf-a3fc1620a6c2" controls crossorigin muted></video>

---

## ✨ Features

- **🎯 Easy integration**
    - No need for `browser extension` / `python` / `headless browser`.
    - Just in-page javascript. Everything happens in your web page.
- **📖 Text-based DOM manipulation**
    - No screenshots. No multi-modal LLMs or special permissions needed.
- **🧠 Bring your own LLMs**
- **🐙 Optional [chrome extension](https://alibaba.github.io/page-agent/docs/features/chrome-extension) for multi-page tasks.**
    - And an [MCP Server (Beta)](https://alibaba.github.io/page-agent/docs/features/mcp-server) to control it from outside

## 💡 Use Cases

- **SaaS AI Copilot** — Ship an AI copilot in your product in lines of code. No backend rewrite.
- **Smart Form Filling** — Turn 20-click workflows into one sentence. Perfect for ERP, CRM, and admin systems.
- **Accessibility** — Make any web app accessible through natural language. Voice commands, screen readers, zero barrier.
- **Multi-page Agent** — Extend your own web agent's reach across browser tabs [chrome extension](https://alibaba.github.io/page-agent/docs/features/chrome-extension).
- **MCP** - Allow your agent clients to control your browser.

## 🚀 Quick Start

### One-line integration

Fastest way to try PageAgent with our free Demo LLM:

```html
<script src="{URL}" crossorigin="true"></script>
```

> **⚠️ For technical evaluation only.** This demo CDN uses our free [testing LLM API](https://alibaba.github.io/page-agent/docs/features/models#free-testing-api). By using it, you agree to its [terms](https://github.com/alibaba/page-agent/blob/main/docs/terms-and-privacy.md).

| Mirrors | URL                                                                                |
| ------- | ---------------------------------------------------------------------------------- |
| Global  | https://cdn.jsdelivr.net/npm/page-agent@1.8.1/dist/iife/page-agent.demo.js         |
| China   | https://registry.npmmirror.com/page-agent/1.8.1/files/dist/iife/page-agent.demo.js |

### NPM Installation

```bash
npm install page-agent
```

```javascript
import { PageAgent } from 'page-agent'

const agent = new PageAgent({
    model: 'qwen3.5-plus',
    baseURL: 'https://dashscope.aliyuncs.com/compatible-mode/v1',
    apiKey: 'YOUR_API_KEY',
    language: 'en-US',
})

await agent.execute('Click the login button')
```

For more programmatic usage, see [📖 Documentations](https://alibaba.github.io/page-agent/docs/introduction/overview).

## 🌟 Awesome Page Agent

Built something cool with PageAgent? Add it here! Open a PR to share your project.

> These are community projects — not maintained or endorsed by us. Use at your own discretion.

| Project  | Description                                                 |
| -------- | ----------------------------------------------------------- |
| _Yours?_ | [Open a PR](https://github.com/alibaba/page-agent/pulls) 🙌 |

## 🤝 Contributing

We welcome contributions from the community! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines and [docs/developer-guide.md](docs/developer-guide.md) for local development workflows.

Please read the [maintainer's note](https://github.com/alibaba/page-agent/issues/349) on principles and current state.

Contributions generated entirely by **bots or AI** without substantial human involvement will **not be accepted**.

## ⚖️ License

[MIT License](LICENSE)

## 👏 Acknowledgments

This project builds upon the excellent work of **[`browser-use`](https://github.com/browser-use/browser-use)**.

`PageAgent` is designed for **client-side web enhancement**, not server-side automation.

```
DOM processing components and prompt are derived from browser-use:

Browser Use <https://github.com/browser-use/browser-use>
Copyright (c) 2024 Gregor Zunic
Licensed under the MIT License

We gratefully acknowledge the browser-use project and its contributors for their
excellent work on web automation and DOM interaction patterns that helped make
this project possible.
```

---

**⭐ Star this repo if you find PageAgent helpful!**
