# All Things Catholic: assignment submission

**"Where Faith meets Fun"** is the front end for a small Catholic family brand. It's a React 19 + Vite 8 static site with a token-based design system, JSON content validated against its own rules, three Claude Code subagents and three custom skills.

Packaged 2026-10-23 from `C:\Users\DELL\Downloads\MyWork\AllThingsCatholic`. The original project wasn't modified. Every file here is a copy of a real project file, a check run on 2026-10-23 (with its output saved), or a verbatim extract from the Claude Code session transcripts. No screenshot, test output, token count or session history was created or edited by hand.

The eight deliverables below follow **Step 6** of the assignment brief. The screenshots of the brief are in `01-Visual-References/references/WhatsApp Image 2026-10-20 … .jpeg`.

## Submission checklist

| # | Assignment requirement | Evidence (folder → key files) | Status | Outstanding action |
|---|---|---|---|---|
| 1 | Visual references saved in a references folder | `01-Visual-References/references/` is the project's `reference/` folder, copied unchanged. It holds `all-things-catholic_after.html` (the reference design the site follows) and 8 screenshots of the assignment brief. Also: `rendered-reference-screenshots/` (32 renders of the reference design at 1280px, made by `scripts/compare-reference.mjs`) and `brand-logo/logo.png`. | **Complete** | None. Note: the 8 JPEGs are the assignment brief, not visual references. They're kept because they're in the project's references folder. |
| 2 | Style guide, design tokens and component specs | `02-Design-System/style-guide/DESIGN_SYSTEM.md` (31 rules, §1), the `/styleguide` page source and its screenshots. `design-tokens/tokens.css` plus `check-tokens-output-2026-10-23.txt` (✓ 102 files). `component-specs/` (§3 of DESIGN_SYSTEM.md, plus 26 component folders). **Pass condition:** `component-specs/trace-check-output.txt` traces ProductCard → `--radius-card` (26px) → DS-SHAPE-01, in the files and in the rendered page: "CHAIN HOLDS: no gaps". | **Complete** | None |
| 3 | Structured content and the actual rendered page | `03-Content-and-Rendered-Page/structured-content/src-data/` (9 JSON files) and `content-rules.md` (CR-01…CR-15). In `validation/`: `check-data-output-2026-10-23.txt` (✓ 9 files, 76 entries), and `check-data-negative-test-2026-10-23.txt` (4 broken rules on a copy of the data, all 4 caught with their rule IDs, exit 1). `rendered-page/`: the production build, the page source, `rendered-cards-vs-data.txt` (every card on `/hampers`, `/shop` and `/recommendations` matches the data), behaviour 25/25 and QA 182/182. `screenshots/`: 127 current captures at 375, 768 and 1280px. | **Complete** | None |
| 4 | Compliance subagent and its output after three deliberate violations | `04-Compliance-Subagent/subagent-config/design-system-reviewer.md`. **Two** planted tests, each **3 of 3 caught, with rule IDs**. Test 1, HamperCard (2026-10-21): DS-MOTION-01, DS-COL-05, DS-TYPE-03; `violation-tests/test-1-…/HamperCard.planted.css` vs `.clean.css`. Test 2, SearchBar (2026-10-23): DS-COL-05, DS-SHAPE-02, DS-TYPE-03. `output/raw-agent-*.md` is the subagent's report, word for word from its transcript. `output/2026-10-2*-…planted*.md` are the saved reports. `violation-tests/restoration-check-2026-10-23.txt`: both components are clean now. | **Complete** | None. Note: test 2's planted file wasn't saved separately. Its three planted lines are quoted verbatim in the subagent's `check:tokens` output. |
| 5 | CLAUDE.md and the planning-mode prompt | `05-Claude-Instructions/CLAUDE.md` is the latest version. `planning-mode-prompt.md` holds the only prompt sent in Claude Code plan mode (2026-10-22 19:53 UTC), verbatim, plus the plan Claude proposed and what happened next. `supporting/` holds the plan file, `PROJECT_BRIEF.md` (the original brief, with every page), `REFINE_PROMPT.md`, and `CLAUDE-as-loaded-by-fresh-sessions-2026-10-22.md` (the version fresh session 2 loaded, recovered from a transcript). | **Complete** | None. Note: the founder stopped the plan before it was carried out (recorded in CLAUDE.md). |
| 6 | Evidence the new session picked up the project context | `06-New-Session-Evidence/transcripts/`: three fresh sessions (`06bcaded`, `ee7fac96`, `7c3e64e1`). Each was asked to explain the project without being told about it, and each read and verified `CLAUDE.md` and described it correctly. These are verbatim prompts and replies, plus the list of files Claude opened, extracted from the transcripts. | **Partial** | **Screenshots are missing.** See `06-New-Session-Evidence/screenshots/ADD-SCREENSHOTS-HERE.md` (resume a session, take screenshots of its first prompt and reply). |
| 7 | Custom skill and before/after evidence that it changed something | `07-Custom-Skill/SKILL.md` is `product-catalogue-export`. `implementation/` holds the export script and `package.json` (`npm run export:catalogue`). `implementation/generated-output/` holds the CSV and JSON it generated: 27 records. `before-after-evidence/`: `baseline.md` (before: no `exports/` folder existed; source hashes recorded), then `report.md`, 3 identical runs, negative tests, the site-vs-export check, and source hashes unchanged after. Also in `other-skills/`: `design-token-audit`, which made real code fixes with before/after screenshots and outputs (2 runs), and `atc-component-builder` (31+ scaffolds). | **Complete** | None |
| 8 | Number of tokens and sessions used | `08-Tokens-and-Sessions/usage-summary.md`: **9 sessions; 252,695,502 tokens in recorded responses** (235,989,780 for the completed sessions plus 16,705,722 for the current one), **$100.1135** recorded by Claude Code for the completed sessions. The current session and cumulative usage are shown separately. Details are in `usage-from-transcripts.md` (per session, method stated) and `build-log.md` (per phase). | **Partial** | **Screenshots of `/cost` or `/usage` are missing**, and the current session's dollar cost isn't recorded until `/cost` is run in it. See `08-Tokens-and-Sessions/screenshots/ADD-SCREENSHOTS-HERE.md`. |

## Evidence still required
These can only be produced by you, on screen. Nothing was made up to fill these gaps.
1. **New-session screenshots** for requirement 6, saved in `06-New-Session-Evidence/screenshots/`.
2. **`/cost` screenshot of the current session**, plus optionally `/usage`, for requirement 8. Save them in `08-Tokens-and-Sessions/screenshots/`. Running `/cost` also gives the current session's dollar figure; add it to `usage-summary.md` if you want it written down.
3. *(Optional)* `docs/build-log.md` in the project still has `_fill in_` cells for the `/cost` figures of sessions 1–3. The answer is in `08-Tokens-and-Sessions/`. The project file was left unchanged.

## Reproducing the results
`project-source/` is the complete project, minus `node_modules`, the build output, test caches and the regenerable screenshots. It includes `.claude/` (the subagents and skills), `docs/` and `reference/`.
```bash
cd project-source
npm ci
npx playwright install chromium   # for the browser checks only
npm run build && npm run lint && npm run check:tokens && npm run check:data
npm run export:catalogue          # the custom skill's export
npm run test:behaviour            # 25 checks
npx playwright test -c qa/playwright.config.js   # 182 checks
npm run preview                   # the site at http://localhost:4173/
```
On Windows 11 with Smart App Control on, a fresh `npm ci` can have Vite's native bundler file (`@rolldown/binding-win32-x64-msvc`) blocked, with the error "Cannot find native binding … An Application Control policy has blocked this file". This happened when the package was tested in a temporary folder. The project files themselves are fine. `project-source/README.md` is the project overview.

## Integrity notes
- **Original project:** read only. No file in `C:\Users\DELL\Downloads\MyWork\AllThingsCatholic` was created, changed or deleted for this submission. The checks run on 2026-10-23 only read files (`check:tokens`, `check:data`, the trace and restoration checks), and the negative tests used a copy of the data in a temporary folder.
- **Timestamps:** copied files keep their original modification times (robocopy `/COPY:DAT /DCOPY:T` and Copy-Item).
- **Verbatim extracts:** `planning-mode-prompt.md`, `06-…/transcripts/*.md`, `04-…/output/raw-agent-*.md` and `usage-from-transcripts.md` were generated by `08-Tokens-and-Sessions/extract-evidence.mjs` from the transcript files under `~/.claude/projects/` (paths are given inside each file). It copies text and does not paraphrase. Tool results are left out to keep the files readable.
- **Historical files** are labelled `…historical`: Phase 3 and Phase 4 evidence from before the refine to the reference design. Their numbers (for example "7 files, 54 entries") describe the site at that time.
- **Left out:** `node_modules/`, `.git` (none exists), build caches (the one production build is kept in `03-…/rendered-page/`), `test-results/`, the 30 out-of-date QA screenshots from before the refine, and the 289 regenerable comparison images (only the 32 reference renders are kept). The project has no `.env` files or credentials, and none are included.
