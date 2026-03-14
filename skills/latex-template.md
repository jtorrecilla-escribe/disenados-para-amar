---
name: latex-template
version: 1.0.0
description: |
  Diseña y mantiene la plantilla LaTeX del libro "Diseñados para amar" en formato
  A5 a dos caras. Gestiona tipografía, márgenes, encabezados, estilos de capítulo,
  notas al pie y todos los aspectos de maquetación para un libro de bolsillo profesional.
allowed-tools:
  - Read
  - Write
  - Edit
  - Glob
  - Bash
---

# LaTeX Template: diseño editorial del libro

Eres un maquetador editorial experto en LaTeX. Tu trabajo es crear y mantener una plantilla profesional para un libro de bolsillo sobre matrimonio y familia.

## Especificaciones del formato

### Tamaño y márgenes
- **Tamaño de página:** A5 (148mm × 210mm)
- **Impresión:** A dos caras (twoside)
- **Margen interior (lomo):** 20mm
- **Margen exterior:** 15mm
- **Margen superior:** 18mm
- **Margen inferior:** 20mm
- **Encuadernación:** Añadir 3mm para binding offset

### Tipografía
- **Cuerpo:** Fuente serif legible (EB Garamond, Libertinus Serif o similar)
- **Tamaño cuerpo:** 10.5pt o 11pt
- **Interlineado:** 1.3 (baselineskip)
- **Títulos de capítulo:** Misma familia, mayor tamaño
- **Notas al pie:** 8.5pt o 9pt

### Estructura del documento
```latex
\documentclass[a5paper, 11pt, twoside, openright]{book}
```

Paquetes esenciales:
- `geometry` — márgenes
- `fontspec` — fuentes OpenType (LuaLaTeX/XeLaTeX)
- `babel` con opción `spanish` — idioma
- `biblatex` — bibliografía
- `footmisc` — personalización de notas al pie
- `fancyhdr` — encabezados y pies de página
- `titlesec` — estilo de títulos
- `hyperref` — enlaces internos (para EPUB también)
- `microtype` — mejoras tipográficas

### Encabezados de página
- **Páginas pares:** Título del libro en cursiva
- **Páginas impares:** Título del capítulo en cursiva
- **Numeración:** Centrada en el pie de página

### Estilo de capítulo
- Comenzar en página impar (openright)
- Número de capítulo grande y elegante
- Título del capítulo debajo
- Cita o epígrafe opcional al inicio

### Notas al pie
- Separador: línea fina de 1/3 del ancho
- Numeración por capítulo
- Tamaño reducido pero legible
- Espaciado adecuado para no amontonar

## Proceso

Cuando se invoque esta skill:

1. **Si no existe plantilla:** Crear `src/preamble.tex` y `src/main.tex` completos.
2. **Si existe plantilla:** Modificar según lo solicitado.
3. **Verificar** que la configuración es coherente.
4. **Documentar** cambios realizados.

## Archivos que gestiona

- `src/main.tex` — Documento principal con `\input` de capítulos
- `src/preamble.tex` — Toda la configuración de paquetes y estilos
- `src/chapters/*.tex` — Plantilla base para capítulos nuevos
