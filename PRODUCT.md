# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Bachelor students in their 2nd and 3rd year at Hogeschool PXL, following the "Projectmanagement" course. They have already worked on projects, so they can apply the concepts to a project of their own. They use the page in three situations:

- during the lesson, working through the exercises in class on 1920x1080 screens;
- at home for self-study, at their own pace after the lesson;
- before the exam, to practise the material again.

## Product Purpose

An interactive learning page for the lesson "Kwaliteitsmanagement" (`source/004 Kwaliteitsmanagement.md`, published at https://janc-pxl.github.io/pxl-projectmanagement-2627/004-kwaliteitsmanagement). Each concept from the lesson becomes something students do rather than read: climb, sort, place, shoot, draw, plot.

The page has succeeded when students can do all three:

1. **Tell related concepts apart:** KSF vs KPI vs doelwaarde vs dagtaak, kwaliteit vs uitwerking, nauwkeurigheid vs precisie, correlatie vs oorzaak.
2. **Apply them to a new project:** for example, write the KSF'en and KPI's for their own project or for Campi.
3. **Stay more engaged** than in a plain lecture.

## Positioning

Part of a series of single-page learning apps for the same course: AgileForNigel, TeachBertPERT, PMTheBasics and this one. All follow the same lesson text and the same PXL house style. What sets this series apart is that each exercise uses the lesson's own examples (restaurant, witgoedfabrikant, hamburger, schietschijf, Spotify, garage, Internet Explorer) plus the recurring fictional project Campi, which also appears in AgileForNigel.

## Operating Context

- In class, the lecturer walks through the lesson and students do the matching exercise on their own screens.
- At home, students revisit sections on their own. Progress for the longer exercises (Campi, visgraat drawing) is kept in the browser with `localStorage`.
- Hosted on GitHub Pages; the page is opened by link from the course site.

## Capabilities and Constraints

- One file, `kwaliteit.html`, with inline CSS and JS. No build step and no framework. Deployed by GitHub Actions on every push to `main`.
- A single scrolling page; the nav links are anchor jumps.
- Max width 1100px, tuned for 1920x1080 student screens. The page also has phone layouts, but phones are not a hard requirement.
- All user-visible content is in Dutch. No em dashes in visible text.
- Lesson terminology is kept as-is: Doel, KSF, KPI, Doelwaarde, dagtaak, kwaliteit, uitwerking, nauwkeurigheid, precisie, Poka Yoke, visgraatdiagram, correlatiediagram.

## Brand Commitments

- PXL Hogeschool house style (`source/2025_10_huisstijlhandboek.pdf`, logo in `source/`), shared with the sibling repos.
- Ben, the recurring guide character, is used under the rules in `source/artwork-ben/IMPLEMENTATIE.md`. He never gives away an answer and never looks worried after a wrong answer.
- Each concept keeps one fixed color across the whole page.

## Evidence on Hand

- The lesson text and its figures: `source/004 Kwaliteitsmanagement.md`.
- Illustrations and photos with their design notes in `source/artwork-*/` and `source/*.webp`.
- No student feedback, usage data or learning results have been collected. Do not invent them.

## Product Principles

1. **Stay true to the lesson.** Definitions and examples follow the lesson text. Nothing may contradict it, and invented additions must be clearly fictional (Campi, Lotte).
2. **Learn by doing, then discuss.** Every concept gets an interaction where the student decides first, and feedback explains why.
3. **Hints, not answers.** Wrong answers get a hint that points to the dimension the student missed. They are not shamed and the answer is not simply revealed.
4. **Contrast teaches.** Concepts that look alike sit side by side so students learn to tell them apart.
5. **Private and local.** No accounts, no tracking, no data leaves the browser.

## Accessibility & Inclusion

WCAG 2.1 AA is a hard requirement: full keyboard use, screen reader support (live regions, `aria-pressed`, `aria-current`, decorative images with `alt=""`), sufficient contrast, and respect for `prefers-reduced-motion`.
