# visual/

Visuelles System jenseits der reinen Web-Tokens.

## Struktur
```
visual/
├── _shared/                  Universelle visuelle Prinzipien
│   ├── principles.md
│   ├── typography.md
│   └── logo-system.md        Hauptlogo + kombinierte Verwendung
├── gss/                      Marke GSS
│   ├── colors.md
│   ├── photography.md
│   └── iconography.md
├── teracue/                  Marke Teracue
│   ├── colors.md
│   ├── photography.md
│   └── iconography.md
└── scf/                      Marke Smart City Factory
    ├── colors.md
    ├── photography.md
    └── iconography.md
```

## Konsultations-Reihenfolge

Bei jedem visuellen Output (Deck, Datenblatt, Social-Card etc.):
1. `_shared/typography.md` und `_shared/logo-system.md` immer
2. `_shared/principles.md` immer
3. Brand-Verzeichnis nach Kontext

Bei Konflikt: **Brand-Override** wie in `voice/`.
