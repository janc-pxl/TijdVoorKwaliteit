# Ben toevoegen aan de kwaliteitspagina

## Opdracht

Pas de bestaande pagina https://janc-pxl.github.io/TijdVoorKwaliteit/kwaliteit.html aan met de meegeleverde Ben-illustraties. Ben is een terugkerende, subtiele begeleider. Behoud de bestaande teksten, inhoudelijke illustraties, oefenlogica en voortgang. Deze opdracht betreft het toevoegen van Ben aan de bestaande UI, geen herontwerp van de oefeningen.

Bekijk eerst de actuele pagina en de bestaande code. De hieronder genoemde titels en anker-ID's zijn aanknopingspunten; controleer ze voordat je wijzigingen maakt. Werk in de bronbestanden van de website. Publiceer alleen als de opdrachtgever dat ook heeft gevraagd.

## Uitgangspunt

Gebruik een beperkt aantal vaste plaatsingen, aangevuld met Ben in feedback en bij afronding. Voeg geen tekstballonnen, extra tellers, herhaalde instructies of labels zoals 'Ben zegt' toe. Laat bestaande teksten het werk doen. Ben mag nooit een antwoord verraden voordat de student een keuze heeft gemaakt.

De assets hebben een transparante achtergrond. De kleine donkere baardvlek onmiddellijk onder de onderlip is in alle zes poses verwijderd. Gebruik uitsluitend deze gecorrigeerde bestanden.

## Bestanden

| Bestand | Betekenis |
|---|---|
| `artwork/ben-welcoming.png` | Welkom, begin van de pagina |
| `artwork/ben-thinking.png` | Reflectie en zelfstandig nadenken |
| `artwork/ben-explaining.png` | Hint, uitleg of belangrijke conclusie |
| `artwork/ben-encouraging.png` | Een juist antwoord of tussentijds succes |
| `artwork/ben-completed.png` | Een volledige oefening afgerond |
| `artwork/ben-worried.png` | Een probleem in een simulatie; niet voor een fout antwoord van de student |

Kopieer de assets naar een passende map in het project, bijvoorbeeld `images/ben/`. Pas de verwijzingen aan de bestaande projectstructuur aan. De illustraties hoeven niet allemaal tegelijk of even vaak gebruikt te worden.

## Aanbevolen basisimplementatie

### 1. Welkom bovenaan

Plaats `ben-welcoming.png` naast de introductietekst onder 'Kritische Succesfactoren & Kritische Prestatie-Indicatoren' (sectie `ksf-kpi`). Houd de keten Doel → KSF → KPI → Doelwaarde intact. Zet Ben niet in één van deze vier begripskaarten.

Richtmaat: 110–140 px breed. Behoud de ruimte voor de titel en tekst; laat de illustratie niet de hoogte van een groot hero-blok bepalen.

### 2. Campi: factoren kiezen

Plaats `ben-thinking.png` naast de bestaande instructie bij 'Welke factoren zijn écht kritisch?' in 'Deel 3 Stel zelf KSF'en en KPI's op voor Campi' (`ksf-campi`, onderdeel `campi-select`). Buiten de keuzebuttons. De geselecteerde buttons blijven herkenbaar door border en kleur, zonder extra zichtbare checkbox.

Richtmaat: 110–140 px. Behoud de uitleg waarom gekozen factoren juist of fout zijn, en behoud het uitwerken van een KSF voordat de student naar de volgende KSF mag.

### 3. Feedback in antwoordoefeningen

Voeg één gedeeld patroon toe aan de bestaande feedbackvlakken, te beginnen bij 'KSF, KPI, doelwaarde of gewone dagtaak?' (`ksf-quiz`). Gebruik hetzelfde patroon waar passend bij:

- 'Plaats het in de matrix' (`ku-place`);
- 'Herken het patroon' (`np-place`);
- 'Investering of kost van fouten?' (`koq-sort`);
- de antwoordfeedback in correlatieoefeningen (`cor-oef`).

| Toestand | Weergave |
|---|---|
| Nog niet geantwoord, geen feedback | Geen Ben in het feedbackvlak |
| Onjuist antwoord met een hint | `ben-explaining.png` naast de bestaande hint |
| Juist antwoord, ook na een hint | `ben-encouraging.png` naast de bestaande uitleg |
| Volledige oefening afgerond | `ben-completed.png` bij een afrondingsblok |

Richtmaat voor antwoordfeedback: 70–90 px breed. Plaats Ben consequent links van de tekst, zonder over de antwoordbuttons te vallen. Laat geen lege ruimte voor een nog verborgen feedbackvlak staan. Houd de feedbacktekst en de voortgang in één keer juist / juist na een hint intact. Een fout antwoord krijgt geen bezorgde of afkeurende Ben.

Koppel de pose aan de bestaande toestanden in de code. Leid succes niet af uit alleen de huidige kaartpositie: het bezoeken van de laatste kaart betekent niet dat de oefening voltooid is.

### 4. Correlatie en oorzaak

Plaats `ben-explaining.png` bij de bestaande toelichting in de stap 'Oorzaak?' van 'Correlatie is geen oorzakelijk verband' (`cor-cause`). Toon hem bij die stap, niet voortdurend bij alle grafieken.

Richtmaat: 110–140 px. Ben mag de grafiek, de assen of de navigatie niet verkleinen of overlappen.

### 5. Volledige afronding

Gebruik `ben-completed.png` bij het volledig afronden van de Campi-oefening, van een antwoordreeks en van 'De checklist van de garagist' (`py-checklist`).

- Campi: pas als alle vereiste factoren zijn uitgewerkt; het openen van 'Overzicht' is op zichzelf geen succescriterium.
- Antwoordreeksen: pas als alle antwoorden volgens de bestaande logica zijn afgerond.
- Garagist: bij het succesvol teruggeven van de auto nadat alle checkliststappen zijn voltooid.

Richtmaat: 110–140 px. Gebruik één afrondingsmoment per oefening. Als bij de laatste kaart tegelijk antwoordfeedback en een apart afrondingsblok zichtbaar zijn, laat Ben alleen in het afrondingsblok staan. Voeg uitsluitend wanneer nodig een korte, feitelijke zin toe, bijvoorbeeld 'Alle kaarten afgewerkt.' Gebruik geen modal, confetti of animatie.

## Optionele uitbreidingen

Deze plaatsen zijn ideeën voor een volgende iteratie, geen noodzakelijke toevoegingen. Implementeer de basis eerst en beoordeel de rust van de pagina.

| Onderdeel | Optionele plaatsing |
|---|---|
| 'Nu jij: KSF'en voor je eigen project' (`ksf-eigen`) | Denkende Ben bij 'Zo klinkt jouw redenering'. De controles zijn hulpmiddelen; toon geen voltooiingspose alsof de inhoud automatisch inhoudelijk is goedgekeurd. |
| Hamburger en schietschijf (`ku-burger`, `np-schijf`) | Uitleggende Ben bij een samenvattende conclusie nadat alle vier combinaties zijn ontdekt. De bestaande visualisatie blijft centraal. |
| 'Zoek de balans' (`koq-balans`) | Uitleggende Ben naast een conclusie. Geen posewisseling bij iedere sliderbeweging en geen pose die de juiste zone vooraf verklapt. |
| 'Poka Yoke in Campi' (`py-campi`) | Bezorgde Ben bij een daadwerkelijk toegelaten fout in de simulatie. Denkende/uitleggende Ben bij de reflectie. Niet bij elk invoerveld en niet bij een gewone validatiemelding. |

Bij de acht voorwerpen in 'Poka Yoke rondom je' zijn de inhoudelijke illustraties al voldoende. Voeg daar geen Ben toe aan elke kaart.

## Vormgeving en toegankelijkheid

- Sluit aan op de warme achtergrond, rustige kaders en bestaande goud-, blauw- en turquoise-accenten. Voeg geen extra gekleurde badge achter Ben toe.
- Houd de oorspronkelijke verhoudingen: `height: auto`, geen vervorming, geen uitsnede van gezicht of handen. Gebruik zo nodig `object-fit: contain`.
- Desktop: feedbackbeeld 70–90 px; introductie of conclusie 110–140 px. Stem dit af op de beschikbare ruimte, niet op een vaste hoogte van tekstblokken.
- Mobiel: tekst krijgt voorrang. Verklein feedbackbeelden naar circa 56–64 px en introductiebeelden naar circa 80–100 px, of zet Ben boven de tekst. Verberg een decoratieve pose als die de leesbaarheid aantoonbaar vermindert. Geen horizontale scroll.
- Behoud de tekst als echte HTML. Als de tekst dezelfde boodschap draagt, gebruik `alt=""` voor de afbeelding. Als de afbeelding zelfstandig betekenis draagt, geef een korte functionele alttekst.
- Laat bestaande toetsenbordbediening, focusgedrag en feedbackaankondigingen intact. Ben verandert de betekenis van een antwoord niet; de tekst vermeldt zelf de uitkomst. Gebruik geen kleur of pose als enige indicator.
- Reserveer waar zinvol de beeldverhouding om verspringen te beperken. Laad afbeeldingen lager op de pagina lui. Vermijd extra animaties.

## Controles voor oplevering

1. Controleer de vaste plaatsingen op desktop en op een smal mobiel scherm.
2. Test een fout antwoord, een juist antwoord na een hint, een meteen juist antwoord, navigeren naar een andere kaart en herbezoeken van een antwoord.
3. Controleer dat Ben verdwijnt of correct wisselt bij een nieuwe toestand; geen oude pose of oude feedback laten staan.
4. Controleer afronding pas na de werkelijke voltooiingscriteria. Test ook hervatten van opgeslagen voortgang.
5. Controleer dat Campi's originele uitleg, selectiefeedback en blokkering van de volgende onvolledige KSF behouden blijven.
6. Controleer de garagist vóór en na volledige checklist en het teruggeven van de auto.
7. Controleer toetsenbordbediening, leesbaarheid en dat afbeeldingen geen bediening of grafiek bedekken.
8. Lever een korte wijzigingsbeschrijving en screenshots van welkom, hintfeedback, Campi en afronding op.

## Aanpak voor een eerste visuele proef

Wanneer eerst een preview gewenst is: begin met Campi's factorkeuze, één quizfeedbackvlak en één afrondingsmoment. Daarmee kan de subtiliteit worden beoordeeld voordat hetzelfde patroon over de pagina wordt uitgerold. Deze zip bevat de assets en instructie; de live website is hiermee nog niet aangepast.
