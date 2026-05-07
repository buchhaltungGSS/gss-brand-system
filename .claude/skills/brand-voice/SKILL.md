---
name: brand-voice
description: GSS Smart Solutions Markensprache (multi-brand) – konsultiert bei Erstellung von Texten für GSS, Teracue oder Smart City Factory. Liest Shared-Prinzipien plus brand-spezifische Voice/Vocabulary/Examples.
---

# Brand Voice – Konsultations-Skill (Multi-Brand)

Beim Erstellen jeglicher kundengerichteter Texte:

1. **Brand bestimmen.** Wer ist Empfänger, welches Produkt, welche Domäne?
   - Hotel-IT, Hospitality-Integrator, ISP → **GSS**
   - Broadcast, BOS, Justiz, Stadien → **TERACUE**
   - Stadtplaner, Industrie, Sensor-/Lichthersteller → **SCF**
   - Konzern-übergreifend (Karriere, Press) → **SHARED**

2. **Lies in dieser Reihenfolge:**
   - `voice/_shared/principles.md` (immer)
   - `voice/_shared/vocabulary.md` (immer)
   - `voice/<brand>/voice.md` (außer SHARED)
   - `voice/<brand>/vocabulary.md` (außer SHARED)
   - `voice/<brand>/examples.md` für passenden Kontext (Newsletter? Pitch? Datenblatt?)

3. **Schreibe nach diesen Vorgaben.**

4. **Self-Check vor Ablieferung:**
   - Sind Brand-spezifische Begriffe verwendet? (`<brand>/vocabulary.md`)
   - Sind verbotene Begriffe vermieden?
   - Stimmt die Tonalität zur Empfänger-Gruppe?
   - Wurde "Made in Germany" / Mutter-Konzern angemessen positioniert?

5. **Bei Konflikt** zwischen `_shared/` und `<brand>/`: Brand-Override gewinnt.
   Bei Konflikt zwischen Skill und User-Anweisung: User darauf hinweisen,
   nicht stillschweigend abweichen.

## Wenn Material dünn ist

Wenn die Brand-Voice-Files (insbesondere SCF) leer / dünn sind:
- Verwende `_shared/`-Prinzipien als Basis
- Sage explizit: "Voice-Material für [Marke] ist begrenzt, ich orientiere
  mich an den allgemeinen GSS-Smart-Solutions-Konventionen plus den
  Brand-Hinweisen aus dem Designsystem."
- Schlage nicht vor, den Output zu publishen, ohne Brand-Owner-Review.
