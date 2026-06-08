# Web Report Guide

Use this guide when the user asks for a beautiful webpage, HTML file, shareable report, printable report, or one independent report per major.

## Output Contract

- Create one standalone `.html` file per major.
- Default location: `reports/YYYY-MM-DD_<major-slug>.html` in the user's current project.
- Start from `assets/web-report-template.html`.
- Inline all CSS and small JavaScript. Do not require a dev server, CDN, image download, or build step.
- Keep the report readable for parents and students on mobile and desktop.
- Do not rely on horizontal table scrolling as the mobile experience; table rows must become labeled cards on phones.
- Keep source links in the report. Mark missing or weak evidence as `待验证`.

## Design Direction

Archetype: editorial consulting report.

Differentiator: a visible verdict rail at the top that turns the whole report into a decision document, not a long article.

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

2. Major breakdown
   - Discipline category, course base, core skills, common misunderstanding, postgraduate need.

3. Industry and job routes
   - Route, industry, job titles, major fit, threshold, four-year judgment.

4. Employer tiers and salary samples
   - Head, middle, and long-tail/regional tiers.
   - 3 representative employers per tier where evidence allows.
   - Salary ranges by fresh graduate, 1-3 years, and 3-5 years.

5. Policy, technology, and market forces
   - Policy, AI/technology, industry cycle, talent supply.

6. Four-year outlook
   - Jobs, plain-language trend labels, reasons, warning signals.

7. Fit and misfit profiles
   - Who should consider the major and who should avoid it.

8. College action plan
   - Year-by-year actions.

9. Alternative majors
   - Alternatives, why they may be better, tradeoffs.

10. Sources and uncertainty
   - Source name, date, link, and what it proves.
   - Data gaps and assumptions.

## Filling Rules

- Replace placeholders like `{{MAJOR}}` and sample rows with actual report content.
- Remove unused rows or sections; never leave placeholder text in a final report.
- Preserve the salary disclaimer.
- If a section has weak evidence, keep the section and mark it as `公开信息不足` or `待验证`.
- Escape user-provided text for HTML if generating programmatically.

## Quick Validation

Before saying the webpage is ready:
- Confirm the file exists under `reports/`.
- Search the file for `{{` and `}}`; no placeholders should remain.
- Confirm it contains `<html`, `<style`, the major name, salary disclaimer, sources section, and at least one table.
- Open with a browser or inspect the file if browser access is unavailable.
- Verify a 390px-wide mobile screenshot or browser view: verdict cards stack vertically and table rows appear as labeled cards, not desktop tables squeezed sideways.
