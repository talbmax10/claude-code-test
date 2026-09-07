# 🔌 MCP: Model Context Protocol | بروتوكول سياق النموذج

> One open protocol that lets any agent use any tool: databases, browsers, GitHub, Figma,
> internal APIs — without writing custom integrations.
>
> بروتوكول مفتوح واحد يمكّن أي وكيل من استخدام أي أداة: قواعد بيانات، متصفحات، GitHub، Figma،
> واجهات داخلية — دون كتابة تكاملات مخصصة.

---

## Part 1 — English

### What is MCP?

The **Model Context Protocol** is an open standard (originated by Anthropic, now
multi-vendor) for connecting AI applications to external tools and data sources. An **MCP
server** exposes *tools*, *resources*, and *prompts* over a standard interface; an **MCP
client** (Claude Code, OpenCode, Hermes, and many others) discovers and calls them.

**Mental model:** MCP servers are to agents what USB is to computers — a standard port for
capabilities. One PostgreSQL MCP server works with every MCP-capable agent you use.

### When MCP is the right tool

✅ **Use MCP when:**
- The capability already exists as a maintained server (GitHub, Postgres, Slack, Playwright, file systems…)
- You want the same toolset across multiple agents
- The data source is outside the project directory

❌ **Skip MCP when:**
- A plain shell command or script would do (don't add a server for `git log`)
- The logic is project-specific — a skill or instruction-file rule is simpler
- You can't review what the server can access

### Client cheat-sheet: adding a server

**Claude Code** (CLI-first, project or user scope):

```bash
claude mcp add playwright -- npx -y @playwright/mcp@latest
claude mcp list                     # verify
# scopes: --scope local (default) | project (.mcp.json in repo) | user
```

**OpenCode** (`opencode.json` in the repo):

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "playwright": {
      "type": "local",
      "command": ["npx", "-y", "@playwright/mcp@latest"]
    }
  }
}
```

**Hermes** (built-in management, incl. OAuth 2.1 for remote servers):

```bash
hermes mcp          # interactive install/configure
hermes tools        # inspect exposed toolsets
```

**OpenClaw:** MCP servers are supported via its tool/plugin configuration in the workspace —
see the official docs for the current syntax.

### Servers worth knowing

| Server | Gives your agent… |
|---|---|
| `@playwright/mcp` | A real browser: navigate, click, screenshot, scrape |
| GitHub / GitLab MCP | Issues, PRs, reviews, releases |
| Postgres / SQLite MCP | Read (and optionally write) schema-aware queries |
| Filesystem MCP | Controlled access to directories outside the project |
| Slack / Discord MCP | Send and read messages |
| Fetch / Search MCP | Live web access |

### Debugging & tips

1. **Start with one server.** Each server adds tools that consume context window and can confuse routing.
2. **Prefer read-only modes** while evaluating (`--read-only` flags or read-only DB users).
3. **If a tool misfires**, ask the agent "list your available MCP tools" — then compare with `mcp list`.
4. **Remote servers** need auth: prefer OAuth-capable servers over long-lived API keys pasted in config.
5. **Stdio vs HTTP:** stdio servers run locally as subprocesses (simple, private); HTTP servers
   run remotely (shareable, need auth). Choose deliberately.

---

## Part 2 — العربية

<div dir="rtl">

### ما هو MCP؟

**بروتوكول سياق النموذج (Model Context Protocol)** معيار مفتوح (بدأه Anthropic وأصبح متعدد
الشركات) لربط تطبيقات الذكاء الاصطناعي بالأدوات ومصادر البيانات الخارجية. يعرض **خادم MCP**
«أدوات» و«موارد» و«أوامر» عبر واجهة قياسية؛ بينما **عميل MCP** (مثل Claude Code و OpenCode و
Hermes وغيرهم كثير) يكتشفها ويستدعيها.

**النموذج الذهني:** خوادم MCP بالنسبة للوكلاء كالـ USB بالنسبة للحاسوب — منفذ قياسي للقدرات.
خادم PostgreSQL واحد يعمل مع كل وكيل يدعم MCP.

### متى يكون MCP هو الأداة الصحيحة؟

✅ **استخدمه عندما:**
- تكون القدرة متوفرة أصلاً كخادم مصان (GitHub، Postgres، Slack، Playwright، أنظمة الملفات…)
- تريد نفس مجموعة الأدوات عبر عدة وكلاء
- يكون مصدر البيانات خارج مجلد المشروع

❌ **تجاوزه عندما:**
- يكفي أمر طرفية أو سكربت عادي (لا تضف خادماً لأجل `git log`)
- تكون المنطق خاصاً بالمشروع — مهارة أو قاعدة في ملف التعليمات أبسط
- تعذّر مراجعة ما يستطيع الخادم الوصول إليه

### ورقة الغش للعملاء: إضافة خادم

**Claude Code** (من سطر الأوامر، بنطاق مشروع أو مستخدم):

```bash
claude mcp add playwright -- npx -y @playwright/mcp@latest
claude mcp list                     # تحقق
# النطاقات: --scope local (افتراضي) | project (ملف .mcp.json في المستودع) | user
```

**OpenCode** (ملف `opencode.json` في المستودع):

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "playwright": {
      "type": "local",
      "command": ["npx", "-y", "@playwright/mcp@latest"]
    }
  }
}
```

**Hermes** (إدارة مدمجة، تشمل OAuth 2.1 للخوادم البعيدة):

```bash
hermes mcp          # تثبيت وضبط تفاعلي
hermes tools        # فحص مجموعات الأدوات المكشوفة
```

**OpenClaw:** يدعم خوادم MCP عبر إعداد الأدوات/الإضافات في مساحة العمل — راجع الوثائق الرسمية
للصيغة الحالية.

### خوادم تستحق المعرفة

| الخادم | يمنح وكيلك… |
|---|---|
| `@playwright/mcp` | متصفحاً حقيقياً: تنقل، نقر، لقطات شاشة، كشط بيانات |
| GitHub / GitLab MCP | التذاكر وطلبات الدمج والمراجعات والإصدارات |
| Postgres / SQLite MCP | استعلامات واعية بالمخطط (قراءة واختيارياً كتابة) |
| Filesystem MCP | وصولاً متحكماً به إلى مجلدات خارج المشروع |
| Slack / Discord MCP | إرسال الرسائل وقراءتها |
| Fetch / Search MCP | وصولاً حياً للويب |

### التنقيح والنصائح

1. **ابدأ بخادم واحد.** كل خادم يضيف أدوات تستهلك نافذة السياق وقد تربك توجيه الاختيار.
2. **فضّل أوضاع القراءة فقط** أثناء التقييم (`--read-only` أو مستخدمي قاعدة بيانات للقراءة فقط).
3. **إذا أخفقت أداة**، اسأل الوكيل "اذكر أدوات MCP المتاحة لك" — ثم قارن مع `mcp list`.
4. **الخوادم البعيدة** تحتاج مصادقة: فضّل الخوادم الداعمة لـ OAuth على مفاتيح API طويلة العمر
   الملصوقة في الإعدادات.
5. **Stdio مقابل HTTP:** خوادم stdio تعمل محلياً كعمليات فرعية (أبسط وأكثر خصوصية)؛ وخوادم
   HTTP تعمل عن بُعد (قابلة للمشاركة وتحتاج مصادقة). اختر بوعي.

</div>
