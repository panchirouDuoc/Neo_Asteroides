# Neo_Asteroides
# Análisis de Peligrosidad de Asteroides NEOs

Este proyecto aplica técnicas de Ciencia de Datos para clasificar la peligrosidad de objetos cercanos a la Tierra (NEOs) utilizando el dataset Neo.

## Objetivo
Desarrollar un flujo completo que incluya limpieza de datos, análisis exploratorio (EDA), modelado supervisado para clasificación de riesgo, y aprendizaje no supervisado para la segmentación de perfiles de asteroides.

## Estructura del Proyecto
El repositorio se organiza de la siguiente manera:
- `data/raw/`: Dataset original `neo.csv`.
- `data/processed/`: Datos transformados y etiquetados con clusters `supervised_data_con_clusters.csv`.
- `notebooks/`: Notebook principal con el flujo de análisis `Taller2.ipynb`.

## Metodología

### 1. Análisis Exploratorio y Preprocesamiento
- Limpieza de columnas irrelevantes (`orbiting_body`, `sentry_object`, etc.).
- Creación de `est_diameter_mean` para simplificar el modelo sin perder información.
- Estandarización de datos mediante `StandardScaler`.

### 2. Modelado Supervisado
Se implementaron y compararon 5 modelos de clasificación:
- Regresión Logística
- Árbol de Decisión (Seleccionado por mejor balance Precision/Recall)
- K-Nearest Neighbors (KNN)
- Support Vector Machine (SVM)
- Gaussian Naive Bayes

**Hiperparametros:** Se utilizó `GridSearchCV` y `RandomizedSearchCV` junto con **Validación Cruzada (K-Fold)** para asegurar la robustez de los modelos.

### 3. Modelado No Supervisado
- **PCA:** Reducción de dimensionalidad para visualización y eficiencia.
- **K-Means Clustering:** Segmentación en 3 perfiles distintos de asteroides, identificando que el Cluster 1 presenta el mayor riesgo relativo.

## Resultados Clave
- Los modelos de **Árbol de Decisión** y **SVM** alcanzaron una precisión superior al **91%**.
- El tamaño del asteroide (Magnitud Absoluta y Diámetro) resultó ser el predictor más crítico para determinar la peligrosidad.

## Requisitos
- Python 3.x
- Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn

---
*asignatura: Programación para la Ciencia de Datos (SCY1101)*
