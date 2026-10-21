[English](README.md) | [Español]

Este repositorio contiene traducciones generadas por IA de libros y ensayos fundamentales relacionados con el **Altruismo Eficaz** y la **Racionalidad**. Mi objetivo es hacer que las ideas de alto impacto sean accesibles para una audiencia global mediante el uso de LLMs (Modelos de Lenguaje Extensos) modernos, preservando el formato y el contexto original.

Las traducciones realizadas están lejísimas de ser perfectas, pero son un buen punto de partida y considero de lejos mejor que estén disponibles en este estado que no lo estén. La perfección es la enemiga de lo bueno, y la disponibilidad de estas traducciones puede ayudar a que más personas se beneficien de estas ideas.

## 📋 Traducciones Disponibles

A continuación se muestra la lista de traducciones completadas. Cada archivo ha sido procesado para mantener notas al pie, enlaces internos y terminología técnica.

| Título del Libro | Idioma | Calidad | Modelo de IA | Notas |
| :--- | :--- | :--- | :--- | :--- |
| **Rationality: From AI to Zombies** | Español | Primer intento revisión básica pendiente | Gemini 2.5 (Cap 1-21)/ 2.5 Flash Lite (22-53)/ 3.1 Flash Lite (54-final) | Lotes de 8000 caracteres | |
| **Doing Good Better** | Español | Primer intento, revisión básica pendiente | Gemini 2.5 Flash Lite | Lotes de 30000 caracteres. Todo menos el final de Notas e Indice |

## 🛠️ Metodología de Traducción

**Traducciones existentes (antes de 2026-10):** hechas con Calibre + el plugin Ebook Translator, usando los modelos Gemini indicados en la tabla.

**Ahora:** el proyecto lo mantiene un pipeline automático en la nube que no necesita Calibre ni mi computadora. Descomprime el EPUB, divide cada capítulo en unidades del tamaño de un párrafo (los enlaces, notas al pie e imágenes se conservan como marcadores numerados), traduce los lotes con Claude (primero el modelo más chico con poco esfuerzo; uno más potente solo donde fallan los controles automáticos), controla cada lote (que no falte nada, que no quede nada en inglés, que los enlaces estén intactos y que se respete el glosario) y vuelve a escribir un EPUB válido. El progreso se guarda después de cada lote, así que el trabajo puede detenerse y retomarse en cualquier momento. Las traducciones existentes no se rehacen: se completan los faltantes y se vuelven a traducir los peores pasajes. Los informes de auditoría y calidad están en `reports/`.

Los libros nuevos se toman de a uno del [EA Archive](https://forum.effectivealtruism.org/posts/DndmvDGStD3gTfhXk/announcing-the-ea-archive) (su [carpeta pública de Google Drive](https://drive.google.com/drive/folders/1CSKOlo2nE9JtD1u8fUssMyTqOoJEeYMQ)) o de archivos puestos en `inbox/`. Las fuentes y notas de licencia están en `sources.md`.

## 🩹 Correcciones y Colaboraciones

Si quieres ayudar a corregir errores o añadir nuevas traducciones, abrí un "Issue" o "Pull Request".

## 🔮 Planes Posibles a futuro

- Añadir más traducciones a más idiomas de demás libros de EA y Racionalidad, principalmente los que están en el [EA Archive](https://forum.effectivealtruism.org/posts/DndmvDGStD3gTfhXk/announcing-the-ea-archive).
- Mejorar la calidad de las traducciones existentes, ya sea manualmente o mediante mejores IAs.
- Arreglar la pérdida de enlaces externos en las traducciones.
- Si hay interés, convertir a Markdown o HTML y añadir la forma de unzip and zip epubs para facilitar las correcciones.
- Glosario de traducciones.
