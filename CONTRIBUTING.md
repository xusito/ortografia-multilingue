# Contributing — Adding a new language

Adding a new language to `ortografia-multilingue` takes one file and one line. No changes to SKILL.md needed.

---

## Steps

### 1. Create `references/[lang].md`

Use the ISO 639-1 two-letter code (e.g., `pt` for Portuguese, `nl` for Dutch, `pl` for Polish).

Copy this template and fill it in:

```markdown
# [Language name] — [Spelling / Orthographie / Ortografía / ...]

## Official dictionaries
- **Primary**: [URL]
- **Secondary**: [URL]

When in doubt about a word, look it up before correcting.

---

## Special characters
[List the language's accent marks, diacritics, special letters]

---

## Spelling rules

### [Rule category 1]

| Error | Correction |
|---|---|
| `wrong` | `correct` |

### [Rule category 2]
...

---

## Common AI translation errors
[List the patterns that AI models typically get wrong in this language]
```

### 2. Update README.md

Add a section for the new language following the existing pattern (language name in its own language, installation, usage phrases).

### 3. Open a pull request

- Title: `Add [Language] support`
- Include a few example corrections in the PR description to show the rules work

---

## Quality checklist

Before submitting, verify your `references/[lang].md`:

- [ ] Uses the official dictionary / academy as the primary source
- [ ] Covers the most common AI spelling mistakes for that language
- [ ] Includes a "words that do NOT need accent" section (to prevent overcorrection)
- [ ] Special characters are correctly encoded (UTF-8)
- [ ] Examples in the error/correction tables are real mistakes, not invented ones

---

## Languages in progress / Planned

| Language | Code | Status |
|----------|------|--------|
| Português | PT | planned |
| Nederlands | NL | planned |
| Polski | PL | planned |
| Galego | GL | planned |

Open an issue if you want to claim a language before starting.

---

## Questions?

Open an issue on GitHub. All contributions welcome.
