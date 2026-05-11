---
name: ortografia-multilingue
description: Corrector ortográfico automático para ES, CA, FR, IT, EN y DE. Actívalo SIEMPRE que generes, edites, traduzcas o revises cualquier texto en español, catalán, francés, italiano, inglés o alemán. Detecta el idioma automáticamente, carga las reglas del diccionario oficial correspondiente y corrige tildes, acentos, diéresis, umlauts, ß y errores ortográficos visibles. Úsalo cuando el usuario diga "revisa la ortografía", "corrígeme esto", "tiene faltas", "check spelling", "vérifie l'orthographe", "correggi", "rechtschreibung", o cualquier variante. También actívalo antes de dar por cerrado cualquier fragmento de texto en estos idiomas.
---

## Objetivo

Corregir errores ortográficos en textos en ES, CA, FR, IT, EN y DE. Foco exclusivo en **ortografía pura**: tildes, acentos, caracteres especiales, grafía correcta de palabras. No es revisión de estilo ni de gramática.

---

## Proceso

1. **Detecta el idioma** del fragmento. Si hay mezcla, trata cada sección por separado.
2. **Lee el archivo de referencia** correspondiente:
   - Español → `references/es.md`
   - Català → `references/ca.md`
   - Français → `references/fr.md`
   - Italiano → `references/it.md`
   - English → `references/en.md`
   - Deutsch → `references/de.md`
3. **Escanea el texto** aplicando las reglas de ese archivo.
4. **Si tienes duda** sobre una palabra, consulta el diccionario oficial indicado en el archivo de referencia antes de corregir. Si la forma original es correcta, no la toques.
5. **Devuelve el texto corregido** directamente.
6. **Muestra la tabla de auditoría** con todas las correcciones realizadas.

---

## Manejo de HTML, JSON y texto mixto

- Corrige solo el **contenido textual visible**: valores de atributos `title`, `alt`, `aria-label`, texto entre etiquetas, strings en JSON.
- No toques: etiquetas HTML, URLs, clases CSS, nombres de variables, keys de JSON, código.
- Respeta entidades HTML ya existentes (`&amp;`, `&nbsp;`, etc.).
- En JSON, devuelve el JSON completo corregido manteniendo la estructura exacta.

---

## Tabla de auditoría

Al final del texto corregido, muestra siempre:

| # | Original | Corrección | Tipo | Contexto |
|---|---|---|---|---|
| 1 | `ejemplo` | `corrección` | Tilde ES / Acento CA / Accent FR / Accento IT / Spelling EN / Umlaut DE | "...4-6 palabras..." |

Si no hay errores: `Sin errores ortográficos detectados.`

Tipos disponibles: `Tilde ES`, `Acento CA`, `Punt volat CA`, `Accent FR`, `Accento IT`, `Spelling EN`, `Apostrophe EN`, `Umlaut DE`, `Eszett DE`, `Majúscula DE`, `Grafía`.

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
  .contexto { color: #6b7280; font-style: italic; font-size: .88rem; }
  .summary { margin-top: 1.5rem; padding: .8rem 1rem; background: #f0fdf4; border-left: 3px solid #16a34a; font-size: .9rem; }
</style>
</head>
<body>
<h1>Informe de correcciones ortograficas</h1>
<p class="meta">Archivo: <strong>[nombre]</strong> | Idioma: <strong>[idioma]</strong> | Fecha: <strong>[fecha]</strong></p>
<table>
<thead><tr><th>#</th><th>Original</th><th>Correccion</th><th>Tipo</th><th>Contexto</th></tr></thead>
<tbody>
  <!-- una fila por corrección:
  <tr>
    <td>1</td>
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
