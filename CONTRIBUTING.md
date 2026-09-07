# Contributing to AI Agents Hub | المساهمة في مركز وكلاء الذكاء الاصطناعي

<div align="center">

**English** below · **العربية** in the [second half](#-المساهمة-في-مركز-وكلاء-الذكاء-الاصطناعي)

</div>

## 🇬🇧 English

Thank you for improving this hub! It's a documentation-only repository: guides, tips, and
examples that help developers, users, and AI agents work with Claude Code, OpenCode, OpenClaw,
and Hermes Agent.

### How to contribute

1. **Open an issue first** for big additions (new agent guide, new section) so we can align
   before you write.
2. Fork / branch, make your change, and open a pull request with a clear description of
   *what changed and why*.
3. Small fixes (typos, broken links, outdated commands) can go straight to a PR.

### Style rules (please follow)

1. **Bilingual by default.** Every document has an English part and an Arabic part (`<div dir="rtl">`).
   If you can write one of the two well but not the other, note it in the PR — a bilingual
   maintainer or contributor will help.
2. **Verify every command.** The agent ecosystem changes weekly. Test install commands and
   flags against the project's current official docs, and link the official source in the guide.
3. **Structure agent guides consistently:**
   `What is it? → Key features table → Installation → First session → Habits/tips → (Security) → Resources`.
4. **Neutral tone.** This hub is community-run and independent. No marketing language; measured,
   practical claims only.
5. **No secrets, no unsafe commands.** Never include commands that disable safety features,
   pipe credentials, or auto-approve destructive actions.
6. **Relative links** between documents so everything works on GitHub and in offline clones.
7. **Arabic quality bar:** natural, professional Modern Standard Arabic (فصحى تقنية واضحة) —
   not literal translation. Technical terms may stay in English when that's what developers use.

### Adding a new agent or tool

- Create `docs/agents/<name>.md` following the existing structure.
- Add rows to the tables in `README.md` (both the English and Arabic sections).
- Add the agent to the comparison table if relevant.
- Mention in the PR that you verified the install commands as of a specific date.

### Commit & PR conventions

- Commit messages: short imperative summary (`docs: add security checklist to openclaw guide`).
- One topic per PR.
- AI-assisted contributions are welcome — but **you** are responsible for verifying accuracy.

### Code of conduct

Be kind, be precise, assume good faith. We're building a resource for everyone, in two languages.

---

## 🇸🇦 العربية

<div dir="rtl">

شكراً لتحسينك هذا المركز! هذا المستودع وثائقي بحت: أدلة ونصائح وأمثلة تساعد المطورين والمستخدمين
والوكلاء الذكيين على العمل مع Claude Code و OpenCode و OpenClaw و Hermes Agent.

### كيف تساهم؟

1. **افتح تذكرة أولاً** للإضافات الكبيرة (دليل وكيل جديد، قسم جديد) لنتفق قبل أن تكتب.
2. اشتق فرعاً (fork/branch)، أجرِ تغييرك، وافتح طلب دمج بوصف واضح لـ *ماذا تغيّر ولماذا*.
3. الإصلاحات الصغيرة (أخطاء مطبعية، روابط معطوبة، أوامر قديمة) تذهب مباشرة كطلب دمج.

### قواعد الأسلوب (نرجو الالتزام بها)

1. **ثنائي اللغة افتراضياً.** كل مستند له جزء إنجليزي وجزء عربي (`<div dir="rtl">`). إن أتمت
   كتابة إحدى اللغتين جيداً دون الأخرى فاذكر ذلك في الطلب — سيساعدك أحد المساهمين ثنائيي اللغة.
2. **تحقق من كل أمر.** منظومة الوكلاء تتغير أسبوعياً. اختبر أوامر التثبيت والخيارات مقابل
   الوثائق الرسمية الحالية، واربط المصدر الرسمي داخل الدليل.
3. **بنية موحدة لأدلة الوكلاء:**
   «ما هو؟ ← جدول المزايا ← التثبيت ← الجلسة الأولى ← العادات والنصائح ← (الأمان) ← المصادر».
4. **نبرة محايدة.** المركز مجتمعي ومستقل. بلا لغة تسويقية؛ ادعاءات عملية متزنة فقط.
5. **لا أسرار ولا أوامر خطرة.** ممنوع إدراج أوامر تعطّل وسائل الأمان أو تمرّر معلومات الاعتماد
   أو توافق تلقائياً على إجراءات مدمرة.
6. **روابط نسبية** بين المستندات حتى يعمل كل شيء على GitHub وفي النسخ المحلية.
7. **معيار الجودة العربية:** فصحى تقنية واضحة وطبيعية — لا ترجمة حرفية. يجوز إبقاء المصطلحات
   التقنية بالإنجليزية إذا كان هذا هو الاستخدام الشائع لدى المطورين.

### إضافة وكيل أو أداة جديدة

- أنشئ `docs/agents/<name>.md` باتباع البنية الموجودة.
- أضف صفاً في جداول `README.md` (القسم الإنجليزي والعربي معاً).
- أضف الوكيل إلى جدول المقارنة إن كان ذلك مناسباً.
- اذكر في طلب الدمج أنك تحققت من أوامر التثبيت بتاريخ محدد.

### قواعد الاعتماد وطلبات الدمج

- رسائل الاعتماد: ملخص قصير بصيغة الأمرية (`docs: إضافة قائمة تحقق أمنية لدليل openclaw`).
- موضوع واحد لكل طلب دمج.
- المساهمات المدعومة بالذكاء الاصطناعي مرحب بها — لكن **أنت** المسؤول عن التحقق من الدقة.

### ميثاق السلوك

كن لطيفاً، وكن دقيقاً، وافترض حسن النية. نبني مورداً للجميع، بلغتين.

</div>
