# GSS Brand System (Multi-Brand)

Zentrale Wahrheit der GSS Smart Solutions Marken-DNA – für Web, Decks, PDFs,
Newsletter, Vertriebsmails, Whitepaper, Social Posts.

GSS Smart Solutions vereint **drei Marken**:

| Marke | Domäne | Akzent |
|---|---|---|
| **GSS** | Entertainment, TV-Empfang, Hospitality | Beere |
| **Teracue** | Broadcast, BOS, Stadien | Deep Blue |
| **Smart City Factory** | Edge Computing, Sensorik | Lila |

Plus übergreifende Konzern-Kommunikation (Shared).

## Workflow

1. Material in `sources/<subfolder>/` ablegen, **Dateinamen mit Brand-Präfix**
   (`gss-`, `teracue-`, `scf-`, `shared-`).
2. Claude Code mit `prompts/extraction.md` laufen lassen.
3. Ergebnis in `voice/_shared/`, `voice/<brand>/`, `visual/_shared/`, `visual/<brand>/` reviewen.
4. Korrekturen committen. Bei jedem Material-Nachschub: Schritt 2 wiederholen.

## Architektur

```
gss-brand-system/
├── sources/                        Roh-Material (Eingabe)
├── voice/
│   ├── _shared/                    Übergreifende Voice
│   ├── gss/                        GSS-Voice
│   ├── teracue/                    Teracue-Voice
│   └── scf/                        Smart City Factory Voice
├── visual/
│   ├── _shared/                    Übergreifende Optik
│   ├── gss/                        GSS-Optik
│   ├── teracue/                    Teracue-Optik
│   └── scf/                        SCF-Optik
├── templates/                      Vorlagen (PPTX, DOCX, PDF, E-Mail)
├── tokens/                         Maschinenlesbar (colors.json etc.)
├── prompts/                        Wiederverwendbare Prompts
└── .claude/
    ├── CLAUDE.md
    └── skills/
        ├── brand-extraction/       Wie aus sources/ Wissen wird (brand-aware)
        ├── brand-voice/            Konsultation für Texte
        └── brand-visual/           Konsultation für Visuals
```

## Konsumierbar durch

- Marketing-Site `gss-website-new` (Token-Sync)
- Portal `my.gss.de` (separates Repo, gleicher Token-Stand)
- Cowork (User wählt diesen Folder als Workspace)
- Claude.ai Web Projekte (Markdown-Files hochladen)
- ChatGPT Custom-GPTs (Action mit GitHub-Raw-URL)
- Automatisierungen: n8n / Make / Zapier (GitHub-API mit Read-Token)
