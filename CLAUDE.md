# Diseñados para amar

## Proyecto
Libro sobre la dimensión antropológica del matrimonio y la familia. Formato libro de bolsillo (A5) en LaTeX a dos caras, con versión EPUB paralela.

## Idioma
Todo el contenido del libro se escribe en **español**. Las instrucciones internas y skills pueden estar en español o inglés.

## Tono y estilo
- Cercano, humano, cálido. Nunca académico-frío ni predicador.
- Dirigido a parejas que se preparan para el matrimonio, no a teólogos.
- Usar la skill `/humanizer` para revisar cada capítulo antes de darlo por terminado.
- Las notas a pie de página llevan las referencias y ampliaciones para no sobrecargar el texto principal.

## Estructura del proyecto
```
disenados/
├── CLAUDE.md              # Este archivo
├── skills.md              # Índice de skills disponibles
├── skills/                # Carpeta de skills
│   ├── humanizer/         # Skill de humanización (github.com/blader/humanizer)
│   ├── footnotes.md       # Skill de notas a pie de página
│   ├── latex-template.md  # Skill de diseño de plantillas LaTeX
│   ├── doctrine-search.md # Skill de búsqueda de doctrina católica
│   ├── epub-build.md      # Skill de generación EPUB
│   └── structure.md       # Skill de estructura narrativa
├── src/                   # Fuentes LaTeX del libro
│   ├── main.tex           # Documento principal
│   ├── preamble.tex       # Preámbulo y configuración
│   └── chapters/          # Capítulos individuales
├── epub/                  # Fuentes y configuración EPUB
├── img/                   # Imágenes
└── build/                 # Archivos generados (PDF, EPUB)
```

## Convenciones LaTeX
- Codificación UTF-8
- Compilar con LuaLaTeX o XeLaTeX (soporte Unicode nativo)
- Un archivo .tex por capítulo en `src/chapters/`
- Notas al pie con `\footnote{}`, referencias con BibLaTeX
- Idioma: `\usepackage[spanish]{babel}`

## Flujo de trabajo
1. Redactar contenido en borrador
2. Aplicar `/humanizer` para revisar tono
3. Aplicar `/footnotes` para añadir referencias y notas
4. Aplicar `/doctrine-search` cuando se necesiten fuentes magisteriales
5. Compilar LaTeX y EPUB para verificar formato

## Fuentes doctrinales principales
- Catecismo de la Iglesia Católica (CIC)
- Gaudium et Spes (Concilio Vaticano II)
- Familiaris Consortio (Juan Pablo II)
- Amoris Laetitia (Francisco)
- Teología del Cuerpo (Juan Pablo II)
- Deus Caritas Est (Benedicto XVI)
- Humanae Vitae (Pablo VI)
- Mulieris Dignitatem (Juan Pablo II)
