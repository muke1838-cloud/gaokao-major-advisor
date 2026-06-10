# Web Report Guide

Use this guide for every complete major analysis report. The default deliverable is a beautiful standalone webpage, not a long chat answer.

## Output Contract

- Create one standalone `.html` file per major.
- Default location: `reports/YYYY-MM-DD_<major-slug>.html` in the user's current project.
- Start from `assets/web-report-template.html`.
- Inline all CSS and small JavaScript. Do not require a dev server, CDN, image download, or build step.
- Keep the report readable for parents and students on mobile and desktop.
- Do not rely on horizontal table scrolling as the mobile experience; table rows must become labeled cards on phones.
- Keep source links in the report. Mark missing or weak evidence as `待验证`.
- In chat, return only a short verdict, the report path, and verification evidence.

## Design Direction

Archetype: editorial magazine report.

Differentiator: a magazine-style issue rail and strong editorial masthead, while preserving decision-report clarity.

Rules:
- Lead with the recommendation, target graduation year, and biggest risk.
- Use restrained colors: ink, paper, muted teal, vermilion, and amber.
- Avoid decorative hero sections. This is an advisory report, not a marketing page.
- Use tables for comparison-heavy sections on desktop; on mobile, preserve the template script that copies table headers into `data-label` attributes so rows read as cards.
- Use plain labels: `上升`, `稳定`, `看人差距大`, `下降`.
- Add `window.print()` support through a print button.

## Required Page Sections

1. Verdict masthead
   - Major, forecast year, recommendation, trend label, generated date.
   - 3-5 key reasons and 1-3 biggest risks.

2. User profile and assumptions
   - Province/rank/school tier/city/postgraduate tolerance/family pressure/risk preference when known.
   - Explicit assumptions when missing.

3. Major breakdown
   - Discipline category, course base, core skills, common misunderstanding, postgraduate need.
   - Official-major check; if the input is not an official major, show safer official alternatives.

4. Industry and job routes
   - Route, industry, job titles, major fit, threshold, four-year judgment.

5. Employer tiers and salary samples
   - Head, middle, and long-tail/regional tiers.
   - 3 representative employers per tier where evidence allows.
   - Salary ranges by fresh graduate, 1-3 years, and 3-5 years.
   - Evidence confidence: 高, 中, 低, or 待验证.

6. Policy, technology, and market forces
   - Policy, AI/technology, industry cycle, talent supply.

7. Four-year outlook
   - Jobs, plain-language trend labels, reasons, warning signals.

8. School-tier and city adjustment
   - Explain how the verdict changes for strong-school, ordinary-undergraduate, junior-college, first-tier-city, and local-stability scenarios where relevant.

9. Fit and misfit profiles
   - Who should consider the major and who should avoid it.

10. College action plan
   - Year-by-year actions.

11. Alternative majors
   - Alternatives, why they may be better, tradeoffs.

12. Sources and uncertainty
   - Source name, date, link, and what it proves.
   - Data gaps and assumptions.

## Filling Rules

- Replace placeholders like `{{MAJOR}}` and sample rows with actual report content.
- Remove unused rows or sections; never leave placeholder text in a final report.
- Preserve the salary disclaimer.
- If a section has weak evidence, keep the section and mark it as `公开信息不足` or `待验证`.
- Escape user-provided text for HTML if generating programmatically.
- Keep the CSS as one coherent style system. Do not stack old skins under new override skins in public templates.

## Quick Validation

Before saying the webpage is ready:
- Confirm the file exists under `reports/`.
- Search the file for `{{` and `}}`; no placeholders should remain.
- Confirm it contains `<html`, `<style`, the major name, salary disclaimer, sources section, and at least one table.
- Open with a browser or inspect the file if browser access is unavailable.
- Verify a 390px-wide mobile screenshot or browser view: verdict cards stack vertically and table rows appear as labeled cards, not desktop tables squeezed sideways.
