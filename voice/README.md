# voice/

Markensprache und Tonalität, gegliedert nach **Shared + per-Brand**.

## Struktur
```
voice/
├── _shared/                  Was für ALLE drei Marken gilt
│   ├── principles.md         Sie-Form, Sprachebene, übergreifende Pillars
│   └── vocabulary.md         Markenname, "Made in Germany"-Phrasing, Cross-Brand-Begriffe
├── gss/                      Marke GSS – Hospitality, Entertainment, TV
│   ├── voice.md
│   ├── vocabulary.md
│   └── examples.md
├── teracue/                  Marke Teracue – Broadcast, BOS
│   ├── voice.md
│   ├── vocabulary.md
│   └── examples.md
└── scf/                      Marke Smart City Factory – Edge, Sensorik
    ├── voice.md
    ├── vocabulary.md
    └── examples.md
```

## Konsultations-Reihenfolge

Bei jedem Text-Output:
1. `_shared/principles.md` immer
2. `_shared/vocabulary.md` immer
3. Brand-spezifisches Verzeichnis nach Kontext (gss / teracue / scf)
4. Bei Cross-Brand-Material (z.B. Karriereseite, Konzern-Newsletter): nur _shared/

Wenn ein Konflikt zwischen `_shared/` und `<brand>/` besteht: **Brand-Spezifisches gewinnt** (Override-Prinzip).
