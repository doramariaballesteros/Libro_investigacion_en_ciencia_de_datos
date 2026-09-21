# 🎯 Proyecto Final

## Predicción mediante Series de Tiempo

📊 **Ciencia de Datos**

---

## 📖 Contexto

En problemas reales de Ciencia de Datos, los datasets disponibles de Series de Tiempo no necesariamente incluyen una salida a predecir. Por ejemplo, es frecuente encontrar datasets que contienen **mediciones, registros históricos o variables descriptivas**, pero que no incluyen directamente una variable de salida (*target*) asociada al problema que se desea resolver.

Esta situación puede presentarse en diferentes contextos, como:

- 📈 **Mercados financieros y criptomonedas:** con *features* de precios de apertura y cierre, valores máximos y mínimos, volumen de negociación, entre otros.
- 🌦️ **Clima:** con *features* de temperatura, humedad, radiación solar, velocidad del viento y otras variables meteorológicas.
- ⚡ **Consumo energético:** registros históricos de consumo, demanda y variables temporales.
- 🚗 **Movilidad y tráfico:** con *features* de flujo vehicular, velocidad, tiempos de desplazamiento y otras mediciones.
- 📡 **Sensores e IoT:** mediciones obtenidas continuamente a partir de dispositivos, máquinas o procesos.

Por lo que, una de las primeras tareas consiste en **comprender los datos disponibles, formular un problema de predicción y determinar cuál será la variable que se desea predecir**.

Por esta razón, en un proyecto de Ciencia de Datos con Series de Tiempo la variable objetivo no siempre corresponde a una columna existente en el dataset. Dependiendo del problema planteado, puede ser necesario **construir el *target* a partir de la información disponible**.

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


Las actividades a realizar se presentan a continuación:

## 📈 Análisis temporal de la serie

Como primera etapa, realiza una **exploración visual del comportamiento de la serie de tiempo**.

Grafica la variable numérica seleccionada en función del tiempo y analiza su evolución durante el periodo considerado.

A partir de la gráfica:

* Identifica si existe una **tendencia general** de crecimiento, disminución o estabilidad.
* Determina si el comportamiento de la serie **cambia a lo largo del tiempo**.
* Identifica **rangos temporales** que presenten comportamientos particulares. Por ejemplo, periodos de varios meses o años con tendencias crecientes, decrecientes o relativamente estables.
* Analiza la presencia de cambios importantes, máximos, mínimos o variaciones abruptas que puedan ser relevantes para comprender la dinámica de la serie.

Para apoyar el análisis, utiliza una **media móvil (*rolling mean*)** que permita suavizar las variaciones de corto plazo y visualizar con mayor claridad la curva de tendencia. Selecciona y justifica el tamaño de la ventana de acuerdo con la **frecuencia de muestreo y el comportamiento de la serie**.

Cuando identifiques comportamientos diferentes, delimita los **rangos de tiempo** correspondientes y describe las principales características observadas en cada uno.

> 💡 **Importante:** no se busca únicamente visualizar la serie. El objetivo es interpretar su comportamiento temporal y determinar si una única tendencia describe adecuadamente todo el periodo analizado o si existen diferentes etapas en su evolución.

## 🔄 Dependencia temporal

Como siguiente etapa, analiza la **dependencia de los valores actuales de la serie respecto a sus valores pasados**.

Calcula y grafica la **Función de Autocorrelación (ACF)** para evaluar la relación entre la serie y sus valores anteriores a diferentes *lags* o retardos temporales.

A partir de la gráfica de ACF:

* Identifica los *lags* que presentan una **autocorrelación significativa**.
* Analiza cómo cambia la autocorrelación a medida que aumenta el *lag*.
* Determina si la influencia de los valores pasados **disminuye rápidamente o se mantiene durante varios retardos**.
* Identifica posibles patrones temporales que puedan sugerir **periodicidad o repetición** en el comportamiento de la serie.
* Interpreta los *lags* identificados teniendo en cuenta la **frecuencia de muestreo** de la serie. Por ejemplo, un *lag* de 12 en una serie mensual representa un periodo de un año.

> 💡 **Importante:** no se busca únicamente generar la gráfica de ACF. Analiza qué información proporciona sobre la dependencia temporal de la serie y cómo podría utilizarse posteriormente en la Ingeniería de Características.


## 🛠️ Ingeniería de Características

A partir del análisis temporal y de dependencia realizado en las etapas anteriores, construye **nuevos *features* que representen información del comportamiento pasado de la serie**.

Genera:

* **4 *features* de tipo *Rolling***, utilizando cuatro tamaños de ventana diferentes.
* **4 *features* de tipo *Lag***, utilizando cuatro retardos temporales diferentes.

Los valores seleccionados para las **ventanas de *Rolling*** y los ***lags*** deben estar justificados a partir de las características de la serie, su frecuencia de muestreo y los resultados obtenidos durante el análisis exploratorio.

Para los *features* de tipo *Rolling*, utiliza la **media móvil (*rolling mean*)** como estadístico de la ventana.

En la construcción de los nuevos *features*, asegúrate de utilizar únicamente **información disponible hasta el instante de tiempo correspondiente**, evitando incorporar información futura que pueda producir *data leakage*.

> 💡 **Importante:** los tamaños de las ventanas y los valores de los *lags* no deben seleccionarse arbitrariamente. Explica qué información temporal busca representar cada uno y por qué puede resultar relevante para el problema de predicción.




### 💡 Construcción de la salida

Suponga que se selecciona un dataset financiero que contiene el precio de cierre de un activo en diferentes instantes de tiempo.

El dataset contiene el precio $P_t$, pero **no contiene una variable que indique si el precio aumentará en el siguiente periodo**.

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

De esta manera, el modelo utilizaría la información disponible hasta el instante \(t\) para predecir el comportamiento del precio en \(t+1\).

> 💡 **Importante**
>
> Este ejemplo es únicamente ilustrativo. Cada grupo deberá formular su propio problema de predicción y definir o construir una variable objetivo coherente con las características del dataset seleccionado.
