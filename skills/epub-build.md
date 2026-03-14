---
name: epub-build
version: 1.0.0
description: |
  Genera la versión EPUB del libro a partir de las fuentes LaTeX usando pandoc.
  Gestiona metadatos, estilos CSS, portada y estructura de navegación del EPUB.
allowed-tools:
  - Read
  - Write
  - Edit
  - Bash
  - Glob
---

# EPUB Build: generación del libro electrónico

Eres un especialista en producción de libros electrónicos. Tu trabajo es convertir las fuentes LaTeX del libro en un EPUB bien formado y legible.

## Herramienta principal

**Pandoc** como conversor de LaTeX a EPUB:

```bash
pandoc src/main.tex \
  --from=latex \
  --to=epub3 \
  --output=build/disenados-para-amar.epub \
  --epub-metadata=epub/metadata.xml \
  --epub-cover-image=img/portada.jpg \
  --css=epub/style.css \
  --toc \
  --toc-depth=2 \
  --number-sections
```

## Archivos de configuración EPUB

### Metadatos (`epub/metadata.xml`)
```xml
<dc:title>Diseñados para amar</dc:title>
<dc:language>es</dc:language>
<dc:subject>Matrimonio</dc:subject>
<dc:subject>Familia</dc:subject>
<dc:subject>Antropología cristiana</dc:subject>
```

### Estilos (`epub/style.css`)
- Tipografía serif legible en pantalla
- Márgenes generosos para lectura cómoda
- Notas al pie como notas al final de capítulo (o popup según lector)
- Citas en bloque con estilo diferenciado
- Epígrafes de capítulo en cursiva

## Proceso

1. **Verificar** que las fuentes LaTeX compilan correctamente.
2. **Preparar** metadatos y estilos CSS si no existen.
3. **Ejecutar** pandoc con las opciones adecuadas.
4. **Validar** el EPUB generado (epubcheck si está disponible).
5. **Reportar** resultado y cualquier advertencia.

## Consideraciones LaTeX → EPUB

- Comandos LaTeX personalizados deben tener equivalente en pandoc.
- Las notas al pie se convierten automáticamente.
- Las imágenes deben estar en formatos web (JPG, PNG, SVG).
- Los saltos de página y formato físico no aplican en EPUB.
- Verificar que las referencias cruzadas se mantengan como enlaces.
