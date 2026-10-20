# BlaulichtBuddy Kartendaten Wien

Die Kartendaten der Offline-Karte Wien in der App BlaulichtBuddy, als
maschinenlesbare Kopie zum freien Download. Downloads:
https://github.com/Frittatensuppe/blaulichtbuddy-kartendaten-wien/releases

Dieses Repo erfüllt das Angebot nach Abschnitt 4.6 der Open Database License
(ODbL) 1.0 für alle, die die Karte nicht in der App, sondern zum Beispiel
auf Screenshots im App Store, auf der Website oder in Präsentationen sehen.
In der App selbst gibt es dieselben Daten unter Karte > Quellenangabe >
Quellen und Lizenzen > Kartendaten teilen.

## Inhalt (Release `kartendaten-wien-20260927`)

| Datei | Inhalt | Größe | SHA-256 |
| --- | --- | --- | --- |
| `map.pmtiles` | Vektorkacheln Wien (PMTiles v3, Mapbox Vector Tiles, gzip, Zoom 0-14) | 32 785 480 Byte | `5a51cdb81583faef0d2ea0c0c462fc03a110c447e001a627fb089c07b49b65e8` |
| `pois.sqlite` | Suchdaten zu Orten und Einrichtungen in Wien (SQLite mit FTS5, 38 996 Objekte) | 5 857 280 Byte | `0afedd53123b714d2352231c3c99e0c44dbd5595224866a3f0d406c1a3f540d5` |
| `blaulichtbuddy-kartendaten-wien-odbl-20260927.tar.gz` | beide Dateien mit `LICENSE`, `NOTICE`, diesem README und `notices/` | siehe `SHA256SUMS` | siehe `SHA256SUMS` |
| `blaulichtbuddy-adressen-wien-cc-by-20260926.tar.gz` (optional) | Adressen der Stadt Wien, getrennt lizenziert (siehe unten) | siehe `SHA256SUMS` | siehe `SHA256SUMS` |
| `SHA256SUMS` | Prüfsummen aller Release-Dateien | | |

Prüfen: `shasum -a 256 -c SHA256SUMS` (macOS) bzw. `sha256sum -c SHA256SUMS`.

## Herkunft und Stand

- **Kacheln:** VersaTiles `osm.20260608.versatiles` (Planetiler-Build,
  Shortbread-Schema 1.0, OpenStreetMap-Stand 2026-06-07). Zuschnitt
  `versatiles convert --bbox-border 1 --bbox 16.154,48.099,16.605,48.342 --max-zoom 14`,
  danach `versatiles convert --compress gzip` (versatiles 4.14.0). Nur
  OpenStreetMap-Daten, keine Landbedeckung von Dritten.
- **Orte und Einrichtungen:** Geofabrik `austria-260922.osm.pbf`
  (Stand 2026-09-22 23:14, SHA-256
  `85c6ad83717f92897c693e3b112781621e9dfb8b2225abada870bdcb536d47e4`).
  Mit osmium ausgewählt: benannte Orte, Haltestellen, Spitäler und weitere
  Einrichtungen innerhalb der Wiener Bezirksgrenzen.

## Lizenz

`map.pmtiles` und `pois.sqlite` sind abgeleitete Datenbanken aus
OpenStreetMap und stehen unter der **Open Database License (ODbL) 1.0**
(Volltext in `LICENSE`, https://opendatacommons.org/licenses/odbl/1-0/).
Du darfst sie nutzen, auch kommerziell, vervielfältigen, bearbeiten und
weitergeben. Wer eine bearbeitete Fassung öffentlich nutzt, muss sie wieder
unter der ODbL anbieten (Share-Alike).

## Namensnennung

> © OpenStreetMap-Mitwirkende, Open Database License 1.0,
> https://www.openstreetmap.org/copyright

## Adressen der Stadt Wien (getrennt lizenziert)

Die Adresssuche der App stammt nicht aus OpenStreetMap, sondern von der
Stadt Wien (Datensatz „Adressen Standorte Wien“, `ogdwien:ADRESSENOGD`,
Abruf 26.09.2026). Sie steht unter **CC BY 4.0**
(https://creativecommons.org/licenses/by/4.0/) und fällt nicht unter die
ODbL, weil sie in einer eigenen Datei ohne Schlüssel oder Verknüpfungen zu
den OpenStreetMap-Daten liegt. Liegt das Archiv
`blaulichtbuddy-adressen-wien-cc-by-20260926.tar.gz` bei, gilt für seinen
Inhalt die Namensnennung „Datenquelle: Stadt Wien – data.wien.gv.at“
(Datensatz: https://www.data.gv.at/katalog/dataset/1d5c2411-9719-4c8f-b99d-57a5f4a4ae41;
Änderung: für Offline-Suche normalisiert und indexiert).

## Kontakt

kontakt@blaulichtbuddy.at. Auf Anfrage senden wir die Daten auch direkt.
