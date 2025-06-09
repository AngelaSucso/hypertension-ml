# Predicción de Hipertensión Arterial con Machine Learning
Se aplicaron modelos de clasificación ya implementados en librerías de aprendizaje automático para predecir la presencia de hipertensión arterial a partir de datos clínicos fácilmente obtenibles. Se replica parcialmente la metodología de dos artículos científicos que utilizan Random Forest y XGBoost para este propósito.

## 📚 Dataset
Se usó el Stroke Prediction Dataset, que incluye variables como:
- Edad
- Género
- Nivel promedio de glucosa
- IMC
- Enfermedades cardíacas
- Estado civil, etc
- Resultado: hipertensión (sí/no)

Este dataset fue elegido por su similitud con los datos utilizados en los artículos originales.

## 🧠 Modelos aplicados
- ✅ Random Forest (con balanceo usando SMOTE)
- ✅ XGBoost (con ajuste básico de parámetros)

Ambos modelos fueron implementados usando librerías estándar como `scikit-learn`, `xgboost`, `imbalanced-learn` y `pandas`, ejecutados en Google Colab.

## 📊 Evaluación
Se utilizaron las siguientes métricas para evaluar los modelos:
- Accuracy
- Precision
- Recall
- F1-score
- Matriz de confusión
- Gráfico de importancia de variables

## 📰 Artículos de referencia
- 📄 Random Forest:  
  Zhao et al. (2021). Predicting the Risk of Hypertension Based on Several Easy-to-Collect Risk Factors.  
  [DOI: 10.3389/fpubh.2021.619429](https://www.frontiersin.org/articles/10.3389/fpubh.2021.619429)

- 📄 XGBoost:  
  Dubey et al. (2024). Explainable and Interpretable Model for the Early Detection of Brain Stroke Using Optimized Boosting Algorithms.  
  [DOI: 10.3390/diagnostics14222514](https://www.mdpi.com/2075-4418/14/22/2514)


## ⚙️ Algoritmo 1: Random Forest
- Modelo: RandomForestClassifier (100 árboles)
- Dataset: Healthcare Stroke Prediction Dataset (Kaggle)
- Balanceo: SMOTE (oversampling de la clase minoritaria)
- Interpretabilidad: importancia de variables según el modelo Random Forest

### 📊 Resultados obtenidos
- Accuracy: 89.2 %
- Precision: 88 % (clase 1)
- Recall: 91 % (clase 1)
- F1-score: 89 %

## ⚙️ Algoritmo 2: XGBoost
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


---

📌 Nota final:
Se busca replicar parte del enfoque de los artículos académicos recientes usando datos tabulares accesibles y modelos clásicos como Random Forest y XGBoost. Aunque los datos no son exactamente los mismos que en los papers, se mantiene la idea principal: evaluar técnicas efectivas y fáciles de implementar para problemas de predicción médica. Los algoritmos basados en árboles siguen siendo una muy buena opción en este tipo de tareas, sobre todo cuando se necesita interpretabilidad, buen rendimiento y facilidad de uso.

