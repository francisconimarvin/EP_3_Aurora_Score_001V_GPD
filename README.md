# AURORA SCORE · Vertex Financial Group

Proyecto de **Gestión de Proyectos de Datos (SCY1102)**, Duoc UC: un score crediticio alternativo para personas sin historial bancario en Chile, Perú, Colombia y México.

**Integrantes:** Marvin Francisconi · Ricardo Illanes
**Docente:** José Luis Barría · **Sección:** AV-V103

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| [`EP_3_Aurora_Score_GPD_001V.ipynb`](EP_3_Aurora_Score_GPD_001V.ipynb) | Prototipo funcional en Python: calidad de datos, preparación, comparación de 5 modelos, motor de decisión, auditoría de equidad, latencia y monitoreo de drift |
| [`Informes/Informe_AURORA_SCORE.docx`](Informes/Informe_AURORA_SCORE.docx) | Informe de la Evaluación Parcial 3: implementación técnica, monitoreo y control |
| [`Informes/AURORA_SCORE_EP3.pptx`](Informes/AURORA_SCORE_EP3.pptx) | Presentación de la Evaluación Parcial 3 |
| [`Informes/Informe_Aurora_Score_2.pdf`](Informes/Informe_Aurora_Score_2.pdf) | Informe de la Evaluación Parcial 2: requerimientos, alcance, CRISP-DM y planificación |

Seguimiento del proyecto en Trello: https://trello.com/b/k42zz9Vq

## Resultados del prototipo

| Indicador | Resultado | Criterio |
|---|---|---|
| AUC en prueba (regresión logística) | 0,846 | 0,75 o más |
| Tasa de aprobación | 92,6 % | — |
| Mora de la cartera aprobada | 7,7 % (sin modelo: 11,6 %) | 9 % o menos |
| Latencia p95 del motor de decisión | 12,9 ms | menos de 8 s (RNF01) |
| Equidad (regla 4/5) | 4 de 4 grupos cumplen | razón de 0,80 o más |
| Avance del plan al cierre de M5 | 77,1 % real vs. 65,0 % planificado (SPI 1,19) | — |

La regresión logística superó a bagging, pasting, Random Forest y gradient boosting, y se eligió también por ser explicable ante el regulador (RF05).

## Cómo ejecutar el notebook

```bash
pip install pandas numpy scikit-learn matplotlib joblib jupyter
jupyter notebook EP_3_Aurora_Score_GPD_001V.ipynb
```

El notebook usa una semilla fija, así que los resultados son los mismos en cada ejecución. Al correrlo crea las carpetas `data/` y `outputs/` con el dataset, el modelo entrenado, la model card y los gráficos.

> **Nota:** el caso de estudio es ficticio y no incluye microdatos, por lo que se generó un dataset sintético de 12.000 solicitudes que replica la estructura del piloto de Chile y Perú. Las métricas deben recalcularse con la cartera real.
