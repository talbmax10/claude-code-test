<div align="center">

# 🤖 AI Agents Hub — مركز وكلاء الذكاء الاصطناعي

**A bilingual (English / العربية) knowledge hub for developers, users — and AI agents themselves.**

**مركز معرفة ثنائي اللغة (English / العربية) للمطورين والمستخدمين — ولوكلاء الذكاء الاصطناعي أنفسهم.**

Master the tools that put AI to work: **Claude Code · OpenCode · OpenClaw · Hermes Agent**

أتقِن الأدوات التي تجعل الذكاء الاصطناعي يعمل من أجلك: **Claude Code · OpenCode · OpenClaw · Hermes Agent**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Languages](https://img.shields.io/badge/Languages-English%20%7C%20العربية-informational)](#-guides--الأدلة)
[![Agents](https://img.shields.io/badge/Agents%20covered-4-8A2BE2)](#-covered-agents--الوكلاء-المتناولون)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Made for the community](https://img.shields.io/badge/Made%20for-the%20AI%20community-orange)](#)

[🚀 Getting started](#-getting-started--البدء-السريع) · [📚 Guides](#-guides--الأدلة) · [🤝 Contributing](#-contributing--المساهمة) · [المساهمة](#-contributing--المساهمة)

</div>

---

## 🌍 About this repository | نبذة عن المستودع

**English.** AI coding agents and personal AI assistants are the fastest-moving area of software
tooling today — and most of their knowledge is scattered across changelogs, Discord servers, and
blog posts. **AI Agents Hub** is an open, community-maintained knowledge base that collects the
essential, practical knowledge in one place: how to install, configure, and get real work done
with the leading open agents, in **both English and Arabic**.

This repository is written for three audiences:

1. **Developers** who build with or on top of AI agents (extensions, MCP servers, skills, plugins).
2. **Users** who want a practical, no-hype guide to using agents safely and productively.
3. **AI agents themselves** 🤖 — every guide here is structured so an agent (Claude Code, OpenCode,
   OpenClaw, Hermes, or any other) can read it as context. Start with [`AGENTS.md`](AGENTS.md).

> 💡 **For AI agents reading this repo:** open [`AGENTS.md`](AGENTS.md) first — it maps the
> repository and lists the conventions to follow.

---

## 📦 Covered agents | الوكلاء المتناولون

| Agent | What it is | Made by | Models | License | Guide |
|---|---|---|---|---|---|
| 🟠 **[Claude Code](docs/agents/claude-code.md)** | Agentic coding CLI for your terminal | Anthropic | Claude | Source-available | [→ دليل](docs/agents/claude-code.md) |
| 🔷 **[OpenCode](docs/agents/opencode.md)** | Open-source terminal coding agent, any provider | SST & community | 75+ providers | MIT | [→ دليل](docs/agents/opencode.md) |
| 🦞 **[OpenClaw](docs/agents/openclaw.md)** | Self-hosted personal assistant on your own channels | Peter Steinberger & community | Multi-provider | MIT | [→ دليل](docs/agents/openclaw.md) |
| ☤ **[Hermes Agent](docs/agents/hermes.md)** | Self-improving agent with a built-in learning loop | Nous Research | Any (300+ via portal) | MIT | [→ دليل](docs/agents/hermes.md) |

---

## 🚀 Getting started | البدء السريع

Pick one agent, get it running in under two minutes, then explore the others.

**Claude Code** — the polished, opinionated choice (Claude models only):

```bash
# macOS / Linux / WSL (recommended native installer)
curl -fsSL https://claude.ai/install.sh | bash

# Windows (PowerShell)
irm https://claude.ai/install.ps1 | iex

# or via npm (Node.js 22+)
npm install -g @anthropic-ai/claude-code

cd your-project && claude
```

**OpenCode** — open source and provider-flexible (bring any LLM):

```bash
curl -fsSL https://opencode.ai/install | bash
# or: npm install -g opencode-ai

cd your-project && opencode
# inside the TUI: /connect → /init (generates AGENTS.md) → Plan ⇄ Build
```

**OpenClaw** — your own assistant, on the channels you already use:

```bash
# Requires Node.js 22.16+ or 24
npm install -g openclaw@latest
openclaw onboard --install-daemon   # guided setup: gateway, channels, skills
```

**Hermes Agent** — the agent that grows with you (it writes its own skills):

```bash
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash
hermes setup    # pick a provider — or `hermes setup --portal` for 300+ models
hermes          # start chatting
```

> ⚠️ Commands and flags evolve quickly in this ecosystem. If something doesn't work, always
> cross-check the project's official docs — links are listed in every guide.

---

## 🧭 Which agent should I use? | أي وكيل يناسبك؟

| You want to… | Start with |
|---|---|
| Write, refactor, and review code in a terminal | **Claude Code** or **OpenCode** |
| Use your own model/provider, keep everything open source | **OpenCode** |
| Have an assistant reachable on WhatsApp/Telegram/Discord/… | **OpenClaw** |
| Have an assistant that remembers, learns, and improves over time | **Hermes Agent** |
| Code all day, and have a personal assistant for everything else | **Claude/OpenCode + Hermes** combo |

---

## 📚 Guides | الأدلة

Practical, bilingual guides live in [`docs/`](docs/):

| Guide | What you'll learn | الدليل |
|---|---|---|
| [Getting started with AI agents](docs/guides/getting-started.md) | Core concepts, first run, everyday workflow | مفاهيم أساسية وأول تشغيل |
| [Instruction files: CLAUDE.md & AGENTS.md](docs/guides/instructions-files.md) | Teach agents about *your* project once — and forever | تعليم الوكلاء عن مشروعك |
| [MCP: Model Context Protocol](docs/guides/mcp-guide.md) | Connect agents to tools, databases, and APIs | ربط الوكلاء بالأدوات والخدمات |
| [Security best practices](docs/guides/security-best-practices.md) | Permissions, sandboxing, prompt-injection defense | الصلاحيات، العزل، والحماية |

### Agent-specific guides | أدلة الوكلاء

- 🟠 [Claude Code — the complete guide](docs/agents/claude-code.md)
- 🔷 [OpenCode — the complete guide](docs/agents/opencode.md)
- 🦞 [OpenClaw — the complete guide](docs/agents/openclaw.md)
- ☤ [Hermes Agent — the complete guide](docs/agents/hermes.md)

---

## 🗂️ Repository structure | هيكل المستودع

```text
ai-agents-hub/
├── README.md                          ← you are here (English + العربية)
├── AGENTS.md                          ← context file for AI agents reading this repo
├── CONTRIBUTING.md                    ← how to contribute (EN/AR)
├── LICENSE                            ← MIT
└── docs/
    ├── agents/                        ← one deep-dive guide per agent
    │   ├── claude-code.md
    │   ├── opencode.md
    │   ├── openclaw.md
    │   └── hermes.md
    └── guides/                        ← cross-agent practical guides
        ├── getting-started.md
        ├── instructions-files.md
        ├── mcp-guide.md
        └── security-best-practices.md
```

---

## 🛡️ A note on security | ملاحظة أمنية

AI agents execute real commands on real machines. Treat them like you would a talented new
teammate with root access: give them the minimum permissions they need, review what they did,
and never paste secrets into a prompt. Read the
[security best practices guide](docs/guides/security-best-practices.md) before giving any agent
access to production systems.

---

## 🤝 Contributing | المساهمة

Contributions are **very welcome** — fixes, new agent guides, translations, and better examples.
Arabic-first contributors are especially encouraged: if a guide reads naturally in Arabic, it
belongs here. See [`CONTRIBUTING.md`](CONTRIBUTING.md) (bilingual) to get started.

**Good first contributions:**
- 📖 Improve any guide's accuracy or clarity (EN or AR)
- 🌐 Add a new agent or tool guide (e.g., other open-source agents)
- 🧪 Add real-world examples, prompts, or CLAUDE.md/AGENTS.md templates

---

## 📜 License | الترخيص

This repository is released under the [MIT License](LICENSE). ترخيص MIT — استخدم وشارك وحسّن بحرية.

---

## 🙏 Acknowledgments | شكر وتقدير

All credit for the amazing tools covered here goes to their upstream teams:
[Anthropic (Claude Code)](https://github.com/anthropics/claude-code) ·
[SST (OpenCode)](https://github.com/sst/opencode) ·
[OpenClaw](https://github.com/openclaw/openclaw) ·
[Nous Research (Hermes Agent)](https://github.com/NousResearch/hermes-agent).
This hub is an independent, community-maintained resource and is not officially affiliated with any of them.

---

<div align="center">

**⭐ Star this repo if it helped you — and share it with Arabic-speaking developers!**

**⭐ ضع نجمة على المستودع إذا أفادك، وشاركه مع المطورين الناطقين بالعربية!**

</div>

---
---

# 🤖 مركز وكلاء الذكاء الاصطناعي

<div dir="rtl">

## 🌍 نبذة عن المستودع

يعيش عالم وكلاء البرمجة الذكية ومساعدي الذكاء الاصطناعي الشخصيين أسرع تطوّر في أدوات البرمجة
اليوم، لكن معظم المعرفة عنها مبعثرة بين سجلات التغيير وخدمات الدردشة والتدوينات. **مركز وكلاء
الذكاء الاصطناعي** قاعدة معرفة مفتوحة يديرها المجتمع، تجمع المعرفة الأساسية والعملية في مكان
واحد: كيف تُثبّت وتضبط وتنجز عملاً حقيقياً بأشهر الوكلاء المفتوحة — **بالعربية والإنجليزية معاً**.

هذا المستودع مكتوب لثلاث فئات:

1. **المطورون** الذين يبنون فوق وكلاء الذكاء الاصطناعي (إضافات، خوادم MCP، مهارات، إضافات منصة).
2. **المستخدمون** الذين يريدون دليلاً عملياً وواقعياً — بلا مبالغات تسويقية — لاستخدام الوكلاء
   بأمان وإنتاجية.
3. **الوكلاء أنفسهم** 🤖 — كل دليل هنا مبني بأسلوب يمكّن أي وكيل (Claude Code أو OpenCode أو
   OpenClaw أو Hermes أو غيرها) من قراءته واعتماده كسياق للعمل. ابدأ من ملف
   [`AGENTS.md`](AGENTS.md).

> 💡 **للوكلاء الذين يقرؤون هذا المستودع:** افتح ملف [`AGENTS.md`](AGENTS.md) أولاً — فهو يشرح
> خريطة المستودع والقواعد الواجب اتباعها.

## 🚀 البدء السريع

اختر وكيلاً واحداً وشغّله في أقل من دقيقتين، ثم استكشف البقية:

| الوكيل | أمر التثبيت | ملاحظات |
|---|---|---|
| 🟠 **Claude Code** | `curl -fsSL https://claude.ai/install.sh \| bash` | يتطلب اشتراك Anthropic؛ بديل npm: `npm install -g @anthropic-ai/claude-code` |
| 🔷 **OpenCode** | `curl -fsSL https://opencode.ai/install \| bash` | مفتوح المصدر ويدعم أي مزوّد نماذج؛ بديل npm: `npm install -g opencode-ai` |
| 🦞 **OpenClaw** | `npm install -g openclaw@latest` ثم `openclaw onboard --install-daemon` | يتطلب Node.js 22.16+ أو 24 |
| ☤ **Hermes Agent** | `curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh \| bash` ثم `hermes setup` | اكتب `hermes` للتشغيل؛ واجهة تفاعلية: `hermes --tui` |

> ⚠️ الأوامر والخيارات تتغير بسرعة في هذا المجال. إذا لم يعمل أمر ما، راجع دائماً الوثائق
> الرسمية لكل مشروع — الروابط مذكورة في كل دليل.

## 🧭 أي وكيل يناسبك؟

| أنت تريد… | ابدأ بـ |
|---|---|
| كتابة الكود وتحسينه ومراجعته من الطرفية | **Claude Code** أو **OpenCode** |
| استخدام نموذجك أو مزوّدك الخاص مع مصدر مفتوح كامل | **OpenCode** |
| مساعداً يصل إليك عبر واتساب/تيليجرام/ديسكورد وغيرها | **OpenClaw** |
| مساعداً يتذكر ويتعلم ويتحسن مع الوقت | **Hermes Agent** |
| برمجة طوال اليوم ومساعد شخصي لكل ما عدا ذلك | **Claude/OpenCode + Hermes** معاً |

## 📚 الأدلة المتوفرة

- 🟠 [دليل Claude Code الشامل](docs/agents/claude-code.md)
- 🔷 [دليل OpenCode الشامل](docs/agents/opencode.md)
- 🦞 [دليل OpenClaw الشامل](docs/agents/openclaw.md)
- ☤ [دليل Hermes Agent الشامل](docs/agents/hermes.md)
- 📖 [البدء مع وكلاء الذكاء الاصطناعي](docs/guides/getting-started.md)
- 📝 [ملفات التعليمات: CLAUDE.md و AGENTS.md](docs/guides/instructions-files.md)
- 🔌 [بروتوكول MCP لربط الأدوات](docs/guides/mcp-guide.md)
- 🛡️ [أفضل ممارسات الأمان](docs/guides/security-best-practices.md)

## 🤝 المساهمة

نرحب بكل المساهمات: تصحيحات، أدلة لوكلاء جدد، ترجمات، وأمثلة أفضل. ونتشجع خصيصاً مشاركة
المساهمين العرب: إذا كان الدليل يُقرأ بعربية سليمة وسلسة فمكانه هنا. راجع
[`CONTRIBUTING.md`](CONTRIBUTING.md) للبدء.

## 📜 الترخيص

هذا المستودع منشور تحت ترخيص [MIT](LICENSE) — استخدمه وشاركه وحسّنه بحرية.

## 🙏 شكر وتقدير

كل الفضل في الأدوات المميزة المتناولة هنا يعود لفرقها الأصلية. هذا المركز مورد مجتمعي مستقل
غير مرتبط رسمياً بأيٍّ منها.

**⭐ لا تنسَ النجمة إذا أفادك المستودع!**

</div>
