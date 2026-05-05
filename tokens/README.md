# tokens/ – maschinenlesbare Brand-Tokens

Diese Files sind die Schnittstelle zu Code-Anwendungen.

- `colors.json` – Marken-Farben in mehreren Notationen (Hex, RGB, Pantone, Beschreibung)
- (typography.json – kommt nach Extraktion)
- (spacing.json – kommt bei Bedarf)

## Konsumieren

### Aus Code
```ts
import colors from 'gss-brand-system/tokens/colors.json';
colors.brand.gss.beere.value;  // "#af026b"
```

### Aus Tools
GitHub-Raw-URL fetchen:
`https://raw.githubusercontent.com/<org>/gss-brand-system/main/tokens/colors.json`

### Aus dem Marketing-Site-Repo
Werte werden gespiegelt in `gss-website-new/packages/tokens/src/index.ts`.
Bei Brand-Änderungen: hier ändern, dann ins Marketing-Repo manuell oder per Sync-Skript syncen.
