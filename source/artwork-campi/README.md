# Campi — begeleide UX

Open index.html met flow.css en flow.js in dezelfde map. Dit is een werkend lokaal UX-prototype; de bestaande website is niet gewijzigd. Het onderdeel "Nu jij — KSF'en voor je eigen project" is niet opgenomen.

## Flow

1. KSF'en kiezen: kies vier uit acht, controleer daarna je selectie. De student kan fouten herstellen. Na de juiste selectie verschijnt een expliciete knop om verder te gaan. Een bevestigde selectie kan via "Selectie aanpassen" opnieuw worden bekeken en gewijzigd.
2. KSF'en uitwerken: één factor tegelijk. Kies en controleer de KPI; kies daarna expliciet om naar de doelwaarde te gaan. Na controle blijft de uitleg staan. De volgende factor wordt pas beschikbaar als alle eerdere factoren volledig zijn uitgewerkt: zowel KPI als doelwaarde moeten juist zijn gecontroleerd. Dit geldt voor de knop Volgende KSF en de vier factornamen. Teruggaan blijft mogelijk, met behoud van keuzes. Een gewijzigde KPI maakt een eerdere doelwaarde ongeldig; deze moet opnieuw gekozen en gecontroleerd worden.
3. Overzicht: beschikbaar zodra de vier factoren compleet zijn. Toont de ingevulde tabel, met een knop om iedere factor terug te bekijken. De afronding benadrukt het verschil tussen factoren opvolgen en het bedrijfsdoel meten.

Het SMART doel blijft op brede schermen tijdens scrollen bovenaan zichtbaar. Op mobiel staat het gewoon boven de oefening om ruimte te bewaren. Geen automatische sprongen na antwoorden. Feedback staat bij de betreffende vraag. Voortgang wordt via localStorage in deze browser bewaard; "Opnieuw oefenen" en "Voortgang wissen" vragen eerst bevestiging.

## Inhoud

De oorspronkelijke Campi-oefening is doorlopen op https://janc-pxl.github.io/TijdVoorKwaliteit/kwaliteit.html#ksf-campi. Introductie, kandidaten, antwoordkeuzes, feedback bij juiste en foutieve antwoorden en de drie cursuszinnen zijn overgenomen uit het origineel. Iedere juiste factor krijgt na controle zijn eigen verklaring, die zichtbaar blijft bij die kaart. Alleen navigatie, begeleiding en de aanvullende slottoelichting hebben nieuwe teksten.

Bij bekendheid is ook de oorspronkelijke formulering "na de eerste lesweek" hersteld. De doelwaarde houdt de oorspronkelijke deadline "tegen eind september". Dit verschil in meetmoment komt uit het origineel; eventuele inhoudelijke harmonisatie is een aparte redactionele keuze.

De UI volgt de eerder gekozen papierstijl: warme achtergrond, ingetogen gouden KSF-accenten, blauwe KPI-panelen en groene doelwaardepanelen. De decoratieve Campi-illustratie heeft een transparante achtergrond en staat in artwork/campi-campus.png. De kandidaten krijgen vooraf geen illustraties die de juiste keuzes verklappen. PROMPTS.md bevat het gebruikte prompt voor het ingebouwde imagegen-gereedschap.

## Gecontroleerd

- Foutieve KSF-selectie corrigeren.
- Foutieve KPI en doelwaarde aanpassen en opnieuw controleren.
- Alle vier factoren afwerken en de eindtabel bekijken.
- Teruggaan vanuit de tabel en een KPI wijzigen: de oude doelwaarde en afrondingsstatus vervallen.
- Herladen bewaart voortgang.
- Weergave op 390 pixels breed: geen horizontale pagina-overloop. De tabel kan op kleine schermen afzonderlijk horizontaal scrollen.
- JavaScript-syntax gecontroleerd.

Een opgeslagen voorbeeld-uitwerken.jpg toont een volledig uitgewerkte factor; de live prototypeweergave kan op een andere stap staan.



De factorkaarten zijn selecteerbare knoppen zonder zichtbare checkbox. Rand en achtergrondkleur tonen de selectie; aria-pressed geeft dezelfde status door aan hulptechnologie. Enter en spatie werken voor selecteren en deselecteren.
