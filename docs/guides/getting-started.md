# 📖 Getting Started with AI Agents | البدء مع وكلاء الذكاء الاصطناعي

> A provider-neutral introduction: what agents are, how to think about them, and how to run
> your first productive session — in any tool.
>
> مقدمة محايدة تجاه الأدوات: ما هي الوكلاء، كيف تفكر فيها، وكيف تشغل أول جلسة منتجة — في أي
> أداة كانت.

---

## Part 1 — English

### 1. What is an "AI agent"?

An **agent** is an AI model in a loop with tools. Instead of only answering text, an agent can:

1. **Read** your files, docs, and command output
2. **Plan** a sequence of steps
3. **Act** — edit files, run shell commands, call APIs
4. **Observe** the results and correct course
5. **Report** what it did, ideally with a reviewable diff

This loop is why agents feel different from chatbots: they don't just *describe* work, they
*do* it — while you stay in control via permissions and review.

### 2. The two families of agents

| Family | Examples | Where they live | Superpower |
|---|---|---|---|
| **Coding agents** | Claude Code, OpenCode | Your terminal & IDE | Deep work on a codebase: features, refactors, reviews, tests |
| **Personal assistants** | OpenClaw, Hermes Agent | Your devices & messaging apps | Always-available helper: messages, schedules, research, skills |

They compose beautifully: code all day with a coding agent, and let a personal assistant handle
research, reminders, and everything else.

### 3. The universal first-run checklist

Whichever agent you pick, the same five steps apply:

1. **Install** (see the [README](../../README.md#-getting-started--البدء-السريع) quick starts).
2. **Authenticate** with your model provider.
3. **Generate the project instructions file** — `CLAUDE.md` or `AGENTS.md` (Claude Code: `/init`,
   OpenCode: `/init`). Commit it to git. See the
   [instruction files guide](instructions-files.md).
4. **Ask for a plan first**, then approve, then execute. Plan-first is the highest-leverage
   habit in agentic coding.
5. **Review every diff** before merging. You are the quality gate.

### 4. Prompting agents: what actually works

- **Give context, not just orders.** "We use FastAPI + SQLAlchemy 2.0, tests run with
  `pytest -q`, never modify `migrations/` by hand" beats "add an endpoint".
- **State the definition of done.** "Done = tests pass + `ruff check` clean + docs updated."
- **Scope small.** One feature per session. Agents drift as sessions grow long; use
  `/compact` (Claude Code) or start fresh sessions and point them at committed work.
- **Interrupt and correct early.** Agents follow course corrections mid-task — pressing
  `Esc` and saying "stop, wrong direction because X" is normal and encouraged.
- **Ask for options on architectural decisions.** "Give me two approaches with trade-offs"
  prevents confident single-track mistakes.

### 5. Everyday workflow patterns

| Pattern | How |
|---|---|
| New feature | Plan mode → approve → implement → run tests → review diff → commit |
| Bug fix | Paste error + steps to reproduce → ask for root cause **before** the fix → fix → regression test |
| Code review | Point the agent at a PR: "review for correctness, security, and edge cases" |
| Refactor | Define invariants first → plan → move in small committed steps → tests after each step |
| Unknown codebase | "Explain the architecture", "trace what happens when X is called", generate a diagram |

### 6. Glossary | مصطلحات

| Term | Meaning |
|---|---|
| MCP (Model Context Protocol) | Open standard for connecting agents to external tools & data — [guide](mcp-guide.md) |
| `CLAUDE.md` / `AGENTS.md` | Instruction files agents read automatically — [guide](instructions-files.md) |
| Subagent | A helper agent spawned for a focused task |
| Skill | A reusable, written procedure an agent can load (core idea in Hermes; usable in others) |
| Plan mode | A mode where the agent proposes changes without executing them |
| Sandbox | An isolated environment (container/VM) limiting what an agent can touch |
| Context window | The model's working memory; long sessions fill it — summarize or restart |
| Prompt injection | A malicious instruction hidden in content the agent reads — [security](security-best-practices.md) |

---

## Part 2 — العربية

<div dir="rtl">

### 1. ما هو «الوكيل الذكي»؟

**الوكيل (Agent)** هو نموذج ذكاء اصطناعي يعمل في حلقة مستمرة مع أدوات. وبدلاً من الاكتفاء
بالردود النصية، يستطيع الوكيل أن:

1. **يقرأ** ملفاتك ووثائقك ومخرجات الأوامر
2. **يخطط** سلسلة خطوات
3. **ينفّذ** — تعدیل الملفات، تشغيل أوامر الطرفية، استدعاء الواجهات البرمجية
4. **يلاحظ** النتائج ويصحح مساره
5. **يبلّغ** عما فعله، ويفضَّل مع فروقات قابلة للمراجعة

هذه الحلقة هي سبب اختلاف الوكلاء عن روبوتات المحادثة: فهم لا *يصفون* العمل فحسب بل *ينفذونه* —
مع بقائك متحكماً عبر الصلاحيات والمراجعة.

### 2. عائلتا الوكلاء

| العائلة | أمثلة | موطنها | قوتها |
|---|---|---|---|
| **وكلاء البرمجة** | Claude Code و OpenCode | طرفيتك ومحررّك | العمل العميق على قاعدة الكود: ميزات، إعادة هيكلة، مراجعات، اختبارات |
| **المساعدون الشخصيون** | OpenClaw و Hermes Agent | أجهزتك وتطبيقات تراسلك | مساعد دائم الإتاحة: رسائل، جدولة، بحث، مهارات |

وتتكامل العائلتان بشكل رائع: برمج طوال اليوم مع وكيل برمجة، ودع مساعداً شخصياً يتولى البحث
والتذكيرات وكل ما عدا ذلك.

### 3. قائمة أول تشغيل العالمية

أي وكيل تختاره، تنطبق عليه الخطوات الخمس نفسها:

1. **ثبّت** (انظر [README](../../README.md#-getting-started--البدء-السريع)).
2. **سجّل الدخول** مع مزوّد النماذج.
3. **ولّد ملف تعليمات المشروع** — `CLAUDE.md` أو `AGENTS.md` (في Claude Code و OpenCode:
   الأمر `/init`)، واعتمده في Git. راجع [دليل ملفات التعليمات](instructions-files.md).
4. **اطلب خطة أولاً**، ثم وافق، ثم نفّذ. «الخطة أولاً» هي العادة الأعلى أثراً في البرمجة
   الوكيلية.
5. **راجع كل الفروقات** قبل الدمج. أنت بوابة الجودة.

### 4. كتابة الأوامر للوكلاء: ما ينجح فعلاً

- **أعطِ سياقاً لا مجرد أوامر.** "نستخدم FastAPI مع SQLAlchemy 2.0، والاختبارات تشتغل بـ
  `pytest -q`، ولا تعدّل مجلد `migrations/` يدوياً" أفضل من "أضف واجهة".
- **حدد معيار الإنجاز.** "ينتهي العمل عندما تنجح الاختبارات ويصبح `ruff check` نظيفاً وتُحدَّث
  الوثائق."
- **صغّر النطاق.** ميزة واحدة لكل جلسة. يتشتت الوكيل تطول الجلسة؛ استخدم `/compact` أو ابدأ
  جلسات جديدة ووجّهها إلى عمل معتمد في Git.
- **قاطع وصحح مبكراً.** الوكلاء يستجيبون للتصحيح أثناء المهمة — الضغط على `Esc` وقول "توقف،
  الاتجاه خاطئ لأن كذا" أمر طبيعي ومشجَّع.
- **اطلب خيارات في القرارات المعمارية.** "أعطني مقاربتين مع المقايضات" يمنع أخطاء الثقة
  العمياء في مسار واحد.

### 5. أنماط العمل اليومية

| النمط | الطريقة |
|---|---|
| ميزة جديدة | وضع الخطة ← موافقة ← تنفيذ ← تشغيل الاختبارات ← مراجعة الفروقات ← اعتماد |
| إصلاح خطأ | الصق رسالة الخطأ وخطوات التكرار ← اطلب السبب الجذري **قبل** الإصلاح ← أصلح ← اختبار انحدار |
| مراجعة كود | وجّه الوكيل إلى طلب الدمج: "راجع الصحة والأمان والحالات الحدية" |
| إعادة هيكلة | عرّف الثوابت أولاً ← خطط ← تحرك بخطوات معتمدة صغيرة ← اختبار بعد كل خطوة |
| مشروع مجهول | "اشرح المعمارية"، "تتبع ما يحدث عند استدعاء X"، ولّد رسماً بيانياً |

### 6. المصطلحات

| المصطلح | المعنى |
|---|---|
| MCP (بروتوكول سياق النموذج) | معيار مفتوح لربط الوكلاء بالأدوات والبيانات — [الدليل](mcp-guide.md) |
| `CLAUDE.md` / `AGENTS.md` | ملفات تعليمات يقرؤها الوكلاء تلقائياً — [الدليل](instructions-files.md) |
| وكيل فرعي | وكيل مساعد يُستدعى لمهمة محددة |
| مهارة | إجراء مكتوب قابل لإعادة الاستخدام يحمّله الوكيل (فكرة مركزية في Hermes وممكنة في غيره) |
| وضع الخطة | وضع يقترح فيه الوكيل التغييرات دون تنفيذها |
| بيئة معزولة | بيئة معزولة (حاوية/آلة افتراضية) تحد مما يمكن للوكيل لمسه |
| نافذة السياق | الذاكرة العاملة للنموذج؛ تمتلئ بالجلسات الطويلة — لخّص أو أعد التشغيل |
| حقن الأوامر | تعليمة خبيثة مخبأة في محتوى يقرؤه الوكيل — [الأمان](security-best-practices.md) |

</div>
