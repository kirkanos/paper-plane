# Paper Plane Launch

Browser-Spiel mit leichter Comic-3D-Optik: Ein Papierflieger wird per Zwille abgeschossen und soll über eine 20 km lange Strecke bis zum Leuchtturm am Ende der Welt kommen. Mit dem verdienten Geld kauft man Upgrades für Abschuss, Flugzeug und Wirtschaft.

## Spielen

Der Prototyp ist eine einzelne Datei ohne Build-Schritt:

```sh
cd prototype
python3 -m http.server 8765
# dann http://localhost:8765/ öffnen
```

Three.js (r147) und der OutlineEffect werden per CDN geladen.

## Steuerung

| | Maus/Tastatur | Touch |
|---|---|---|
| Zielen | Maus ziehen wie an einer Zwille, oder `↑ ↓ ← →` | Finger ziehen |
| Abschuss | loslassen bzw. `Leertaste` halten und loslassen | loslassen |
| Fliegen | `W/S` hoch/runter, `A/D` lenken, oder Maus halten und bewegen | virtueller Joystick (Finger ziehen) |
| Boost | `Leertaste` | Boost-Knopf |

## Inhalt

- 9 Landschaften: Schulwiese, Felder & Dörfer, Seenplatte, Meer, Wüste, Herbstwald, Schneegebirge, Sturmküste, Ziel-Insel
- Wetter, das zum Ende hin härter wird: Gegenwind, Böen, Regen, Sandsturm, Schnee, Sturm mit Blitzen
- 7 Flugzeuge, jeweils mit 5 Tuning-Stufen; ist eins voll getunt, schaltet das nächste Upgrade das nächste Flugzeug frei
- Upgrade-Linien in Sets (z. B. Flügel → Triebwerk → Düsen → Nachbrenner), sichtbar am Modell
- 4 Abschussgeräte: Zwille, Katapult, Federkanone, Dampfschleuder
- Boni: Münzen, Sternmünzen, Turbo-Ringe, Treibstoff-Kanister, Ballons, Entdecker-Bonus
- Die Welt wird beim Fliegen kachelweise nachgeladen; der Spielstand liegt im `localStorage`

## Nächste Schritte

Laut Plan soll der Prototyp in ein Vite- und TypeScript-Projekt mit getrennten Modulen (Physik, Welt, Upgrades, UI) überführt werden.
