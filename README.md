# ortografia-multilingue

Automatic spell checker skill for Claude Code — 6 European languages.

---

## Supported languages

| Flag | Code | Language | What it checks | Official dictionary |
|------|------|----------|---------------|---------------------|
| 🇪🇸 | ES | Español | Tildes (esdrújulas, llanas, agudas), interrogativas, monosílabos | [RAE](https://rae.es) |
| 🏴 | CA | Català | Accent grave/agut, punt volat (l·l), ce trencada (ç), diéresis | [DIEC](https://dlc.iec.cat) · [Optimot](https://optimot.gencat.cat) |
| 🇫🇷 | FR | Français | Accent aigu/grave/circonflexe, tréma, cédille (ç), ligatures (œ æ), majúscules | [Académie française](https://academie-francaise.fr) |
| 🇮🇹 | IT | Italiano | Accenti tonici finali (città, caffè), monosillabi distintivi (è/e, sì/si) | [Treccani](https://treccani.it) |
| 🇬🇧 | EN | English | Common misspellings, homophones (its/it's, their/there), apostrophes, US/UK variants | [Merriam-Webster](https://merriam-webster.com) · [Oxford](https://oxfordlearnersdictionaries.com) |
| 🇩🇪 | DE | Deutsch | Umlauts (ä ö ü), Eszett (ß vs ss), Großschreibung der Substantive | [Duden](https://duden.de) |

---

## How it works

1. Detects the language automatically
2. Loads the rules for that language from the official dictionary reference
3. Consults the official dictionary when uncertain about a word
4. Returns the corrected text
5. Shows an audit table with every change made
6. On request: generates a downloadable HTML report with color-coded corrections per language

---

## Install

**Option A — clone:**
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

**Option B — download `.skill` file** from [Releases](https://github.com/xusito/ortografia-multilingue/releases) and run in Claude Code:
```
/install-skill ortografia-multilingue.skill
```

---

## Usage

The skill activates automatically when you generate or edit text in any of the 6 languages. You can also trigger it manually in any language:

| Language | Trigger phrases |
|----------|----------------|
| ES | "revisa la ortografía", "corrígeme esto", "tiene faltas" |
| CA | "revisa l'ortografia", "corregeix això", "té faltes" |
| FR | "vérifie l'orthographe", "corrige ça", "il y a des fautes" |
| IT | "controlla l'ortografia", "correggi questo", "ci sono errori" |
| EN | "check the spelling", "fix spelling mistakes", "proofread this" |
| DE | "Rechtschreibung prüfen", "das korrigieren", "Rechtschreibfehler" |

To get an HTML report with all corrections: say **"HTML report"** / **"informe HTML"** / **"rapport HTML"**.

---

## Example output

```
Correcciones ortográficas:
- instal·lacións → instal·lacions   [Acento CA]
- comúnicació   → comunicació       [Acento CA]
- dinamico      → dinámico          [Tilde ES]
- francais      → français          [Cédille FR]
- citta         → città             [Accento IT]
- uber          → über              [Umlaut DE]
```

---

## Adding a new language

See [CONTRIBUTING.md](CONTRIBUTING.md) — adding a language is just one markdown file.

Languages planned: PT · NL · PL · GL

---

## License

MIT — free to use, modify and share.
