# ☤ Hermes Agent — Complete Guide | الدليل الشامل

> "The agent that grows with you." An open-source, self-improving personal AI agent by
> Nous Research — it learns skills from experience, remembers across sessions, and meets you
> wherever you are: terminal, desktop, or messaging apps.
>
> «الوكيل الذي ينمو معك». وكيل شخصي مفتوح المصدر يتطور ذاتياً من Nous Research — يتعلم مهارات
> من تجربته، ويتذكر عبر الجلسات، ويقابلك أينما كنت: الطرفية أو سطح المكتب أو تطبيقات التراسل.

**Official links | الروابط الرسمية:** [GitHub](https://github.com/NousResearch/hermes-agent) · [Website](https://hermes-ai.net)

---

## Part 1 — English

### What is it?

Hermes Agent is an **open-source, self-hosted AI agent** from Nous Research (the lab behind the
Hermes family of open models), released under the MIT license in February 2026 and growing
rapidly since. Its defining idea is a **built-in learning loop**: after completing a complex
task, Hermes distills the procedure into a reusable **skill**; skills improve with use; and a
persistent memory (SQLite full-text search + LLM summarization) lets it recall context from
months ago. Where coding agents like Claude Code and OpenCode are session-based, Hermes is
designed as a **long-lived assistant** with one memory across every surface: a CLI (with an Ink
TUI), a desktop app, and messaging gateways.

### Key features

| Feature | What it means in practice |
|---|---|
| Learning loop | Solves a task → distills it into a reusable skill → gets faster and cheaper next time |
| Persistent memory | Cross-session recall with full-text search; builds a model of your preferences |
| Every surface | CLI (`hermes`), TUI (`hermes --tui`), desktop apps, and gateways: Telegram, Discord, Slack, WhatsApp, Signal, email, and more |
| Any model | OpenAI, Anthropic, OpenRouter, or Nous Portal (300+ models, one subscription) |
| 40+ built-in tools | Browser, search, images, voice, files, code execution in sandboxes, cron scheduling |
| Subagents | Spawn helpers with their own terminals and sandboxes |
| MCP support | Manage MCP servers with `hermes mcp` (incl. OAuth 2.1 flows for remote servers) |
| Multi-agent talk | A2A protocol support and Bot Mode for coordinating multiple agents |

### Installation

```bash
# Linux / macOS / WSL2 / Android (Termux) — official installer
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash

# Windows native (PowerShell)
iex (irm https://hermes-agent.nousresearch.com/install.ps1)

# After install — reload your shell, then:
hermes setup            # configure your provider (or: hermes setup --portal)
hermes                  # start chatting
hermes --tui            # interactive TUI mode
```

### Your first session

```text
> Hello! Who are you and what can you do?
> Research <topic> and write a structured summary — save it as a project.
> Remember: I prefer concise answers with code examples.     ← memory at work
```

**Habits that make Hermes dramatically better:**

1. **Let it build skills — then reuse them.** When a task completes well, ask Hermes to save
   the procedure as a skill. Next time, it loads the skill instead of reasoning from scratch.
2. **Tell it your preferences explicitly.** "Remember that I prefer X" feeds its persistent
   user model — one of its core differentiators.
3. **Use projects for ongoing work.** Long-running efforts (research, content pipelines,
   operations) benefit from per-project memory and scheduling.
4. **Start with `hermes setup --portal`** if you don't want to juggle provider API keys — one
   subscription covers 300+ models and bundled tool gateway services.
5. **Curate skills.** Skills are powerful but community-shared skills deserve review before
   you trust them (see the security guide).

### Hermes vs. the others

| | Hermes Agent | OpenClaw | Claude Code / OpenCode |
|---|---|---|---|
| Primary role | Long-lived personal agent | Personal assistant gateway | Coding agents |
| Learns skills automatically | ✅ | ❌ | ❌ |
| Cross-session memory | ✅ (first-class) | Limited | Project files only |
| Messaging gateways | ✅ (many) | ✅ | ❌ |
| Model flexibility | Any provider | Multi-provider | Claude / any provider |
| Open source | ✅ MIT | ✅ MIT | ❌ / ✅ |

---

## Part 2 — العربية

<div dir="rtl">

### ما هو؟

Hermes Agent وكيل ذكي **مفتوح المصدر** تستضيفه بنفسك، من تطوير Nous Research (المختبر العائد
عائلة نماذج Hermes المفتوحة)، أُطلق بترخيص MIT في فبراير 2026 ونما بسرعة منذ ذلك الحين. فكرته
المحورية هي **حلقة التعلم المدمجة**: بعد إنجاز مهمة معقدة، يُقطّر Hermes الإجراء إلى **مهارة**
قابلة لإعادة الاستخدام؛ وتتحسن المهارات بالاستخدام؛ وذاكرة دائمة (بحث نصي كامل في SQLite مع
تلخيص بالنماذج اللغوية) تتيح له استحضار سياق منذ شهور. وحيث إن وكلاء البرمجة مثل Claude Code
و OpenCode قائمون على الجلسات، صُمم Hermes كمساعد **طويل العمر** بذاكرة واحدة عبر كل الواجهات:
سطر الأوامر (مع واجهة TUI) وتطبيقات سطح المكتب وبوابات التراسل.

### أبرز المزايا

| الميزة | المعنى عملياً |
|---|---|
| حلقة التعلم | يحل المهمة ← يتحولها إلى مهارة قابلة لإعادة الاستخدام ← يصبح أسرع وأرخص في المرة التالية |
| ذاكرة دائمة | استدعاء عبر الجلسات ببحث نصي كامل، وتبني نموذجاً لتفضيلاتك |
| كل الواجهات | سطر الأوامر (`hermes`)، وواجهة TUI (`hermes --tui`)، وتطبيقات سطح المكتب، وبوابات: تيليجرام وديسكورد وسلاك وواتساب وسيجنال والبريد وغيرها |
| أي نموذج | OpenAI و Anthropic و OpenRouter أو Nous Portal (أكثر من 300 نموذج باشتراك واحد) |
| أكثر من 40 أداة مدمجة | متصفح، بحث، صور، صوت، ملفات، تنفيذ كود معزول، جدولة دورية |
| وكلاء فرعيون | يطلق مساعدين بأطرافية وبيئات معزولة خاصة بهم |
| دعم MCP | إدارة خوادم MCP عبر `hermes mcp` (يشمل مسارات OAuth 2.1 للخوادم البعيدة) |
| تنسيق الوكلاء | دعم بروتوكول A2A ووضع Bot Mode لتنسيق عدة وكلاء |

### التثبيت

```bash
# لينكس / ماك / WSL2 / أندرويد (Termux) — المثبّت الرسمي
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash

# ويندوز أصلي (PowerShell)
iex (irm https://hermes-agent.nousresearch.com/install.ps1)

# بعد التثبيت — أعد تحميل الطرفية ثم:
hermes setup            # اضبط مزوّدك (أو: hermes setup --portal)
hermes                  # ابدأ المحادثة
hermes --tui            # الوضع التفاعلي TUI
```

### جلستك الأولى

```text
> مرحباً! من أنت وما الذي تستطيع فعله؟
> ابحث عن <موضوع> واكتب ملخصاً منظماً — واحفظه كمشروع.
> تذكّر: أفضّل الإجابات الموجزة مع أمثلة برمجية.     ← الذاكرة الدائمة في العمل
```

**عادات تجعل Hermes أفضل بكثير:**

1. **دعه يبني المهارات ثم أعد استخدامها.** عندما تنجز مهمة بنجاح، اطلب من Hermes حفظ الإجراء
   كمهارة. في المرة القادمة يحمّل المهارة بدل التفكير من الصفر.
2. **أخبره بتفضيلاتك صراحة.** عبارة "تذكّر أنني أفضّل كذا" تغذي نموذج المستخدم الدائم — وهي من
   أبرز نقاط تميزه.
3. **استخدم المشاريع للأعمال المستمرة.** الجهود طويلة الأمد (بحث، خطوط إنتاج محتوى، عمليات)
   تستفيد من ذاكرة لكل مشروع ومن الجدولة.
4. **ابدأ بـ `hermes setup --portal`** إن لم ترغب بإدارة مفاتيح مزوّدين متعددين — اشتراك واحد
   يغطي أكثر من 300 نموذج مع خدمات بوابة أدوات مدمجة.
5. **دقّق في المهارات.** المهارات قوية، لكن مهارات المجتمع تحتاج مراجعة قبل الثقة بها (راجع
   دليل الأمان).

### Hermes مقارنة بغيره

| | Hermes Agent | OpenClaw | Claude Code / OpenCode |
|---|---|---|---|
| الدور الأساسي | وكيل شخصي طويل العمر | بوابة مساعد شخصي | وكلاء برمجة |
| يتعلم مهارات تلقائياً | ✅ | ❌ | ❌ |
| ذاكرة عبر الجلسات | ✅ (مواطن أول) | محدودة | ملفات المشروع فقط |
| بوابات التراسل | ✅ (كثيرة) | ✅ | ❌ |
| مرونة النماذج | أي مزوّد | عدة مزوّدين | Claude / أي مزوّد |
| مصدر مفتوح | ✅ MIT | ✅ MIT | ❌ / ✅ |

</div>

---

*Know something missing or outdated? [Open an issue or PR](../../CONTRIBUTING.md) — bilingual fixes are especially welcome.*
