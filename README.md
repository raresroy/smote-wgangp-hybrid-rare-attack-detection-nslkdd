# Técnicas híbridas de SMOTE y GANs para mejorar la precisión en la detección de ataques raros

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Year](https://img.shields.io/badge/Year-2026-lightgrey)

**Autor:** Emerson Aldair Espinoza Soncco · emersonaldairespinoza@gmail.com
**Año:** 2026
**Dataset:** NSL-KDD

---

## Resumen

El desequilibrio extremo de clases en los sistemas de detección de intrusiones
degrada severamente la capacidad de los algoritmos para identificar amenazas
críticas e infrecuentes. Este estudio propone una hibridación metodológica que
integra SMOTE y WGAN-GP mediante un ratio estructural del 60%, evaluada sobre
NSL-KDD con Random Forest bajo validación cruzada estratificada de 10 pliegues,
frente a un Imbalance Ratio de 1295.06.

**Palabras clave:** hibridación SMOTE-WGAN, detección de ataques raros,
sistemas de detección de intrusiones, desequilibrio de clases, sensibilidad algorítmica.

## Ideas destacadas

1. La hibridación SMOTE-GAN incrementa la sensibilidad (TPR) en la clase minoritaria de 0.5633 a 0.7500.
2. El modelo propuesto maximiza la robustez equilibrada, elevando el MCC a 0.7819.
3. El ensamblaje estructural asegura estabilidad operativa, reduciendo la desviación estándar a ±0.0856.

## Resultados principales (clase U2R)

| Métrica | Modelo base | SMOTE + WGAN-GP (60%) |
|---|---|---|
| TPR (Sensibilidad) | 0.5633 | **0.7500** |
| F1-Score | 0.6516 | **0.7765** |
| MCC | 0.6799 | **0.7819** |
| PR-AUC | 0.7952 | **0.8404** |
| Desv. estándar F1 | ±0.1647 | **±0.0856** |

**Prueba de McNemar:** p = 9.77×10⁻⁴ (U2R) y p = 1.70×10⁻⁴ (R2L). Se rechaza la hipótesis nula.

## Metodología

1. **Dataset:** NSL-KDD (KDDTrain+ / KDDTest+), Imbalance Ratio = 1295.06.
2. **Preprocesamiento:** codificación de variables categóricas, normalización, agrupación en clases (Normal, DoS, Probe, R2L, U2R).
3. **Sobremuestreo híbrido:** SMOTE + WGAN-GP con ratio estructural del 60%.
4. **Clasificador:** Random Forest.
5. **Validación:** validación cruzada estratificada de 10 pliegues.
6. **Métricas:** TPR, F1-Score, MCC, PR-AUC, desviación estándar entre pliegues.
7. **Significancia estadística:** prueba de McNemar.

## Estructura del repositorio

```
├── paper/
│   └── paper_smote_wgangp_2026.pdf
├── data/
│   ├── KDDTrain+.txt
│   ├── KDDTest+.txt
│   └── README_data.md        # fuente y descripción del dataset
├── notebooks/
│   └── resultados.ipynb      # experimentos y resultados reproducibles
├── sistematizacion/
│   └── fuentes_y_revision    # matriz de sistematización de la literatura
└── README.md
```

## Dataset

NSL-KDD, versión depurada de KDD'99 (Tavallaee et al., 2009).
Fuente: https://www.unb.ca/cic/datasets/nsl.html


## Licencia

Código bajo licencia MIT. El dataset NSL-KDD pertenece a sus autores originales.

## Contacto

Emerson Aldair Espinoza Soncco · emersonaldairespinoza@gmail.com · https://www.linkedin.com/in/emerson-espinoza/