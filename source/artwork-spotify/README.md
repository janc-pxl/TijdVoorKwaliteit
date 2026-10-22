# Albumhoezen voor het Spotify-voorbeeld

24 albumhoezen voor Deel 3 "Aanbevelingen op Spotify" in Nauwkeurigheid versus precisie:
4 nummers uit Lottes luistergeschiedenis, 10 aanbevelingen en 10 zelf ontdekte nummers.

## Bron
Opgehaald via de iTunes Search API (`itunes.apple.com/search`, land BE) op basis van titel en artiest.
De gevonden track, artiest en album staan in `_matches.json`. "DtMF" (Bad Bunny) gebruikt de hoes van het album
*DeBÍ TiRAR MáS FOToS*; "Europapa" de hoes van de single.

## Bestanden
- Hier: de originelen, 600 x 600 px, JPEG q92, met de slug van de titel als bestandsnaam.
- In `img/`: `spot-<slug>.jpg`, 260 x 260 px, JPEG q84 (op de pagina ongeveer 130 px breed, dus scherp op 2x).

## Auteursrecht
De hoezen zijn auteursrechtelijk beschermd en horen bij de platenlabels en artiesten. Ze staan hier enkel ter
illustratie in niet-commercieel lesmateriaal van Hogeschool PXL. Wie ze verwijdert: zet in `kwaliteit.html` het
veld `img` van de nummers op een lege waarde of verwijder de `<img>` in `spotSong()`; de tegel valt dan terug
op de gekleurde achtergrond per genre (`SPOT_GENRES`).
