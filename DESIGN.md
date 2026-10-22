---
name: Tijd voor kwaliteit
description: Interactieve lespagina kwaliteitsmanagement, PXL Projectmanagement
colors:
  primary: "#030203"
  gold: "#AE9A64"
  page-bg: "#f8f7f5"
  card: "#ffffff"
  border: "#e0ddd6"
  text: "#1a1a1a"
  muted: "#666666"
  surface-soft: "#f6f5f2"
  surface-sunk: "#f3f1ec"
  surface-chip: "#efece5"
  ink-soft: "#6f695e"
  ink-faint: "#8f897d"
  line-strong: "#8a8578"
  line-dashed: "#c9c4b8"
  line-control: "#d6d1c6"
  concept-doel: "#030203"
  concept-ksf: "#AE9A64"
  concept-ksf-dark: "#7a6535"
  concept-kpi: "#5b7fa6"
  concept-kpi-dark: "#46698f"
  concept-target: "#2a9d8f"
  concept-target-dark: "#1f7a6f"
  concept-task: "#8a8a8a"
  concept-task-dark: "#5f5f5f"
  quality: "#c2410c"
  quality-dark: "#a3360a"
  grade: "#8b5cf6"
  grade-dark: "#6d3fd6"
  accuracy: "#0e7490"
  precision: "#a21caf"
  invest: "#3b74c4"
  invest-dark: "#2f5fa3"
  fail: "#d1495b"
  fail-dark: "#b3263a"
  ok-bg: "#eef6f2"
  ok-line: "#b7d9cd"
  err-bg: "#fbefeb"
  err-line: "#e6c3ba"
  err-ink: "#b3261e"
  hint-bg: "#f4efe2"
  hint-line: "#ddd2b4"
typography:
  headline:
    fontFamily: "Raleway, sans-serif"
    fontSize: "2rem"
    fontWeight: 900
  title:
    fontFamily: "Raleway, sans-serif"
    fontSize: "1.15rem"
    fontWeight: 800
  label:
    fontFamily: "Raleway, sans-serif"
    fontSize: "0.88rem"
    fontWeight: 800
  body:
    fontFamily: "Arial, system-ui, sans-serif"
    fontSize: "0.95rem"
    lineHeight: 1.55
rounded:
  panel: "12px"
  card: "8px"
  small: "6px"
components:
  panel:
    backgroundColor: "{colors.card}"
    rounded: "{rounded.panel}"
  status-ok:
    backgroundColor: "{colors.ok-bg}"
    textColor: "{colors.concept-target-dark}"
  status-error:
    backgroundColor: "{colors.err-bg}"
    textColor: "{colors.err-ink}"
  status-hint:
    backgroundColor: "{colors.hint-bg}"
    textColor: "{colors.concept-ksf-dark}"
---

# Design System: Tijd voor kwaliteit

De tokens staan in `:root` bovenaan de `<style>` van `kwaliteit.html`; de gedeelde componenten volgen in het blok "DESIGN SYSTEM: GEDEELDE COMPONENTEN". Er is geen apart bestand: de pagina blijft één HTML-bestand zonder build.

## Overview

Een rustige, warme lespagina in de PXL-huisstijl: zwart, goud en een gebroken witte achtergrond. Elke oefening is één wit **paneel** op die achtergrond. Binnen een paneel scheiden dunne lijnen de delen; er staan geen kaarten in kaarten. De kleur komt van de **begrippen**: elk begrip heeft één vaste kleur die overal terugkomt, zodat studenten aan de kleur herkennen waarover het gaat.

Wat studenten juist doen, blijft zichtbaar staan: een overzicht dat zich vult, een matrix met fiches, een tijdlijn met chips. Zo wordt het resultaat van de oefening meteen de samenvatting.

**Key characteristics:**
- Eén paneel per oefening, dunne scheidingslijnen erbinnen.
- Vaste begripskleuren, met een donkere variant voor kleine tekst.
- Labels in gewone schrijfwijze; geen hoofdletterlabels behalve de huisstijlbadge boven een sectietitel.
- Status met zachte tinten (juist, fout, na een hint), niet met dikke gekleurde randen.

## Colors

### Primary
- **PXL-zwart** (`--primary`, #030203): titels, de zwarte doelbalk in elk overzicht, primaire knoppen.
- **PXL-goud** (`--gold`, #AE9A64): huisstijlbadge, actieve stappen, voortgangsbalken.

### Begripskleuren
Elk begrip heeft een vaste kleur (`--c-*`). Voor tekst kleiner dan 18px gebruik je de donkere variant (`--c-*-dark`), die op wit minstens 4.5:1 haalt.

| Begrip | Kleur | Donker (kleine tekst) |
|---|---|---|
| Doel | `--c-doel` #030203 | (zelfde) |
| KSF | `--c-ksf` #AE9A64 | `--c-ksf-dark` #7a6535 |
| KPI | `--c-kpi` #5b7fa6 | `--c-kpi-dark` #46698f |
| Doelwaarde | `--c-target` #2a9d8f | `--c-target-dark` #1f7a6f |
| Gewone dagtaak | `--c-task` #8a8a8a | `--c-task-dark` #5f5f5f |
| Kwaliteit / Uitwerking | `--c-quality` #c2410c / `--c-grade` #8b5cf6 | `--c-quality-dark` #a3360a / `--c-grade-dark` #6d3fd6 |
| Nauwkeurigheid / Precisie | `--c-accuracy` #0e7490 / `--c-precision` #a21caf | (al donker genoeg) |
| Investeren / Kost van fouten | `--c-invest` #3b74c4 / `--c-fail` #d1495b | `--c-invest-dark` #2f5fa3 / `--c-fail-dark` #b3263a |

### Neutral
- **Pagina** (`--bg`, #f8f7f5) en **paneel** (`--card`, #ffffff) met **rand** (`--border`, #e0ddd6).
- **Zacht vlak** (`--surface-soft`, #f6f5f2): notities, voorbeelden, hover.
- **Verzonken vlak** (`--surface-sunk`, #f3f1ec): de zijkolom met het overzicht naast een opdracht.
- **Chip** (`--surface-chip`, #efece5): neutrale statuschip, voorbeeldvak.
- **Zachte tekst** (`--ink-soft`, #6f695e) en **vage tekst** (`--ink-faint`, #8f897d, enkel groot of decoratief).
- **Lijnen**: `--line-strong` (#8a8578) voor verbindingen in bomen en tijdlijnen, `--line-dashed` (#c9c4b8) voor lege plaatsen, `--line-control` (#d6d1c6) voor uitgeschakelde bedieningen.

### Status
- **Juist**: `--ok-bg` #eef6f2 met `--ok-line` #b7d9cd, tekst in `--c-target-dark`.
- **Fout**: `--err-bg` #fbefeb met `--err-line` #e6c3ba, tekst in `--err-ink` #b3261e.
- **Na een hint**: `--hint-bg` #f4efe2 met `--hint-line` #ddd2b4, tekst in `--c-ksf-dark`.

### Named Rules
**De vaste-kleurregel.** Een begrip heeft overal dezelfde kleur. Nieuwe secties gebruiken de bestaande `--c-*`-tokens en bedenken geen nieuwe kleur voor een bestaand begrip.

**De kleine-tekstregel.** Kleine tekst in een begripskleur gebruikt altijd de `-dark`-variant.

## Typography

**Titels en labels:** Raleway (600 tot 900). **Lopende tekst:** Arial / system-ui.

- **Sectietitel** (h2, Raleway 900, 2rem).
- **Deeltitel** (h3, Raleway 800, 1.15rem, met "Deel n" ervoor).
- **Titel in een paneel** (Raleway 900, 1.1 tot 1.4rem).
- **Label** (Raleway 800, ongeveer 0.86 tot 0.95rem, gewone schrijfwijze).
- **Tekst** (Arial, 0.9 tot 0.98rem, regelhoogte 1.5 tot 1.55).
- **Cijfers in metingen en formules**: `font-variant-numeric: lining-nums` (Raleway heeft standaard mediaevale cijfers).

### Named Rules
**De gewone-schrijfwijzeregel.** Geen labels in hoofdletters met letterspatiëring. Enige uitzondering: de goudkleurige huisstijlbadge boven een sectietitel (gedeeld met de zusterrepos).

## Layout

Maximaal 1100px breed, één kolom per sectie. Een oefening gebruikt vaak twee kolommen in één paneel: links de opdracht, rechts wat zich vult (of omgekeerd). Vaste breekpunten in het bestand: 1000px (zijkolommen worden bovenaan gestapeld), 900px, 760px, 720px, 620px en 420px. Op een gsm gaat alles onder elkaar; wat de student eerst moet lezen (het doel, de schijf) komt bovenaan.

## Elevation & Depth

Plat. Diepte komt van tonen: een wit paneel op de warme pagina, een verzonken zijkolom in het paneel. Schaduwen alleen voor zwevende elementen zoals de tooltip in de kostengrafiek.

## Shapes

- **Paneel**: `--r-panel` (12px).
- **Kaart, vak, knop in een paneel**: `--r-card` (8px).
- **Chip in een rij, feedback, invoerveld**: `--r-small` (6px). Ronde fiches en tokens gebruiken een volle pil.
- Randen zijn 1px (`--border`) of 1.5px voor klikbare vakken. Geen gekleurde zij- of bovenbalken op afgeronde kaarten.

## Components

**Paneel** (`.panel`): het witte werkvlak met dunne rand en `--r-panel`. Gebruikt door de Campi-oefening, de twee assenpanelen, de twee plaatsingsborden, de schietschijf, de stappenkaders (Spotify, visgraat, correlatie), de kostentabel, de tijdlijn, de Poka Yoke-vergelijking en de introductiepanelen. Binnenin scheiden dunne lijnen (`border-top: 1px solid var(--border)`) de delen.

**Mappentabs** (`.ladder-tabs` + `.ladder-tab`, met `.ladder-panel`): voorbeelden of situaties als tabs bovenop één paneel. De actieve tab is wit en loopt door in het paneel. Gebruikt in de KSF-ladder en de KSF-quiz.

**Stappenbalk** (`.spot-steps`): genummerde stappen met een balk erboven (goud = gezien, zwart = huidig); de kolommen volgen het aantal stappen. Gebruikt in Spotify, de visgraat en het correlatievoorbeeld.

**Assenmatrix** (`.bm`): een 2x2-matrix waarbij de knoppen Hoog/Laag de assen zelf zijn. Kleuren per as via `--yd`/`--xd`/`--yt`/`--xt` (`.bm-np` voor nauwkeurigheid/precisie).

**Plaatsingsbord** (`.place-board` met `.pm-cell` en `.pm-token`): links de opdracht, rechts een grote matrix die zich vult met genummerde fiches (groen = in één keer juist, donkergoud = na een hint). Gebruikt in kwaliteit/uitwerking en nauwkeurigheid/precisie.

**Overzicht dat zich vult**: een zwarte doelbalk met daaronder plaatsen die zich vullen tijdens de oefening (`.cl`, `.qz-ladder`, `.campi-tree`). Lege plaatsen hebben een stippelrand (`--line-dashed`), verbindingslijnen gebruiken `--line-strong`.

**Feedback** (`benFeedback`, `.campi-feedback`): een tint in de statuskleuren met een volledige dunne rand. Ben verschijnt bij hints en succes volgens de regels in CLAUDE.md.

## Do's and Don'ts

- **Do** gebruik `.panel` voor elk nieuw werkvlak en scheid de delen erbinnen met dunne lijnen.
- **Do** laat wat de student juist doet zichtbaar staan (fiches, chips, een overzicht dat zich vult).
- **Do** gebruik tokens; een nieuwe kleur die vaker dan twee keer terugkomt, wordt een token in `:root` en komt in dit document.
- **Don't** zet kaarten in kaarten, en gebruik geen gekleurde zijbalk of dikke gekleurde bovenrand als accent.
- **Don't** gebruik hoofdletterlabels, behalve de huisstijlbadge.
- **Don't** gebruik het woord "ladder" buiten Deel 1 van KSF en KPI (zie CLAUDE.md).
