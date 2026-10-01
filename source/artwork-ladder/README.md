# Artwork — Tijd voor Kwaliteit

14 losse PNG-afbeeldingen met transparante achtergrond, in de afgesproken editorialstijl met papiertextuur. De beelden zijn met de ingebouwde image_gen-tool afzonderlijk gemaakt; kleine details kunnen afwijken van de compositievoorbeelden.

## Bestanden

| Onderdeel | Bestand |
|---|---|
| Intro: Doel | intro-doel.png |
| Intro: KSF | intro-ksf.png |
| Intro: KPI | intro-kpi.png |
| Intro: Doelwaarde | intro-doelwaarde.png |
| Restaurant: Marktaandeel | restaurant-marktaandeel.png |
| Restaurant: Klantentevredenheid | restaurant-klantentevredenheid.png |
| Restaurant: Kwaliteit van het eten | restaurant-kwaliteit-eten.png |
| Fabrikant: Hoge productkwaliteit | fabrikant-productkwaliteit.png |
| Fabrikant: Hoge procesopbrengsten | fabrikant-procesopbrengsten.png |
| Fabrikant: Lage productiekosten | fabrikant-productiekosten.png |
| Fabrikant: Marktaandeel | fabrikant-marktaandeel.png |
| Tab: Restaurant | tab-restaurant.png |
| Tab: Wasmachinefabrikant | tab-wasmachinefabrikant.png |
| Inzicht / opmerking | inzicht-lampje.png |

## Plaatsing

Gebruik de KSF-illustraties klein rechts in de goldkleurige kaarten, ongeveer 80–100 CSS-pixels breed. Hergebruik dezelfde afbeelding op ongeveer 40–48 pixels naast de dynamische titel van het uitlegblok. De tabafbeeldingen kunnen 24–28 pixels breed worden. De introbeelden zijn geschikt voor ongeveer 240–300 pixels breed. Dit zijn startmaten; pas ze aan de beschikbare ruimte aan.

De beelden zijn decoratief bij tekst die dezelfde betekenis al benoemt. Gebruik daarom alt="" zodat schermlezers de informatie niet dubbel voorlezen. Gebruik geen afbeelding als vervanging van kaarttekst, quizstatus of numerieke waarden.

Voorbeeld:

```html
<img class="ksf-artwork"
     src="images/restaurant-marktaandeel.png"
     alt=""
     loading="lazy"
     decoding="async">
```

```css
.ksf-artwork {
  display: block;
  width: 90px;
  max-width: 30%;
  height: auto;
  object-fit: contain;
  flex-shrink: 0;
}
```

Bewaar ruimte tussen titel en afbeelding, liefst met flex of grid. Verberg of verklein de decoratieve afbeelding op smalle schermen als de titel anders in de knel komt.

De originele bestanden zijn ruim bemeten (1536 × 1024; tabs 1254 × 1254). Voor een lichte website kun je zelf kleinere PNG- of WebP-versies exporteren met behoud van alpha. Het pakket bevat de originelen.

## Overzicht

Open overzicht.html voor een galerij met alle losse beelden op lichte en donkere achtergrond. In voorbeelden/ staan de drie compositievoorbeelden ter referentie; gebruik de losse bestanden voor de webpagina. PROMPTS.md bevat de generatieprompts van deze levering.

