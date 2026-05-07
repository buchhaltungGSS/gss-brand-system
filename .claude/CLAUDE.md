# GSS Brand System – Projekt-Memory (Multi-Brand)

## Was ist das?

Dieses Repo ist die **zentrale Wahrheit der GSS Smart Solutions Marken-DNA**
für alle Outputs: Web, Pitch-Decks, PDFs, Newsletter, Vertriebs-Mails,
Whitepaper, Social Posts.

GSS Smart Solutions vereint **drei Marken** mit eigenständigen Identitäten,
gemeinsamer Mutter-DNA:

| Marke | Domäne | Akzentfarbe |
|---|---|---|
| **GSS** | Entertainment, TV-Empfang, Hospitality | Beere #af026b |
| **Teracue** | Broadcast, BOS, Stadien | Deep Blue #19009b |
| **Smart City Factory** | Edge Computing, Sensorik, V2X | Lila #492483 |

Übergreifende Konzern-Kommunikation = "Shared" (z.B. Karriereseite, Konzern-PR).

## Konsumenten

- die Marketing-Website (gss-website-new)
- das Download-Portal (my.gss.de Repo)
- ad-hoc Erstellung (Cowork: PowerPoint, PDF, Word)
- AI-Tools (ChatGPT-Projekte, Custom-GPTs)
- Automatisierungen (n8n / Make / Zapier mit GitHub-Raw)

## Repo-Struktur

```
sources/                  Roh-Materialien (Eingabe, NICHT editieren)
  newsletter/
  presentations/
  emails/
  datasheets/
  landingpages/
  wish-design/
  misc/

voice/                    Sprache (Output – Multi-Brand)
  _shared/                  übergreifende Voice-Konventionen
  gss/                      GSS-spezifische Voice
  teracue/                  Teracue-spezifische Voice
  scf/                      Smart City Factory Voice

visual/                   Optik nicht-Web (Output – Multi-Brand)
  _shared/                  übergreifende visuelle Prinzipien (Logo-System, Typo)
  gss/                      GSS-spezifische Farben/Foto/Icons
  teracue/
  scf/

templates/                wiederverwendbare Strukturen (PPTX, DOCX, PDF, E-Mail, Social)
tokens/                   maschinenlesbare Brand-Tokens (Web + Print)
prompts/                  wiederverwendbare Prompts für Outputs
.claude/skills/           brand-extraction, brand-voice, brand-visual
```

## Workflow

1. Material in `sources/<subfolder>/` ablegen.
   Konvention für Dateinamen: `<brand-prefix>-<beschreibung>-<datum>.<ext>`
   - `gss-newsletter-empfangstechnik-2024-Q3.pdf`
   - `teracue-pitch-bos-leitstelle-2024-09.pdf`
   - `scf-whitepaper-edge-v2x-2024.pdf`
   - `shared-karriere-konzern-2024.html`
   Wenn Brand unklar → einfach beschreibend benennen, Claude Code wird beim
   Inventarisieren nachfragen.

2. Extraktion: Claude Code mit `prompts/extraction.md` laufen lassen.
   Brand-aware – Findings landen automatisch in der richtigen Marken-Sektion.

3. Iterieren: `EXTRACTION_REPORT.md` reviewen, korrigieren, ergänzen.

## Override-Prinzip (Shared vs Brand)

- `_shared/` enthält, was für **alle drei Marken** gilt.
- `<brand>/` enthält Brand-spezifische **Abweichungen oder Ergänzungen**.
- Bei Konflikt: Brand-spezifisches gewinnt.
- Wenn ein Pattern in allen drei Marken gleich auftaucht: gehört es nach `_shared/`,
  nicht dreimal kopiert in die Brand-Files.

## Verbote (übergreifend)

- Quell-Material niemals editieren.
- LAN1 Hotspots GmbH niemals öffentlich mit GSS verknüpfen.
- Aus dünnem Material nicht überextrapolieren.
- Keine erfundenen Brand-Konventionen.
- Belege liefern bei jeder Aussage.

## Skills in `.claude/skills/`

- **brand-extraction** – Anleitung zum brand-aware Destillieren von sources/
- **brand-voice** – Konsultation bei jeder Text-Erstellung
- **brand-visual** – Konsultation bei jedem visuellen Output

Beim Erstellen neuer Outputs liest Claude beide Skills + die für die Ziel-Marke
relevanten Files in `voice/<brand>/` und `visual/<brand>/`, plus immer `_shared/`.
