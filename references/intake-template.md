# Intake Template

Use this template when the user wants a personalized Gaokao major report. The major is the only required field. Do not force the user to fill every optional field.

## User-Facing Form

```text
准备报考的专业或方向：

所在省份：

高考分数或位次区间：

目标院校层次：
（985 / 211 / 双一流 / 普通公办本科 / 民办本科 / 专科 / 不确定）

是否接受读研、规培、考证或长期学习：
（接受 / 不接受 / 不确定）

目标城市或城市层级：
（一线 / 新一线 / 省会 / 地级市 / 县城 / 不限）

家庭经济压力：
（低 / 中 / 高）

风险偏好：
（求稳 / 均衡 / 愿意冲高回报）

兴趣方向：

不喜欢的工作类型：
（例如销售、加班、轮班、长期出差、强社交、体力劳动）

是否接受异地、加班、轮班、一线实践：

是否有家庭资源、行业资源或城市资源：
```

## Assumption Rules

- If only the major is provided, write: `本报告按全国通用情况分析，未纳入省份、位次、目标院校层次和家庭情况。`
- If score/rank or school tier is missing, avoid over-personalized verdicts about admission competitiveness.
- If family pressure is high, penalize routes that require long unpaid training, long postgraduate study, or uncertain early income.
- If the user does not accept postgraduate study, penalize majors where strong outcomes usually require graduate school, licenses, or standardized training.
- If the user prefers local stability, include regional employers and public-service-adjacent routes instead of only national head companies.
- If the user wants high upside and accepts risk, highlight routes with skill leverage but clearly state competition and failure risk.
