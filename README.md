# Wohnungssuche Leipzig

Eine übersichtliche Weboberfläche für meine laufende Wohnungssuche in Leipzig.

Die Seite bündelt aktuelle Wohnungsangebote, bewertet sie nach einem festen Punkteschema und stellt das Ergebnis als laufend aktualisiertes Ranking dar.

## Ziel

Gesucht werden Wohnungen in Leipzig mit folgenden Grundkriterien:

- mindestens **1,5 Zimmer**
- mindestens **27 m²**
- maximal **600 € Warmmiete**
- bevorzugter Einzug: **01.10.2026**
- spätestens akzeptierter Einzug: **01.11.2026**

Zusätzliche Pluspunkte gibt es unter anderem für:

- Balkon oder Loggia
- Neubau oder frisch sanierter Zustand
- gute Lage und ÖPNV-Anbindung
- gute Parkplatzsituation
- sichere Abstellmöglichkeiten für ein Motorrad

## Fahrzeug- und Parkplatzkriterien

Berücksichtigt werden sowohl kostenlose als auch kostenpflichtige Parkmöglichkeiten.

### Auto

Mögliche Optionen:

- kostenloses Straßenparken
- Bewohnerparken
- Außenstellplatz
- Carport
- Garage
- Tiefgarage
- Parkhaus

Bei Garage, Tiefgarage oder Parkhaus gilt:

> **Mindest-Durchfahrtshöhe: 2,10 m**

Ist die Höhe unbekannt, wird die Parkmöglichkeit nur vorsichtig bewertet.

### Motorrad

Zusätzlich wird geprüft, ob es beispielsweise folgende Möglichkeiten gibt:

- ausgewiesene Motorradstellplätze
- Garage oder Tiefgarage
- Innenhof
- abschließbare Abstellbereiche
- geeignete Außenstellplätze

## Bewertungssystem

Jede aktive Wohnung wird bei jeder Aktualisierung vollständig neu bewertet.

| Kriterium | Punkte |
|---|---:|
| Warmmiete / Preis-Leistung | 22 |
| Größe / Grundriss | 16 |
| Einzugstermin | 12 |
| Lage / ÖPNV | 12 |
| Auto-Parken | 10 |
| Motorrad-Parken | 5 |
| Balkon / Loggia | 8 |
| Zustand | 10 |
| Ausstattung / Zusatzkosten | 5 |
| **Gesamt** | **100** |

Dadurch kann sich das Ranking jederzeit ändern, wenn neue Inserate hinzukommen oder bestehende Angebote aktualisiert werden.

## Umgang mit entfernten Inseraten

Wenn ein Inserat erstmals nicht mehr verfügbar ist:

1. wird es aus dem aktiven Ranking entfernt
2. erscheint es einmal als **„Entfernt / nicht mehr verfügbar“**
3. verschwindet es beim nächsten Lauf vollständig aus der normalen Übersicht

Im Google Sheet kann es zusätzlich dauerhaft im Archiv erhalten bleiben.

## Dateien

### `index.html`

Enthält die komplette Weboberfläche.

Funktionen:

- Top-3-Übersicht
- vollständiges Ranking
- Suche nach Adresse oder Stadtteil
- Sortierung nach Ranking, Score, Warmmiete oder Größe
- Filter für Balkon / Loggia
- Filter für bekannte Parkmöglichkeiten
- Anzeige von Auto- und Motorrad-Parkinformationen
- Direktlinks zu den Wohnungsinseraten
- Darstellung des Bewertungsschemas

### `data.json`

Enthält die aktuellen Wohnungsdaten.

Die Website lädt diese Datei dynamisch. Dadurch muss für Aktualisierungen hauptsächlich nur `data.json` geändert werden.

Enthalten sind unter anderem:

- Rang
- Score
- Adresse
- Stadtteil
- Warmmiete
- Wohnfläche
- Zimmer
- Einzug
- Balkon / Loggia
- Zustand
- Auto-Parken
- Motorrad-Parken
- Zusatzkosten
- Direktlink zum Inserat
- zuletzt entfernte Inserate

## Google Sheet

Parallel zur Website wird eine Google-Tabelle als dauerhafte Datenbasis geführt:

[Wohnungssuche Leipzig – Ranking](https://docs.google.com/spreadsheets/d/1zJefs6LvCuujjflSr7ssTcr562eCE7vMitIRLQrFUx4/edit)

Dort werden unter anderem folgende Bereiche gepflegt:

- **Aktuelles Ranking**
- **Neu & Änderungen**
- **Archiv**
- **Bewertungsschema**

## GitHub Pages

Die Website kann direkt über GitHub Pages veröffentlicht werden.

### Einrichtung

1. Repository öffnen
2. **Settings**
3. **Pages**
4. unter **Build and deployment**
5. **Deploy from a branch**
6. Branch: `main`
7. Ordner: `/ (root)`
8. **Save**

Danach sollte die Website unter folgender Adresse erreichbar sein:

`https://zenoxess.github.io/Wohnungssuche/`

## Aktualisierung

Die Wohnungssuche läuft regelmäßig und prüft:

- neue Inserate
- deaktivierte Inserate
- Preisänderungen
- geänderte Verfügbarkeit
- neue Parkplatzinformationen
- Zustand und Ausstattung
- Ranking-Veränderungen

Bei relevanten Änderungen wird das gesamte Ranking neu bewertet.

---

Dieses Repository dient ausschließlich als persönliche Übersicht für die Wohnungssuche.
