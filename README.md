# ortografia-multilingue

A Claude Code skill for automatic spell checking in 6 European languages: **ES · CA · FR · IT · EN · DE**

---

## 🇪🇸 Español

### ¿Qué hace?
Corrector ortográfico automático para textos en español, catalán, francés, italiano, inglés y alemán. Detecta el idioma, aplica las reglas del diccionario oficial y devuelve el texto corregido con una tabla de auditoría de cambios. Bajo petición genera un informe HTML descargable.

### Instalación
```bash
# Opción A: clonar el repositorio en tu carpeta de skills
git clone https://github.com/TU_USUARIO/ortografia-multilingue ~/.claude/skills/ortografia-multilingue

# Opción B: descargar el archivo .skill desde Releases y ejecutar en Claude Code
/install-skill ortografia-multilingue.skill
```

### Uso
El skill se activa automáticamente cuando generas o editas texto en cualquiera de los 6 idiomas. También puedes invocarlo manualmente:
- "revisa la ortografía de este texto"
- "corrígeme esto"
- "tiene faltas ortográficas"
- "informe HTML" — genera un archivo HTML con todas las correcciones

---

## 🏴 Català

### Què fa?
Corrector ortogràfic automàtic per a textos en espanyol, català, francès, italià, anglès i alemany. Detecta l'idioma, aplica les regles del diccionari oficial i retorna el text corregit amb una taula d'auditoria de canvis.

### Instal·lació
```bash
git clone https://github.com/TU_USUARI/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Ús
S'activa automàticament en generar o editar text en qualsevol dels 6 idiomes. També: "revisa l'ortografia", "corrija això", "té faltes".

---

## 🇫🇷 Français

### Que fait-il ?
Correcteur orthographique automatique pour les textes en espagnol, catalan, français, italien, anglais et allemand. Détecte la langue, applique les règles du dictionnaire officiel et renvoie le texte corrigé avec un tableau d'audit des modifications.

### Installation
```bash
git clone https://github.com/TON_UTILISATEUR/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Utilisation
S'active automatiquement lors de la génération ou l'édition de texte dans l'une des 6 langues. Aussi : "vérifie l'orthographe", "corrige ça", "il y a des fautes", "rapport HTML".

---

## 🇮🇹 Italiano

### Cosa fa?
Correttore ortografico automatico per testi in spagnolo, catalano, francese, italiano, inglese e tedesco. Rileva la lingua, applica le regole del dizionario ufficiale e restituisce il testo corretto con una tabella di audit delle modifiche.

### Installazione
```bash
git clone https://github.com/TUO_UTENTE/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Utilizzo
Si attiva automaticamente durante la generazione o modifica di testo in una delle 6 lingue. Anche: "controlla l'ortografia", "correggi questo", "ci sono errori", "report HTML".

---

## 🇬🇧 English

### What does it do?
Automatic spell checker for texts in Spanish, Catalan, French, Italian, English and German. Detects the language, applies the rules of the official dictionary, and returns the corrected text with an audit table of changes. On request, generates a downloadable HTML report.

### Installation
```bash
# Option A: clone into your skills folder
git clone https://github.com/YOUR_USERNAME/ortografia-multilingue ~/.claude/skills/ortografia-multilingue

# Option B: download the .skill file from Releases
/install-skill ortografia-multilingue.skill
```

### Usage
Activates automatically when generating or editing text in any of the 6 languages. You can also invoke it manually:
- "check the spelling of this text"
- "fix the spelling mistakes"
- "HTML report" — generates an HTML file with all corrections

---

## 🇩🇪 Deutsch

### Was macht es?
Automatischer Rechtschreibprüfer für Texte auf Spanisch, Katalanisch, Französisch, Italienisch, Englisch und Deutsch. Erkennt die Sprache, wendet die Regeln des offiziellen Wörterbuchs an und gibt den korrigierten Text mit einer Änderungsübersicht zurück.

### Installation
```bash
git clone https://github.com/DEIN_BENUTZERNAME/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Verwendung
Wird automatisch aktiviert, wenn Text in einer der 6 Sprachen erstellt oder bearbeitet wird. Auch: "Rechtschreibung prüfen", "das korrigieren", "HTML-Bericht".

---

## Supported languages / Idiomas soportados

| Code | Language | Dictionary |
|------|----------|------------|
| ES | Español | RAE — rae.es |
| CA | Català | DIEC — dlc.iec.cat |
| FR | Français | Académie française |
| IT | Italiano | Treccani — treccani.it |
| EN | English | Merriam-Webster / Oxford |
| DE | Deutsch | Duden — duden.de |

---

## Adding a new language / Añadir un idioma

See [CONTRIBUTING.md](CONTRIBUTING.md) — adding a language is just one new file.

## License

MIT — free to use, modify and share.
