# 🟠 Claude Code — Complete Guide | الدليل الشامل

> Anthropic's agentic coding tool that lives in your terminal and turns descriptions of what you
> want into real, reviewed code changes.
>
> أداة البرمجة الوكيلية من Anthropic التي تعيش في طرفيتك وتحوّل وصف ما تريده إلى تغييرات برمجية
> حقيقية قابلة للمراجعة.

**Official links | الروابط الرسمية:** [Docs](https://docs.anthropic.com/en/docs/claude-code) · [GitHub](https://github.com/anthropics/claude-code) · [Status](https://status.anthropic.com)

---

## Part 1 — English

### What is it?

Claude Code is an **agentic coding CLI** from Anthropic. Instead of autocomplete-in-an-editor, it
works like a teammate: you describe a task in natural language, it explores your codebase, edits
files, runs commands and tests, and reports back with a diff you can review. It reads and writes
across your whole project, keeps persistent project memory in `CLAUDE.md`, and can be extended
with MCP servers, custom slash commands, hooks, and subagents.

### Key features

| Feature | What it means in practice |
|---|---|
| Agentic search & edits | Understands large codebases without you hand-picking files |
| `CLAUDE.md` memory | Persistent, versioned project instructions the agent reads every session |
| Plan mode | Discuss and approve an approach before a single file changes |
| Subagents | Delegate focused tasks (e.g., code review, test writing) to specialized helpers |
| Hooks | Run your own commands on tool events (e.g., auto-format after every edit) |
| MCP support | Connect databases, browsers, issue trackers, and internal tools |
| Git & CI native | Works with worktrees, pull requests, and GitHub Actions |

### Installation

```bash
# macOS / Linux / WSL — recommended native installer
curl -fsSL https://claude.ai/install.sh | bash

# Windows PowerShell
irm https://claude.ai/install.ps1 | iex

# Alternative: npm (Node.js 22+)
npm install -g @anthropic-ai/claude-code
```

You need a Claude **Pro, Max, Team, or Enterprise** subscription, or an Anthropic Console
account with API billing. Sign in on first run: `claude` → follow the browser prompt.

### Your first session

```bash
cd your-project
claude              # start interactive session
> /init             # scan the repo and generate CLAUDE.md
> Explain this project's architecture
> Implement <feature> — plan first
```

**Habits that make Claude Code dramatically better:**

1. **Commit `CLAUDE.md` to git.** Write your stack, conventions, build/test commands, and
   "never do" rules in it. It is the single highest-leverage file for agent quality.
2. **Use plan mode** (`Shift+Tab` to toggle) for anything non-trivial. Approve the plan, then
   let it execute.
3. **Review diffs like a senior engineer reviews a junior's PR.** The agent is fast; you are
   the quality gate.
4. **Push back.** "That approach leaks state between tests — use fixtures" beats accepting
   mediocre code and fixing it later.
5. **Keep sessions focused.** One feature or bug per session produces cleaner history than
   day-long meandering sessions.

### Essential commands

| Command | Purpose |
|---|---|
| `claude` | Start an interactive session |
| `claude -p "query"` | One-shot, non-interactive run (great for scripts/CI) |
| `/init` | Generate or update `CLAUDE.md` |
| `/memory` | Edit instruction files |
| `/agents` | Manage subagents |
| `/mcp` | Manage MCP servers |
| `/compact` | Summarize a long conversation to free context |
| `/permissions` | Review tool permissions |
| `claude --version`, `claude doctor` | Version and health check |

---

## Part 2 — العربية

<div dir="rtl">

### ما هو؟

Claude Code أداة برمجة وكيلية (Agentic) من Anthropic تعمل من سطر الأوامر. بدلاً من الإكمال
التلقائي داخل المحرر، تعمل كزميل فريق: تصف المهمة بلغة طبيعية، فيستكشف مشروعك ويعدّل الملفات
ويشغّل الأوامر والاختبارات، ثم يعود إليك بفروقات (diffs) قابلة للمراجعة. يقرأ مشروعك بأكمله
ويكتب فيه، ويحتفظ بذاكرة دائمة للمشروع في ملف `CLAUDE.md`، ويمكن توسيعه عبر خوادم MCP والأوامر
المخصصة والخطافات (hooks) والوكلاء الفرعيين (subagents).

### أبرز المزايا

| الميزة | المعنى عملياً |
|---|---|
| بحث وتعديل وكيلي | يفهم المشاريع الكبيرة دون أن تختار له الملفات يدوياً |
| ذاكرة `CLAUDE.md` | تعليمات دائمة للمشروع يقرؤها الوكيل في كل جلسة |
| وضع التخطيط | ناقش الخطة ووافق عليها قبل تغيير أي ملف |
| وكلاء فرعيون | فوّض مهام محددة (مراجعة كود، كتابة اختبارات) لمساعدين متخصصين |
| الخطافات Hooks | شغّل أوامرك عند أحداث معينة (مثل التنسيق التلقائي بعد كل تعديل) |
| دعم MCP | اربط الوكيل بقواعد البيانات والمتصفحات وأنظمة التذاكر وأدواتك الداخلية |
| تكامل مع Git وCI | يعمل مع الفروع وطلبات الدمج وGitHub Actions |

### التثبيت

```bash
# ماك / لينكس / WSL — المثبّت الأصلي (الموصى به)
curl -fsSL https://claude.ai/install.sh | bash

# ويندوز (PowerShell)
irm https://claude.ai/install.ps1 | iex

# بديل: npm (يتطلب Node.js 22+)
npm install -g @anthropic-ai/claude-code
```

تحتاج اشتراك Claude (Pro أو Max أو Team أو Enterprise) أو حساب Anthropic Console بفوترة API.
سجّل الدخول عند أول تشغيل بالأمر `claude` واتبع نافذة المتصفح.

### جلستك الأولى

```bash
cd your-project
claude              # بدء جلسة تفاعلية
> /init             # فحص المشروع وتوليد ملف CLAUDE.md
> اشرح معمارية هذا المشروع
> نفّذ الميزة التالية — مع وضع الخطة أولاً
```

**عادات تجعل Claude Code أفضل بكثير:**

1. **اعتمد `CLAUDE.md` في Git.** اكتب فيه التقنيات والمعايير وأوامر البناء والاختبار والقواعد
   الممنوعة. هو الملف الأعلى أثراً على جودة الوكيل إطلاقاً.
2. **استخدم وضع الخطة** (`Shift+Tab`) لكل مهمة غير بسيطة: وافق على الخطة ثم اتركه ينفذ.
3. **راجع الفروقات كمراجع خبير يراجع عمل مبتدئ.** الوكيل سريع، لكنك أنت بوابة الجودة.
4. **اعترض عند الحاجة.** عبارة "هذا الحل يسرّب الحالة بين الاختبارات — استخدم fixtures" أفضل من
   قبول كود متواضع ثم إصلاحه لاحقاً.
5. **اجعل الجلسات مركزة.** مهمة واحدة لكل جلسة تعطي سجل عمل أنظف من جلسات طويلة مشتتة.

### أوامر أساسية

| الأمر | الغرض |
|---|---|
| `claude` | بدء جلسة تفاعلية |
| `claude -p "سؤال"` | تشغيل لمرة واحدة غير تفاعلي (مثالي للسكربتات وCI) |
| `/init` | توليد أو تحديث `CLAUDE.md` |
| `/memory` | تعديل ملفات التعليمات |
| `/agents` | إدارة الوكلاء الفرعيين |
| `/mcp` | إدارة خوادم MCP |
| `/compact` | تلخيص محادثة طويلة لتوفير السياق |
| `/permissions` | مراجعة صلاحيات الأدوات |
| `claude doctor` | فحص سلامة التثبيت |

</div>

---

*Know something missing or outdated? [Open an issue or PR](../../CONTRIBUTING.md) — bilingual fixes are especially welcome.*
