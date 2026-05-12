---
name: ortografia-multilingue
description: >
  Corrector ortográfico automático para 11 idiomas europeos (ES, CA, FR, IT, EN, DE, PT, PL, SV, DA, NO).
  Actívalo SIEMPRE que generes, edites, traduzcas o revises cualquier texto en español, catalán, francés,
  italiano, inglés, alemán, portugués, polaco, sueco, danés o noruego. Detecta el idioma automáticamente,
  carga las reglas del diccionario oficial correspondiente y corrige tildes, acentos, diéresis, umlauts, ß,
  ogonki polacos, vogais nasais portuguesas y caracteres especiales nórdicos (å æ ø). Úsalo cuando el usuario
  diga revisa la ortografía, corrígeme esto, tiene faltas, check spelling, vérifie l'orthographe, correggi,
  rechtschreibung, sprawdź pisownię, stavningskontroll, o cualquier variante. También actívalo antes de dar
  por cerrado cualquier fragmento de texto en estos idiomas.
---

## Objetivo

Corregir errores ortográficos en 11 idiomas europeos. Foco en **ortografía pura**: tildes, acentos, caracteres especiales, grafía correcta, vocabulario de estilo IA. No es revisión de gramática ni redacción.

---

## Proceso

1. **Detecta el idioma** del fragmento.

2. **Texto mixto (opción 3):** Si el texto mezcla dos idiomas, pregunta antes de continuar:
   > "Este texto mezcla [idioma A] y [idioma B]. ¿A qué idioma aplico las correcciones ortográficas?"
   Espera respuesta antes de corregir.

3. **Variante del mismo idioma (opción 4):** Si detectas inconsistencia de variante dentro del mismo texto (inglés US/UK mezclado, portugués PT/BR mezclado, noruego Bokmål/Nynorsk mezclado), pregunta:
   > "Este texto mezcla [variante A] y [variante B]. ¿En cuál quieres que lo unifique?"
   Espera respuesta antes de corregir.

4. **Lee el archivo de referencia** correspondiente:
   - Español → `references/es.md`
   - Català → `references/ca.md`
   - Français → `references/fr.md`
   - Italiano → `references/it.md`
   - English → `references/en.md`
   - Deutsch → `references/de.md`
   - Português → `references/pt.md`
   - Polski → `references/pl.md`
   - Svenska → `references/sv.md`
   - Dansk → `references/da.md`
   - Norsk → `references/no.md`

5. **Escanea el texto** aplicando las reglas de ese archivo, incluyendo la lista de vocabulario IA a evitar.

6. **Falsos positivos — NO corregir (opción 1):**
   - Nombres propios de personas, empresas, marcas y productos (`Coca-Cola`, `WordPress`, `iPhone`)
   - URLs, dominios y rutas (`codigo-qr.es`, `/ca/reformes/`)
   - Código: etiquetas HTML, clases CSS, variables, funciones, keys de JSON
   - Términos técnicos establecidos en el sector (`SEO`, `API`, `SaaS`, `JSON-LD`)
   - Palabras en otro idioma usadas intencionalmente (p.ej. anglicismos en texto español que son nombres de producto)
   - Si tienes duda sobre si una palabra es nombre propio o error, búscala en el diccionario antes de corregir.

7. **Si tienes duda** sobre una palabra, consulta el diccionario oficial indicado en el archivo de referencia antes de corregir. Si la forma original es correcta, no la toques.

8. **Devuelve el texto corregido** directamente.

9. **Muestra la tabla de auditoría** con todas las correcciones realizadas.

---

## Manejo de HTML, JSON y texto mixto

- Corrige solo el **contenido textual visible**: valores de atributos `title`, `alt`, `aria-label`, texto entre etiquetas, strings en JSON.
- No toques: etiquetas HTML, URLs, clases CSS, nombres de variables, keys de JSON, código.
- Respeta entidades HTML ya existentes (`&amp;`, `&nbsp;`, etc.).
- En JSON, devuelve el JSON completo corregido manteniendo la estructura exacta.

---

## Tabla de auditoría

Al final del texto corregido, muestra siempre:

| # | Prioridad | Original | Corrección | Tipo | Contexto |
|---|---|---|---|---|---|
| 1 | 🔴 Alta | `ejemplo` | `corrección` | Tilde ES | "...4-6 palabras..." |

Si no hay errores: `Sin errores ortográficos detectados.`

### Criterios de prioridad

**🔴 Alta** — errores visibles de inmediato o que cambian el significado:
- Error en `<title>`, `<h1>`, `<h2>`, `meta description`, `og:title`
- Monosílabo con/sin acento que cambia significado (ES: `el`/`él`, IT: `e`/`è`, FR: `ou`/`où`)
- Signo de apertura faltante en ES/CA (`¿`, `¡`)
- Comillas o puntuación incorrectas en FR (guillemets, espacio antes de `!`)
- Umlaut completamente omitido en DE que hace la palabra irreconocible

**🟡 Media** — errores ortográficos estándar en cuerpo de texto:
- Tilde faltante en esdrújula o aguda en ES
- Acento faltante en final de palabra IT (`città`, `caffè`)
- Acento faltante en CA (`també`, `però`, `és`)
- Mayúscula faltante en sustantivo DE
- Carácter especial faltante (`ç`, `ß`, `ą`, `å`, etc.)

**🟢 Baja** — estilo o variante, no error ortográfico puro:
- Vocabulario IA detectado (sugerencia de sustitución)
- Inconsistencia de variante US/UK o PT/BR
- Ligatura opcional en FR (`oeuvre` → `œuvre`)
- Decimal o separador de miles incorrecto

### Tipos disponibles
`Tilde ES` · `Vocab IA ES` · `Puntuación ES` · `Acento CA` · `Punt volat CA` · `Accent FR` · `Vocab IA FR` · `Ponctuation FR` · `Accento IT` · `Vocab IA IT` · `Spelling EN` · `Apostrophe EN` · `Vocab IA EN` · `Punctuation EN` · `Umlaut DE` · `Eszett DE` · `Majúscula DE` · `Vocab IA DE` · `Nasal PT` · `Cedilha PT` · `Vocab IA PT` · `Ogonek PL` · `Vocab IA PL` · `Specialtecken SV` · `Vocab IA SV` · `Specialtegn DA` · `Vocab IA DA` · `Spesialtegn NO` · `Vocab IA NO` · `Grafía`

---

## Informe HTML

Cuando el usuario pida "informe HTML", "listado HTML", "exportar correcciones" o similar, genera `ortografia_informe.html` en el directorio de trabajo con esta estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Informe ortografico</title>
<style>
  body { font-family: system-ui, sans-serif; max-width: 960px; margin: 2rem auto; padding: 0 1rem; color: #1a1a1a; }
  h1 { font-size: 1.4rem; border-bottom: 2px solid #e5e7eb; padding-bottom: .5rem; }
  .meta { color: #6b7280; font-size: .9rem; margin-bottom: 1.5rem; }
  table { width: 100%; border-collapse: collapse; font-size: .92rem; }
  th { background: #f3f4f6; text-align: left; padding: .6rem .8rem; font-weight: 600; }
  td { padding: .55rem .8rem; border-bottom: 1px solid #e5e7eb; vertical-align: top; }
  tr:hover td { background: #fafafa; }
  .original { color: #dc2626; font-family: monospace; }
  .correcto { color: #16a34a; font-family: monospace; font-weight: 600; }
  .tipo { display: inline-block; padding: .15rem .5rem; border-radius: 9999px; font-size: .78rem; font-weight: 500; }
  .es { background:#dbeafe; color:#1d4ed8; }
  .ca { background:#fce7f3; color:#9d174d; }
  .fr { background:#fef9c3; color:#854d0e; }
  .it { background:#dcfce7; color:#166534; }
  .en { background:#f3e8ff; color:#6b21a8; }
  .de { background:#ffedd5; color:#9a3412; }
  .pt { background:#d1fae5; color:#065f46; }
  .pl { background:#fef3c7; color:#78350f; }
  .sv { background:#e0e7ff; color:#3730a3; }
  .da { background:#fce7f3; color:#831843; }
  .no { background:#f0fdf4; color:#166534; }
  .contexto { color: #6b7280; font-style: italic; font-size: .88rem; }
  .pri { display: inline-block; padding: .15rem .4rem; border-radius: 9999px; font-size: .78rem; font-weight: 600; }
  .pri-alta { background:#fee2e2; color:#991b1b; }
  .pri-media { background:#fef9c3; color:#854d0e; }
  .pri-baja { background:#dcfce7; color:#166534; }
  .summary { margin-top: 1.5rem; padding: .8rem 1rem; background: #f0fdf4; border-left: 3px solid #16a34a; font-size: .9rem; }
</style>
</head>
<body>
<h1>Informe de correcciones ortograficas</h1>
<p class="meta">Archivo: <strong>[nombre]</strong> | Idioma: <strong>[idioma]</strong> | Fecha: <strong>[fecha]</strong></p>
<table>
<thead><tr><th>#</th><th>Prioridad</th><th>Original</th><th>Correccion</th><th>Tipo</th><th>Contexto</th></tr></thead>
<tbody>
  <!-- una fila por corrección:
  <tr>
    <td>1</td>
    <td><span class="pri pri-alta">Alta</span></td>
    <td><span class="original">palabra</span></td>
    <td><span class="correcto">corrección</span></td>
    <td><span class="tipo es">Tilde ES</span></td>
    <td><span class="contexto">"...contexto..."</span></td>
  </tr>
  -->
</tbody>
</table>
<div class="summary">Total: <strong>[N]</strong> correcciones</div>
</body>
</html>
```

Clases de color por idioma: `.es`, `.ca`, `.fr`, `.it`, `.en`, `.de`.

Tras guardar el archivo, indica la ruta exacta para que el usuario pueda abrirlo en el navegador.
