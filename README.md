# 🏦 Modelo de Scoring para Clientes con Potencial de Reinversión en Depósitos a Plazo

![Scoring](https://image.lexica.art/full_webp/753b96a1-05fd-4881-a935-52738ee72151)

Este proyecto tiene como objetivo desarrollar un modelo de **Machine Learning** que evalúe y clasifique a los clientes de un banco según su **probabilidad de volver a invertir en depósitos a plazo**. El modelo asigna un **score o ranking** a cada cliente para facilitar la toma de decisiones comerciales y optimizar las campañas de retención y reinversión.

---

## 📊 Objetivo del Proyecto

- Identificar patrones de comportamiento de clientes que históricamente han reinvertido en depósitos a plazo.
- Predecir la probabilidad de reinversión futura para cada cliente.
- Generar un **ranking ordenado** por score de potencial reinversión.
- Facilitar la focalización de campañas comerciales y personalización de ofertas.

---

## 🛠️ Tecnologías Utilizadas

- **Python** 3.10+
- **Pandas** para el análisis de datos
- **Scikit-learn** para modelos de clasificación
- **XGBoost / LightGBM** para boosting (según experimentación)
- **Matplotlib / Seaborn** para visualización
- **MLflow** (opcional) para trazabilidad de experimentos

---

## 🧩 Estructura del Proyecto
```
├── data/
│ ├── raw/ # Datos originales
│ └── processed/ # Datos preprocesados para el modelo
├── models/
│ └── model.pkl # Modelo entrenado serializado
├── notebooks/
│ ├── EDA.ipynb # Análisis exploratorio de datos
│ └── Training.ipynb # Entrenamiento del modelo
├── src/
│ └── features_engineering.py
│ └── train_model.py
├── scoring/
│ └── scoring_pipeline.py # Script de scoring por lotes
└── README.md
```

---

## 📈 Variables del Modelo

El modelo utiliza variables históricas y transaccionales como:

- Edad del cliente
- Tenencia histórica de depósitos a plazo
- Monto promedio invertido
- Número de productos contratados
- Antigüedad en el banco
- Actividad en los últimos 3-6 meses
- Score crediticio (si aplica)

---

## 🧠 Modelo de Machine Learning

Se entrenaron distintos modelos de clasificación:

- Regresión logística (baseline)
- Random Forest
- XGBoost

Se seleccionó el modelo con mejor **AUC-ROC**, **Precision@K** y capacidad de interpretación. El modelo devuelve una probabilidad (`score`) de reinversión, que luego se ordena en un ranking.

---

## 📊 Métricas de Evaluación

- Accuracy: 0.81
- ROC-AUC: 0.88
- Precision@Top10%: 0.71

---

## 🔄 Pipeline de Scoring

Se incluye un script para aplicar el modelo entrenado a nuevos datos de clientes:

```bash
python scoring/scoring_pipeline.py --input data/new_clients.csv --output results/scores.csv
```
## 🧪 Próximos Pasos
Incorporar feedback de campañas anteriores (modelo iterativo)

A/B testing con campañas personalizadas basadas en score

Integrar con plataformas de marketing del banco

## 📬 Contacto
- Desarrollado por: Ángel Troncoso
- Contacto: angeltroncoso2019@outlook.es
- LinkedIn [www.linkedin.com/in/angeltroncoso]  
- GitHub [https://github.com/AngelTroncoso]
- Portfolio [https://angeltroncoso.github.io/business_analytics_pro/]



