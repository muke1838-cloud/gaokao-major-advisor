---
name: gaokao-major-advisor
description: Use when helping Gaokao students, parents, counselors, or education advisors evaluate a university major choice, map majors to industries and jobs, compare employer tiers and salary samples, or forecast four-year career potential for China college application decisions.
---

# Gaokao Major Advisor

## Overview

Help a Gaokao student evaluate whether a target major still leads to promising industries and jobs four years after enrollment. Treat the output as decision support, not a guarantee or one-size-fits-all recommendation.

## Core Rules

- Use fresh research for current industry, policy, company, and salary claims. If web access is unavailable, say the current-data part is unverified and provide only a framework.
- Cite sources with publish/access dates for policy, industry trend, company tiering, and salary evidence.
- Never fabricate company salary, hiring demand, or policy support. Mark unknowns as `待验证` or `公开信息不足`.
- Separate evidence from judgment: show what the sources say, then explain the inference.
- Avoid saying a major is simply "good" or "bad"; judge fit by student profile, entry barriers, risk, and four-year outlook.
- Use the current date to calculate the forecast year. If today is 2026, forecast the student's situation around 2030.

## Workflow

1. Clarify the input.
   - Required: target major.
   - Useful: province, score/rank band, preferred city, family budget, tolerance for postgraduate study, interests, disliked work styles, risk preference.
   - If only a major is provided, continue with a national/general analysis and state the assumptions.

2. Normalize the major.
   - Identify the official major name, discipline category, similar majors, common misunderstandings, and typical core courses.
   - Split the major into hard skills, transferable skills, credential requirements, and likely postgraduate needs.

3. Map to industries and jobs.
   - Group opportunities into `主航道`, `相邻航道`, and `备选航道`.
   - For each route, list representative job titles, required skills, entry thresholds, and whether the major is a strong or weak fit.
   - Keep only routes with a credible connection to the major.

4. Research the market.
   - Gather evidence for policy, technology, industry demand, company hiring, salary samples, and education/credential barriers.
   - Prefer primary or near-primary sources: government policy, official statistics, company career pages, public job postings, credible industry reports, listed-company disclosures, and major recruiting platforms.
   - Read `references/research-framework.md` for the detailed evidence checklist and scoring model.

5. Segment companies for each important job route.
   - List 3 representative `头部` companies, 3 `腰部` companies, and 3 `长尾/区域型` employers.
   - Define why each tier was chosen, using market share, brand, hiring volume, revenue, funding, product importance, or regional influence.
   - Do not label long-tail companies as inferior; explain tradeoffs such as salary ceiling, stability, learning density, and location.

6. Estimate salary and treatment.
   - Show salary as ranges, not single numbers.
   - Separate `应届/校招`, `1-3年`, and `3-5年` when possible.
   - Include city, role, company tier, sample source, sample date, and confidence level.
   - Explain non-salary factors: overtime, mobility, licensing, postgraduate premium, and cyclical layoffs.

7. Forecast four-year potential.
   - Classify each route as `上升`, `稳定`, `看人差距大`, or `下降`.
   - Consider AI/automation, industrial upgrading, government policy, capital spending, demographics, supply of graduates, and credential inflation.
   - State leading indicators the student should keep watching during college.

8. Give the decision recommendation.
   - Provide a concise verdict: `推荐`, `谨慎推荐`, `不优先推荐`, or `只适合特定学生`.
   - Explain who fits this major, who should avoid it, and what to do during college to preserve career options.
   - Include alternatives: adjacent majors, double-major/minor choices, certifications, internships, competitions, or postgraduate directions.

## Output Shape

Use `references/report-template.md` unless the user asks for a shorter answer. Keep Chinese output clear enough for parents and students to understand.

When the user asks for a webpage, HTML file, shareable report, printable report, or one report per major:

- Create one standalone static HTML file per major.
- Save it under `reports/YYYY-MM-DD_<major-slug>.html` in the user's current project unless the user provides another path.
- Use `references/web-report-guide.md` and `assets/web-report-template.html`.
- Keep all CSS and any tiny JavaScript inline so the file opens directly in a browser without a dev server.
- Do not put generated user reports inside the skill directory unless the user explicitly asks to edit examples or assets.

Minimum sections:

1. 结论先行
2. 专业拆解
3. 行业和岗位匹配
4. 公司层级与薪资样本
5. 趋势、政策和科技影响
6. 四年后判断
7. 适合/不适合人群
8. 大学四年行动建议
9. 信息来源与不确定性

## References

- `references/research-framework.md`: Use for evidence gathering, company tiering, salary handling, trend scoring, and risk rules.
- `references/report-template.md`: Use for the final Chinese report structure.
- `references/web-report-guide.md`: Use when creating a standalone webpage report.
- `assets/web-report-template.html`: Copy and fill when the user wants an individual HTML report.

## Quality Bar

- Good analysis names uncertainty directly and gives a practical next step.
- Bad analysis overstates certainty, uses old salary data without dates, lists famous companies without explaining fit, or treats a hot industry as automatically good for every student.
- If evidence conflicts, show both sides and make a conservative call.
