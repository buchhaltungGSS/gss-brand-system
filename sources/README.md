# sources/ – Roh-Materialien

Hier kommt alles rein, was die GSS-Smart-Solutions-Marken heute zeigen.

## Subfolder (nach Material-Typ)

- `newsletter/`     – Newsletter-Ausgaben
- `presentations/`  – Pitch-Decks, Webinar-Slides (idealerweise als PDF-Export)
- `emails/`         – Vertriebs- und Marketing-Mails (anonymisiert!)
- `datasheets/`     – Produkt-Datenblätter
- `landingpages/`   – existierende Web-Texte
- `wish-design/`    – Wunsch-Referenzen, inkl. dem Marketing-Site-Prototyp
- `misc/`           – alles sonstige Marken-Material

## Brand-Tagging über Dateinamen

Da GSS Smart Solutions drei Marken hat (GSS, Teracue, Smart City Factory),
muss Claude Code beim Lesen jedes Files die Marke kennen. Konvention:

**Dateinamen mit Brand-Präfix beginnen lassen:**

| Brand | Präfix | Beispiel |
|---|---|---|
| GSS (Hospitality, Entertainment, TV) | `gss-` | `gss-newsletter-empfangstechnik-2024-Q3.pdf` |
| Teracue (Broadcast, BOS) | `teracue-` | `teracue-pitch-bos-leitstelle-2024-09.pdf` |
| Smart City Factory (Edge, V2X) | `scf-` | `scf-whitepaper-edge-v2x-2024.pdf` |
| Übergreifend (Konzern-Material) | `shared-` | `shared-karriere-2024.html` |
| Brand unklar | (kein Präfix) | `pressemeldung-2023.pdf` – Claude Code fragt |

**Wenn du den Präfix vergisst:** auch ok – Claude Code erkennt die Brand
beim Lesen aus dem Inhalt und fragt bei Unklarheit nach.

## Spielregeln

1. **Niemals Original-Files editieren.** Reinkopieren, fertig.
2. **PII-Anonymisierung in Mails:** Empfänger-Namen, Telefonnummern,
   Vertrags-Details schwärzen. Stil-Information OK, persönliche Daten nicht.
3. **PowerPoint:** lieber als PDF exportieren – Text-Extraktion ist sauberer.
4. **Format-Empfehlungen:**
   - Newsletter: PDF oder HTML
   - Pitch-Decks: PDF (aus PPTX exportiert)
   - E-Mails: reiner Text (.txt) oder Markdown
   - Datenblätter: PDF (Original)
   - Landingpages: HTML / Markdown
5. **Große Files (>10 MB):** lieber Auszug erstellen als alles hochladen.
   Git verträgt das nicht gut – stattdessen `sources-large/` (gitignored).
6. **Dateinamen kurz und sprechend.**

## Nach jedem Material-Batch

- `git add sources/` und commiten
- Extraktion neu laufen lassen (`prompts/extraction.md`)
- `EXTRACTION_REPORT.md` und Diff in `voice/` / `visual/` reviewen
