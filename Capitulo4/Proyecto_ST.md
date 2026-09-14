# 🎯 Proyecto Final

## Predicción mediante Series de Tiempo

📊 **Ciencia de Datos**

---

## 📖 Contexto

En problemas reales de Ciencia de Datos, los datasets disponibles de Series de Tiempo no necesariamente incluyen una salida a predecir. Es decir, es frecuente encontrar datasets que contienen **mediciones, registros históricos o variables descriptivas**, pero que no incluyen directamente una variable de salida (*target*) asociada al problema que se desea resolver.

Esta situación puede presentarse en diferentes contextos. Por ejemplo:

- 📈 **Mercados financieros y criptomonedas:** precios de apertura y cierre, valores máximos y mínimos, volumen de negociación, entre otros.
- 🌦️ **Clima:** temperatura, humedad, radiación solar, velocidad del viento y otras variables meteorológicas.
- ⚡ **Consumo energético:** registros históricos de consumo, demanda y variables temporales.
- 🚗 **Movilidad y tráfico:** flujo vehicular, velocidad, tiempos de desplazamiento y otras mediciones.
- 📡 **Sensores e IoT:** mediciones obtenidas continuamente a partir de dispositivos, máquinas o procesos.

En estos casos, una de las primeras tareas consiste en **comprender los datos disponibles, formular un problema de predicción y determinar cuál será la variable que se desea predecir**.

Por esta razón, en un proyecto de Ciencia de Datos la variable objetivo no siempre corresponde a una columna existente en el dataset. Dependiendo del problema planteado, puede ser necesario **construir el *target* a partir de la información disponible**.

En este proyecto, cada grupo deberá seleccionar un dataset correspondiente a una **serie de tiempo real** y desarrollar un problema de clasificación, aplicando la metodología de análisis e Ingeniería de Características (*Feature Engineering*, FE) estudiada en el **Caso de Estudio 1**.

Posteriormente, deberán ampliar la metodología mediante la incorporación de una nueva técnica de Ingeniería de Características y evaluar su aporte al desempeño del modelo.

---

## 🔎 Selección del dataset

Cada grupo deberá seleccionar una serie de tiempo disponible en:

👉 [FRED – Federal Reserve Economic Data](https://fred.stlouisfed.org/)

El dataset seleccionado deberá contener:

- Una **variable temporal**.
- Una **única variable numérica de interés** (*feature*).

La variable temporal no será considerada un *feature* original del dataset.

Cada grupo deberá identificar y documentar:

- Nombre y descripción de la serie seleccionada.
- Unidad de medida.
- Frecuencia de muestreo.
- Periodo de tiempo seleccionado.
- Número de observaciones disponibles.

El periodo de análisis deberá proporcionar una cantidad suficiente de observaciones para desarrollar los experimentos de Ingeniería de Características. Por esta razón, su extensión deberá seleccionarse teniendo en cuenta la frecuencia de muestreo de la serie.


### 💡 Construcción de la salida

Suponga que se selecciona un dataset financiero que contiene el precio de cierre de un activo en diferentes instantes de tiempo.

El dataset contiene el precio \(P_t\), pero **no contiene una variable que indique si el precio aumentará en el siguiente periodo**.

Una posible pregunta de predicción sería:

> **¿Es posible predecir, utilizando la información disponible hasta el instante \(t\), si el precio aumentará en el siguiente periodo?**

Para responder esta pregunta podría construirse una variable objetivo:

$$
y_t =
\begin{cases}
1, & \text{si } P_{t+1} > P_t \\
0, & \text{si } P_{t+1} \leq P_t
\end{cases}
$$

donde:

- $y_t = 1$: el precio **sube** en el siguiente periodo.
- $y_t = 0$: el precio **no sube** en el siguiente periodo.
- 
De esta manera, el modelo utilizaría la información disponible hasta el instante \(t\) para predecir el comportamiento del precio en \(t+1\).

> 💡 **Importante**
>
> Este ejemplo es únicamente ilustrativo. Cada grupo deberá formular su propio problema de predicción y definir o construir una variable objetivo coherente con las características del dataset seleccionado.
