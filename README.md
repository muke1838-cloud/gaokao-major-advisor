# Gaokao Major Advisor

Gaokao Major Advisor is an AI skill for helping Chinese Gaokao students, parents, counselors, and education advisors evaluate university major choices.

It connects a major to realistic industries, job routes, employer tiers, salary samples, policy and technology trends, and a four-year career outlook.

## What It Does

- Normalizes official and non-official major inputs.
- Maps majors to industries, job routes, and entry requirements.
- Compares head, middle, and long-tail or regional employers.
- Estimates salary ranges with source and confidence notes.
- Considers AI, policy, industry cycles, city differences, school tier, postgraduate requirements, and family constraints.
- Produces a standalone HTML report in an editorial magazine style.

## Core Inputs

Only the target major is required.

Optional context improves personalization:

- Province and score or rank band
- Target school tier
- Undergraduate or junior-college route
- Preferred city or region
- Family income pressure
- Willingness to pursue postgraduate study, standardized training, certificates, or licenses
- Risk preference
- Interests and disliked work styles
- Family, city, or industry resources

If only a major is provided, the skill generates a national/general analysis and states the assumptions.

## Output

The default output is a standalone static HTML report, not a long chat reply.

The report includes:

1. Verdict first
2. Student profile and assumptions
3. Major breakdown
4. Industry and job mapping
5. Employer tiers and salary samples
6. Policy, technology, and market trends
7. Four-year job outlook
8. School-tier and city-tier adjustment
9. Fit and misfit profiles
10. College action plan
11. Alternative majors
12. Sources and uncertainty

## Design Direction

HTML reports use a required editorial magazine report style:

- Paper-like background
- Ink-like body text
- Muted teal, vermilion, and amber accents
- Strong masthead and issue rail
- Mobile-responsive table cards
- Inline CSS and JavaScript
- No CDN, external fonts, build tools, or server dependency

## Repository Structure

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
├── assets/
│   └── web-report-template.html
└── references/
    ├── intake-template.md
    ├── report-template.md
    ├── research-framework.md
    └── web-report-guide.md
```

## Usage

Use this skill when a user asks to evaluate a university major, choose a Gaokao application direction, compare major-related jobs, or forecast the career potential of a major four years after enrollment.

Example prompt:

```text
使用 gaokao-major-advisor，帮我分析“计算机科学与技术”这个专业四年后的就业前景。
```

For better personalization:

```text
使用 gaokao-major-advisor，帮我分析“临床医学”。
省份：广东
位次：约 18000
目标院校层次：211 或强双非
是否接受读研/规培：接受
家庭经济压力：中
风险偏好：求稳
目标城市：广州、深圳或省会城市
```

## Evidence Rules

The skill requires fresh research for current industry, policy, employer, and salary claims.

If web/current-data access is unavailable, the output must clearly say the current-data part is unverified and should only be treated as a framework.

The skill must not fabricate salary data, hiring demand, employer tiers, or policy support.

## License

MIT
