# 📝 Instruction Files: CLAUDE.md & AGENTS.md | ملفات التعليمات

> The highest-leverage files in agentic coding: how to teach an agent about *your* project once
> — and benefit forever.
>
> الملفات الأعلى أثراً في البرمجة الوكيلية: كيف تعلّم الوكيل عن مشروعك مرة واحدة — وتستفيد
> إلى الأبد.

---

## Part 1 — English

### Why instruction files matter

Every session, an agent starts nearly blank. Instruction files (`CLAUDE.md` for Claude Code,
`AGENTS.md` for OpenCode and other AGENTS.md-compatible agents) are loaded automatically at
session start. They replace hundreds of repeated explanations with one versioned document that
lives next to your code — reviewed in pull requests like any other code.

**A good instruction file typically doubles agent usefulness.** A bad one (bloated, vague,
contradictory) actively hurts. This guide shows the difference.

### What goes in — and what doesn't

| ✅ Include | ❌ Leave out |
|---|---|
| Stack & versions ("Python 3.12, FastAPI, SQLAlchemy 2.0") | Everything the agent can discover by reading the code |
| Build/test/lint commands ("`pytest -q`", "`npm run typecheck`") | Long tutorials and prose |
| Conventions ("uv for packages, no default exports") | Secrets, keys, tokens — never |
| Boundaries ("never edit `migrations/` by hand") | Duplicated info that belongs in docs |
| House rules ("commit messages follow Conventional Commits") | Contradictory rules gathered over time — prune them |

### Hierarchy: layered instructions

Instructions are layered, closest wins:

```text
~/CLAUDE.md            ← personal, all your projects (user-global)
repo/CLAUDE.md         ← project-wide, committed to git — the main one
repo/CLAUDE.local.md   ← personal, project-specific, gitignored
repo/subdir/CLAUDE.md  ← deeper paths override/add for that subtree
```

OpenCode and other agents use `AGENTS.md` with the same layering idea
(`~/AGENTS.md`, `repo/AGENTS.md`, `repo/subdir/AGENTS.md`).

### A battle-tested starter template

```markdown
# Project instructions

## Stack
- Python 3.12 · FastAPI · SQLAlchemy 2.0 (async) · Postgres 16
- Frontend: React 18 + TypeScript in `web/`

## Commands
- Tests: `pytest -q` (must pass before every commit)
- Lint: `ruff check . && npx tsc --noEmit`
- Run dev stack: `make dev`

## Conventions
- Package manager: uv (never pip directly)
- No default exports in `web/src`
- Errors: raise domain errors in `app/errors.py`, never bare `Exception`

## Boundaries
- Never edit `migrations/versions/` by hand — use `alembic revision --autogenerate`
- Never touch `.env` or anything under `infra/secrets/`

## Definition of done
- New/changed behavior has tests
- `make check` (tests + lint + types) passes
```

### Maintenance rules

1. **Treat it as code.** PRs that change behavior must update the instruction file in the same PR.
2. **When the agent repeats the same mistake twice, add a rule.** That's the file growing real experience.
3. **Prune monthly.** Rules that no longer apply make the rest look optional.
4. **Share `AGENTS.md`-style content between agents.** The [agents.md standard](https://agents.md) is
   tool-neutral; Claude Code reads `CLAUDE.md` — a one-line `CLAUDE.md` that says "Read AGENTS.md"
   or a symlink keeps both worlds in sync.

---

## Part 2 — العربية

<div dir="rtl">

### لماذا تهم ملفات التعليمات؟

يبدأ الوكيل كل جلسة شبه فارغ. ملفات التعليمات (`CLAUDE.md` لـ Claude Code، و`AGENTS.md` لـ
OpenCode وسائر الأدوات المتوافقة) تُحمَّل تلقائياً عند بدء الجلسة. وتستبدل مئات الشروحات
المتكررة بوثيقة واحدة معتمدة في الإصدارات تعيش بجانب الكود — وتُراجع في طلبات الدمج كأي كود.

**ملف التعليمات الجيد يضاعف فائدة الوكيل عادةً.** والسيئ (المتضخم، الغامض، المتناقض) يضر
فعلياً. هذا الدليل يوضح الفرق.

### ما يدخل — وما لا يدخل

| ✅ أدخل | ❌ اتركه |
|---|---|
| التقنيات والإصدارات («بايثون 3.12، FastAPI، SQLAlchemy 2.0») | كل ما يستطيع الوكيل اكتشافه بقراءة الكود |
| أوامر البناء/الاختبار/الفحص («`pytest -q`»، «`npm run typecheck`») | الشروحات الطويلة والنثر |
| المعايير («uv لإدارة الحزم، ممنوع default exports») | الأسرار والمفاتيح والرموز — أبداً |
| الحدود («لا تعدّل `migrations/` يدوياً») | معلومات مكررة مكانها الوثائق |
| قواعد الفريق («رسائل الاعتماد تتبع Conventional Commits») | القواعد المتناقضة المتراكمة — نقّحها |

### التسلسل الهرمي: تعليمات طبقية

التعليمات طبقية، والأقرب يفوز:

```text
~/CLAUDE.md            ← شخصي، لكل مشاريعك (عام للمستخدم)
repo/CLAUDE.md         ← عام للمشروع، معتمد في Git — الأهم
repo/CLAUDE.local.md   ← شخصي خاص بالمشروع، مستثنى من Git
repo/subdir/CLAUDE.md  ← المسارات الأعمق تلغي/تضيف لذلك الفرع
```

ويستخدم OpenCode وسائر الوكلاء `AGENTS.md` بالفكرة الطبقية نفسها
(`~/AGENTS.md`، `repo/AGENTS.md`، `repo/subdir/AGENTS.md`).

### قالب بداية مُجرَّب

```markdown
# تعليمات المشروع

## التقنيات
- بايثون 3.12 · FastAPI · SQLAlchemy 2.0 (async) · Postgres 16
- الواجهة: React 18 + TypeScript في `web/`

## الأوامر
- الاختبارات: `pytest -q` (يجب نجاحها قبل كل اعتماد)
- الفحص: `ruff check . && npx tsc --noEmit`
- تشغيل بيئة التطوير: `make dev`

## المعايير
- مدير الحزم: uv (لا تستخدم pip مباشرة أبداً)
- ممنوع default exports في `web/src`
- الأخطاء: ارفع أخطاء النطاق من `app/errors.py`، وممنوع `Exception` المجردة

## الحدود
- لا تعدّل `migrations/versions/` يدوياً — استخدم `alembic revision --autogenerate`
- لا تلمس `.env` أو أي شيء تحت `infra/secrets/`

## معيار الإنجاز
- كل سلوك جديد/معدّل له اختبارات
- ينجح `make check` (اختبارات + فحص + أنواع)
```

### قواعد الصيانة

1. **عامل الملف ككود.** طلبات الدمج التي تغيّر السلوك يجب أن تُحدّث ملف التعليمات في نفس الطلب.
2. **عندما يكرر الوكيل الخطأ نفسه مرتين، أضف قاعدة.** هكذا ينمو الملف بخبرة حقيقية.
3. **نقّح شهرياً.** القواعد التي لم تعد تنطبق تجعل الباقي يبدو اختيارياً.
4. **شارك محتوى `AGENTS.md` بين الوكلاء.** معيار [agents.md](https://agents.md) محايد تجاه
   الأدوات؛ و Claude Code يقرأ `CLAUDE.md` — سطر واحد فيه "Read AGENTS.md" أو رابط رمزي يبقي
   العالمين متزامنين.

</div>
