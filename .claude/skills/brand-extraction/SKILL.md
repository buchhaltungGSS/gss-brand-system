---
name: brand-extraction
description: Anleitung zum Destillieren der GSS Smart Solutions Markenidentität aus den Roh-Materialien in sources/ in strukturiertes Wissen unter voice/, visual/, templates/. **Brand-aware**: erkennt für jedes Quellmaterial die zugehörige Marke (GSS, Teracue, Smart City Factory) und routet Findings entsprechend. Wird verwendet beim ersten Befüllen des Brand-Systems und bei jeder Aktualisierung, wenn neue Quellen hinzukommen.
---

# Brand-Extraktion: Workflow (Multi-Brand)

## Drei Marken, drei Audiences

GSS Smart Solutions vereint drei Marken mit unterschiedlichen Tonalitäten,
Vokabularen und Zielgruppen:

| Marke | Domäne | Typische Empfänger |
|---|---|---|
| **GSS** | Entertainment, TV, Hospitality | Hotel-IT, Klinik-IT, ISP, Kabelnetzbetreiber, Hospitality-Integratoren |
| **Teracue** | Broadcast, BOS, Stadien | Broadcast-Engineer, Polizei/Justiz-Beschaffung, Compliance-Officer, Stadiontechnik |
| **Smart City Factory** | Edge, Sensorik, V2X | Stadtplaner, Industrie-Engineering, Sensor-/Lichthersteller-Kooperationen |

Plus **übergreifende Konzern-Kommunikation** (Karriere, Konzern-Newsletter,
Pressemeldungen über alle drei Marken hinweg) – die zählt zu "Shared".

## Eingabe & Brand-Detection

Beim Lesen jedes Files in `sources/`:

1. **Brand identifizieren** – aus:
   - Dateinamen-Präfix (`gss-...`, `teracue-...`, `scf-...`, `shared-...`)
   - Inhalt: erwähnte Produkte (Smart Server → GSS, ENC-400 → Teracue, Edge-Compute → SCF)
   - Empfänger / Kontext (Hotel-Kette → GSS, Polizei → Teracue, Stadt → SCF)
   - Visuell: Akzentfarbe (Beere → GSS, Deep-Blue → Teracue, Lila → SCF)

2. **Wenn unsicher**: in `INVENTORY.md` als `🟡 Brand-Zuordnung unklar` markieren
   und User um Bestätigung bitten, **bevor** Findings irgendwohin geschrieben werden.

3. **Cross-Brand-Material** (z.B. eine Karriereseite über GSS Smart Solutions als Konzern):
   markieren als `shared`, Findings in `voice/_shared/` und `visual/_shared/`.

## Erste Lesephase – Inventur (brand-tagged)

Erstelle `sources/INVENTORY.md` mit Tabelle:

| Datei | Brand | Kontext | Datum (geschätzt) | Empfänger (vermutet) | 1-Satz-Zusammenfassung |
|---|---|---|---|---|---|

Brand-Werte: `GSS`, `TERACUE`, `SCF`, `SHARED`, `🟡 unklar`.

## Output-Routing

Findings werden je nach Brand-Tag in unterschiedliche Ziel-Files geschrieben:

| Quelle | Findings landen in |
|---|---|
| `gss`-tagged | `voice/gss/`, `visual/gss/` |
| `teracue`-tagged | `voice/teracue/`, `visual/teracue/` |
| `scf`-tagged | `voice/scf/`, `visual/scf/` |
| `shared`-tagged | `voice/_shared/`, `visual/_shared/` |

**Zusatz-Logik:** wenn ein Befund in mehreren Brand-Quellen ähnlich auftaucht
(z.B. Sie-Form in allen Newslettern, "Made in Germany" in allen Datenblättern),
heb ihn nach `voice/_shared/` oder `visual/_shared/` und vermerke nur Abweichungen
in den Brand-Files.

## Stil-Mining – pro Brand

Für jede Marke achte beim Lesen ihrer Quellen auf:

### Sprache
- Sie/Du-Konvention (sollte überall Sie sein – falls nicht: Notiz)
- Aktiv- vs Passiv-Anteil
- Satzlänge / -komplexität
- Fachterminus-Dichte (Teracue tendenziell höher)
- Anglizismen-Akzeptanz

### Vokabular
- Brand-spezifische Begriffe (z.B. nur GSS sagt "Hotel-TV-Management")
- Verbote (was wird konsequent vermieden?)
- Produkt-Eigennamen (verbindliche Schreibweise)

### Tonalität
- GSS: vermutet wärmer/service-orientiert? Belegen.
- Teracue: vermutet sachlich/sicherheitsfokussiert? Belegen.
- SCF: vermutet zukunftsorientiert? Belegen.

### Visuelles
- Brand-Farben-Verwendung im konkreten Material (welche Farbe für welche UI-Rolle?)
- Foto-Stil pro Brand (Hospitality-Settings vs. Server-Räume vs. Smart-City)
- Icon-Stil

## Output-Files (Soll-Zustand nach Extraktion)

```
voice/_shared/principles.md         übergreifende Voice-Prinzipien
voice/_shared/vocabulary.md         übergreifende Begriffe
voice/gss/voice.md                  GSS-Tonalität
voice/gss/vocabulary.md             GSS-Begriffe
voice/gss/examples.md               GSS-Beispieltexte
voice/teracue/...                   analog
voice/scf/...                       analog

visual/_shared/principles.md
visual/_shared/typography.md
visual/_shared/logo-system.md
visual/gss/colors.md
visual/gss/photography.md
visual/gss/iconography.md
visual/teracue/...                  analog
visual/scf/...                      analog
```

## Iteration & Belege

JEDE Aussage bekommt einen Beleg-Verweis mit Brand-Tag:

```markdown
### Begrüßung in GSS-Vertriebsmails
"Sehr geehrte/r [Vorname Nachname]," ist Standard.
Ausnahme: bei bekannten Kontakten "Lieber [Vorname]," (3 von 7 gesichteten Mails).

> Belege:
> - sources/emails/gss-cold-vertrieb-2024-03.txt:1
> - sources/emails/gss-bestand-2024-08.txt:1
> Brand-Tag: GSS
```

## Extraction Report

Erzeuge `EXTRACTION_REPORT.md` im Repo-Root mit:
- Anzahl gelesene Files **pro Brand**
- Was wurde extrahiert (Cross-Reference auf Output-Files)
- Brand-spezifische Lücken (z.B. "SCF: nur 2 Files in sources/, sehr begrenzte Aussagekraft")
- Widersprüche (intra-brand und cross-brand)
- Vermutungen (`🟡 ZU PRÜFEN`)
- Welche Quell-Materialien fehlen?
- Welche Themen brauchen menschliche Entscheidung?

## Was du NICHT machst

- Eigenständig "verbessern" – wir extrahieren den IST-Zustand.
- Aus zu wenig Material überextrapolieren. Bei SCF: lieber sagen
  "zu wenige Beispiele für belastbare Aussage" als raten.
- Quell-Material editieren oder verschieben.
- Brand-Annahmen treffen ohne Beleg.
- Cross-Brand-Universalien einfach in eine Brand-Datei schreiben –
  immer prüfen, ob das nicht nach `_shared/` gehört.
