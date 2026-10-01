# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project
Interactive learning webapp that teaches students quality management (kwaliteitsmanagement). Part of the PXL Hogeschool "Projectmanagement" course series, next to AgileForNigel, TeachBertPERT and PMTheBasics.

## Source materials (in `source/` folder)
- `source/004 Kwaliteitsmanagement.md` — the lesson content and structure (copied from `pxl-projectmanagement-2627/content/`, published at https://janc-pxl.github.io/pxl-projectmanagement-2627/004-kwaliteitsmanagement)
- `source/2025_10_huisstijlhandboek.pdf` — PXL corporate identity / huisstijlhandboek
- `source/1314_logo_pxl_bol_witrand.png` — original PXL logo (high-res)

- `source/burger_<kwaliteit>_<uitwerking>.webp` — four hamburger photos for the Kwaliteit versus Uitwerking section (originals)
- `source/concept_<doel|ksf|kpi|doelwaarde>.webp` — four transparent illustrations for the concept cards (originals); `source/concept_kaarten_ontwerp.webp` is the design mockup they came with

**Image pipeline:** originals stay in `source/`; the page uses resized copies in `img/`, made with Python/Pillow. Photos: JPEG, 700px wide, quality ~84, convert to RGB first. Illustrations with a transparent background: WebP with alpha, transparent border cropped, 560px wide. Only add images when asked.

## Requirements
- Single-page scroll layout (all sections on one page, nav links are anchor scrolls)
- Clean, modern design
- Max-width: 1100px (optimized for 1920x1080 student screens)

## Hosting — GitHub Pages
The site is published via GitHub Actions to GitHub Pages.

- **Workflow**: `.github/workflows/deploy.yml` — triggers on every push to `main`
- **Source setting**: GitHub Pages → Source must be set to **GitHub Actions** (in repo Settings → Pages)
- No build step — the entire repo root is uploaded as the Pages artifact
- `index.html` only redirects to `kwaliteit.html`, so the root URL works too
- **Gotcha:** Pushing workflow files requires the `workflow` OAuth scope. If rejected, add the file via GitHub web UI instead.

## Styling — PXL Hogeschool huisstijl
Same design tokens, typography, nav (hamburger + scroll spy), footer, badges and callouts as the sibling repos (see `../AgileForNigel/CLAUDE.md`).

**Extra tokens on this page:** every concept has a fixed color that is reused everywhere (cards, ladder rungs, quiz buttons, table headers, highlighter marks):
- `--c-doel` (black) = Doel
- `--c-ksf` / `--c-ksf-dark` (gold) = KSF
- `--c-kpi` (blue) = KPI
- `--c-target` (green) = Doelwaarde
- `--c-task` (grey) = gewone dagtaak

Key words in sentences are wrapped in `<mark class="hl-ksf|hl-kpi|hl-target">`; they get an animated highlighter stripe in the concept color.

## Language
All page content is in **Dutch** (Nederlands).
Do NOT use em dashes (—, `&mdash;`, `—`) in any user-visible text. Use periods, colons, commas, or parentheses instead.

## Architecture
Single-file HTML page (`kwaliteit.html`) with inline `<style>` and `<script>` — no build step, no framework.

**Pattern:** data array → render function that rebuilds DOM via `innerHTML` → click handler updating global state → progress bar → summary card (`.summary.visible`) when everything is done.

**Current sections in `kwaliteit.html`:**
- `#ksf-kpi` — Kritische Succesfactoren & Kritische Prestatie-Indicatoren. Intro with 4 concept cards (Doel → KSF → KPI → Doelwaarde), each with an illustration on top (`img/concept_*.webp`, decorative, `alt=""`; the arrows between the cards sit at title height), then four parts:
  1. `#ksf-ladder` (prefix `ladder-`): "Beklim de KSF-ladder". The two lesson examples (restaurant, wasmachinefabrikant) in `LADDER_EXAMPLES[]`. Doel on top, one column per KSF with KPI/doelwaarde hidden until the student steps through. Every rung is its own button (`ladderRungClick(i, s)`): KSF selects the column, KPI and doelwaarde toggle, but always as a staircase (`ladderLevel[key]` = 1..3 is the visible level; hiding the KPI also hides the doelwaarde, and clicking a doelwaarde while the KPI is hidden only nudges it and shows a hint). The Vorige/Volgende buttons change the same level. `ladderVisited` (completion ✓) stays once a KSF reached level 3. Each step shows one sentence from the lesson's thinking frame ("Om het doel te bereiken is het noodzakelijk ... te hebben" / "De beste aanduiding ... is ..." / "We weten dat we op het goede spoor zijn indien ...") plus a note. `lowerBetter: true` marks KPIs where the target is a maximum.
  2. `#ksf-quiz` (prefix `quiz-`): sorter with 12 cards in 3 new contexts (`QUIZ_CONTEXTS`, `QUIZ_ITEMS`). Four answers: KSF, KPI, Doelwaarde, Dagtaak. The "dagtaak" category teaches that daily tasks are necessary but not critical. Hints depend on (chosen, correct) via `QUIZ_HINTS`.
  3. `#ksf-campi` (prefix `campi-`): builder for the Campi campus app (same fictional project as in AgileForNigel's Planning Poker). Step 1: find the 4 real KSF'en among 8 candidates (`CAMPI_CANDS`). Step 2: per KSF pick the best KPI and doelwaarde (`CAMPI_KSFS`). Step 3: result table in the lesson's KSF | KPI | Doel format.
  4. `#ksf-eigen` (prefix `own-`): free-form builder for the student's own project with live sentences and a simple checklist.
- `#kwaliteit-uitwerking` — Kwaliteit versus Uitwerking. Two definition cards (colors `--c-quality` orange, `--c-grade` purple), then:
  1. `#ku-burger` (prefix `burger-`, shared matrix classes `ku-`): two segmented toggles (kwaliteit/uitwerking hoog/laag) plus a clickable 2x2 matrix, synced. The hamburger from the lesson is shown as one of four photos (`img/burger_*.jpg`, file name per combination in `BURGER_COMBOS[k].img`). All four are stacked in `#burger-photo` and crossfade via the `.on` class. Texts per combination in `BURGER_COMBOS` (keys `'qu'`, e.g. `'10'` = hoge kwaliteit, lage uitwerking).
  2. `#ku-place` (prefix `place-`): 8 situations (`PLACE_ITEMS`, including Campi v1/v2) to place in the matrix. Hints name the wrong dimension. Reuses the `quiz-` card, dot and feedback styles.
- `#kosten-kwaliteit` — Kosten van kwaliteit (prefix `koq-`). Two cards "Investeren in kwaliteit" / "Besparen op kwaliteit" (colors `--c-invest` blue, `--c-fail` red; this pair was checked with the dataviz palette validator, the total line uses ink `--primary`). Then:
  1. `#koq-balans`: interactive SVG chart (`initKoqChart`) of the classic cost-of-quality model with relative costs, no euros: `koqInvest(x)` rising, `koqFail(x)` falling, `koqTotal(x)` U-shaped with the minimum `KOQ_OPT` around x = 41. Slider, pointer and arrow keys set `koqSet(x)`; a marker with tooltip (hidden on phones) and a side panel show the three values, the zone (`KOQ_ZONES`: low < 25, mid 25-58, high > 58) and a Campi example. Summary when all three zones are visited.
  2. `#koq-sort`: 12 expenses (`KOQ_ITEMS`) sorted into "Investering in kwaliteit" vs "Kost van fouten", collected in two tally columns. Ends with a callout that links to the Poka Yoke section.
- `#poka-yoke` — Poka Yoke (prefix `py-`). Intro with the meaning of the name (poka + yoke(ru)) and Zero-Defects, then:
  1. `#py-rondom`: 8 flip cards (`PY_ITEMS`, emoji icons, no images) with everyday Poka Yoke's; the back names the prevented mistake and the kind (`prevent` = maakt de fout onmogelijk, `warn` = waarschuwt). Both faces share one CSS grid cell so the card grows with the longest face.
  2. `#py-checklist`: the garage checklist from the lesson (`PY_CHECKS`). The "Auto teruggeven" button uses `aria-disabled` (still clickable) so a click can highlight the missing steps; links to the Definition of Done.
  3. `#py-campi`: a Campi room-booking form with four toggleable Poka Yoke's (`PY_GUARDS`: date picker from today, end hour only after begin hour, room dropdowns, button lock). Room codes follow the real PXL format `DH.z<zone>v<verdiep>.<lokaal>` (e.g. DH.z2v02.23): zones 1-3, floors 00-02, rooms 01-25 (`PY_ZONES`, `PY_FLOORS`, `PY_NRS`). Without the guard the code is typed freely and `pyRoomProblem()` explains what is wrong; with the guard three dropdowns build the code. With the guards off, students make the four mistakes (`PY_ERRORS`: past, order, room, double = same booking twice within 4 s); with them on, the mistakes become impossible. Summary when all four were made and all four guards are on.

## Development
No build commands. Open `kwaliteit.html` directly in a browser to test. The deploy workflow uploads the entire repo root as a static site.
