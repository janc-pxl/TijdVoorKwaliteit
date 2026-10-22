---
target: concept cards Doel/KSF/KPI/Doelwaarde
total_score: 12
max_score: 28
na_heuristics: 1,3,9
p0_count: 1
p1_count: 2
target_identity: "file:C:\\Users\\20003936\\gitpxl\\TijdVoorKwaliteit\\kwaliteit.html"
target_fingerprint: "sha256:c9da6119fab119fc289c9fdcd092d82b3e509ad78a9d317e0da20510bfc894c2"
target_path: "C:\\Users\\20003936\\gitpxl\\TijdVoorKwaliteit\\kwaliteit.html"
timestamp: 2026-10-22T09-17-05Z
slug: kwaliteit-html
---
# Critique: concept cards (Doel, KSF, KPI, Doelwaarde) in #ksf-kpi

Method: dual-agent (A: design review · B: detector + browser)

## Heuristics (applicable max 28; 1, 3, 9 n/a: static intro block)
| # | Heuristic | Score | Key issue |
|---|---|---|---|
| 1 | Visibility of status | n/a | static |
| 2 | Match real world | 2 | stock metaphors (dartboard, gears, chart, speedometer), not the lesson's examples |
| 3 | User control | n/a | static |
| 4 | Consistency | 2 | name line: expansions for KSF/KPI vs paraphrases for Doel/Doelwaarde; horizontal flow contradicts the vertical ladder |
| 5 | Error prevention | 2 | no KSF vs dagtaak distinction, which the quiz tests next |
| 6 | Recognition | 2 | no example chain to recognise in the ladder |
| 7 | Flexibility | 1 | useless as quick exam reference |
| 8 | Minimalism | 1 | 4 text levels, image takes ~40% of each card, 5 illustrations in one screen |
| 10 | Help | 2 | lesson sentence frames missing |
| Total | | 12/28 (43%) | Poor |

## Specificity verdict
Generic. One-to-one build of the AI mockup source/concept_kaarten_ontwerp.webp: colored top border, spot illustration on a blob, big title, subtitle, bold question, grey paragraph. Four equal peers for content that is a tree (1 Doel, n KSF, each 1 KPI + 1 doelwaarde).

## Detector
CLI: 57 findings on the full page, 0 contrast or text-size findings on the cards. On the cards: border-accent-on-rounded (.concept-card l.155, also .ku-def, .koq-def, .cor-def, .vg-fact). Nearby: kicker-above-heading (.badge), side-tab (.callout). Measured: arrow ::after #ae9a64 2.58:1 (below 3:1 non-text), Doelwaarde abbr 3.32:1 and KPI abbr 4.17:1 (pass only as large text), desc 12.8px #666.

## Priority issues
1. [P0] Flat row of four peers teaches a pipeline; the lesson structure is a tree. Fix: intro becomes a miniature of the ladder with the restaurant example (Doel bar, 2-3 KSF stubs, one KPI + doelwaarde). /impeccable layout
2. [P1] Cliché AI spot illustrations (blob, leaves, dash lines, shiny 3D gold gears; clashes with Ben). Fix: drop them or replace with content. /impeccable distill
3. [P1] Four redundant text levels (KPI says the same thing three times). Fix: two levels: term + expansion, then the lesson's sentence frame filled with the example. /impeccable clarify
4. [P2] Type and color details: question (Raleway 800 14.7px) outranks name (Arial 700 13.6px); desc 12.8px; template-style 5px top border on rounded card; arrow 2.58:1. /impeccable typeset
5. [P2] Semantics: divs not headings, no list, arrow is generated content. Fix: ol + h3, aria-hidden connectors. /impeccable audit

## Personas
- First-timer: cannot see one Doel has several KSF; no example chain; no dagtaak warning before the quiz.
- Screen reader: no headings to jump, order not announced.
- Exam reviewer: no official sentence frames; definitions spread over 4 lines.

## Minor
Phone stack 1279px for ~120 words; 2x2 layout at 620-900px reads as a Z without arrows; only Doel has an example; callout repeats the lead.
