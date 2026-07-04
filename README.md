# Minería de Datos Aplicada al Análisis de Reputación Digital

<div align="center">

![Python](https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.4-F7931E?style=for-the-badge&logo=scikit-learn)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-FF6F00?style=for-the-badge&logo=tensorflow)
![Status](https://img.shields.io/badge/Status-Completado-brightgreen?style=for-the-badge)

<br>

<img src="https://readme-typing-svg.herokuapp.com?font=Lexend+Giga&size=24&pause=1000&color=4A90E2&center=true&vCenter=true&width=700&lines=Análisis+de+Sentimiento+en+Aerolíneas;NLP+%7C+Machine+Learning+%7C+TF-IDF;Clasificación+de+Tweets+en+Tiempo+Real" />

</div>

---

## Resumen del Proyecto

Este proyecto desarrolla un sistema de clasificación de sentimiento para tweets de aerolíneas, aplicando técnicas de **Procesamiento de Lenguaje Natural (NLP)** y **Machine Learning** para detectar automáticamente quejas de clientes en tiempo real. El objetivo es permitir que el equipo de Customer Service priorice tweets negativos, reduciendo el impacto en la reputación de la aerolínea y mejorando la retención de pasajeros.

**Metodología:** CRISP-DM  
**Dataset:** Twitter US Airline Sentiment (+14,000 tweets)  
**Clasificación:** 3 clases (negative, neutral, positive)

---

## Objetivos del Negocio

| Criterio | Objetivo |
|----------|----------|
| **Principal** | Clasificar tweets en Positivo, Negativo o Neutral en tiempo real |
| **Prioridad** | Detectar tweets negativos (Recall ≥ 80%) |
| **Impacto** | Reducir crisis de reputación y mejorar retención de clientes |

### Análisis de Costos

| Concepto | Estimación (USD) |
|----------|:---:|
| **Soporte por interacción** | $5 - $10 |
| **Customer Acquisition Cost (CAC)** | $100 - $150 |
| **Customer Lifetime Value (CLV)** | $500 - $2,000+ |

| Escenario | Impacto | Estimación |
|-----------|---------|:---:|
| **TP** (Negativo detectado) | Retención de cliente | **+$150** |
| **FP** (Falsa alarma) | Atención innecesaria | **-$10** |
| **FN** (Queja no detectada) | Pérdida de cliente | **-$150** |

**Conclusión:** El costo de un Falso Negativo es **15 veces mayor** que el de un Falso Positivo.

---

## Estructura del Proyecto (CRISP-DM)

| Fase | Descripción |
|------|-------------|
| **Fase 1 — Business Understanding** | Definición de objetivos, análisis de costos, criterios de éxito |
| **Fase 2 — Data Understanding** | Carga, EDA, entropía, bigramas, análisis de nulos |
| **Fase 3 — Data Preparation** | Limpieza (RegEx), TF-IDF, partición estratificada |
| **Fase 4 — Modeling** | Entrenamiento de 13 modelos con GridSearch y class_weight |
| **Fase 5 — Evaluation** | Matrices de confusión, curvas ROC, ranking, interpretabilidad |
| **Fase 6 — Deployment** | Exportación del mejor modelo (`.joblib`) y conclusiones |

---

## Modelos Evaluados

| Categoría | Modelos |
|-----------|---------|
| **Lineales** | Logistic Regression, SVM |
| **Árboles** | Decision Tree, Random Forest, XGBoost |
| **Probabilísticos** | Naive Bayes (Sin/Con GS) |
| **Redes Neuronales** | MLP (Sin/Con GS), Keras (MLP) |
| **Ensamble** | Voting, Stacking, Blending |

---

## Resultados

### Mejor Modelo: Keras (MLP)

| Métrica | Valor |
|---------|:---:|
| **F1-Weighted** | 0.7678 |
| **Recall (Negativos)** | 0.8755 |
| **AUC-ROC** | 0.8856 |
| **Precisión (Negativos)** | 0.851 |

### Modelo por Métrica

| Métrica | Ganador |
|---------|---------|
| **AUC-ROC** | Keras (MLP) — 0.8856 |
| **F1-Weighted** | Keras (MLP) — 0.7678 |
| **Recall (Negativos)** | Naive Bayes (Sin GS) — 0.9749 |
| **Accuracy** | MLP (Sin GS) — 0.7747 |

### Método de Youden — Optimización de Umbral

| Modelo | Umbral Youden | Recall con 0.5 | Recall Youden |
|--------|:---:|:---:|:---:|
| **Keras (MLP)** | **0.5227** | 0.8821 | **0.8755** |
| MLP (Con GS) | 0.5788 | 0.8892 | 0.8575 |
| MLP (Sin GS) | 0.6170 | 0.9007 | 0.8537 |
| Voting | 0.5737 | 0.8461 | 0.8057 |
| SVM | 0.6531 | 0.8936 | 0.8051 |

---

##Tecnologías Utilizadas

| Categoría | Herramientas |
|-----------|--------------|
| **Lenguaje** | Python 3.12 |
| **Entorno** | Jupyter Notebook / Google Colab |
| **Manipulación de datos** | Pandas, NumPy |
| **NLP** | scikit-learn (TF-IDF, CountVectorizer) |
| **ML Clásico** | scikit-learn (LR, SVM, Árboles, RF, NB) |
| **Boosting** | XGBoost |
| **Redes Neuronales** | TensorFlow / Keras |
