# Career Asset Report Template — Three-File Output

Generate THREE files with clean language separation. The `-data` file is the single source of truth
for downstream AI processing (CV generation, keyword search, market exploration).

---

## File 1: `career-asset-{name}-data-{date}.md` — AI-Readable Data

Purpose: Structured asset data for downstream AI consumption. English fields, machine-parseable.

```markdown
# Career Asset Data — {Name}
**Generated**: {YYYY-MM-DD}
**Version**: 1.0

---

## Asset Inventory

Each asset is a structured record with traceability.

| id | asset_en | asset_zh | category | evidence | confidence | metrics |
|----|----------|----------|----------|----------|------------|---------|
| A01 | {English description} | {中文描述} | {category} | "User said: ..." | high/medium/low | {key metrics} |

**Categories:** professional_experience | project_delivery | hidden_asset | cross_domain_combo | credential | network | education

---

## Skills-to-Keywords Mapping

| cluster_id | cluster_name | en_keywords | zh_keywords |
|------------|-------------|-------------|-------------|
| K01 | {cluster} | kw1, kw2, kw3... | 关键词1, 关键词2... |

---

## Information Gaps

| gap_id | asset_ref | what_missing | why_important | how_to_fill |
|--------|-----------|-------------|---------------|-------------|
| G01 | A05 | {description} | {HR reason} | {suggested action} |

---

## Constraints

| field | value |
|-------|-------|
| location | {city/country, remote/hybrid/onsite} |
| salary_floor | {amount} {currency}/month |
| salary_target | {amount} {currency}/month |
| visa | {status} |
| avoid | {industries or roles to exclude} |

---

## CV Generation Base

### professional_summary_en
{3-4 lines, keyword-dense, quantified. No banned words.}

### work_experience
[{role, company, dates, bullets[]}]

### competencies
[phrase1, phrase2, ...] (6-8 keyword phrases)

### projects
[{name, description, metrics, url_if_any}]

### education
[{degree, school, year, notes}]

### certifications
[{name, status}]

### skills
{grouped by category}

### languages
[{language, level}]

---

## Market Exploration (appended after Phase 8)

### {cluster_name}
- signal_strength: strong/moderate/exploratory
- snapshot_date: {YYYY-MM-DD}
- roles_found: [{title, source}]
- common_skills: [skill1, skill2]
- suggested_search_keywords_en: [kw1, kw2]
- suggested_search_keywords_zh: [关键词1, 关键词2]
```

---

## File 2: `career-asset-{name}-zh-{date}.md` — Human-Readable (Chinese)

Purpose: Clean Chinese output for the user's own reading and sharing.
No English mixed in. No machine-oriented fields.

```markdown
# 🧭 职业资产报告 — {姓名}
**生成日期**：{YYYY-MM-DD}

---

## 个人画像

{段落形式，个性化总结。包含：当前职业阶段、核心优势、超能力、关键约束。}

---

## 资产清单

### 专业经历

| # | 资产 | 证据来源 | 完整度 |
|---|------|---------|--------|
| 1 | {中文描述} | 用户原话："..." | 完整 / 待补充 |

### 隐藏资产（副业/项目/跨界）

| # | 资产 | 证据来源 | 完整度 |
|---|------|---------|--------|
| 11 | {中文描述} | 用户原话："..." | 完整 / 待补充 |

### 跨界组合
{从 Area 2 交叉领域追问中挖掘出的罕见能力组合}

### 证书与资质

### 其他资源（人脉/平台/区域优势）

---

## 搜索关键词

| 能力方向 | 建议搜索关键词 |
|---------|---------------|
| {方向名称} | 关键词1、关键词2、关键词3... |

---

## 信息缺口

| # | 缺失项 | 为什么重要 | 如何补充 |
|---|--------|-----------|---------|
| 1 | {缺少什么} | {HR为什么想看} | {建议怎么补} |

---

## 市场方向灵感

{Phase 8 WebSearch 结果的中文版本，附加在最后}

⚠️ 搜索快照于 {YYYY-MM-DD}。市场变化快，输入"刷新"可重新搜索。
```

---

## File 3: `career-asset-{name}-en-{date}.md` — Human-Readable (English)

Purpose: Clean English output. CV-ready sections. No Chinese mixed in.

```markdown
# Career Asset Report — {Name}
**Generated**: {YYYY-MM-DD}

---

## Professional Summary

{3-4 lines. Keyword-dense, quantified, no banned words, no cliché phrases.
Optimized for 6-second recruiter scan — strongest claim first.}

---

## Work Experience

### {Company} — {Title}
*{Dates} | {Location}*

- {Bullet 1 — strongest quantified achievement}
- {Bullet 2}
- {Bullet 3}
- {Bullet 4}
- {Bullet 5}

{Repeat for each role. Bullets follow HR rules: quantified, specific, varied openers.}

---

## Key Competencies

{6-8 keyword phrases in flex format, e.g.:}
Project Delivery (50+ projects, 5M+ RMB scale) · AI Workflow Automation · etc.

---

## Projects & Side Ventures

### {Project Name}
- {Description with metrics}
- {Tool/technology used}

---

## Education

| Degree | Institution | Year |
|--------|-------------|------|

---

## Certifications

- {Name} ({status})

---

## Skills

**{Category}:** skill1, skill2, skill3...
**{Category}:** skill1, skill2...

---

## Languages

- {Language} ({level})

---

## Market Direction Inspiration

{Phase 8 WebSearch results, English version, appended at end.
One subsection per direction with: why it fits, typical roles, suggested keywords, signal strength.}

⚠️ Search snapshot from {YYYY-MM-DD}. Market changes. Input "refresh" to re-search.
```

---

## Generation Rules (apply to ALL three files)

1. **No language mixing** — `-zh` never contains English, `-en` never contains Chinese, `-data` uses English fields only
2. **Every claim traceable** — each asset must reference exact user words
3. **No invented metrics** — `[NEEDS METRIC]` where quantification is genuinely unknown
4. **No banned words** — check English banned phrases AND Chinese banned phrases per `hr-quality-rules.md`
5. **Specificity over abstraction** — name tools, numbers, clients, timeframes
6. **Vary sentence openers** — no two consecutive bullets start with the same verb in `-en` file
7. **Gaps are honest** — missing information is not a failure, it's a next step
