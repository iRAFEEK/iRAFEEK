# Rafeek Hanna

**`git log --author="Rafeek" --since="6 months ago"`** returns, roughly: a graph pass inside PyTorch's on-device runtime, a church management platform in Arabic, and a great deal of reading other people's code very carefully before touching it.

CS at Minerva University, San Francisco, class of 2029. Backend-leaning. Currently looking for a **Summer 2027 software engineering internship**.

📍 San Francisco · ✉️ rafeek.abdo@uni.minerva.edu · [LinkedIn](https://www.linkedin.com/in/rafeek-hanna-b89254363/)

---

## Things I've built

### ⛪ [Ekklesia](https://www.miaekklesia.com) — church management, Arabic-first
`Next.js 15` · `TypeScript` · `Supabase` · `PostgreSQL` · `Twilio` · `Resend`

Most churches I know run on three WhatsApp groups and a spreadsheet someone's cousin made in 2019. Visitors show up once and are never followed up with. Ekklesia replaces all of it: QR-powered visitor registration with an automatic follow-up pipeline, attendance tracking with at-risk alerts, small groups and prayer requests, volunteer scheduling, a song library with presenter mode, and a Bible reader — multi-tenant, Arabic-first and fully RTL, with a six-level role model from `super_admin` down to `member`.

Priced at cost. No margin, no tiers. **[It's live →](https://www.miaekklesia.com)**

**What I own:**
- Tenant isolation across ~94 PostgreSQL tables — row-level security policies plus active-membership checks, so no query can wander into another church's data
- Post-deployment verification for the live app: SSR rendering, cron authentication, and schema drift

*Co-built with a small team. The source is private — it holds real congregation data — but I'm happy to walk through the architecture, or grant repo access for a code review. Just ask.*

### 🧠 [decision-ledger](https://github.com/iRAFEEK/decision-ledger) — "wait, why did we decide that?"
`Python` · `FastAPI` · `PostgreSQL + pgvector` · `Redis/arq` · `Next.js` · `Docker`

Every engineering decision your team ever made is sitting in a Slack thread nobody can find. This watches Slack events and huddle transcripts, spots the decisions, and indexes them as embeddings so you can ask in plain English why something is the way it is. Ingestion runs on a worker queue behind the API, so a firehose of messages never blocks a read.

### 📄 [ats-analyzer](https://github.com/iRAFEEK/ats-analyzer) — the robot that reads your résumé, explained
`Next.js` · `FastAPI` · `spaCy` · `Sentence-Transformers` · `GPT-4`

Upload a PDF, DOCX, or a photo of a résumé and get coverage, experience, and education scores back — each one pointing at the exact span of text it came from, plus warnings about the formatting quirks that make ATS parsers choke.

### 📋 [Rafeek_SMMA](https://github.com/iRAFEEK/Rafeek_SMMA) — project management
`Flask` · `PostgreSQL` · `SQLAlchemy` — role-based access, Kanban boards, client dashboards.

---

## Things other people built that I've touched

| Project | What I contributed |
| --- | --- |
| [pytorch/executorch](https://github.com/pytorch/executorch/pull/21552) | `ReplaceSliceCopyWithSlicePass` — an EXIR graph pass that spots contiguous, unit-step `slice_copy` nodes able to alias the base buffer instead of copying it. On a phone or a wearable, that's a whole tensor copy removed from every single inference |
| [apache/airflow](https://github.com/apache/airflow/pull/70343) | An optional `static_url` on `BaseOperatorLink`. If a link is a constant, it no longer needs an XCom write and a metadata-DB read on every task run. Default behaviour unchanged, so nobody's DAG breaks |
| [pandas-dev/pandas](https://github.com/pandas-dev/pandas/pull/62650) | Linked 11 API-reference pages back to the user guides that explain them, closing #62357. Small diff, long review — worth every round of it |
| [wso2/identity-apps](https://github.com/wso2/identity-apps/pull/10382) | A 400 on the self-registration redirect, traced to a `claims` JSON parameter that was HTML-escaped but never URL-encoded. Nine characters of the fix, most of the work in reproducing it |

### Field notes

Longer write-ups — how I picked the issue, what the codebase actually looked like from the inside, and how the review went:

- [**Re-inplacing `slice_copy` in ExecuTorch**](https://github.com/iRAFEEK/su26-ai301-contribution4) — finding an aliasing case an existing pass already handled for `view_copy`
- [**Skipping XCom for constant operator links in Airflow**](https://github.com/iRAFEEK/su26-ai301-contribution3) — removing an abstract method without breaking every subclass that implements it
- [**Chasing a 400 through the WSO2 login flow**](https://github.com/iRAFEEK/su26-ai301-contribution) — reproducing the failure before writing a line of the fix

---

## Toolbox

**Languages** Python · TypeScript · JavaScript · SQL · Java (I read it; PRs pending)
**Backend** FastAPI · Flask · SQLAlchemy · Alembic · PostgreSQL · pgvector · Redis · Supabase
**Frontend** Next.js · React · Tailwind · Prisma
**Tooling** Docker · Git · GitHub Actions · pytest

---

## Currently

Contributing to Apache Airflow and PyTorch ExecuTorch · shipping Ekklesia · looking for a Summer 2027 internship.

If you maintain something I've sent a PR to and want a follow-up, open an issue on any repo here or just email me. I read everything.
