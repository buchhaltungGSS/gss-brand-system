# Prompt: Erst-Befüllung des Brand-Systems

Kopiere folgenden Prompt in Claude Code, sobald `sources/` mit Material gefüllt ist:

---

Hi Claude Code, ich habe sources/ mit Brand-Materialien befüllt. Bitte
führe die Erst-Extraktion durch:

1. Lies .claude/skills/brand-extraction/SKILL.md – das ist deine Anleitung.
2. Lies .claude/CLAUDE.md für Kontext.
3. Inventarisiere sources/ in sources/INVENTORY.md (Tabelle).
4. Lies alle Materialien.
5. Befülle nach den Vorgaben aus brand-extraction:
   - voice/voice-and-tone.md
   - voice/vocabulary.md
   - voice/examples-by-context.md
   - voice/dos-and-donts.md
   - visual/colors.md (Verwendungsregeln, Tokens existieren schon)
   - visual/typography.md
   - visual/photography.md
   - visual/iconography.md
   - visual/logo-usage.md
6. Erzeuge EXTRACTION_REPORT.md im Repo-Root mit:
   - Was hast du extrahiert?
   - Wo waren die Quellen widersprüchlich?
   - Wo fehlt Material? (welche Subfolder zu dünn?)
   - Welche Aussagen sind 🟡 unsicher?
   - Welche Themen brauchen menschliche Entscheidung?

Belege jede Aussage mit dem Quell-Pfad in sources/.
Editiere niemals sources/.
Übertreibe nicht – wo wenige Belege da sind, sag es offen.

Frag mich nach Bestätigung, BEVOR du templates/ angehst – das ist Phase 2.
