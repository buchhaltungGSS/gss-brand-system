# sources/ – Roh-Materialien

Hier kommt alles rein, was die GSS-Marke heute zeigt.

## Was kann hier landen
- Newsletter (PDF, HTML-Export, oder einfach Text)
- Pitch-Decks und interne Präsentationen (PPTX, PDF, oder Text-Export)
- Vertriebs-Mails (anonymisiert: Empfänger raus, Inhalt rein)
- Datenblätter (PDF)
- Bestehende Landingpage-Texte (HTML/Markdown)
- Whitepaper, Case Studies
- Wunsch-Beispiele ("so wollen wir aussehen", inkl. Konkurrenz-Refs)

## Subfolder

- `newsletter/`     – Newsletter-Ausgaben
- `presentations/`  – Pitch-Decks, Webinar-Slides
- `emails/`         – Vertriebs- und Marketing-Mails (anonymisiert!)
- `datasheets/`     – Produkt-Datenblätter
- `landingpages/`   – existierende Web-Texte
- `wish-design/`    – Wunsch-Referenzen, inkl. dem Marketing-Site-Prototyp
- `misc/`           – alles sonstige Marken-Material

## Spielregeln

1. **Niemals Original-Files editieren.** Reinkopieren, fertig.
2. **Anonymisierung von Mails:** Empfänger-Namen, Telefonnummern,
   Vertrags-Details schwärzen. Stil-Information = OK, PII = nicht OK.
3. **Dateinamen:** kurz, beschreibend, mit Datum wenn bekannt.
   Beispiel: `2024-Q3-newsletter-empfangstechnik.pdf`
4. **Kein git-add für sehr große Dateien (>10 MB).** Stattdessen
   nach `sources-large/` (gitignored) und Pfad in INVENTORY.md notieren.

## Nach dem Hinzufügen
Nach jedem Batch neuer Quellen: einmal Claude Code mit dem
`brand-extraction`-Skill drüberlaufen lassen, dann `voice/`, `visual/`
und `EXTRACTION_REPORT.md` reviewen.
