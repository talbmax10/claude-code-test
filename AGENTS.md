# AGENTS.md — Context for AI agents | سياق للوكلاء الذكيين

> This file follows the [agents.md](https://agents.md) open standard. If you are an AI agent
> (Claude Code, OpenCode, OpenClaw, Hermes, or any other) working in or with this repository,
> start here.
>
> يتبع هذا الملف معيار agents.md المفتوح. إذا كنت وكيلاً ذكياً يعمل في هذا المستودع أو معه،
> فابدأ من هنا.

---

## 1. What this repository is | ما هذا المستودع

- **English:** A bilingual (English/Arabic) documentation hub that helps developers, users, and
  AI agents master agentic AI tools: Claude Code, OpenCode, OpenClaw, and Hermes Agent.
  It contains **documentation only** — no application source code, no build system.
- **العربية:** مركز توثيق ثنائي اللغة (عربي/إنجليزي) يساعد المطورين والمستخدمين والوكلاء الذكيين
  على إتقان أدوات الوكلاء: Claude Code و OpenCode و OpenClaw و Hermes Agent. المستودع وثائقي
  بالكامل — لا يحتوي كود تطبيق ولا نظام بناء.

## 2. Repository map | خريطة المستودع

| Path | Contents |
|---|---|
| `README.md` | Hub overview, quick starts, navigation (EN + AR) |
| `docs/agents/*.md` | One deep-dive guide per agent |
| `docs/guides/*.md` | Cross-agent guides (getting started, instruction files, MCP, security) |
| `CONTRIBUTING.md` | Style rules and contribution workflow |
| `LICENSE` | MIT |

## 3. Conventions to respect | قواعد أساسية

1. **Bilingual structure:** every document has an English part and an Arabic part. Arabic
   sections are wrapped in `<div dir="rtl">` and must use natural, professional Arabic
   (فصحى تقنية واضحة) — not machine-literal translation.
2. **Never invent install commands or flags.** The agent ecosystem changes fast. Verify every
   command against the project's official docs before adding or changing it, and keep the
   "official links" table in each agent guide accurate.
3. **Relative links only** between documents in this repo, so links work on GitHub and in
   offline clones.
4. **Neutral and factual:** this hub is community-run and not affiliated with any upstream
   project. Avoid marketing claims; prefer measured, practical language.
5. **Security first:** never include commands that pipe secrets, disable safety features, or
   auto-approve destructive actions. Every agent has a security section — keep it honest.

## 4. Common tasks | مهام شائعة

- **Add/improve a guide:** follow the structure of an existing guide
  (`What is it? → Install → First session → Tips → Resources`), in both languages, then check
  every link and command.
- **Fix a translation:** keep the English and Arabic sections semantically identical; if you
  change one, update the other in the same pull request.
- **Add a new agent:** create `docs/agents/<name>.md`, add rows to the tables in `README.md`
  (both languages), and update `CONTRIBUTING.md` if you introduce new conventions.

## 5. Definition of done | معيار الاكتمال

A change is complete when: content is accurate and verified, both language sections match,
all links resolve, tables are valid Markdown, and the tone matches the existing guides.
