# GSS Brand System – Projekt-Memory

## Was ist das?

Dieses Repo ist die **zentrale Wahrheit der GSS Smart Solutions Marke** für alle Outputs:
Web, Pitch-Decks, PDFs, Newsletter, Vertriebs-Mails, Whitepaper, Social Posts.

Es wird konsumiert von:
- der Marketing-Website (gss-website-new)
- dem Download-Portal (my.gss.de Repo)
- ad-hoc Erstellung (Cowork: PowerPoint, PDF, Word)
- AI-Tools von Vertrieb und Marketing (ChatGPT-Projekte, Custom-GPTs)
- Automatisierungen (n8n / Make / Zapier können Markdown via GitHub-Raw lesen)

## Workflow

1. **`sources/`** – Roh-Materialien aus eurem Tagesgeschäft:
   newsletter, presentations, emails, datasheets, landingpages, wish-design.
   Hier kommen PDFs, PPTX-Exports, Mailtexte, Webseiten-Auszüge rein.
   Subfolder pro Materialtyp. Auf Vollständigkeit kommt es nicht an –
   was kommt, kommt; gerne auch heterogen.

2. **Extraktion** – Claude Code liest die Sources und destilliert
   strukturiertes Wissen in:
   - `voice/`     – Tonalität, Vokabular, Beispiele pro Kontext
   - `visual/`    – Farben, Typo, Logo, Foto-Direction (über reine Tokens hinaus)
   - `templates/` – wiederverwendbare Strukturen für PPTX, DOCX, PDF, E-Mail, Social
   - `tokens/`    – maschinenlesbare Exports (TS, JSON, CSS)

3. **Iteration** – ihr lest die destillierten Files, korrigiert, ergänzt.
   Claude Code lernt aus Korrekturen und passt die Files an.
   Output ist nie "fertig", sondern lebt mit dem Unternehmen mit.

4. **Konsumieren** – andere Repos/Tools binden das Brand-System ein:
   - per Git-Submodule
   - per Sync-Skript (Copy-Paste-Automation)
   - per direktem Fetch von GitHub-Raw-URLs
   - per gleichzeitig geöffnetem Workspace-Folder

## Wichtige Regeln

- **Quell-Material niemals editieren.** `sources/` bleibt unverändert –
  ist Beweis-Spur, nicht Arbeits-Material. Erkenntnisse werden in
  `voice/`, `visual/` etc. abgelegt, mit Verweis auf die Quelle.

- **Belege liefern.** Wenn du in `voice/vocabulary.md` schreibst
  "GSS sagt 'Lösung' nie ohne Kontext, immer 'Signal-Distributions-Lösung'",
  dann verweise auf die konkrete Stelle in `sources/` (Datei + Zeile/Slide).

- **Behaupte nicht, erkenne.** Wenn das Material widersprüchlich ist
  (z.B. mal "Du", mal "Sie"), benenne den Widerspruch in
  `voice/voice-and-tone.md` und frage uns, statt zu raten.

- **Trenne Beobachtung von Empfehlung.** Was IST der Stil heute,
  vs. was sollte er sein. Letzteres markieren wir explizit.

- **Deutschland-Standard.** Hauptsprache Deutsch, Höflichkeitsform "Sie".
  Englische Varianten nur, wo explizit gewünscht (z.B. internationale
  Datenblätter).

## Zielgruppen-Matrix

GSS hat verschiedene Empfänger-Gruppen mit unterschiedlicher Tonalität:

| Empfänger | Tonalität | Beispielkanal |
|---|---|---|
| Planer / Fachplaner | Technisch, präzise, kein Marketing | Datenblatt, Beratungsgespräch |
| Systemintegrator | Beratung auf Augenhöhe, Detailtiefe | Pitch-Deck, OEM-Anfrage |
| Hotel-/Klinik-IT | Ergebnis-orientiert, weniger Tech-Tiefe | Landing Page, Cold-Mail |
| BOS/Justiz | Sicherheit, Compliance, sachlich | Whitepaper, Ausschreibung |
| Endkunde | NICHT angesprochen – kein Direktvertrieb | – |

## Skills in `.claude/skills/`

- **brand-voice**     Wie wir schreiben (Ton, Wortwahl, Satzbau).
- **brand-visual**    Wie wir aussehen (über Web-Design hinaus).
- **brand-extraction** Wie aus Sources strukturiertes Wissen wird.

Alle drei wirken zusammen: bei jeder Output-Erstellung
(z.B. "Schreibe einen Newsletter") konsultiert Claude beide
relevanten Skills + die Materialien in `sources/`.
