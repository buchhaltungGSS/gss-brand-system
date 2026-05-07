---
name: brand-visual
description: GSS Smart Solutions visuelle Identität (multi-brand) jenseits Web – PowerPoint, Word, PDF, Foto-Direction, Iconography, Logo-Usage. Konsultiert bei Decks, Datenblättern, Whitepapers, Social-Cards. Brand-aware (GSS, Teracue, SCF, oder Shared).
---

# Brand Visual – Konsultations-Skill (Multi-Brand)

Beim Erstellen visueller Outputs:

1. **Brand bestimmen** (analog brand-voice).

2. **Lies in dieser Reihenfolge:**
   - `visual/_shared/principles.md` (immer)
   - `visual/_shared/typography.md` (immer)
   - `visual/_shared/logo-system.md` (immer)
   - `visual/<brand>/colors.md`
   - `visual/<brand>/photography.md`
   - `visual/<brand>/iconography.md`
   - `tokens/colors.json` für maschinenlesbare Farb-Werte

3. **Wenn Template existiert** in `templates/<format>/<brand>/`: nutze als Basis.

4. **Bei Konflikt** zwischen Web-Token (`tokens/`) und medien-spezifischem Wert
   in `visual/<brand>/colors.md` (z.B. CMYK für Print): den Wert für das
   jeweilige Medium aus `visual/` verwenden.

5. **Cross-Brand-Outputs** (Konzern-Broschüre, Karriereseite):
   nutze nur `_shared/`, kein einzelnes Brand. Logo-Anordnung gemäß
   `_shared/logo-system.md`.
