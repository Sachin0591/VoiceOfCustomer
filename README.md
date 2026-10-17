# Resonance: Voice of Customer Intelligence

A product concept and clickable prototype for a tool that helps product managers **see what repeats across customer calls, in the customers' own words**.

> **New here?** Start with the [prototype](prototype/index.html) (2 minutes), then skim the [PRD](docs/Resonance-PRD.pdf) (9 pages).

## The idea in plain words

- A product manager running customer discovery holds 5 to 15 calls per initiative. Each is 8,000 to 10,000 words, and nobody re-reads them all.
- **The problem:** patterns are invisible, the last or loudest customer dominates, AI summaries paraphrase without a source, and a theme can't reach a roadmap without being framed.
- **The solution:** one **repository per initiative**. Upload call transcripts, and Resonance finds the themes that repeat across calls. Each theme is backed by the customer's **exact quote**, with speaker, date and timestamp. A theme ends in a framed **opportunity**.

**Three decisions that shape the product**
1. **Quote first, summary second.** A paraphrase is not evidence.
2. **The repository is the unit, not the meeting.** One call is a summary; three or more is a pattern.
3. **The tool stops where judgment starts.** It drafts the problem statement and leaves the hypothesis blank for the PM.

## What's in this repo

| Path | What it is |
|---|---|
| [`docs/Resonance-PRD.pdf`](docs/Resonance-PRD.pdf) | Product Requirements Document v1.0: problem, goals, metrics, personas, requirements, risks, launch plan. |
| [`prototype/index.html`](prototype/index.html) | Clickable prototype of the four core screens. One file, no install: open it in a browser. |

## The PRD at a glance

| Section | Summary |
|---|---|
| Who it's for | **Maya, the discovery PM** (primary). Dev, the product lead, reads and challenges. Customer success is out of v1. |
| Core flow | Create repository → upload meetings (.docx transcripts) → read insights → check the source quote → frame as opportunity. |
| Four insight tabs | Pain, positives, improvements, emerging trends: ranked theme cards with label, signal strength, meeting count and lead quote. |
| North star | Evidence-backed opportunities per active repository per month (must cite quotes from 2 or more meetings). |
| Priorities | **P0** completes the loop (upload, insight, evidence, decision). **P1** adds trust and repeatability (review, saved opportunities). **P2** can wait (trends, export, Jira). |
| Out of scope for v1 | Audio/video/PDF, real-time insights, team workspaces, integrations beyond Jira, auto-prioritization. |

**Where it stands (per the PRD):** the extraction pipeline is built and tested on 2 real transcripts (209 claims, 35 themes, 95.9% of quotes verified as exact source text). The four screens are prototyped on illustrative data. Upload endpoint, customer tagging, opportunity list, trends and hosting are not built.

## The prototype: what you can try

The prototype uses illustrative sample data, not real customer calls.

1. **Repositories:** one card per initiative, with counts and the strongest pain signal.
2. **Workspace:** four tabs of ranked theme cards, each with a lead quote and a "Frame as opportunity" action.
3. **Meeting detail:** everything from one call, grouped by claim type, with jump links.
4. **Frame as opportunity:** evidence locked, problem drafted, who is affected, signal read-only, and an empty hypothesis for the PM to write.

```bash
open prototype/index.html                  # option 1: open the file
python3 -m http.server 8000                # option 2: serve, then visit /prototype/
```

The prototype loads fonts from Google Fonts, so it needs an internet connection to look right.

## Building the real app with Lovable

This repo is meant to be linked to [Lovable](https://lovable.dev). It has no app scaffold yet, so Lovable can generate the project in the repo root. Suggested first prompt:

> Build a React + TypeScript app that reproduces the clickable prototype in `prototype/index.html`, following the requirements in `docs/Resonance-PRD.pdf`. Use mock data first. Screens: Repositories, Workspace (four insight tabs), Meeting detail, Frame as opportunity. Build the P0 requirements first.

Repo settings in place for this (same layout as the Feature Store repo):
- `.gitignore` covers Node, Vite, env files and editor files.
- `.gitattributes` marks `docs/` and `prototype/` as documentation, so GitHub language stats reflect the app code once it exists.
- `.editorconfig` keeps formatting consistent.
- Keep `docs/` and `prototype/` as reference material; let Lovable own `src/`, `package.json` and other root app files.

## Status

Concept and prototype stage. Pipeline built locally; no hosted backend, authentication or real customer data in this repo.

**Author:** Sachin Doddamani · PRD v1.0, 17 Oct 2026
