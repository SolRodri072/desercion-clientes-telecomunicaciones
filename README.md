# ¿Quién se va y por qué?

## Análisis de la deserción de clientes en telecomunicaciones

Proyecto de Ciencia de Datos orientado al análisis de la deserción de clientes (churn) en empresas de telecomunicaciones, utilizando técnicas de limpieza de datos, análisis exploratorio, análisis estadístico y modelado predictivo.

---

## 1. Integrantes

- Juan Sebastian Alvarez Ortegon
- Maria Natalia Medina Rojas
- Sol Daniela Rodriguez Castellanos
- Valery Mariana Sanchez Albarracin

---

## 2. Descripción del proyecto

La retención de clientes es uno de los principales retos de las empresas de telecomunicaciones debido a la alta competencia y a la facilidad con la que los usuarios pueden cambiar de proveedor.

En este proyecto se analiza la relación entre diferentes características de los clientes y su abandono del servicio. Para esto se realiza un proceso de limpieza, procesamiento y análisis exploratorio de datos utilizando Python, seguido de un análisis estadístico y la construcción de modelos predictivos.

El propósito es identificar patrones y factores asociados con el abandono de clientes que puedan servir como apoyo para desarrollar estrategias de retención.

---

## 3. Pregunta de investigación

> ¿Qué relación existe entre el tipo de contrato, el servicio de internet, el método de pago y la antigüedad de los clientes con su abandono (churn)?

---

## 4. Objetivo

Analizar la relación entre las características de los clientes y su abandono del servicio mediante técnicas de limpieza, procesamiento, análisis exploratorio y modelado predictivo en Python.

---

## 5. Datos utilizados

Para el desarrollo del proyecto se utilizó el **Telco Customer Churn Dataset**, obtenido de Kaggle.

La base de datos cuenta con:

- 7.043 clientes.
- 21 variables.
- Información demográfica.
- Información sobre los servicios contratados.
- Información de facturación.
- La variable objetivo `Churn`.

Entre las variables analizadas se encuentran:

- Género.
- Adulto mayor.
- Pareja.
- Dependientes.
- Antigüedad (`tenure`).
- Servicio de telefonía.
- Servicio de internet.
- Servicios adicionales.
- Tipo de contrato.
- Método de pago.
- Cargo mensual.
- Cargo total.
- `Churn`.

---

## 6. Limpieza y preparación de los datos

Antes de realizar el análisis se llevó a cabo un proceso de limpieza y transformación de los datos.

Las principales actividades fueron:

1. Normalización de los nombres de las columnas.
2. Verificación de registros duplicados mediante `customerID`.
3. Limpieza de espacios sobrantes en las variables de texto.
4. Conversión de `TotalCharges` de texto a formato numérico mediante `pd.to_numeric`.
5. Tratamiento de los valores faltantes.
6. Imputación mediante la mediana en las variables correspondientes.
7. Cálculo de algunos valores faltantes de `TotalCharges` mediante la operación `tenure × MonthlyCharges`.
8. Identificación de valores sin información confiable mediante la categoría `"No registrado"`.

Este proceso permitió organizar y preparar la información para las siguientes etapas del análisis.

---

## 7. Análisis exploratorio de datos

Se realizó un análisis exploratorio para identificar patrones relacionados con la deserción de clientes.

La tasa global de abandono encontrada en la base fue aproximadamente del **26,5 %**.

Se analizaron principalmente las relaciones entre `Churn` y las siguientes variables:

- Tipo de contrato.
- Servicio de internet.
- Método de pago.
- Antigüedad del cliente.
- Cargo mensual.
- Cargo total.

### Principales hallazgos

- Los contratos de mayor duración presentan menores niveles de abandono.
- Los clientes con contratos de menor duración presentan un mayor riesgo de churn.
- La fibra óptica presentó una tasa de abandono superior a DSL en el análisis realizado.
- Los métodos de pago automáticos mostraron mejores niveles de retención.
- Los primeros 12 meses representan un periodo crítico para la retención.
- Los clientes que abandonan presentan, en promedio, menor antigüedad y un cargo mensual más alto.

---

## 8. Análisis estadístico

Se realizaron pruebas estadísticas con el objetivo de determinar si los patrones observados en el análisis exploratorio presentaban asociaciones estadísticamente significativas.

Para las variables categóricas se utilizaron pruebas de **Chi-cuadrado**.

También se utilizó la prueba **Mann-Whitney U** para realizar comparaciones entre los grupos de clientes que abandonaron y los que permanecieron.

Los resultados permitieron identificar asociaciones estadísticamente significativas entre algunas de las variables analizadas y la variable `Churn`.

---

## 9. Modelado predictivo

El problema se planteó como una clasificación binaria:

- `Churn = Yes` → 1
- `Churn = No` → 0

Se utilizaron dos modelos de clasificación:

### Regresión Logística

Se utilizó como modelo interpretable para analizar la relación de las variables con la probabilidad de abandono.

### Random Forest

Se utilizó como modelo predictivo basado en múltiples árboles de decisión y para analizar la importancia de las variables.

### Preparación de los datos

Los datos fueron divididos de la siguiente manera:

- 80 % para entrenamiento.
- 20 % para prueba.
- División estratificada.
- Codificación de variables categóricas mediante One-Hot Encoding.

---

## 10. Evaluación de los modelos

Los modelos fueron evaluados mediante diferentes métricas:

- Accuracy.
- Precision.
- Recall.
- F1-score.
- ROC-AUC.

Los resultados mostraron un desempeño cercano al **79 % de accuracy** para ambos modelos.

El **Random Forest** presentó un desempeño general destacado frente a la Regresión Logística en las métricas analizadas.

También se utilizó una matriz de confusión para evaluar el comportamiento del Random Forest sobre el conjunto de prueba.

---

## 11. Principales resultados

A partir del análisis realizado se identificaron los siguientes resultados:

1. El tipo de contrato presenta una relación importante con la deserción de clientes.
2. Una mayor antigüedad del cliente se relaciona con una menor probabilidad de abandono.
3. La fibra óptica presentó una mayor asociación con el churn frente a DSL en el análisis realizado.
4. Los primeros 12 meses representan un periodo importante para implementar estrategias de retención.
5. Los métodos de pago automáticos presentan mejores niveles de retención.
6. El Random Forest presentó un desempeño general destacado frente a la Regresión Logística.
7. Las variables relacionadas con el cargo total, la antigüedad y el cargo mensual tuvieron una importancia relevante dentro del modelo Random Forest.

---

## 12. Conclusiones

A partir del análisis exploratorio, estadístico y predictivo se concluye que:

- El **tipo de contrato** es uno de los factores más relevantes relacionados con el abandono.
- Una mayor **antigüedad** se relaciona con una menor probabilidad de abandono.
- La combinación de **fibra óptica y cheque electrónico** aparece asociada con un mayor riesgo de churn.
- Los primeros meses de permanencia representan un periodo importante para implementar estrategias de retención.
- Los modelos predictivos permiten identificar patrones asociados con la deserción de clientes.
- El **Random Forest** presentó un desempeño general destacado en comparación con la Regresión Logística.

---

## 13. Recomendaciones

A partir de los resultados obtenidos se plantean las siguientes recomendaciones:

1. Priorizar estrategias de retención para clientes con entre 0 y 12 meses de antigüedad.
2. Investigar las causas del churn asociado al servicio de fibra óptica, considerando factores como precio, soporte y competencia.
3. Incentivar la migración desde métodos de pago manuales hacia métodos de pago automáticos.
4. Promover la migración desde contratos mensuales hacia contratos de mayor duración.
5. Utilizar los resultados del análisis para orientar estrategias de retención de clientes.

---

## 14. Estructura del repositorio

```text
desercion-clientes-telecomunicaciones/
│
├── README.md
│
├── InformeFinalDesercionDeClientes.pdf
│
├── DesercionDeClientes.pdf
│
├── DesercionDeClientes_Informe.ipynb
│
├── telco_data (1).csv
│
└── telco_data_limpio (1).csv

---

## 15. Instrucciones para ejecutar el código

### Requisitos

Para ejecutar el proyecto se recomienda utilizar:

- Google Colab.
- Python 3.
- Jupyter Notebook.

Las principales librerías utilizadas son:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
scipy
```

### Ejecución

#### Paso 1. Abrir el notebook

Abrir el archivo `DesercionDeClientes_Informe.ipynb` que se encuentra en este repositorio.

#### Paso 2. Abrir el notebook en Google Colab

Cargar el archivo `.ipynb` en Google Colab para ejecutar el proyecto.

#### Paso 3. Cargar los archivos de datos

Cargar en Google Colab los archivos CSV incluidos en este repositorio:

- `telco_data (1).csv`
- `telco_data_limpio (1).csv`

#### Paso 4. Ejecutar las celdas

Ejecutar las celdas del notebook en orden, desde el inicio hasta el final.

El notebook contiene las siguientes etapas:

1. Carga de los datos.
2. Exploración inicial.
3. Limpieza de los datos.
4. Transformación y preparación de los datos.
5. Análisis exploratorio.
6. Análisis estadístico.
7. Preparación de los datos para el modelado.
8. Entrenamiento de los modelos.
9. Evaluación de los modelos.
10. Análisis de resultados y conclusiones.

### Librerías utilizadas

Las principales librerías utilizadas en el proyecto son:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

from scipy.stats import chi2_contingency, mannwhitneyu

from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import (
    accuracy_score,
    precision_score,
    recall_score,
    f1_score,
    roc_auc_score,
    confusion_matrix
)
```
---

Este proyecto demuestra cómo el uso de herramientas de Ciencia de Datos permite transformar datos en información útil para comprender el comportamiento de los clientes, identificar factores relacionados con la deserción y apoyar la toma de decisiones orientadas a la retención.

**Gracias por visitar nuestro proyecto.**
