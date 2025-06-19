# Predicción de Hipertensión Arterial con Modelos Avanzados
Se aplicaron modelos de clasificación para predecir la presencia de hipertensión arterial a partir de datos clínicos fácilmente obtenibles. La metodología replica parcialmente dos enfoques recientes: uno basado en boosting de árboles (XGBoost) y otro en aprendizaje profundo para datos tabulares (TabNet).

## 📚 Dataset
Se usó el Stroke Prediction Dataset, que incluye variables como:
- Edad
- Género
- Nivel promedio de glucosa
- IMC
- Enfermedades cardíacas
- Tipo de trabajo, residencia y tabaquismo  
- Resultado: hipertensión (sí/no)

Este dataset fue elegido por su similitud con los datos utilizados en los artículos originales.

## 🧠 Modelos aplicados
- ✅ TabNet (modelo de deep learning para datos tabulares)
- ✅ XGBoost (con ajuste básico de parámetros)

Ambos modelos fueron implementados en Google Colab usando librerías como `xgboost`, `pytorch-tabnet`, `imbalanced-learn`, `scikit-learn` y `pandas`.

## 📊 Evaluación
Se utilizaron las siguientes métricas para evaluar los modelos:
- Accuracy
- Precision
- Recall
- F1-score
- Matriz de confusión
- Gráfico de importancia de variables

---

## 📰 Artículos de referencia
- 📄 XGBoost:  
  Dubey et al. (2024). Explainable and Interpretable Model for the Early Detection of Brain Stroke Using Optimized Boosting Algorithms.  
  [DOI: 10.3390/diagnostics14222514](https://www.mdpi.com/2075-4418/14/22/2514)
- 📄 TabNet:  
  Arik & Pfister (2021). *When Do Neural Nets Outperform Boosted Trees on Tabular Data?*   
  [https://doi.org/10.48550/arXiv.2305.02997](https://arxiv.org/pdf/2305.02997)

---

## ⚙️ Algoritmo 1: XGBoost
- Modelo: XGBClassifier (100 árboles, eval_metric="logloss")
- Dataset: Healthcare Stroke Prediction Dataset (Kaggle)
- Balanceo: muestreo híbrido
  - Undersampling de la clase mayoritaria
  - Oversampling con SMOTE de la clase minoritaria
- Interpretabilidad: gráfico SHAP para explicar la importancia de cada variable

### 📊 Resultados obtenidos
- Accuracy: 83.5 %
- Precision: 82 % (clase 1)
- Recall: 85 % (clase 1)
- F1-score: 83 %

## ⚙️ Modelo 2: TabNet

- Modelo: `TabNetClassifier` (entrenado por hasta 200 épocas con early stopping)
- Dataset: Healthcare Stroke Prediction Dataset (Kaggle)
- Balanceo de clases: SMOTE
- Normalización: `StandardScaler`
- Interpretabilidad: gráfico de **importancia de variables** basado en `feature_importances_` del modelo

### 📊 Resultados obtenidos
- Accuracy: 85.8 %
- Precision: 85 % (clase 1)
- Recall: 88 % (clase 1)
- F1-score: 86 %

---

📌 Nota final:
Este trabajo busca replicar enfoques actuales para la predicción médica usando datos tabulares accesibles. Mientras que XGBoost representa un enfoque clásico basado en árboles potenciados, TabNet se posiciona como una alternativa moderna basada en redes neuronales profundas. Ambos ofrecen buen rendimiento, pero TabNet demuestra ser competitivo incluso frente a algoritmos tradicionalmente dominantes en este tipo de datos.
