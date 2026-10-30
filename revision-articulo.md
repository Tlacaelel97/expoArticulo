# Revisión de la presentación contra Brüningk et al. (2019)

Fuente leída: PDF local en Zotero, `9DTPKSN9/Brüningk et al. - 2019 - A cellular automaton model for spheroid response to radiation and hyperthermia treatments.pdf` (12 páginas). DOI: https://doi.org/10.1038/s41598-019-54117-x.

## Alcance de esta versión

Se conservaron los temas principales propuestos y se completaron con contenido del artículo. Las diapositivas posteriores a referencias siguen en `slides.md`, ocultas con `hide: true`. Las definiciones generales de biología se mantienen mínimas; no se han consultado las fuentes citadas por el artículo como si se hubieran leído directamente.

Hay 20 diapositivas visibles. Las notas incluyen tiempos, explicación oral, referencias de página y matices que no conviene cargar en pantalla. El guion suma 18:30, con 1:30 de margen hasta el límite de 20 min. Los 5 min de preguntas van aparte. Es una estimación para ensayar, no una duración medida.

| Bloque | Diapositivas | Tiempo |
|---|---|---:|
| Apertura, pregunta e introducción | 1–10 | 7:00 |
| Modelo | 11–14 | 5:20 |
| Calibración y resultados | 15–18 | 4:40 |
| Conclusiones y referencias | 19–20 | 1:30 |
| Margen | | 1:30 |

## Contenido contrastado e incorporado

| Tema | Evidencia en el artículo | Incorporación |
|---|---|---|
| Pregunta principal | Resumen e introducción, pp. 1–2 | Supervivencia clonogénica parecida no determina una misma dinámica de crecimiento; límites de BEQD basada solo en supervivencia. |
| Esferoides | Introducción y métodos, pp. 1–2 | Agregados 3D avasculares; HCT116; 300 células sembradas; tratamiento día 4; seguimiento 3 semanas. |
| Hipoxia y proliferación | Figura 4, p. 7; discusión, p. 9 | Imagen original, marcadores y evolución temporal. Sin hipoxia significativa al tratar. |
| Autómata | Métodos, p. 2 | Una célula por vóxel de 12 μm, malla típica 200³, reloj y fases, vecindarios Moore/von Neumann, G0 reversible, sin migración explícita. |
| Oxigenación | Ecuación 1, pp. 2–3; resultados, pp. 6–7 | Difusión-consumo, exterior 100 mmHg, umbral 11 mmHg; equilibrio dentro de cada iteración; muerte y eliminación probabilísticas. |
| RT | Ecuaciones 2–3 y figura 1, pp. 3–4 | Lineal-cuadrático, ponderación por ciclo y OER; muerte al intentar división; células G0 dañadas pueden persistir. |
| HT | Ecuaciones 4–5, pp. 3–4 | AlphaR ajustado a 3D, muerte independiente de proliferación, eliminación y reoxigenación; meseta y retrasos en notas. |
| RTHT | Figura 2 y métodos, p. 5 | Producto de supervivencias, α y β dependientes de dosis térmica, asignación de vías de muerte. |
| Ajuste / validación | Métodos, pp. 5–6 | Ajuste con 10 Gy y 240 CEM43; validación con otras dosis; combinación sin nuevos ajustes. |
| Control sin tratar | Figuras 3–5, pp. 6–7 | R²=0.99 del ajuste; duplicación 28 h; diferencias de oxígeno de hasta 15 %. |
| RT y HT | Figura 6 y resultados, pp. 7–8 | RT: R² 0.95–0.98; HT: 0.94–0.98; desacuerdo temprano de diámetro tras HT. |
| Combinación | Figura 6, p. 8 | R²=0.86, 0.88 y 0.96 para 2 Gy + 160, 80 y 40 CEM43, respectivamente. |
| Límites y proyección | Discusión y conclusiones, pp. 9–10 | Una línea celular, limitaciones de malla/geometría, ausencia de vasculatura, inmunidad, pH/glucosa explícitos y necesidad de validación adicional. |

## Correcciones respecto al borrador

- Se corrigieron ortografía y términos: célula, autómatas, oxígeno, hipertermia, etc.
- El resumen dejó de ser un párrafo largo y se convirtió en la pregunta conductora.
- Se separó la definición de esferoide del problema de equivalencia biológica de dosis.
- No se atribuyó toda la muerte a apoptosis. La vía RT del modelo es muerte mitótica y la vía HT es una regla temporal independiente de proliferación; no se resuelven vías moleculares.
- Se distinguió hipoxia (bajo oxígeno) de necrosis y de quiescencia (reposo reversible).
- No se presentó OER como calibrado en estos experimentos: faltó hipoxia significativa al día de tratamiento.
- No se interpretó la buena concordancia de curvas como prueba de eficacia clínica ni de unicidad del mecanismo.
- No se afirmó que 10 Gy y 240 CEM43 sean una pareja cuantitativamente isoefectiva demostrada por la figura 6.
- Se reemplazaron imágenes genéricas y ejemplos de temas por figuras del estudio.

## Contexto que todavía requiere investigación externa

1. **Biología celular y ciclo:** fuente introductoria para acompañar las fases y una futura ilustración de la célula.
2. **Apoptosis:** definición, contraste con otras formas de muerte y una imagen/animación específica. El artículo no es un estudio molecular de apoptosis.
3. **Cáncer:** definición general y bases biológicas si se desea ampliar la introducción actual; evitar epidemiología que no contribuya a la pregunta.
4. **RT/HT como tratamientos:** ampliar fundamentos físicos o contexto clínico solo si hace falta para la audiencia. Los parámetros experimentales de este estudio no son recomendaciones clínicas.

Conviene dedicar cualquier ampliación a reemplazar parte de la introducción, pues los 7 minutos ya están asignados. No se añaden revisiones de literatura extensas ni una lista completa de las 51 referencias del artículo para una charla de 20 minutos.

## Material que queda en notas o fuera de pantalla

- Ecuaciones completas de AlphaR por tramos, modelo analítico radial de Grimes, todos los parámetros probabilísticos y detalles instrumentales.
- El diagrama del ciclo es didáctico: la entrada a G0 en el algoritmo ocurre al no encontrar espacio al intentar la división, no por una regla de transición desde G1.
- No se reprodujeron las figuras 1–3: las reglas se resumieron en tabla/diagramas y el resultado de oxigenación se informó con su comparación y límite.
- El texto anuncia un futuro repositorio de código; no se comprobó si llegó a publicarse. Los datos se ofrecen bajo solicitud al autor en el documento original.

## Figuras y atribución

Los PNG en `public/figures/` son recortes del PDF original:

- `bruningk-2019-fig4.png`: histología, p. 7.
- `bruningk-2019-fig5.png`: control sin tratar, p. 7.
- `bruningk-2019-fig6-rt-ht.png`: filas RT/HT, p. 8; el eje temporal compartido se aclara en el pie de la slide.
- `bruningk-2019-fig6-rtht.png`: fila de combinación con eje temporal, p. 8.

Crédito: Brüningk et al. (2019), Scientific Reports 9, 17674. https://doi.org/10.1038/s41598-019-54117-x. Licencia CC BY 4.0, https://creativecommons.org/licenses/by/4.0/. Modificación: recorte y rasterización; sin alterar datos. La licencia consta en p. 12 del PDF. Se conservaron leyendas, escalas y etiquetas de los paneles usados.

## Verificación técnica

- `npm run build`: compilación de producción correcta.
- Comprobación en Chromium a 1280 × 720: se recorrieron las 20 diapositivas, las cuatro figuras cargaron y no se detectaron errores de sintaxis de Mermaid ni desbordamiento vertical del contenedor.
- Inspección de capturas de portada, ciclo, histología, ecuaciones, combinación, resultados, conclusiones y referencias. Se ajustaron estilos globales, presentación de R² y extensión del recorte de la figura 6 para conservar las etiquetas.
- Las notas de 20 diapositivas suman 18:30. Hace falta ensayo oral para confirmar el ritmo real.
