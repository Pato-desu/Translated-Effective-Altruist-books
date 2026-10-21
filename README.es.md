[English](README.md) | [Español]

Este repositorio contiene traducciones generadas por IA de libros y ensayos fundamentales relacionados con el **Altruismo Eficaz** y la **Racionalidad**. Mi objetivo es hacer que las ideas de alto impacto sean accesibles para una audiencia global mediante el uso de LLMs (Modelos de Lenguaje Extensos) modernos, preservando el formato y el contexto original.

Las traducciones realizadas están lejísimas de ser perfectas, pero son un buen punto de partida y considero de lejos mejor que estén disponibles en este estado que no lo estén. La perfección es la enemiga de lo bueno, y la disponibilidad de estas traducciones puede ayudar a que más personas se beneficien de estas ideas.

## 📋 Traducciones Disponibles

A continuación se muestra la lista de traducciones completadas. Cada archivo ha sido procesado para mantener notas al pie, enlaces internos y terminología técnica.

| Título del Libro | Idioma | Calidad | Modelo de IA | Notas |
| :--- | :--- | :--- | :--- | :--- |
| **Rationality: From AI to Zombies** | Español | Primer intento revisión básica pendiente | Gemini 2.5 (Cap 1-21)/ 2.5 Flash Lite (22-53)/ 3.1 Flash Lite (54-final) | Lotes de 8000 caracteres. Enlaces externos recuperados con Claude (2026-10), 97,8 % conservados | |
| **Doing Good Better** | Español | Primer intento, revisión básica pendiente | Gemini 2.5 Flash Lite | Lotes de 30000 caracteres. Faltantes completados y enlaces externos recuperados con Claude (2026-10) |

## 🛠️ Metodología de Traducción

**Traducciones existentes (antes de 2026-10):** hechas con Calibre + el plugin Ebook Translator, usando los modelos Gemini indicados en la tabla.

**Ahora:** el proyecto lo mantiene un pipeline automático en la nube que no necesita Calibre ni mi computadora. Descomprime el EPUB, divide cada capítulo en unidades del tamaño de un párrafo (los enlaces, notas al pie e imágenes se conservan como marcadores numerados), traduce los lotes con Claude (primero el modelo más chico con poco esfuerzo; uno más potente solo donde fallan los controles automáticos), controla cada lote (que no falte nada, que no quede nada en inglés, que los enlaces estén intactos y que se respete el glosario) y vuelve a escribir un EPUB válido. El progreso se guarda después de cada lote, así que el trabajo puede detenerse y retomarse en cualquier momento. Las traducciones existentes no se rehacen: se completan los faltantes y se vuelven a traducir los peores pasajes. Los informes de auditoría y calidad están en `reports/`.

Los libros nuevos se toman de a uno del [EA Archive](https://forum.effectivealtruism.org/posts/DndmvDGStD3gTfhXk/announcing-the-ea-archive) (su [carpeta pública de Google Drive](https://drive.google.com/drive/folders/1CSKOlo2nE9JtD1u8fUssMyTqOoJEeYMQ)) o de archivos puestos en `inbox/`. Las fuentes y notas de licencia están en `sources.md`.

## ⚙️ Comandos

Python 3.11, `pip install -r requirements.txt`; se ejecutan desde esta carpeta. Sin Calibre.

```
python -m pytest                                        # pruebas
python scripts/epub.py check <epub>... [--lenient]      # control estructural de un EPUB
python scripts/epub.py audit                            # audita cada original contra su EPUB en español -> reports/
python scripts/epub.py split <libro> <idioma>           # corta un libro en lotes (idioma: es o zh)
python scripts/epub.py status <libro> <idioma>          # avance, reintentos, lotes atascados
python scripts/epub.py qa <libro> <idioma>              # control de calidad de los lotes traducidos
python scripts/epub.py merge <libro> <idioma>           # reconstruye el archivo traducido
python scripts/patch.py split <libro> es                # solo los pasajes que siguen en inglés
python scripts/links.py <libro> es                      # recupera enlaces externos perdidos en la traducción
python scripts/consistency.py <libro> es --mine 30      # informe de consistencia de términos -> reports/
python scripts/pdfread.py <archivo.pdf>                 # PDF de texto -> capítulos en Markdown en work/
python scripts/mdepub.py <libro.md> --out <archivo.epub> --lang zh-Hans   # capítulos en Markdown -> un EPUB
```

## 🇨🇳 Libros en chino (en curso)

*The Precipice* y *What We Owe the Future* se traducen primero al chino simplificado, un EPUB por libro en `Chinese/`. El lector de PDF, el encargo en chino, el glosario (`glossary.zh.tsv`), el control de calidad y el generador de EPUB están listos; la traducción empieza en cuanto los dos PDF de origen estén en `inbox/`. Esta tabla recibirá sus filas cuando terminen.

## ⚖️ Licencias y atribución

- *Rationality: From AI to Zombies*, de Eliezer Yudkowsky (MIRI), se publica bajo CC BY-NC-SA 3.0. La traducción al español es una obra derivada bajo la misma licencia: atribución, no comercial, compartir igual.
- *Doing Good Better*, de William MacAskill, es un libro publicado; los derechos de traducción pertenecen al autor y a la editorial. La traducción se comparte aquí como un esfuerzo de accesibilidad sin fines comerciales; si un titular de derechos se opone, abrí un Issue y se retirará.
- De cada libro nuevo se anota en `sources.md` de dónde viene y qué se sabe de su licencia; los libros con una licencia claramente restrictiva no se traducen.

## ➕ Cómo añadir un libro

1. Poné el EPUB (o un PDF de texto, Markdown, HTML o texto plano) en `inbox/` y agregá una línea a `QUEUE.md`, o abrí un Issue con un enlace.
2. Ejecutá `python scripts/epub.py split <libro> <idioma>`, traducí los lotes, `python scripts/epub.py qa <libro> <idioma>` y luego `merge`. Los detalles están en `TRANSLATE.md` (español), `TRANSLATE.zh.md` (chino) y `DISPATCH.md`.
3. Comprobá el resultado con `python scripts/epub.py check` y `audit`.

## 🩹 Correcciones y Colaboraciones

Si quieres ayudar a corregir errores o añadir nuevas traducciones, abrí un "Issue" o "Pull Request".

## 🔮 Planes Posibles a futuro

- Añadir más traducciones a más idiomas de demás libros de EA y Racionalidad, principalmente los que están en el [EA Archive](https://forum.effectivealtruism.org/posts/DndmvDGStD3gTfhXk/announcing-the-ea-archive).
- Mejorar la calidad de las traducciones existentes, ya sea manualmente o mediante mejores IAs.
- Si hay interés, convertir a Markdown o HTML y añadir la forma de unzip and zip epubs para facilitar las correcciones.
- Revisión por muestreo y retraducción de los peores pasajes.
