# Comparación LDA vs QDA - Wine Dataset

Proyecto de Métodos Numéricos / Machine Learning. Compara Análisis Discriminante Lineal (LDA) y Análisis Discriminante Cuadrático (QDA) sobre el Wine Dataset, sin tratamiento previo de los datos.

**Autora:** Odeth Espinoza Feijoo — Universidad de Guayaquil (CDDEIA-ELNO)

## Contenido del repositorio

- `LDA_QDA_Wine_Espinoza.ipynb` — cuaderno de Google Colab con el desarrollo completo: exploración de datos, visualización, preparación, implementación de LDA y QDA, comparación de métricas y fronteras de decisión.
- `Informe_LDA_QDA_Espinoza.pdf` — informe técnico con el marco teórico de LDA y QDA y el análisis de resultados.
- `wine_dataset.csv` — copia del Wine Dataset utilizado (también se puede obtener directamente desde scikit-learn, ver abajo).

## Cómo ejecutar el proyecto

1. Abrir `LDA_QDA_Wine_Espinoza.ipynb` en Google Colab (Archivo → Subir cuaderno, o subirlo a Google Drive y abrirlo con Colab).
2. Ejecutar todas las celdas en orden (Entorno de ejecución → Ejecutar todas).
3. El dataset se carga automáticamente desde scikit-learn con:
   ```python
   from sklearn.datasets import load_wine
   wine = load_wine()
   ```
   No es necesario subir ningún archivo adicional; `wine_dataset.csv` se incluye únicamente como respaldo.
4. Requisitos: `numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn` (todos preinstalados en Google Colab).

## Principales hallazgos

- El Wine Dataset (178 muestras, 13 variables químicas, 3 clases) no presenta valores faltantes y las clases están razonablemente balanceadas.
- Variables como `flavanoids`, `color_intensity` y `proline` muestran alto poder discriminante entre cultivares.
- **LDA** obtuvo accuracy = 0.981, precision (macro) = 0.982, recall (macro) = 0.984, F1-score (macro) = 0.983, con fronteras de decisión lineales.
- **QDA** obtuvo clasificación perfecta sobre el conjunto de prueba (accuracy = 1.000), con fronteras de decisión cuadráticas más flexibles.
- La diferencia de desempeño entre ambos modelos es pequeña en este dataset, ya que las clases están bien separadas; QDA logra una ligera ventaja al permitir covarianzas distintas por clase.
- LDA es preferible con muestras reducidas por su simplicidad y menor riesgo de sobreajuste; QDA es preferible cuando hay evidencia de covarianzas distintas entre clases y suficientes datos por clase para estimarlas de forma confiable.

## Referencias

- Hastie, T., Tibshirani, R., & Friedman, J. (2009). *The Elements of Statistical Learning* (2nd ed.). Springer.
- James, G., Witten, D., Hastie, T., & Tibshirani, R. (2021). *An Introduction to Statistical Learning with Applications in R* (2nd ed.). Springer.
- Scikit-learn developers. Linear and Quadratic Discriminant Analysis — documentación oficial.
