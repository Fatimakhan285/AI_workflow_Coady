# CLAUDE.md — AI Workflow Seminar

**Project:** AI Workflow Seminar
**Type:** teaching
**Working Branch:** main

---

## Project Overview

A 3-hour seminar teaching PhD researchers how to use Claude Code for empirical research workflows. Covers GitHub basics, Claude Code installation, core concepts (tools, agents, CLAUDE.md, rules, skills), and hands-on examples with R and LaTeX projects. The repository itself serves as both the teaching material and a reference implementation of a Claude Code workflow.

---

## Skills (Slash Commands)

| Command | What It Does |
|---------|-------------|
| `/compile-paper` | Compile LaTeX manuscript (latexmk + biber) |
| `/run-pipeline` | Run main.r and verify all outputs |
| `/proofread [file]` | Grammar, typo, and consistency review |
| `/review-r [file]` | R code quality and reproducibility review |
| `/review-paper [file]` | Full manuscript review (identification, econometrics, citations) |
| `/validate-bib` | Cross-reference citations vs bibliography |
| `/devils-advocate [file]` | Challenge design decisions |

---

## Project Structure

```
project/
├── CLAUDE.md
├── .claude/                     # Agents, rules, skills
├── code/
│   ├── main.r                   # Reproduces all results
│   ├── 01_clean_data.r
│   ├── 02_make_panel.r
│   ├── 03_estimation.r
│   └── 04_figures.r
├── raw_data/                    # NOT in git
├── temp_data/                   # NOT in git
├── outputs/
│   ├── tables/
│   └── figures/
├── manuscript/
│   ├── main.tex                 # Compile from project root
│   └── references.bib
├── literature/                  # NOT in git
├── quality_reports/
│   ├── plans/
│   └── session_logs/
└── lab_journal.md               # NOT in git
```

**Compilation:** `latexmk -pdf manuscript/main.tex` from the project root.

---

## What Goes in Git

- **Commit:** code, outputs (tables/figures), manuscript, .Rproj
- **Do NOT commit:** raw_data/, temp_data/, literature/, lab_journal.md, .Rhistory, .RData

---

## Lab Journal

Maintain `lab_journal.md` in the project root (gitignored). Update at session end:
- What was accomplished
- Issues encountered
- Next steps
