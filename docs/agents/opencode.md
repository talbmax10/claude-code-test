# 🔷 OpenCode — Complete Guide | الدليل الشامل

> The open-source AI coding agent built for the terminal. Provider-agnostic, LSP-aware, and
> fully yours to inspect and modify.
>
> وكيل البرمجة الذكي مفتوح المصدر المبني للطرفية: محايد تجاه مزوّد النماذج، يدعم LSP، ومفتوح
> للفحص والتعديل بالكامل.

**Official links | الروابط الرسمية:** [Website & Docs](https://opencode.ai) · [GitHub](https://github.com/sst/opencode) · [Models](https://opencode.ai/zen)

---

## Part 1 — English

### What is it?

OpenCode is a **free, open-source AI coding agent for the terminal**, built by the SST team and
community. Its core promise is **flexibility without lock-in**: it runs with 75+ LLM providers
(Anthropic, OpenAI, Google, local Ollama models, and more), while providing a native, themeable
TUI with LSP integration, multiple parallel sessions, and shareable session links. If you want a
Claude Code–style workflow but with your own models — or full source availability — OpenCode is
the reference option.

### Key features

| Feature | What it means in practice |
|---|---|
| Any provider | 75+ LLM providers, or a curated set via OpenCode Zen; log in with Claude Pro/Max too |
| Native TUI | Fast, themeable terminal UI — plus a headless server mode for automation |
| LSP-aware | Automatically loads the right language servers for better navigation and edits |
| `AGENTS.md` first-class | `/init` analyzes your repo and writes an `AGENTS.md` you commit to git |
| Plan ⇄ Build modes | Switch between planning a change and executing it with one keystroke |
| Multi-session | Run several agents in parallel on the same project |
| Share links | Share a session link so teammates can review what the agent did |
| MCP support | Extend with tools: browsers, databases, internal APIs |

### Installation

```bash
# Recommended one-liner (macOS / Linux)
curl -fsSL https://opencode.ai/install | bash

# or via npm
npm install -g opencode-ai

# or via Homebrew
brew install sst/tap/opencode
```

Then authenticate with at least one provider:

```bash
opencode auth login    # pick a provider and paste your API key
```

### Your first session

```bash
cd your-project
opencode
# inside the TUI:
/connect          # attach to a project/provider if needed
/init             # analyze the repo → generates AGENTS.md — commit it to git!
# Tab             # switch Plan ⇄ Build modes
/share            # optional: create a shareable session link
```

**Habits that make OpenCode dramatically better:**

1. **Commit `AGENTS.md`.** It is OpenCode's memory: structure, conventions, commands. Regenerate
   it with `/init` after big refactors, then hand-tune it.
2. **Plan before you build.** Describe the feature in Plan mode, confirm the approach, then
   flip to Build mode and let it implement.
3. **Use parallel sessions for independent tasks** — e.g., one agent writing code, another
   writing tests — but avoid two agents editing the same files.
4. **Pick the model per task.** Strong models for architecture and tricky bugs; fast/cheap
   models for mechanical edits. Switch with the model selector in the TUI.
5. **Prefer OpenCode Zen models** if you don't want to evaluate providers yourself — they are
   tested with the agent's tool calling.

### Tips & notes

- OpenCode is **client/server**: the TUI is a frontend, which enables remote and scripted usage.
- `AGENTS.md` is an open standard shared by several agents — one file benefits both OpenCode and
  other AGENTS.md-compatible tools.
- Works best in a real git repository: the agent can inspect diffs, history, and branches to
  understand your intent.

---

## Part 2 — العربية

<div dir="rtl">

### ما هو؟

OpenCode وكيل برمجة ذكي **مجاني ومفتوح المصدر** يعمل من الطرفية، تطوّره فريق SST والمجتمع.
وعدده الأساسي هو **المرونة دون حبس**: يعمل مع أكثر من 75 مزوّد نماذج لغوية (Anthropic و OpenAI
و Google ونماذج Ollama المحلية وغيرها)، مع واجهة طرفية أصلية قابلة للتخصيص تدعم LSP وجلسات
متوازية متعددة وروابط مشاركة للجلسات. إذا أردت تجربة شبيهة بـ Claude Code لكن بنماذجك الخاصة
ومصدر مفتوح كامل، فـ OpenCode هو الخيار المرجعي.

### أبرز المزايا

| الميزة | المعنى عملياً |
|---|---|
| أي مزوّد نماذج | أكثر من 75 مزوّداً، أو مجموعة مختارة عبر OpenCode Zen، كما يدعم دخول Claude Pro/Max |
| واجهة طرفية أصلية | واجهة سريعة قابلة للتخصيص، مع وضع خادم بلا واجهة للأتمتة |
| يدعم LSP | يحمّل خوادم اللغات المناسبة تلقائياً لملاحة وتعديلات أدق |
| `AGENTS.md` مواطن أول | أمر `/init` يحلل المشروع ويكتب ملف `AGENTS.md` تعتمده في Git |
| وضعا Plan ⇄ Build | بدّل بين تخطيط التغيير وتنفيذه بضغطة زر |
| جلسات متوازية | شغّل عدة وكلاء على نفس المشروع في الوقت نفسه |
| روابط المشاركة | شارك رابط الجلسة ليراجع زملاؤك ما فعله الوكيل |
| دعم MCP | وسّعه بأدوات: متصفحات، قواعد بيانات، واجهات داخلية |

### التثبيت

```bash
# السطر الواحد الموصى به (ماك / لينكس)
curl -fsSL https://opencode.ai/install | bash

# أو عبر npm
npm install -g opencode-ai

# أو عبر Homebrew
brew install sst/tap/opencode
```

ثم سجّل الدخول مع مزوّد واحد على الأقل:

```bash
opencode auth login    # اختر المزوّد والصق مفتاح API
```

### جلستك الأولى

```bash
cd your-project
opencode
# من داخل الواجهة:
/connect          # الاتصال بالمشروع/المزوّد عند الحاجة
/init             # تحليل المشروع ← يولّد AGENTS.md — اعتمده في Git!
# Tab             # التبديل بين وضعي Plan و Build
/share            # اختياري: رابط قابل للمشاركة للجلسة
```

**عادات تجعل OpenCode أفضل بكثير:**

1. **اعتمد `AGENTS.md` في Git.** هو ذاكرة OpenCode: البنية والمعايير والأوامر. أعد توليده بأمر
   `/init` بعد التعديلات الكبيرة ثم اضبطه يدوياً.
2. **خطط قبل التنفيذ.** صِف الميزة في وضع Plan، وافق على المقاربة، ثم انتقل إلى Build ليبدأ
   التنفيذ.
3. **استخدم الجلسات المتوازية للمهام المستقلة** — وكيل يكتب الكود وآخر يكتب الاختبارات — لكن
   تجنّب وكيلين يعدّلان نفس الملفات.
4. **اختر النموذج حسب المهمة.** نماذج قوية للمعمارية والمشاكل الصعبة، ونماذج سريعة/رخيصة
   للتعديلات الآلية.
5. **استخدم نماذج OpenCode Zen** إن لم ترغب بتقييم المزوّدين بنفسك — فهي مختبرة مع استدعاء
   الأدوات في الوكيل.

### ملاحظات مهمة

- OpenCode مبني بمعمارية **عميل/خادم**: الواجهة الطرفية مجرد طبقة أمامية، ما يتيح الاستخدام
  عن بُعد والبرمجي.
- ملف `AGENTS.md` معيار مفتوح تشاركه عدة وكلاء — ملف واحد يفيد OpenCode وغيره من الأدوات
  المتوافقة.
- يعمل بأفضل شكل داخل مستودع Git حقيقي: يستطيع الوكيل فحص الفروقات والسجل والفروع لفهم نيتك.

</div>

---

*Know something missing or outdated? [Open an issue or PR](../../CONTRIBUTING.md) — bilingual fixes are especially welcome.*
