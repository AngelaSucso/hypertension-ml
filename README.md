# Predicción de Hipertensión Arterial con Modelos Avanzados
Se aplicaron modelos de clasificación para predecir la presencia de hipertensión arterial a partir de datos clínicos fácilmente obtenibles. La metodología replica parcialmente dos enfoques recientes: uno basado en boosting de árboles (XGBoost) y otro en aprendizaje profundo para datos tabulares (TabNet).

## 📚 Datasets
### 💉 [Blood Pressure Dataset](https://www.kaggle.com/datasets/pavanbodanki/blood-press/data)  
Se usó el **Blood Pressure Dataset** correspondiente a XGBoost, que contiene variables relacionadas con:
- Blood_Pressure_Abnormality  
- Level_of_Hemoglobin  
- Genetic_Pedigree_Coefficient  
- Age  
- BMI  
- Sex
- Pregnancy  
- Smoking  
- Physical_activity 
- **Resultado:** presión arterial (alta o normal)  
🔗 [Disponible en Kaggle](https://www.kaggle.com/datasets/pavanbodanki/blood-press/data)

### 🧠 [Hypertension Risk Model Dataset](https://www.kaggle.com/datasets/khan1803115/hypertension-risk-model-main)  
Se usó el **Hypertension Risk Model Dataset** correspondiente a TabNet, que considera factores de riesgo como:
- Edad  
- Género  
- Peso y altura  
- IMC  
- Consumo de sal  
- Nivel de estrés  
- Actividad física y herencia genética  
- **Resultado:** riesgo de hipertensión (sí/no)  
🔗 [Disponible en Kaggle](https://www.kaggle.com/datasets/khan1803115/hypertension-risk-model-main)

---

## 🧠 Modelos aplicados
- ✅ XGBoost (con ajuste básico de parámetros)
- ✅ TabNet (modelo de deep learning para datos tabulares)

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

## Evaluación comparativa intercambiando datasets para los modelos

### ⚙️ Algoritmo 1: XGBoost
- Modelo: XGBClassifier (100 árboles, eval_metric="error")
- Dataset: Hypertension Risk Model Main (Kaggle)
- Interpretabilidad: gráfico SHAP para explicar la importancia de cada variable

#### 📊 Resultados obtenidos
- Accuracy: **88.3 %**
- Precision: **81 %** (clase 1)
- Recall: **82 %** (clase 1)
- F1-score: **81 %** (clase 1)

### ⚙️ Modelo 2: TabNet

- Modelo: `TabNetClassifier` (entrenado por hasta 200 épocas con early stopping)
- Dataset: Blood Pressure Dataset (Kaggle)
- Interpretabilidad: gráfico de **importancia de variables** basado en `feature_importances_` del modelo

#### 📊 Resultados obtenidos
- Accuracy: **87.5 %**
- Precision: **88 %** (clase 1)
- Recall: **86 %** (clase 1)
- F1-score: **87 %** (clase 1)

---

📌 Nota final:
Este trabajo busca replicar enfoques actuales para la predicción médica usando datos tabulares accesibles. Mientras que XGBoost representa un enfoque clásico basado en árboles potenciados, TabNet se posiciona como una alternativa moderna basada en redes neuronales profundas. Ambos ofrecen buen rendimiento, pero TabNet demuestra ser competitivo incluso frente a algoritmos tradicionalmente dominantes en este tipo de datos.
