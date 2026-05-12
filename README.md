# ortografia-multilingue

Automatic spell checker skill for Claude Code — 6 European languages.

---

## Supported languages

| Flag | Code | Language | What it checks | Official dictionary |
|------|------|----------|---------------|---------------------|
| 🇪🇸 | ES | Español | Tildes (esdrújulas, llanas, agudas), interrogativas, monosílabos | [RAE](https://rae.es) |
| 🏴 | CA | Català | Accent grave/agut, punt volat (l·l), ce trencada (ç), diéresis | [DIEC](https://dlc.iec.cat) · [Optimot](https://optimot.gencat.cat) |
| 🇫🇷 | FR | Français | Accent aigu/grave/circonflexe, tréma, cédille (ç), ligatures (œ æ), majuscules | [Académie française](https://academie-francaise.fr) |
| 🇮🇹 | IT | Italiano | Accenti tonici finali (città, caffè), monosillabi distintivi (è/e, sì/si) | [Treccani](https://treccani.it) |
| 🇬🇧 | EN | English | Common misspellings, homophones (its/it's, their/there), apostrophes, US/UK variants | [Merriam-Webster](https://merriam-webster.com) · [Oxford](https://oxfordlearnersdictionaries.com) |
| 🇩🇪 | DE | Deutsch | Umlauts (ä ö ü), Eszett (ß vs ss), Großschreibung der Substantive | [Duden](https://duden.de) |

---

## Example output

```
- instal·lacións → instal·lacions   [Acento CA]
- dinamico       → dinámico         [Tilde ES]
- francais       → français         [Cédille FR]
- citta          → città            [Accento IT]
- seperate       → separate         [Spelling EN]
- uber           → über             [Umlaut DE]
```

On request, generates a color-coded HTML report with all corrections grouped by language.

---

## 🇪🇸 Español

### ¿Qué hace?
Corrector ortográfico automático para textos en español, catalán, francés, italiano, inglés y alemán. Detecta el idioma, aplica las reglas del diccionario oficial y devuelve el texto corregido con una tabla de auditoría de cambios. Bajo petición genera un informe HTML descargable.

### Instalación
```bash
# Opción A: clonar en tu carpeta de skills
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue

# Opción B: descargar el .skill desde Releases
/install-skill ortografia-multilingue.skill
```

### Uso
Se activa automáticamente al generar o editar texto en cualquiera de los 6 idiomas. También puedes invocarlo manualmente:
- "revisa la ortografía de este texto"
- "corrígeme esto" / "tiene faltas ortográficas"
- "informe HTML" — genera un archivo HTML con todas las correcciones

---

## 🏴 Català

### Què fa?
Corrector ortogràfic automàtic per a textos en espanyol, català, francès, italià, anglès i alemany. Detecta l'idioma, aplica les regles del diccionari oficial i retorna el text corregit amb una taula d'auditoria de canvis. A petició genera un informe HTML descarregable.

### Instal·lació
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Ús
S'activa automàticament en generar o editar text en qualsevol dels 6 idiomes. També:
- "revisa l'ortografia" / "corregeix això" / "té faltes"
- "informe HTML" — genera un fitxer HTML amb totes les correccions

---

## 🇫🇷 Français

### Que fait-il ?
Correcteur orthographique automatique pour les textes en espagnol, catalan, français, italien, anglais et allemand. Détecte la langue, applique les règles du dictionnaire officiel et renvoie le texte corrigé avec un tableau d'audit des modifications. Sur demande, génère un rapport HTML téléchargeable.

### Installation
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Utilisation
S'active automatiquement lors de la génération ou l'édition de texte dans l'une des 6 langues. Aussi :
- "vérifie l'orthographe" / "corrige ça" / "il y a des fautes"
- "rapport HTML" — génère un fichier HTML avec toutes les corrections

---

## 🇮🇹 Italiano

### Cosa fa?
Correttore ortografico automatico per testi in spagnolo, catalano, francese, italiano, inglese e tedesco. Rileva la lingua, applica le regole del dizionario ufficiale e restituisce il testo corretto con una tabella di audit delle modifiche. Su richiesta genera un report HTML scaricabile.

### Installazione
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Utilizzo
Si attiva automaticamente durante la generazione o modifica di testo in una delle 6 lingue. Anche:
- "controlla l'ortografia" / "correggi questo" / "ci sono errori"
- "report HTML" — genera un file HTML con tutte le correzioni

---

## 🇬🇧 English

### What does it do?
Automatic spell checker for texts in Spanish, Catalan, French, Italian, English and German. Detects the language, applies the rules of the official dictionary, and returns the corrected text with an audit table of changes. On request, generates a downloadable HTML report.

### Installation
```bash
# Option A: clone into your skills folder
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue

# Option B: download the .skill file from Releases
/install-skill ortografia-multilingue.skill
```

### Usage
Activates automatically when generating or editing text in any of the 6 languages. You can also trigger it manually:
- "check the spelling" / "fix spelling mistakes" / "proofread this"
- "HTML report" — generates an HTML file with all corrections

---

## 🇩🇪 Deutsch

### Was macht es?
Automatischer Rechtschreibprüfer für Texte auf Spanisch, Katalanisch, Französisch, Italienisch, Englisch und Deutsch. Erkennt die Sprache, wendet die Regeln des offiziellen Wörterbuchs an und gibt den korrigierten Text mit einer Änderungsübersicht zurück. Auf Anfrage wird ein herunterladbarer HTML-Bericht erstellt.

### Installation
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Verwendung
Wird automatisch aktiviert, wenn Text in einer der 6 Sprachen erstellt oder bearbeitet wird. Auch:
- "Rechtschreibung prüfen" / "das korrigieren" / "Rechtschreibfehler"
- "HTML-Bericht" — erstellt eine HTML-Datei mit allen Korrekturen

---

## Adding a new language / Añadir un idioma

See [CONTRIBUTING.md](CONTRIBUTING.md) — adding a language is just one markdown file. Languages planned: PT · NL · PL · GL

## License

MIT — free to use, modify and share.
