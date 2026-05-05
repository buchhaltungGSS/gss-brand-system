---
name: brand-extraction
description: Anleitung zum Destillieren der GSS-Markenidentität aus den Roh-Materialien in sources/ in strukturiertes Wissen unter voice/, visual/, templates/. Wird verwendet beim ersten Befüllen des Brand-Systems und bei jeder Aktualisierung, wenn neue Quellen hinzukommen.
---

# Brand-Extraktion: Workflow

## Eingabe
- Alles, was unter `sources/` liegt: PDFs, PPTX-Exports (auch als reiner Text-Dump),
  E-Mail-Texte, gecrawlte Webseiten, Datenblätter, Newsletter.
- Subfolder geben Hinweis auf Kontext (z.B. `sources/emails/` = transaktional/dialogisch).

## Erste Lesephase – Inventur

Bevor du irgendwas extrahierst:

1. Liste alle Dateien in `sources/`. Erstelle in `sources/INVENTORY.md` eine Tabelle:
   `| Datei | Kontext | Datum (geschätzt) | Zielgruppe (vermutet) | Größe |`
2. Für jede Datei: 1-Satz-Zusammenfassung, was drin ist.
3. Frag nach, wenn ein Subfolder leer ist – brauchen wir mehr Material?

## Zweite Lesephase – Stil-Mining

Beim Lesen achtest du auf:

### Sprache
- **Du oder Sie?** Konsistent? Zielgruppen-abhängig?
- **Aktiv vs. Passiv** – Anteil schätzen
- **Satzlänge** – kurz und präzise oder ausschweifend?
- **Fachbegriffe** – wann erklärt, wann vorausgesetzt
- **Fremdwörter / Anglizismen** – welche werden benutzt, welche vermieden
- **Typische Satzanfänge** (Header, Hook-Lines)
- **CTA-Wording** – exakte Phrasen, keine Paraphrase
- **Begrüßung / Verabschiedung** in Mails

### Vokabular
- **Begriffe, die GSS bevorzugt** (z.B. "Kopfstation" vs "Headend",
  "Signaldistribution" vs "Verteilung")
- **Begriffe, die GSS vermeidet** (z.B. niemals "Lösungsanbieter" wenn nie verwendet)
- **Marken-spezifische Wendungen** (z.B. "Made in Germany", "seit 1992", "Erfinder der Kopfstation")
- **Disclaimer-Sprache** für Compliance (BOS-Kontext)

### Struktur
- **Welche Sektionen wiederholen sich** in Newslettern, Decks, Datenblättern?
- **Welche Reihenfolge** (Hook → Lösung → Beweis → CTA?)
- **Welche Headline-Muster** (Frage? These? Provokation?)
- **Boilerplate** – wiederkehrende Schluss-Absätze, Footer-Texte

### Visuelles (aus PPTX/PDF/HTML)
- **Farb-Verwendung** – wo Beere, wo Aubergine, wo Slate
- **Foto-Stil** – Stockfotos? Eigene? Was wird gezeigt (Hardware? Personen? Räume?)
- **Icon-Stil** – Outline? Filled? Custom?
- **Layout-Konventionen** – Grid, Whitespace, Headline-Größen

## Output – wo was hinkommt

- `voice/voice-and-tone.md` – Top-Level-Prinzipien, Pillars
- `voice/vocabulary.md` – Bevorzugte/vermiedene Begriffe in Tabellen
- `voice/examples-by-context.md` – Snippets pro Kanal:
  Vertriebs-Cold-Mail, Newsletter-Lead, Datenblatt-Intro,
  Hero-Headline, Cookie-Banner, 404-Seite, Reklamations-Antwort
- `voice/dos-and-donts.md` – Schwarz/Weiß-Liste
- `visual/colors.md` – mit Pantone, CMYK, RGB, Hex pro Marke
- `visual/typography.md` – inkl. Office-Fallbacks (Calibri etc.)
- `visual/photography.md` – Art-Direction, Beispiel-Refs
- `visual/iconography.md` – Stil-Definition
- `visual/logo-usage.md` – Schutzräume, Min-Größen, Verbote
- `templates/...` – konkret nachbaubare Vorlagen

## Iteration

Nach erstem Durchlauf:
1. Erstelle `EXTRACTION_REPORT.md` im Repo-Root: was hast du extrahiert,
   wo waren Lücken, wo widersprachen sich die Quellen.
2. Markiere Vermutungen mit "🟡 ZU PRÜFEN".
3. Liste explizit, welche Quell-Materialien noch fehlen, um das Bild zu vervollständigen.

User korrigiert, du integrierst.

## Belege

JEDE Aussage in den output-Files bekommt einen Beleg-Verweis:

```markdown
### Begrüßung in Vertriebs-Mails
"Sehr geehrte/r [Vorname Nachname]," ist Standard.
Ausnahme: bei bekannten Kontakten "Lieber [Vorname]," (3 von 7 gesichteten Mails).

> Belege: sources/emails/sample-vertrieb-2024-03.txt:1, sources/emails/sample-bestand-2024-08.txt:1
```

## Was du NICHT machst

- Eigenständig "verbessern" oder modernisieren – wir extrahieren den IST-Zustand.
  Verbesserungs-Vorschläge gehen in einen separaten `RECOMMENDATIONS.md`,
  nicht in die Stil-Files.
- Aus zu wenig Material überextrapolieren. Lieber sagen
  "zu wenige Beispiele für belastbare Aussage" als raten.
- Quell-Material editieren oder verschieben.
