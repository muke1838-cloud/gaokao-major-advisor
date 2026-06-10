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
- Treat the major name as the minimum input, not the full decision context. Personalize the conclusion when province, score/rank, school tier, postgraduate tolerance, city preference, family pressure, or risk preference are available.
- If the input is not an official college major, do not force it into a normal report. Explain the mismatch, map it to credible official majors or career routes, and warn when it is unsuitable as a direct employment-oriented major bet.

## Input Contract

Required:
- Target major or intended study direction.

Useful optional fields:
- Province and score/rank band.
- Target school tier: 985, 211, Double First-Class, ordinary public undergraduate, private undergraduate, junior college, or uncertain.
- Undergraduate or junior-college route if known.
- Preferred city, region, or city tier.
- Family budget or pressure to earn income quickly.
- Willingness to pursue postgraduate study, standardized training, licenses, certificates, or long-term study.
- Interest areas and disliked work styles.
- Risk preference: stable, balanced, or high-upside.
- Whether the student accepts relocation, overtime, shifts, field work, or heavy social interaction.
- Family, city, or industry resources if the user volunteers them.

If only the major is provided, continue with a national/general report and explicitly label the assumptions. Do not block the analysis with repeated questions.

## Workflow

1. Clarify the input.
   - Use the input contract above.
   - If only a major is provided, continue with a national/general analysis and state the assumptions.

2. Normalize the major.
   - Identify the official major name, discipline category, similar majors, common misunderstandings, and typical core courses.
   - Split the major into hard skills, transferable skills, credential requirements, and likely postgraduate needs.
   - If it is a non-standard, folk, religious, hobby, job-title, or industry-direction input, first map it to official major choices and explain the limits.

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
   - Score the route across demand growth, policy support, technology impact, entry barrier, supply pressure, salary upside, stability, and major fit. Use `references/research-framework.md` for the scoring rubric.
   - State leading indicators the student should keep watching during college.

8. Give the decision recommendation.
   - Provide a concise verdict: `推荐`, `谨慎推荐`, `不优先推荐`, or `只适合特定学生`.
   - Explain who fits this major, who should avoid it, and what to do during college to preserve career options.
   - Adjust the verdict by likely school tier and city tier when the user provides province, score/rank, or target institutions.
   - Include alternatives: adjacent majors, double-major/minor choices, certifications, internships, competitions, or postgraduate directions.

## Output Shape

For every complete major analysis, create a standalone static HTML report by default. The chat response should only summarize the verdict briefly and provide the file path plus validation evidence.

Use Markdown only when:
- the user explicitly asks for a quick text answer,
- the user is brainstorming before requesting a full report,
- web/current-data access is unavailable and the user only wants a framework.

If web/current-data access is unavailable:
- Do not invent current salary, employer tiers, policies, or hiring demand.
- Produce a framework-only report or a clearly marked unverified draft.
- Mark all current-data claims as `待验证`, and tell the user which evidence must be refreshed.

When creating the report:

- Create one standalone static HTML file per major.
- Save it under `reports/YYYY-MM-DD_<major-slug>.html` in the user's current project unless the user provides another path.
- Use `references/web-report-guide.md` and `assets/web-report-template.html`.
- Keep all CSS and any tiny JavaScript inline so the file opens directly in a browser without a dev server.
- Do not put generated user reports inside the skill directory unless the user explicitly asks to edit examples or assets.

Use `references/report-template.md` only as the content outline behind the webpage. Keep Chinese output clear enough for parents and students to understand.

Minimum sections:

1. 结论先行
2. 用户画像与分析假设
3. 专业拆解
4. 行业和岗位匹配
5. 公司层级与薪资样本
6. 趋势、政策和科技影响
7. 四年后判断
8. 不同学校层次和城市层级下的结论变化
9. 适合/不适合人群
10. 大学四年行动建议
11. 信息来源与不确定性

## References

- `references/intake-template.md`: Use when asking the user for optional context or building a prompt for another agent.
- `references/research-framework.md`: Use for evidence gathering, company tiering, salary handling, trend scoring, and risk rules.
- `references/report-template.md`: Use for the final Chinese report structure.
- `references/web-report-guide.md`: Use when creating a standalone webpage report.
- `assets/web-report-template.html`: Copy and fill when the user wants an individual HTML report.

## Quality Bar

- Good analysis names uncertainty directly and gives a practical next step.
- Bad analysis overstates certainty, uses old salary data without dates, lists famous companies without explaining fit, or treats a hot industry as automatically good for every student.
- If evidence conflicts, show both sides and make a conservative call.
