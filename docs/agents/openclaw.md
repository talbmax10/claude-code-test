# 🦞 OpenClaw — Complete Guide | الدليل الشامل

> Your own personal AI assistant, running on your own devices, answering on the messaging
> channels you already use — WhatsApp, Telegram, Discord, Slack, iMessage, and many more.
>
> مساعدك الذكي الشخصي الذي يعمل على أجهزتك الخاصة ويجيبك عبر قنوات التراسل التي تستخدمها
> أصلاً — واتساب وتيليجرام وديسكورد وسلاك و iMessage وغيرها كثير.

**Official links | الروابط الرسمية:** [GitHub](https://github.com/openclaw/openclaw) · [Docs](https://docs.openclaw.ai)

> ℹ️ Fun fact: OpenClaw began life in late 2025 as "Clawdbot", was briefly renamed "Moltbot",
> and settled on **OpenClaw** in early 2026 — same lobster 🦞, new shell.

---

## Part 1 — English

### What is it?

OpenClaw is a **free, open-source personal AI assistant** you self-host on your own hardware
(Mac, Linux box, or VPS — Windows via WSL2). Unlike coding agents that live in your terminal,
OpenClaw is a **gateway**: a long-running daemon that connects your favorite LLM to the
messaging apps you already use, so you can message your assistant the way you message a friend.
It can answer questions, run scheduled jobs, control tools and skills, draft replies, and more —
under your control, on your infrastructure, with your API keys.

### Key features

| Feature | What it means in practice |
|---|---|
| Your channels | WhatsApp, Telegram, Discord, Slack, Signal, iMessage (BlueBubbles), IRC, Matrix, Teams, LINE, and more |
| Self-hosted gateway | A daemon (`openclaw gateway`) you own — your data stays on your machine |
| Multi-provider | Bring your preferred model/provider via API keys |
| Skills system | Extend behavior with community skills or your own |
| Scheduled & proactive | Cron-style jobs, reminders, and watches — not just reactive chat |
| Voice & Canvas | Speak/listen on supported apps; render live canvases |
| Control plane CLI | `openclaw` CLI to onboard, monitor, message, and doctor your install |

### Installation

```bash
# Requires Node.js 22.16+ or 24 (macOS, Linux, or Windows via WSL2)
npm install -g openclaw@latest
# or: pnpm add -g openclaw@latest

# Guided setup: configures gateway, workspace, channels, and skills
openclaw onboard --install-daemon

# Run the gateway (the daemon usually handles this after onboarding)
openclaw gateway --port 18789 --verbose
```

### Your first session

```bash
# Talk to your assistant from the CLI
openclaw agent --message "What can you do for me?" --thinking high

# Send a message to a connected channel
openclaw message send --to +1234567890 --message "Hello from my own assistant"
```

After onboarding, pair your messaging app (e.g., scan the WhatsApp/Telegram link from the
onboard flow) and simply **message your assistant like a contact**.

**Habits that make OpenClaw dramatically better:**

1. **Start narrow.** Connect *one* channel and one provider first. Add more only after you
   trust the setup.
2. **Write a workspace personality/instructions file.** Like `CLAUDE.md` for coding agents —
   tell your assistant who it is, what it may do, and what's off-limits.
3. **Use `openclaw doctor`** when anything misbehaves; it diagnoses the most common gateway
   and channel issues.
4. **Update regularly and deliberately** (`npm i -g openclaw@latest`), then re-run `doctor`.
   The project moves fast.
5. **Mind the security section below** — a messaging-connected agent is powerful; treat access
   like you'd treat access to your shell.

### Security notes (read this!)

- The assistant can execute tools with your credentials. **Only connect channels and skills you
  actually use**, and keep pairing restricted to your own accounts.
- Prefer running the gateway on a dedicated user/machine or container; don't expose the gateway
  port to the internet.
- Review the official docs' security guidance before enabling tool-heavy skills on public
  channels.

---

## Part 2 — العربية

<div dir="rtl">

### ما هو؟

OpenClaw مساعد ذكي شخصي **مجاني ومفتوح المصدر** تستضيفه بنفسك على أجهزتك (ماك أو خادم لينكس أو
VPS — وويندوز عبر WSL2). وعلى خلاف وكلاء البرمجة الذين يعيشون في الطرفية، OpenClaw هو
**بوابة (Gateway)**: خدمة خلفية دائمة تربط نموذجك المفضل بتطبيقات التراسل التي تستخدمها أصلاً،
فتحاور مساعدك كما تحاور صديقاً. يستطيع الإجابة عن الأسئلة، وتشغيل مهام مجدولة، والتحكم بالأدوات
والمهارات، وصياغة الردود، وغيرها — تحت سيطرتك، على بنيتك التحتية، وبمفاتيحك الخاصة.

حقيقة طريفة: بدأ المشروع أواخر 2025 باسم "Clawdbot" ثم عُرف باسم "Moltbot" لفترة وجيزة، قبل أن
يستقر على اسم **OpenClaw** مطلع 2026 — نفس السلطعون 🦞 بصدفة جديدة.

### أبرز المزايا

| الميزة | المعنى عملياً |
|---|---|
| قنواتك التي تستخدمها | واتساب، تيليجرام، ديسكورد، سلاك، سيجنال، iMessage، IRC، Matrix، Teams، LINE وغيرها |
| بوابة تستضيفها بنفسك | خدمة دائمة تملكها — بياناتك تبقى على جهازك |
| دعم عدة مزوّدين | استخدم نموذجك ومزوّدك المفضل عبر مفاتيح API |
| نظام المهارات | وسّع سلوكه بمهارات المجتمع أو بمهارات تكتبها بنفسك |
| مجدول واستباقي | مهام دورية وتذكيرات ومراقبة — وليس مجرد محادثة تفاعلية |
| صوت و Canvas | تحدث واستمع في التطبيقات الداعمة، واعرض لوحات حية |
| واجهة أوامر | أمر `openclaw` للتهيئة والمراقبة والمراسلة والتشخيص |

### التثبيت

```bash
# يتطلب Node.js 22.16+ أو 24 (ماك، لينكس، أو ويندوز عبر WSL2)
npm install -g openclaw@latest

# الإعداد الموجّه: يضبط البوابة ومساحة العمل والقنوات والمهارات
openclaw onboard --install-daemon

# تشغيل البوابة (الخدمة الدائمة تتولى ذلك عادةً بعد التهيئة)
openclaw gateway --port 18789 --verbose
```

### أول استخدام

```bash
# تحدث مع مساعدك من الطرفية
openclaw agent --message "ما الذي تستطيع فعله لي؟" --thinking high

# أرسل رسالة إلى قناة متصلة
openclaw message send --to +1234567890 --message "مرحباً من مساعدي الشخصي"
```

بعد التهيئة، اربط تطبيق التراسل (بالمسح الضوئي لواتساب/تيليجرام مثلاً من خطوات `onboard`)، ثم
**راسل مساعدك كما تراسل أي جهة اتصال**.

**عادات تجعل OpenClaw أفضل بكثير:**

1. **ابدأ بضيق النطاق.** اربط قناة واحدة ومزوّداً واحداً أولاً، ولا تضف المزيد إلا بعد أن تثق
   بالإعداد.
2. **اكتب ملف شخصية/تعليمات لمساحة العمل.** مثل `CLAUDE.md` في وكلاء البرمجة: عرّف هوية
   المساعد، وما يجوز له، وما هو ممنوع.
3. **استخدم `openclaw doctor`** عند أي خلل؛ فهو يشخّص أكثر مشاكل البوابة والقنوات شيوعاً.
4. **حدّث بانتظام وبعناية** (`npm i -g openclaw@latest`) ثم أعد تشغيل `doctor` — فالمشروع
   سريع التطور.
5. **التزم بالقسم الأمني أدناه** — الوكيل المتصل بقنوات التراسل قوي جداً؛ تعامل مع وصوله كما
   تتعامل مع الوصول إلى طرفيتك.

### ملاحظات أمنية (اقرأها!)

- المساعد ينفّذ أدوات بمعلومات اعتمادك. **اربط القنوات والمهارات التي تحتاجها فعلاً فقط**،
  وأبقِ الاقتران محصوراً بحساباتك أنت.
- فضّل تشغيل البوابة تحت مستخدم/جهاز مخصص أو داخل حاوية، ولا تفضّح منفذ البوابة للإنترنت.
- راجع الإرشادات الأمنية في الوثائق الرسمية قبل تمكين مهارات كثيرة الأدوات على قنوات عامة.

</div>

---

*Know something missing or outdated? [Open an issue or PR](../../CONTRIBUTING.md) — bilingual fixes are especially welcome.*
