# ortografia-multilingue

Automatic spell checker skill for Claude Code — 11 European languages.

---

## Supported languages

| Flag | Code | Language | What it checks | Official dictionary |
|------|------|----------|---------------|---------------------|
| 🇪🇸 | ES | Español | Tildes (esdrújulas, llanas, agudas), interrogativas, monosílabos | [RAE](https://rae.es) |
| 🏴 | CA | Català | Accent grave/agut, punt volat (l·l), ce trencada (ç), diéresis | [DIEC](https://dlc.iec.cat) · [Optimot](https://optimot.gencat.cat) |
| 🇫🇷 | FR | Français | Accent aigu/grave/circonflexe, tréma, cédille (ç), ligatures (œ æ), majuscules | [Académie française](https://academie-francaise.fr) |
| 🇮🇹 | IT | Italiano | Accenti tonici finali (città, caffè), monosillabi distintivi (è/e, sì/si) | [Treccani](https://treccani.it) |
| 🇬🇧 | EN | English | Common misspellings, homophones (its/it's, their/there), apostrophes, US/UK variants | [Merriam-Webster](https://merriam-webster.com) |
| 🇩🇪 | DE | Deutsch | Umlauts (ä ö ü), Eszett (ß vs ss), Großschreibung der Substantive | [Duden](https://duden.de) |
| 🇵🇹 | PT | Português | Vogais nasais (ã õ), cedilha (ç), acentos, variantes PT/BR | [Priberam](https://priberam.pt) · [Michaelis](https://michaelis.uol.com.br) |
| 🇵🇱 | PL | Polski | Ogonki (ą ę), ó/u, ż/rz, ś ź ć ń, łL | [PWN](https://sjp.pwn.pl) |
| 🇸🇪 | SV | Svenska | å ä ö (mai aa/ae/oe), majúscules de dies i mesos | [SAOL](https://svenska.se) |
| 🇩🇰 | DA | Dansk | å æ ø (mai aa/ae/oe), store/små bogstaver | [DDO](https://ordnet.dk) |
| 🇳🇴 | NO | Norsk | å æ ø, Bokmål vs Nynorsk, store/små bokstaver | [Bokmålsordboka](https://ordbokene.no) |

---

## Live example

**[codigo-qr.es](https://codigo-qr.es)** — a multilingual QR code SaaS built in ES, CA, FR, IT, EN and DE. All copy and UI text are spell-checked with this skill before publishing. A real-world example of the skill catching and correcting orthographic errors across 6 languages.

---

## Example output

```
- instal·lacións → instal·lacions   [Acento CA]
- dinamico       → dinámico         [Tilde ES]
- francais       → français         [Cédille FR]
- citta          → città            [Accento IT]
- seperate       → separate         [Spelling EN]
- uber           → über             [Umlaut DE]
- nao            → não              [Vogal nasal PT]
- bede           → będę             [Ogonek PL]
- gar            → går              [Specialtecken SV]
- laese          → læse             [Specialtegn DA]
- gar            → går              [Spesialtegn NO]
```

On request, generates a color-coded HTML report with all corrections grouped by language.

---

## 🇪🇸 Español

### ¿Qué hace?
Corrector ortográfico automático para 11 idiomas europeos. Detecta el idioma, aplica las reglas del diccionario oficial y devuelve el texto corregido con una tabla de auditoría. Bajo petición genera un informe HTML descargable.

### Instalación
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Uso
Se activa automáticamente al generar o editar texto en cualquiera de los 11 idiomas. También: "revisa la ortografía", "corrígeme esto", "tiene faltas", "informe HTML".

---

## 🏴 Català

### Què fa?
Corrector ortogràfic automàtic per a 11 idiomes europeus. Detecta l'idioma, aplica les regles del diccionari oficial i retorna el text corregit amb una taula d'auditoria.

### Instal·lació
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Ús
S'activa automàticament. També: "revisa l'ortografia", "corregeix això", "té faltes", "informe HTML".

---

## 🇫🇷 Français

### Que fait-il ?
Correcteur orthographique automatique pour 11 langues européennes. Détecte la langue, applique les règles du dictionnaire officiel et renvoie le texte corrigé avec un tableau d'audit.

### Installation
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Utilisation
S'active automatiquement. Aussi : "vérifie l'orthographe", "corrige ça", "il y a des fautes", "rapport HTML".

---

## 🇮🇹 Italiano

### Cosa fa?
Correttore ortografico automatico per 11 lingue europee. Rileva la lingua, applica le regole del dizionario ufficiale e restituisce il testo corretto con una tabella di audit.

### Installazione
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Utilizzo
Si attiva automaticamente. Anche: "controlla l'ortografia", "correggi questo", "ci sono errori", "report HTML".

---

## 🇬🇧 English

### What does it do?
Automatic spell checker for 11 European languages. Detects the language, applies the rules of the official dictionary, and returns the corrected text with an audit table. On request, generates a downloadable HTML report.

### Installation
```bash
# Option A: clone
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue

# Option B: download .skill from Releases
/install-skill ortografia-multilingue.skill
```

### Usage
Activates automatically. Also: "check the spelling", "fix spelling mistakes", "HTML report".

---

## 🇩🇪 Deutsch

### Was macht es?
Automatischer Rechtschreibprüfer für 11 europäische Sprachen. Erkennt die Sprache, wendet die Regeln des offiziellen Wörterbuchs an und gibt den korrigierten Text mit einer Änderungsübersicht zurück.

### Installation
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Verwendung
Wird automatisch aktiviert. Auch: "Rechtschreibung prüfen", "das korrigieren", "HTML-Bericht".

---

## 🇵🇹 Português

### O que faz?
Corretor ortográfico automático para 11 idiomas europeus. Detecta o idioma, aplica as regras do dicionário oficial e devolve o texto corrigido com uma tabela de auditoria. Suporta variantes PT (Portugal) e BR (Brasil).

### Instalação
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Uso
Ativa-se automaticamente ao gerar ou editar texto em qualquer dos 11 idiomas. Também: "revisa a ortografia", "corrige isto", "tem erros", "relatório HTML".

---

## 🇵🇱 Polski

### Co robi?
Automatyczny korektor pisowni dla 11 języków europejskich. Wykrywa język, stosuje zasady oficjalnego słownika i zwraca poprawiony tekst z tabelą zmian.

### Instalacja
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Użycie
Aktywuje się automatycznie. Również: "sprawdź pisownię", "popraw to", "są błędy", "raport HTML".

---

## 🇸🇪 Svenska

### Vad gör den?
Automatisk stavningskontroll för 11 europeiska språk. Identifierar språket, tillämpar reglerna i den officiella ordboken och returnerar den korrigerade texten med en ändringsöversikt.

### Installation
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Användning
Aktiveras automatiskt. Även: "stavningskontroll", "rätta detta", "det finns fel", "HTML-rapport".

---

## 🇩🇰 Dansk

### Hvad gør det?
Automatisk stavekontrol for 11 europæiske sprog. Registrerer sproget, anvender reglerne i den officielle ordbog og returnerer den rettede tekst med en ændringsoversigt.

### Installation
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Brug
Aktiveres automatisk. Også: "stavekontrol", "ret dette", "der er fejl", "HTML-rapport".

---

## 🇳🇴 Norsk

### Hva gjør det?
Automatisk stavekontroll for 11 europeiske språk. Gjenkjenner språket, bruker reglene i den offisielle ordboken og returnerer den rettede teksten med en endringslogg. Støtter både Bokmål og Nynorsk.

### Installasjon
```bash
git clone https://github.com/xusito/ortografia-multilingue ~/.claude/skills/ortografia-multilingue
```

### Bruk
Aktiveres automatisk. Også: "stavekontroll", "rett dette", "det er feil", "HTML-rapport".

---

## Adding a new language / Añadir un idioma

See [CONTRIBUTING.md](CONTRIBUTING.md) — adding a language is just one markdown file.

Languages planned: RO · NL · CS · HU · GL

## License

MIT — free to use, modify and share.
