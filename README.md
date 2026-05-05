# GSS Brand System

Zentrale Wahrheit der GSS Smart Solutions Marke – für Web, Decks, PDFs, Newsletter,
Vertriebsmails, Whitepaper, Social. Single Source of Truth, von Menschen + KI gemeinsam gepflegt.

## Was hier passiert

`sources/` enthält reale Marken-Artefakte (Newsletter, Decks, Mails, Datenblätter, ...).
Daraus destilliert Claude Code strukturiertes Wissen in `voice/`, `visual/`, `templates/`, `tokens/`.
Andere Tools und Repos konsumieren dieses Wissen.

## Quick Start

1. Repo lokal klonen oder Workspace öffnen.
2. Material in `sources/<passender-subfolder>/` ablegen.
3. In Claude Code (oder Cowork) den Extraktions-Prompt aus `prompts/extraction.md` ausführen.
4. Ergebnis reviewen, bei Bedarf in den `voice/`- und `visual/`-Files nachschärfen.
5. Bei jedem Material-Nachschub: Schritt 3 wiederholen.

## Architektur-Karte

```
gss-brand-system/
├── sources/             ← Roh-Material (Eingabe)
├── voice/               ← Sprache (Output)
├── visual/              ← Optik nicht-Web (Output)
├── templates/           ← Vorlagen (Output)
├── tokens/              ← Maschinenlesbar (Output)
├── prompts/             ← Wiederverwendbare Prompts
└── .claude/
    ├── CLAUDE.md
    └── skills/
        ├── brand-extraction/
        ├── brand-voice/
        └── brand-visual/
```

## Konsum durch andere Systeme

- **gss-website-new**: bezieht Tokens via Sync nach `packages/tokens/`
- **my.gss.de Portal-Repo**: bezieht denselben Token-Stand
- **Cowork (Claude Desktop)**: User wählt diesen Folder als Workspace
- **Claude.ai Web**: relevante `.md`-Files in ein Projekt hochladen
- **ChatGPT-Projekte / Custom-GPTs**: gleiches – Files reinladen oder über Action GitHub-Raw fetchen
- **Automatisierungen (n8n / Make / Zapier)**: GitHub-API mit Read-Only-Token
- **MCP-Server**: dieses Repo als Filesystem-Mount oder Knowledge-Base

## Lebende Doku

Brand-Systeme sind nie "fertig". Bei jedem neuen Output und jeder Korrektur:
zurück ins Repo, Erkenntnis als kleine PR. Über die Zeit entsteht
ein präzises Bild der echten Marke, nicht eines erfundenen Ideals.
