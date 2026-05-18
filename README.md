# 审稿答复质量审计

匿名化审稿与答复质量审计 skill。

`review-response-quality-audit` 用于帮助审稿人分析论文、审稿意见和作者答复，区分真正解决、正当澄清、部分解决和答复修辞风险。它强调审稿人侧的质量审计，不用于帮助作者回避问题。

## 能做什么

- 审计审稿意见与作者答复。
- 对单篇论文生成匿名审稿意见。
- 识别论文正文中的包装性写法，例如 scope 扩张、limitation 弱化、表面中性但引导性强的表述。
- 检查 claim、实验、机制解释和复现细节中的细微逻辑漏洞。
- 模拟作者可能的防御性回应，帮助审稿人提前准备追问。
- 对照回避式答复与真正硬核解决所需证据。

## 启动菜单

本 skill 启动后必须先展示菜单，并询问使用者要做哪一项，不直接开始分析。

1. `已有 review / rebuttal 审计`
2. `单篇论文审查`
3. `回避式答复 vs 硬核回答对照`
4. `匿名案例归纳`


## 单篇论文审查

单篇论文审查固定输出：

1. `分析了什么、没分析什么`
2. `匿名论文主张与证据边界`
3. `审稿意见草案`
4. `论文正文包装性写法审计`
5. `细微逻辑漏洞审计与答复模拟`
6. `作者可能答复预演`
7. `审稿人追问与硬核解决标准`
8. `最终审稿建议`

该流程固定包含：

- 正文包装性写法审计；
- 细微逻辑漏洞审计与答复模拟；
- 作者可能答复预演；
- 审稿人追问；
- 硬核修复标准。

其中 `细微逻辑漏洞审计与答复模拟` 必须同时包含：

- flaw type；
- where it appears；
- why it matters；
- likely author response move；
- why that response may be insufficient；
- reviewer follow-up；
- hard-fix threshold。

## 已有 Review / Rebuttal 审计

对于已有审稿意见和作者答复，本 skill 会检查：

- 是否新增证据；
- 是否明确收缩 claim；
- claim 收缩是否进入论文正文层面；
- 答复是否只是降低表面压力；
- 什么证据才算真正解决问题。

默认四类结论：

| 结论 | 判定标准 |
|---|---|
| `硬核解决` | 新实验、新证明、新消融，或明确收缩 claim 并落实到论文层面。 |
| `正当澄清` | 问题确属理解偏差，澄清后没有回避证据责任。 |
| `部分解决` | 有一定补充，但原 concern 仍未完全消除。 |
| `答复修辞风险` | 答复听起来合作，但没有实质解决问题。 |

## 常见答复修辞风险

- 补丁承诺：承诺之后补，但当前公开证据不足。
- 礼貌缓冲：感谢和认同很多，但事实没有变化。
- 澄清重构：把实质疑问改写成误解或措辞问题。
- future-work 吸收：把当前必要验证转成未来工作。
- 范围切割：只在答复中缩小 scope，正文 claim 未同步收窄。
- 公平性防御：以不可比为由回避关键比较。
- 目标场景重框：把宽泛 claim 改成特定场景 claim。
- 正交化处理：把影响主结论的问题说成独立问题。
- 软性承认：把硬缺陷软化成可选增强项。
- 过线但留刺：综合意见认可，但关键 limitation 没进入最终 claim 边界。

## 证据纪律

输出时必须区分：

- `paper-stated`
- `reply-stated`
- `reasonable inference`
- `not reported`

没有公开证据时写 `未见公开证据`，不要脑补。

## 示例

```text
请启动 $review-response-quality-audit
```

```text
选择 2：单篇论文审查。请对这篇论文做匿名审查。
```

```text
选择 1：已有 review / rebuttal 审计。下面是审稿意见和作者答复，请判断哪些问题真正解决了。
```


---

# Review Response Quality Audit

An anonymized review and rebuttal quality-audit skill.

`review-response-quality-audit` helps reviewers analyze papers, review comments, and author rebuttals. It distinguishes real resolution, legitimate clarification, partial resolution, and rebuttal rhetoric risk. The skill focuses on reviewer-side quality auditing and is not intended to help authors evade reviewer concerns.

## What It Does

- Audits reviewer concerns and author responses.
- Reviews a single paper and generates anonymized reviewer comments.
- Identifies paper-body packaging language, such as scope inflation or softened limitations.
- Detects subtle logic flaws in claims, experiments, mechanisms, and reproducibility.
- Simulates likely author response moves for reviewer-defense purposes.
- Compares evasive or partial responses against hard-fix standards.

## Startup Menu

After startup, the skill must first show the menu and ask the user which task they want to perform. It must not start analysis directly.

1. `Existing review / rebuttal audit`
2. `Single-paper review`
3. `Evasive rebuttal vs hard-fix response comparison`
4. `Anonymous case synthesis`

## Single-Paper Review

For a single paper, the skill produces:

1. `What was analyzed and what was not analyzed`
2. `Anonymous paper claims and evidence boundaries`
3. `Draft reviewer comments`
4. `Paper-body packaging-language audit`
5. `Subtle logic-flaw audit and rebuttal simulation`
6. `Likely author rebuttal preplay`
7. `Reviewer follow-up questions and hard-fix standards`
8. `Final review recommendation`

This workflow always includes:

- paper-body packaging-language audit;
- subtle logic-flaw audit and rebuttal simulation;
- likely author rebuttal preplay;
- reviewer follow-up questions;
- hard-fix standards.

The `Subtle logic-flaw audit and rebuttal simulation` section must include all of the following:

- flaw type;
- where it appears;
- why it matters;
- likely author response move;
- why that response may be insufficient;
- reviewer follow-up;
- hard-fix threshold.

## Review / Rebuttal Audit

For existing review comments and author rebuttals, the skill checks:

- whether new evidence was added;
- whether the claim was explicitly narrowed;
- whether the claim narrowing reached the paper-body level;
- whether the rebuttal merely reduced surface pressure;
- what evidence would count as a real fix.

Default conclusion categories:

| Category | Meaning |
|---|---|
| `硬核解决` | New evidence, proof, ablation, experiment, or paper-level claim narrowing. |
| `正当澄清` | A legitimate clarification that does not evade evidence responsibility. |
| `部分解决` | Some progress, but the original concern remains partly unresolved. |
| `答复修辞风险` | The response sounds cooperative but does not substantively fix the issue. |

## Common Rebuttal Rhetoric Risks

- Patch promise: promising to add something later while current public evidence remains insufficient.
- Politeness buffer: using extensive thanks and agreement while the facts remain unchanged.
- Clarification reframing: rewriting a substantive concern as a misunderstanding or wording issue.
- Future-work absorption: moving necessary current validation into future work.
- Scope slicing: narrowing the scope only in the rebuttal while the paper-body claim remains unchanged.
- Fairness defense: avoiding a key comparison by arguing that it is not comparable.
- Target-scenario reframing: turning a broad claim into a claim about a specific scenario.
- Orthogonalization: presenting a problem that affects the main conclusion as an independent issue.
- Soft concession: softening a hard flaw into an optional enhancement.
- Accepted but unresolved: acknowledging the overall concern while leaving a key limitation outside the final claim boundary.

## Evidence Discipline

Output must distinguish:

- `paper-stated`
- `reply-stated`
- `reasonable inference`
- `not reported`

If public evidence is missing, it says `未见公开证据` rather than filling gaps by assumption.

## Examples

```text
Please start $review-response-quality-audit
```

```text
Choose 2: Single-paper review. Please perform an anonymous review of this paper.
```

```text
Choose 1: Existing review / rebuttal audit. Below are the reviewer comments and author rebuttal. Please judge which concerns were truly resolved.
```
