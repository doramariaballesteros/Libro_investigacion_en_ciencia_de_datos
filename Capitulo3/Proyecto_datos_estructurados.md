# 📘 Ciencia de Datos

## Capítulos relacionados

- 📊 Capítulo 4. Clasificación supervisada.
- 🧩 Capítulo 5. Preparación de datos e Ingeniería de Características.
- 🧪 Capítulo 6. Diseño Experimental para Ciencia de Datos.

---

# 🎯 Proyecto

# Optimización Experimental de un Pipeline de Ciencia de Datos para Predicción de Abandono de Clientes

---

# 📖 Contexto

Las organizaciones generan diariamente grandes volúmenes de información que permiten comprender el comportamiento de sus clientes y apoyar la toma de decisiones mediante modelos de Ciencia de Datos.

En este proyecto asumirán el papel de un equipo de científicos de datos encargado de mejorar un modelo de clasificación desarrollado previamente para predecir el abandono de clientes (*Customer Churn*).

A diferencia de los ejercicios tradicionales, donde el objetivo consiste únicamente en implementar un algoritmo, en un escenario profesional es común partir de una solución existente y preguntarse cómo mejorarla.

Para ello, los científicos de datos diseñan experimentos que les permiten evaluar el impacto de diferentes estrategias de preparación de datos, ingeniería de características y modelamiento antes de decidir cuál alternativa incorporar al pipeline definitivo.

---

# 🎯 Problema a resolver

Cada grupo recibirá como punto de partida el notebook desarrollado durante la clase.

El objetivo consiste en actualizar experimentalmente el pipeline de Ciencia de Datos mediante la incorporación de nuevas estrategias de preparación de datos y evaluar objetivamente el impacto de cada modificación sobre el desempeño del modelo de clasificación.

Al finalizar el proyecto deberán recomendar la mejor solución sustentando su decisión mediante evidencia experimental.

---

# 🧩 Etapas del proyecto

## 🔎 Etapa 1. Reproducción del caso de estudio

Ejecute el notebook desarrollado durante la clase y familiarícese con el pipeline de Ciencia de Datos implementado.

Como mínimo deberá comprender:

- El problema de clasificación planteado.
- Las variables utilizadas en el modelo.
- El pipeline de preparación de datos.
- El modelo de clasificación implementado.
- Las métricas utilizadas para evaluar el desempeño.

Este notebook constituirá la solución base sobre la cual deberán desarrollarse todos los experimentos del proyecto.

---

## 🛠️ Etapa 2. Actualización del pipeline de preparación de datos

A partir del pipeline desarrollado en clase, diseñe una nueva versión del pipeline incorporando estrategias adicionales de preparación de datos.

Como mínimo deberán realizar las siguientes tareas de construcción:

### 🧩 Construcción de una nueva característica (Feature Engineering)

Diseñe e incorpore al menos una nueva característica que no haya sido desarrollada durante la clase.

La nueva característica deberá justificarse técnicamente y explicar por qué podría aportar información útil para el problema de clasificación.

Algunos ejemplos pueden ser:

- combinación de variables;
- relaciones entre variables;
- discretización de variables continuas;
- indicadores derivados;
- variables categóricas construidas a partir de reglas de negocio.

La lista anterior es únicamente ilustrativa. Cada grupo podrá proponer cualquier otra estrategia debidamente justificada.

---

### 🩹 Implementación de una nueva estrategia de imputación

Implemente una estrategia de imputación diferente a la desarrollada durante la clase.

Algunas alternativas que pueden investigar son:

- imputación mediante mediana;
- KNN Imputer;
- imputación por regresión;
- imputación condicionada por grupos;
- Iterative Imputer;
- otras estrategias reportadas en la literatura.

La estrategia seleccionada deberá justificarse técnicamente.

---

### 🔄 Implementación de una nueva transformación de datos

Implemente al menos una transformación adicional diferente a las desarrolladas durante la clase.

Algunas alternativas que pueden investigar son:

- escalamiento (StandardScaler, MinMaxScaler, RobustScaler);
- normalización;
- discretización de variables continuas;
- codificación ordinal;
- Target Encoding;
- Frequency Encoding;
- tratamiento de valores atípicos (Outliers);
- transformación logarítmica;
- transformación Box-Cox;
- otras transformaciones debidamente justificadas.

La estrategia seleccionada deberá justificarse técnicamente.

---

## 🧪 Etapa 3. Diseño experimental

Con el fin de evaluar objetivamente el impacto de las modificaciones realizadas, cada grupo deberá diseñar y ejecutar un conjunto de experimentos.

Como mínimo deberán realizar los siguientes experimentos:

- Experimento Base (Notebook desarrollado durante la clase).
- Experimento 1. Nueva característica.
- Experimento 2. Nueva estrategia de imputación.
- Experimento 3. Nueva transformación de datos.
- Experimento 4. Pipeline actualizado (integrando las tres modificaciones).

> 📌 **Importante**
>
> Cada modificación deberá evaluarse inicialmente de manera independiente, manteniendo constante el resto del pipeline.
>
> Posteriormente deberá evaluarse el desempeño del pipeline incorporando conjuntamente todas las modificaciones realizadas.

### 📋 Tabla 1. Diseño Experimental (Ejemplo ilustrativo)

Cada grupo deberá documentar el diseño de sus experimentos utilizando una tabla similar a la siguiente.

| Experimento | Hipótesis | Actualización del pipeline | Métricas evaluadas | ¿Se acepta la hipótesis? |
|-------------|-----------|----------------------------|--------------------|--------------------------|
| Base | — | Pipeline desarrollado durante la clase. | Accuracy, Precision, Recall y F1-score | — |
| E1 | La incorporación de una nueva característica permitirá mejorar el F1-score del modelo. | Incorporación de una nueva característica (Feature Engineering). | Accuracy, Precision, Recall y F1-score | Sí / No |
| E2 | La implementación de una nueva estrategia de imputación permitirá mejorar el F1-score del modelo. | Cambio de la estrategia de imputación. | Accuracy, Precision, Recall y F1-score | Sí / No |
| E3 | La incorporación de una nueva transformación de datos permitirá mejorar el F1-score del modelo. | Incorporación de una nueva transformación de datos. | Accuracy, Precision, Recall y F1-score | Sí / No |
| E4 | La combinación de las tres modificaciones permitirá obtener un mejor F1-score que cada modificación por separado. | Pipeline de preparación de datos actualizado. | Accuracy, Precision, Recall y F1-score | Sí / No |
| E5 | Un nuevo modelo de clasificación permitirá mejorar el F1-score respecto al modelo desarrollado durante la clase. | Cambio del modelo de clasificación. | Accuracy, Precision, Recall y F1-score | Sí / No |

> 📌 **Importante**
>
> Aunque en todos los experimentos deberán calcular **Accuracy, Precision, Recall y F1-score**, la **métrica objetivo del proyecto será F1-score**. En consecuencia, las hipótesis deberán formularse buscando mejorar esta métrica y las conclusiones deberán justificar los resultados obtenidos con base en ella.
---

## 🤖 Etapa 4. Investigación e incorporación de un nuevo modelo de clasificación

Investigue un modelo de clasificación diferente al desarrollado durante la clase e incorpórelo al pipeline actualizado.

Algunas alternativas q ue pueden investigar son: Random Forest; Regresión Logística; Support Vector Machine (SVM); K-Nearest Neighbors (KNN); XGBoost;LightGBM; CatBoost; Gradient Boosting; Naive Bayes; Redes Neuronales; cualquier otro modelo de clasificación debidamente justificado.

El nuevo modelo deberá compararse con el modelo base utilizando las mismas métricas de evaluación.

### 📋 Tabla 2. Evaluación del efecto del modelo de clasificación (Ejemplo ilustrativo)

Con el fin de analizar el impacto del modelo de clasificación sobre diferentes versiones del pipeline de preparación de datos, cada grupo deberá realizar los siguientes experimentos.

| Experimento | Pipeline de preparación de datos | Modelo de clasificación | Accuracy | Precision | Recall | F1-score |
|-------------|----------------------------------|--------------------------|----------|-----------|--------|----------|
| M1 | Baseline (desarrollado durante la clase) | Árbol de Decisión | | | | |
| M2 | Baseline (desarrollado durante la clase) | Nuevo modelo | | | | |
| M3 | Mejor pipeline obtenido en la Etapa 3 | Árbol de Decisión | | | | |
| M4 | Mejor pipeline obtenido en la Etapa 3 | Nuevo modelo | | | | |

> 📌 **Importante**
>
> Compare el efecto del nuevo modelo de clasificación sobre el pipeline desarrollado durante la clase y sobre el mejor pipeline obtenido en la Etapa 3.
>
> Analice si el cambio de clasificador produce el mismo comportamiento en ambas soluciones o si su impacto depende del pipeline de preparación de datos utilizado.

---

## 🏆 Etapa 5. Análisis del impacto de las estrategias implementadas

A partir de los resultados obtenidos en las Etapas 3 y 4, analice el efecto de las modificaciones realizadas sobre el desempeño del sistema de clasificación.

Como mínimo deberán responder las siguientes preguntas:

1. **¿Cuál fue el impacto sobre el desempeño del clasificador al actualizar el pipeline de preparación de datos mediante nuevas estrategias de ingeniería de características, imputación y transformación de datos?**

2. **¿Cuál fue el impacto de cambiar el modelo de clasificación al utilizar dos versiones diferentes del pipeline de preparación de datos (pipeline desarrollado durante la clase y pipeline actualizado)?**

Finalmente, seleccione la mejor solución obtenida durante el proyecto y justifique técnicamente su decisión utilizando la evidencia experimental obtenida.
