# 📘 Investigación en Ciencia de Datos

> **Repositorio oficial del libro**
>
> **Investigación en Ciencia de Datos**  
> **Dora María Ballesteros**  
> **Editorial Redipe, 2026**

---

## 📖 Sobre este repositorio

Este repositorio contiene el material práctico del libro **Investigación en Ciencia de Datos** (Editorial Redipe, 2026).

El libro combina los fundamentos teóricos con casos de estudio completamente reproducibles desarrollados en **Python** mediante **Jupyter Notebooks**, permitiendo al lector seguir paso a paso el proceso de análisis de datos, ingeniería de características y construcción de modelos predictivos.

Los **Capítulos 1 y 2** corresponden a contenidos teóricos.

Los **Capítulos 3 y 4** incluyen cuatro casos de estudio completamente reproducibles, desarrollados mediante Jupyter Notebooks.

El **Capítulo 5** utiliza dos frameworks de investigación desarrollados en co-autoría.

---

# 📚 Casos de estudio

| Capítulo | Caso de estudio | Notebook | Dataset |
|-----------|-----------------|:--------:|:-------:|
| **3** | COVID-19 (Bogotá) | 📒 [Abrir](Capitulo3/Caso_estudio1/COVID-19.ipynb) | 📄 [Dataset](Capitulo3/Caso_estudio1/covid_2020_mayo.csv) |
| **3** | Bank Churn | 📒 [Abrir](Capitulo3/Caso_estudio2/Bank_churn.ipynb) | 📄 [Dataset](Capitulo3/Caso_estudio2/Bank_churn.csv) |
| **4** | Clima | 📒 [Abrir](Capitulo4/Caso1/Clima.ipynb) | 📄 [Dataset](Capitulo4/Caso1/clima.csv) |
| **4** | TWLO Prices | 📒 [Abrir](Capitulo4/Caso2/Twlo_prices.ipynb) | 📄 [Dataset](Capitulo4/Caso2/twlo_prices.csv) |

---

# 📊 Capítulo 3. Datos estructurados

## Caso de estudio 1. COVID-19 (Bogotá)

📒 **Notebook:**  
[COVID-19.ipynb](Capitulo3/Caso_estudio1/COVID-19.ipynb)

📄 **Dataset:**  
[covid_2020_mayo.csv](Capitulo3/Caso_estudio1/covid_2020_mayo.csv)

### Objetivo

Realizar un análisis exploratorio de un conjunto de datos de casos reportados de COVID-19 en Bogotá utilizando herramientas de Ciencia de Datos.

### Contenido del notebook

- Lectura del dataset COVID-19 de Bogotá.
- Previsualización del dataset.
- Tipos de datos.
- Distribución de los estados reportados.
- Distribución de los estados reportados por localidad.
- Conversión de la fecha de diagnóstico.
- Distribución temporal de los estados.
- Casos de contagio por género.
- Casos de contagio por día de diagnóstico.
- Evolución acumulada de casos de COVID-19.
- Distribución de casos según edad.
- Distribución de fallecidos según edad.
- Casos de contagio y fallecidos por localidad.
- Tasa de mortalidad por localidad.

---

## Caso de estudio 2. Bank Churn

📒 **Notebook:**  
[Bank_churn.ipynb](Capitulo3/Caso_estudio2/Bank_churn.ipynb)

📄 **Dataset:**  
[Bank_churn.csv](Capitulo3/Caso_estudio2/Bank_churn.csv)

### Objetivo

Desarrollar el flujo completo de preparación de datos para un problema de clasificación orientado a la predicción del abandono de clientes bancarios.

### Contenido del notebook

#### 1. Análisis Exploratorio de Datos (EDA)

- Lectura del dataset.
- Previsualización.
- Información general del dataset.
- Tipo de datos.
- Valores no nulos.
- Distribución de la variable objetivo.
- Proporción por clase.

#### 2. Transformación de variables

- Conversión de la variable **Gender**.
- Codificación **One-Hot Encoding** de la variable **Geography**.
- Análisis de la variable **Surname**.
- Construcción de una nueva característica mediante probabilidad condicionada.
- Eliminación de la columna **Surname**.

#### 3. Imputación de datos

- Identificación de datos faltantes.
- Imputación de la variable **Age**.
- Imputación de **HasCrCard**.
- Imputación de **IsActiveMember**.

#### 4. Limpieza del dataset

- Eliminación de columnas innecesarias.

#### 5. Modelamiento

- Preparación de los datos.
- Entrenamiento de un Árbol de Decisión.
- Predicción.

---

# ⏳ Capítulo 4. Series de Tiempo

## Caso de estudio 1. Clima

📒 **Notebook:**  
[Clima.ipynb](Capitulo4/Caso1/Clima.ipynb)

📄 **Dataset:**  
[clima.csv](Capitulo4/Caso1/clima.csv)

### Objetivo

Construir un modelo de clasificación del estado climático utilizando Ingeniería de Características (*Feature Engineering*).

### Contenido del notebook

#### 1. Preparación del dataset

- Lectura del dataset.
- Información general.
- Eliminación de datos faltantes.
- Conversión de la variable temporal.
- Definición del índice temporal.

#### 2. Análisis Exploratorio de Datos

- Codificación del estado climático.
- Evolución temporal de las variables.
- Entrenamiento inicial de un modelo Random Forest.

#### 3. Ingeniería de Características

- Matriz de correlación.
- Variables tipo **Lag**.
- Variables tipo **Rolling**.
- Variables tipo **Expanding**.
- Preparación del nuevo dataset.
- Importancia de las variables.

---

## Caso de estudio 2. TWLO Prices

📒 **Notebook:**  
[Twlo_prices.ipynb](Capitulo4/Caso2/Twlo_prices.ipynb)

📄 **Dataset:**  
[twlo_prices.csv](Capitulo4/Caso2/twlo_prices.csv)

### Objetivo

Desarrollar un modelo predictivo para una serie temporal financiera mediante técnicas de Ingeniería de Características.

### Contenido del notebook

#### 1. Análisis Exploratorio

- Lectura del dataset.
- Información general.
- Conversión de la fecha en índice temporal.
- Visualización de la serie temporal.
- Construcción de la variable objetivo.
- Cálculo del retorno diario.
- Definición de la variable **daily_target**.

#### 2. Entrenamiento inicial

- Preparación del dataset.
- División entre entrenamiento y validación.
- Entrenamiento de un Árbol de Decisión.

#### 3. Ingeniería de Características

- Construcción automática de nuevas variables mediante la función `add_statistical_fe()`.
- Visualización de los nuevos features.
- Distribución del dataset.
- Actualización del dataframe.

#### 4. Modelo final

- Entrenamiento con Ingeniería de Características.
- Ajuste de hiperparámetros.
- Reentrenamiento del modelo.
- Importancia de las variables.

---

# 🎙️ Capítulo 5. Frameworks utilizados

Los ejemplos desarrollados en el **Capítulo 5** hacen uso de dos frameworks de código abierto desarrollados como resultado de proyectos de investigación realizados en **coautoría**, los cuales complementan los conceptos presentados en el libro y permiten al lector experimentar con aplicaciones reales de Procesamiento Digital de Señales e Inteligencia Artificial.

## 🎤 Imitation

Framework de código abierto para realizar imitación de voz mediante Procesamiento Digital de Señales.

🔗 https://github.com/doramariaballesteros/Imitation-using-Signal-Processing

---

## 🔊 FakeVoiceFinder

Framework de código abierto para la detección de voz sintética y deepfakes de audio.

🔗 https://github.com/DEEP-CGPS/FakeVoiceFinder

---

# 🎯 Objetivos de aprendizaje

A través de los notebooks el lector aprenderá a:

- 📊 Realizar Análisis Exploratorio de Datos (EDA).
- 🧹 Limpiar y transformar datasets.
- 🔧 Construir nuevas variables mediante Ingeniería de Características.
- 🤖 Entrenar modelos de Machine Learning.
- ⏳ Trabajar con Series de Tiempo.
- 🎙️ Aplicar técnicas de Procesamiento Digital de Señales.
- 🧠 Utilizar herramientas de Inteligencia Artificial.

---

# 💻 Requisitos

Los notebooks fueron desarrollados en **Python** utilizando bibliotecas ampliamente empleadas en Ciencia de Datos, entre ellas:

- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Seaborn
- OpenCV (en los capítulos correspondientes)

Los notebooks pueden ejecutarse en:

- Jupyter Notebook
- JupyterLab
- Google Colab

---

# 📖 Referencia del libro

**Ballesteros, D. M. (2026).**  
*Investigación en Ciencia de Datos.*  
Editorial Redipe.  
ISBN: **978-1-957395-63-0**

---

# 👩‍🏫 Sobre la autora

**Dora María Ballesteros** es profesora e investigadora de la **Universidad Militar Nueva Granada (Colombia)**. Su trabajo se centra en Ciencia de Datos, Inteligencia Artificial, Procesamiento Digital de Señales y Aprendizaje Profundo. Es autora de diversos libros y artículos científicos en Ciencia de Datos, Inteligencia Artificial y Procesamiento Digital de Señales, promoviendo el desarrollo de recursos educativos y herramientas de software de código abierto para la comunidad académica.

---

# 📄 Licencia

Este repositorio se distribuye con fines académicos y educativos. Consulte el archivo **LICENSE** para conocer los términos de uso.
