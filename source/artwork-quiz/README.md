# Drie situaties — twaalf kaarten

## Afbeeldingen
- situatie-webshop.png: sportschoen, schoendoos en tas.
- situatie-it-helpdesk.png: monitor met headset.
- situatie-fitnesscentrum.png: halter, sportmat en drinkfles.

Alle drie zijn transparante PNG's van 1536 × 1024 pixels, gemaakt met de ingebouwde image_gen-tool in de afgesproken papierstijl. Gebruik circa 110–145 CSS-pixels breed naast de situatienaam; 40–55 pixels in de groepsnavigatie. Gebruik alt="" omdat de tekst de situatie al benoemt.

## Klikbaar vormgevingsvoorstel
Open voorstel.html; CSS en JavaScript zitten in aparte bestanden. Geen externe libraries, lettertypes of netwerkverzoeken. Alle twaalf kaartteksten en de drie doelen zijn overgenomen van de oorspronkelijke pagina: https://janc-pxl.github.io/TijdVoorKwaliteit/kwaliteit.html

De navigatie, antwoordselecties en situatiewissels werken. Dit is een lokaal ontwerpvoorbeeld; er is geen beoordeling van antwoorden. De bestaande website is niet aangepast.

## Ontwerpkeuzes
1. Twaalf losse bolletjes worden drie groepen met een situatienaam. In elke groep zijn de bolletjes genummerd van 1 tot 4; kaartbereiken en extra aantallen zijn weggelaten.
2. De huidige groep krijgt een goudkleurig kader. De actieve kaart is zwart gevuld. Dit is een positieweergave, geen voortgangsscore.
3. De situatie heeft een blijvende kop met illustratie, situatienaam en doel. Dubbele kaarttellers en extra uitleg over de aantallen zijn weggelaten.
4. Op kaart 4 heet de knop "Naar IT-helpdesk →"; op kaart 8 "Naar Fitnesscentrum →". Zo wordt de wissel vooraf aangekondigd.
5. Bij elke overstap naar een andere situatie, ook bij teruggaan of rechtstreeks springen, verschijnt "Nieuwe situatie: … Lees het nieuwe doel." De melding blijft staan tot de volgende interactie; er is geen timer.
6. Een aparte aria-live-regio kondigt situatie, doel en kaarttekst aan bij navigatie. De banner heeft role="status"; de huidige kaart heeft aria-current="step".
7. De bestaande categorie-kleuren goud, blauw, groen en grijs behouden hun betekenis. Situaties worden onderscheiden met naam, beeld en groepering; er worden geen nieuwe scenario-kleuren gebruikt.
8. Op mobiel staan de drie navigatiegroepen onder elkaar en de antwoordknoppen in twee kolommen.

## Aansluiten op de bestaande quiz
Gebruik de beelden en structuur met de bestaande quizlogica. Vervang die beoordelingslogica niet door de voorbeeldselectie uit voorstel.js.

Bij een nulgebaseerde kaartindex:
```js
const situationIndex = Math.floor(cardIndex / 4); // 0, 1, 2
const localCardNumber = (cardIndex % 4) + 1;      // 1 tot 4
const situationChanged =
  Math.floor(previousCardIndex / 4) !== situationIndex;
```
Werk bij elke kaartwissel tegelijk de situatienaam, illustratie, het doel en gemarkeerde navigatiegroep bij. Koppel de banner aan situationChanged, niet uitsluitend aan kaart 5 of 9: zo worden rechtstreekse sprongen en terugnavigatie ook goed behandeld. Bij de eerste render hoeft geen wisselmelding te verschijnen.

Gebruik de bestaande telling van beoordeelde kaarten voor de echte voortgangsbalk. Het voorbeeld telt alleen kaarten met een gekozen antwoord.

## Controle
Desktop: de overstappen 4→5 en 8→9 gecontroleerd. Mobiel: gecontroleerd op een viewport van 390 pixels; geen horizontale overloop en alle afbeeldingen geladen. De lokale voorbeeldquiz bewaart keuzes bij heen- en terugnavigatie zolang het document open blijft.

voorbeeld-it-helpdesk.jpg toont de desktopweergave bij de overstap naar kaart 5.


