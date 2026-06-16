---
name: software-graduate-thesis-workflow
description: Use when drafting, revising, structuring, or checking Chinese software engineering/professional master thesis materials, including thesis chapters, opening reports, citations, research cards, PlantUML diagrams, LaTeX outputs, and docs/ material organization.
---

# Software Graduate Thesis Workflow

## Overview

Use this skill to turn software project facts, literature evidence, design material, and test evidence into reusable thesis-writing material. Keep this file as the router; load detailed reference files only when the task needs them.

## Workflow

1. Identify the artifact type: thesis chapter, opening report, citation/reference list, research card, material directory structure, or LaTeX result.
2. Load only the required reference:
   - Citation cleanup or bibliography entries: `references/citation-style.md`.
   - Thesis chapters, Markdown drafts, or LaTeX thesis content: `references/thesis-format.md`; also load citation rules when references are involved.
   - Opening report/proposal content: `references/proposal-format.md`; also load citation rules when references are involved.
   - `docs/` structure, research cards, chapter material staging, or result placement: `references/document-structure.md`.
   - PlantUML source files, architecture figures, UML diagrams, or generated diagram images: `references/plantuml.md`; also load document-structure rules when deciding file placement.
   - LaTeX result directories, PDF generation, or final deliverable placement: `references/document-structure.md`.
3. Establish source boundaries before writing:
   - Literature facts come from `docs/research/`.
   - Technology facts can come from `docs/research/` or from the project itself, including code, dependencies, configuration, architecture, deployment, and runtime behavior.
   - When the project already uses a technology, treat it as a research trigger: investigate that technology and comparable alternatives, then use the findings to support domestic/foreign research status, related technology introduction, and technology selection logic in `docs/intro/`.
   - Requirements, architecture, implementation, and testing facts come from project code plus `docs/requirements/`, `docs/architecture/`, and `docs/test/`.
   - Final LaTeX outputs, generated PDFs, figures copied into deliverables, and build notes belong in `results/thesis/` for the thesis and `results/thesis-proposal/` for the opening report.
   - If an older project uses top-level `research/`, `project/`, or `results/`, treat them as legacy source material and normalize new guidance toward `docs/`.
4. Preserve evidence while drafting: keep citations, labels, figure/table references, and traceability notes unless the user explicitly asks to remove them.
5. If PDF generation fails once, stop PDF generation work. Do not retry, install compilation environments, or chase local toolchain fixes only to produce the PDF. Maintain a complete LaTeX directory under `results/thesis/` or `results/thesis-proposal/`; the user can zip it and import it into the school's official website to generate the PDF with XeLaTeX.
6. Do not invent papers, experiments, metrics, module behavior, or school format rules. If evidence is missing, mark the gap or ask for the missing source.

## Writing Rules

- Write formal Chinese academic prose for software engineering or professional master theses.
- Define scope before claims. Use qualifiers such as "原型系统", "给定实验环境", "测试拓扑", or the supported protocol/resource range.
- Separate existing technology capability from the author's work. Do not present mature protocols, security mechanisms, middleware, databases, frameworks, or tools as original contributions unless the thesis work actually changes them.
- In research-status sections, summarize existing work and its limitations before introducing this thesis. Do not prematurely describe the thesis solution inside the literature review.
- In technology-selection sections, connect project-adopted technologies to research evidence and comparable alternatives before justifying why the thesis uses them.
- In requirements, design, and testing chapters, prefer traceable statements: source or scenario -> requirement/design decision -> verification.

## Common Mistakes

- Treating `docs/` as application runtime documentation. It is thesis-writing material and evidence staging.
- Copying all collected literature into the thesis. Select representative sources that serve the argument.
- Writing implementation details as requirements. Requirements should stay mostly solution-neutral unless a technology is a hard constraint.
- Claiming production-grade security, performance, or availability without corresponding deployment and test evidence.
- Replacing evidence gaps with broad adjectives such as "高效", "安全", "先进", or "完善".
