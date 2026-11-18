---
name: paper-quick-report
description: Read academic or technical papers, especially local PDF papers, and produce a fast structured report for users who want to quickly understand a paper. Use when asked to read, summarize, explain, report on, or quickly understand a paper, preprint, arXiv PDF, research article, benchmark paper, or technical manuscript.
---

# Paper Quick Report

## Goal

Produce a concise but high-signal paper report that helps the user understand the paper quickly: what it claims, what problem it solves, how it works, what evidence supports it, and how to judge its value.

## Reading Workflow

1. Identify the paper title, authors, author affiliations/institutions, venue/date if present, page count, and artifact path or URL.
2. Read the abstract, introduction, method, experiments/results, limitations, and conclusion.
3. Inspect figures and tables visually when available. Do not rely only on extracted text, because paper claims often live in plots, captions, and ablation tables.
4. Extract the central question, not just the topic. Phrase it as the tension or uncertainty the paper resolves.
5. Capture the method at the right abstraction level: core idea first, then architecture/training/data/control details only if they explain the contribution.
6. Pull exact headline numbers from main tables and figures. Prefer a few decisive numbers over a full metric dump.
7. Separate author claims from your judgment. Make clear when a conclusion is supported by experiments and when it is your interpretation.

For PDFs, use available PDF tools to extract text and render important pages. If extraction is messy, render key pages and inspect them visually.

## Report Structure

Answer in the user's language. For Chinese users, use Chinese section labels and natural technical phrasing.

Use the eight sections below in order unless the user requests a different format. Put the paper's original title on its own line at the top as a Markdown level-two heading (`##`). Start each section with a standalone level-three heading (`###`) and leave a blank line before its content. Use the Chinese headings in the template for Chinese reports.

1. Paper metadata
   - List the authors, author affiliations/institutions, venue and date when available, page count, and artifact path or URL. The source link can appear directly below the paper title, as in the template.
   - If affiliations or dates are absent from the paper, say `未在论文中找到` rather than guessing.
   - Keep long author lists compact by preserving names but grouping shared affiliations when possible.

2. One-sentence summary
   - State the paper's core contribution and why it matters.

3. Core problem
   - Explain what bottleneck, assumption, gap, or research question the paper targets.
   - Avoid generic restatement of the field.

4. Method
   - Introduce the core idea, then walk through the main steps from input to output. Use two or three short paragraphs or bullets when the method has several steps.
   - Explain what each key component does, how the components connect, and how the central design choice addresses the paper's problem.
   - Include the training data, objectives, stages, or inference and deployment procedure where those details help explain the contribution. For empirical or benchmark papers, describe the study design and evaluation procedure.
   - Keep equations out unless they clarify the idea.

5. Key experiments/results
   - List benchmark/task settings and the most important numbers.
   - Include ablations that answer the paper's central question.
   - Mention real-world experiments separately from simulation if both exist.

6. Important insight
   - Explain the main takeaway beyond raw performance.
   - This is often the design lesson, empirical finding, or changed assumption.

7. Limitations
   - Include limitations stated by the authors and obvious residual risks.
   - Be specific: dataset scale, task coverage, compute/hardware dependence, generalization, latency, evaluation design, or missing comparisons.

8. Your judgment
   - Give a pragmatic assessment of what the paper is really valuable for.
   - State whether it is more of an algorithm paper, systems paper, benchmark paper, infrastructure paper, or empirical design study.
   - Mention what to watch next or how the idea should influence future work.

## Style Rules

- Lead with the answer, not background.
- Keep the report compact: usually 6-10 short paragraphs or bullets.
- Use exact model/task names and numeric results when available.
- Avoid overclaiming. Say `论文显示`, `作者认为`, or `我的判断是` when the source of the claim matters.
- Prefer "what changed" over "what exists": focus on what the paper adds relative to prior work.
- If a paper has many tables, summarize only the table(s) that support the main claim.
- If the paper is weak or underspecified, say so directly and explain why.

## Minimal Output Template

```markdown
## 论文原标题

我读的是 [paper.pdf](/absolute/path/paper.pdf)。

### 论文信息

- 作者：...
- 单位：...
- 发表场所和日期：...
- 页数：...

### 一句话概括

...

### 核心问题

...

### 方法

介绍方法的核心思路和从输入到输出的主要步骤。

说明关键模块各自的作用和衔接方式，按需补充训练数据、目标或推理流程。

### 关键实验结果

该方法在给定任务上的成功率为 …%。

### 最重要的洞见

...

### 局限

...

### 我的判断

...
```
