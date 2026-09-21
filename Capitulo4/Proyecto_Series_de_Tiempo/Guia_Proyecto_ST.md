# 🎯 Proyecto Final

## Predicción mediante Series de Tiempo

> **Dora María Ballesteros**  
> *Investigación en Ciencia de Datos*  
> Primera edición, 2026  
> ISBN: 978-1-957395-63-0  
> 🔗 **[Consultar el libro en Editorial REDIPE](https://editorial.redipe.org/index.php/1/catalog/book/245)**
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

# 🔎 1. Selección del dataset

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

Las actividades a realizar se presentan a continuación.

---

# 📈 2. Análisis temporal de la serie

Como primera etapa, realiza una **exploración visual del comportamiento de la serie de tiempo**.

Grafica la variable numérica seleccionada en función del tiempo y analiza su evolución durante el periodo considerado.

A partir de la gráfica:

- Identifica si existe una **tendencia general** de crecimiento, disminución o estabilidad.
- Determina si el comportamiento de la serie **cambia a lo largo del tiempo**.
- Identifica **rangos temporales** que presenten comportamientos particulares. Por ejemplo, periodos de varios meses o años con tendencias crecientes, decrecientes o relativamente estables.
- Analiza la presencia de cambios importantes, máximos, mínimos o variaciones abruptas que puedan ser relevantes para comprender la dinámica de la serie.

Para apoyar el análisis, utiliza una **media móvil (*rolling mean*)** que permita suavizar las variaciones de corto plazo y visualizar con mayor claridad la curva de tendencia. Selecciona y justifica el tamaño de la ventana de acuerdo con la **frecuencia de muestreo y el comportamiento de la serie**.

Cuando identifiques comportamientos diferentes, delimita los **rangos de tiempo** correspondientes y describe las principales características observadas en cada uno.

> 💡 **Importante:** no se busca únicamente visualizar la serie. El objetivo es interpretar su comportamiento temporal y determinar si una única tendencia describe adecuadamente todo el periodo analizado o si existen diferentes etapas en su evolución.

---

# 🔄 3. Dependencia temporal

Como siguiente etapa, analiza la **dependencia de los valores actuales de la serie respecto a sus valores pasados**.

Calcula y grafica la **Función de Autocorrelación (ACF)** para evaluar la relación entre la serie y sus valores anteriores a diferentes *lags* o retardos temporales.

A partir de la gráfica de ACF:

- Identifica los *lags* que presentan una **autocorrelación significativa**.
- Analiza cómo cambia la autocorrelación a medida que aumenta el *lag*.
- Determina si la influencia de los valores pasados **disminuye rápidamente o se mantiene durante varios retardos**.
- Identifica posibles patrones temporales que puedan sugerir **periodicidad o repetición** en el comportamiento de la serie.
- Interpreta los *lags* identificados teniendo en cuenta la **frecuencia de muestreo** de la serie. Por ejemplo, un *lag* de 12 en una serie mensual representa un periodo de un año.

> 💡 **Importante:** no se busca únicamente generar la gráfica de ACF. Analiza qué información proporciona sobre la dependencia temporal de la serie y cómo podría utilizarse posteriormente en la Ingeniería de Características.

---

# 🛠️ 4. Ingeniería de Características

A partir del análisis temporal y de dependencia realizado en las etapas anteriores, construye **nuevos *features* que representen información del comportamiento pasado de la serie**.

Genera:

- **4 *features* de tipo Rolling**, utilizando cuatro tamaños de ventana diferentes.
- **4 *features* de tipo Lag**, utilizando cuatro retardos temporales diferentes.

Los valores seleccionados para las ventanas de *Rolling* y los *lags* deben estar justificados a partir de las características de la serie, su frecuencia de muestreo y los resultados obtenidos durante el análisis exploratorio.

Para los *features* de tipo *Rolling*, utiliza la **media móvil (*rolling mean*)** como estadístico de la ventana.

En la construcción de los nuevos *features*, asegúrate de utilizar únicamente **información disponible hasta el instante de tiempo correspondiente**, evitando incorporar información futura que pueda producir *data leakage*.

> 💡 **Importante:** los tamaños de las ventanas y los valores de los *lags* no deben seleccionarse arbitrariamente. Explica qué información temporal busca representar cada uno y por qué puede resultar relevante para el problema de predicción.

---

# 🎯 5. Construcción de la salida

La serie seleccionada en **[FRED – Federal Reserve Economic Data](https://fred.stlouisfed.org/)** contiene una única variable numérica \(X_t\), registrada en diferentes instantes de tiempo, y **no contiene una variable de salida (*target*)**.

Por esta razón, cada grupo deberá formular un **problema de clasificación binaria** y construir una variable objetivo numérica, codificada como **0 y 1**, a partir de la información disponible en la serie.

## 💡 Ejemplo

Supón que la serie seleccionada en **FRED** corresponde a la tasa de cambio **USD/COP**, expresada en pesos colombianos por dólar.

Una posible pregunta de predicción sería:

> **¿Es posible predecir, utilizando la información disponible hasta el instante \(t\), si el precio aumentará más de un 1 % en el siguiente periodo?**

La variable objetivo podría construirse como:

$$
y_t =
\begin{cases}
1, & \text{si } P_{t+1} > 1.01P_t \\
0, & \text{si } P_{t+1} \leq 1.01P_t
\end{cases}
$$

donde:

- \(y_t=1\): el precio **aumenta más de un 1 %** en el siguiente periodo.
- \(y_t=0\): el precio **no aumenta más de un 1 %** en el siguiente periodo.

Por ejemplo, si el precio actual es \(P_t=3000\):

$$
1.01P_t=1.01(3000)=3030
$$

Por lo tanto, la clase será \(y_t=1\) si en el siguiente periodo el precio **supera 3030**.

Una vez construida la variable de salida, **analiza su distribución y determina si existe desbalance entre las clases 0 y 1**.

> 💡 **Importante:** el umbral del **1 % es únicamente ilustrativo**. Cada grupo deberá definir y justificar el criterio utilizado para construir su variable objetivo, teniendo en cuenta las características y el comportamiento de la serie seleccionada.
>
> La información futura puede utilizarse para **construir la salida que se desea predecir**, pero no debe incorporarse como *feature* del modelo.

---

# 🤖 6. Modelamiento y experimentación

A partir de los *features* construidos y de la variable objetivo definida, desarrolla **seis experimentos** utilizando el mismo algoritmo de clasificación y las mismas condiciones de entrenamiento y evaluación.

> 💡 **Recomendación para la división Train/Test:**  
> La división de los datos debe respetar siempre el **orden temporal** de las observaciones. Antes de definir el porcentaje de Train y Test:
>
> - Grafica la serie indicando visualmente los periodos correspondientes a **Train y Test**.
> - Analiza qué **comportamientos temporales** de la serie quedan incluidos en cada conjunto.
> - Verifica el **número de observaciones** y la **distribución de las clases** en Train y Test.
> - Selecciona y justifica el porcentaje de división de acuerdo con las características de la serie.
>
> El conjunto de Test debe contener un número suficiente de observaciones que permita evaluar el modelo considerando el comportamiento temporal de la serie. Una vez seleccionada la división, **mantén el mismo Train/Test en todos los experimentos**.

Mantén la **misma partición de entrenamiento y prueba en los seis experimentos** para garantizar que los resultados obtenidos sean comparables.

## 🧪 Experimento 1 – Baseline

Construye un modelo utilizando:

- *Feature* original.
- Variable de salida.

Este experimento corresponde al **Baseline** y establece el punto de referencia para evaluar el aporte de la Ingeniería de Características.

---

## 🧪 Experimento 2 – Rolling

Construye un modelo utilizando:

- *Feature* original.
- 4 *features* de tipo *Rolling*.
- Variable de salida.

Analiza el aporte de los *features* construidos mediante ventanas temporales respecto al **Baseline**.

Obtén y analiza la **importancia de características** para identificar el aporte de los diferentes *features* de tipo *Rolling*.

---

## 🧪 Experimento 3 – Lags

Construye un modelo utilizando:

- *Feature* original.
- 4 *features* de tipo *Lag*.
- Variable de salida.

Analiza el aporte de la información correspondiente a valores anteriores de la serie respecto al **Baseline**.

Obtén y analiza la **importancia de características** para identificar el aporte de los diferentes *features* de tipo *Lag*.

---

## 🧪 Experimento 4 – Expanding

Consulta el funcionamiento de ***Expanding*** aplicado a Series de Tiempo y analiza sus diferencias respecto a *Rolling*.

A partir de la consulta:

- Construye **un *feature* de tipo Expanding**.
- Define y justifica la forma en que se calcula.
- Explica qué información temporal representa.
- Asegúrate de utilizar únicamente información disponible hasta el instante correspondiente, evitando *data leakage*.

Construye un modelo utilizando:

- *Feature* original.
- 1 *feature* de tipo *Expanding*.
- Variable de salida.

Analiza el aporte del nuevo *feature* respecto al **Baseline** y su importancia dentro del modelo.

---

## 🧪 Experimento 5 – Integración de *features*

Construye un modelo utilizando:

- *Feature* original.
- 4 *features* de tipo *Rolling*.
- 4 *features* de tipo *Lag*.
- 1 *feature* de tipo *Expanding*.
- Variable de salida.

Analiza el comportamiento del modelo cuando se integra toda la información generada mediante Ingeniería de Características.

Obtén y analiza la **importancia de características** para determinar el aporte de los diferentes tipos de *features* dentro de la solución integrada.

---

## 🧪 Experimento 6 – Selección por importancia de características

A partir de la **importancia de características** obtenida en los experimentos anteriores:

- Selecciona el *feature* de tipo **Rolling con mayor importancia**.
- Selecciona el *feature* de tipo **Lag con mayor importancia**.
- Incorpora el *feature* de tipo **Expanding construido en el Experimento 4**.

Construye un modelo utilizando únicamente estos **tres *features*** y la variable de salida. En este experimento **no utilices el *feature* original**.

Analiza si una representación reducida, construida exclusivamente a partir de información temporal, permite obtener un desempeño comparable o superior al de los experimentos anteriores.

---

## 📊 Evaluación y análisis

Para cada uno de los seis experimentos reporta:

- **Matriz de confusión**.
- **Accuracy**.
- **Precision por clase**.
- **Recall por clase**.
- **F1-score por clase**.
- **Importancia de características**, cuando corresponda.

Utiliza las **mismas condiciones de entrenamiento y evaluación** en todos los experimentos para garantizar que los resultados sean comparables.

Finalmente, compara los seis experimentos y responde:

> **¿Con cuál de las soluciones desarrolladas te quedarías y por qué?**

Justifica la respuesta a partir de la **matriz de confusión, las métricas obtenidas para cada clase, la importancia de características y el número de *features* utilizados**. No sustentes la decisión únicamente en el valor de *Accuracy*.

---
# 📓 7. Entregable – Notebook

Cada grupo deberá entregar un **Notebook desarrollado en Python** que documente de manera organizada y reproducible el desarrollo completo del proyecto.

El Notebook deberá incluir:

- **Descripción de la serie seleccionada:** nombre, fuente, unidad de medida, frecuencia de muestreo, periodo de análisis y número de observaciones.
- **Análisis temporal de la serie:** gráfica de la serie original, análisis de tendencias y rangos temporales, y curva de tendencia obtenida mediante *Rolling*.
- **Análisis de dependencia temporal:** gráfica de la Función de Autocorrelación (**ACF**) e interpretación de los *lags* identificados.
- **Ingeniería de Características:** construcción y justificación de los 4 *features* de tipo *Rolling* y los 4 *features* de tipo *Lag*.
- **Construcción de la variable de salida:** definición de las clases 0 y 1, justificación del criterio utilizado y análisis de la distribución de las clases.
- **Modelamiento y experimentación:** desarrollo completo de los **seis experimentos** definidos en el proyecto.
- **Evaluación de los experimentos:** matriz de confusión, Accuracy, Precision, Recall y F1-score por clase para cada experimento, así como la importancia de características cuando corresponda.
- **Comparación de resultados:** análisis comparativo de los seis experimentos y selección de la solución final a partir de la evidencia obtenida.
- **Conclusiones:** principales hallazgos derivados del análisis temporal, la Ingeniería de Características y la experimentación.

El Notebook deberá integrar **código, resultados, gráficas e interpretación**. No se considerará suficiente presentar únicamente la ejecución del código o las salidas generadas.

> 💡 **Importante:** el Notebook constituye la **evidencia completa del desarrollo del proyecto**. Todos los resultados utilizados durante la sustentación deberán estar respaldados por los análisis y experimentos incluidos en este entregable.

---

# 🖼️ 8. Material para la sustentación – Póster

Para la sustentación, cada grupo deberá elaborar un **póster académico** que sintetice visualmente el problema desarrollado, las decisiones metodológicas y los principales resultados obtenidos.

El póster deberá incluir como mínimo:

- **Serie seleccionada y problema de predicción:** identificación de la serie, fuente, periodo, frecuencia de muestreo y pregunta de predicción.
- **Comportamiento temporal:** gráfica de la serie y curva de tendencia obtenida mediante *Rolling*, destacando los principales comportamientos identificados.
- **Dependencia temporal:** gráfica de la **ACF** y una breve interpretación de los *lags* relevantes.
- **Ingeniería de Características:** ventanas utilizadas para los *features* de tipo *Rolling*, retardos seleccionados para los *features* de tipo *Lag* y *feature* de tipo *Expanding* incorporado.
- **Variable de salida:** definición de las clases 0 y 1 y criterio utilizado para su construcción.
- **Resultados de los seis experimentos:** tabla comparativa que presente **Accuracy, Precision, Recall y F1-score por clase**.
- **Matriz de confusión de la solución seleccionada**.
- **Importancia de características:** representación que permita sustentar el aporte de los *features* y las decisiones realizadas durante la experimentación.
- **Conclusiones:** identificación de la solución seleccionada y justificación de la decisión a partir de los resultados obtenidos.

El póster deberá presentar la información de manera **sintética, legible y visual**, priorizando gráficas, tablas y resultados relevantes sobre grandes bloques de texto.

> 💡 **Importante:** el póster es un **material de apoyo para la sustentación** y no reemplaza el Notebook. Su propósito es comunicar de manera clara la historia del proyecto: **qué problema se formuló, qué decisiones se tomaron, qué se experimentó, qué resultados se obtuvieron y qué solución se seleccionó**.
---

# 🧪 RÚBRICA DE EVALUACIÓN

## RA 6.1 – EXPERIMENTACIÓN

**RA 6.1.** Diseña y ejecuta experimentos computacionales sobre datos estructurados, series de tiempo y señales de voz, comparando distintas estrategias de análisis, preprocesamiento, ingeniería de características o modelado, interpretando los resultados mediante métricas apropiadas y proponiendo mejoras a partir de la evidencia obtenida.

### Criterio 1

**Diseña y ejecuta experimentos computacionales sobre una serie de tiempo, comparando estrategias de Ingeniería de Características e interpretando los resultados mediante métricas de clasificación.**

### Acciones observables

1. **Diseña y ejecuta** experimentos utilizando **Baseline, Rolling y Lags** para comparar diferentes estrategias de Ingeniería de Características.
2. **Interpreta** los resultados obtenidos en los experimentos utilizando **matriz de confusión, Precision, Recall y F1-score por clase**.

### Rúbrica de evaluación

| Nivel | Valor / Rango | Descriptor |
|---|---:|---|
| **Bajo** | **0.0** | **No diseña ni ejecuta** los experimentos con Baseline, Rolling y Lags, y **no interpreta** los resultados mediante la matriz de confusión, Precision, Recall y F1-score por clase. |
| **Medio** | **2.5 – 4.5** | **Diseña y ejecuta parcialmente** los experimentos con Baseline, Rolling y Lags, e **interpreta de manera incompleta** los resultados mediante la matriz de confusión, Precision, Recall y F1-score por clase. |
| **Alto** | **5.0** | **Diseña y ejecuta de manera completa y correcta** los experimentos con Baseline, Rolling y Lags, e **interpreta de manera completa y correcta** los resultados mediante la matriz de confusión, Precision, Recall y F1-score por clase. |

---

## 🔎 RA 7.1 – AUTOAPRENDIZAJE

**RA 7.1.** Investiga, selecciona e incorpora de manera autónoma una técnica, herramienta o estrategia relacionada con Ciencia de Datos que no haya sido desarrollada explícitamente en clase, justificando su integración dentro de la solución de un problema basado en datos estructurados, series de tiempo o señales de voz mediante Python.

### Criterio 2

**Investiga, incorpora y evalúa de manera autónoma la técnica Expanding en el Experimento 4 como estrategia de Ingeniería de Características para Series de Tiempo mediante Python.**

### Acción observable

**Investiga e incorpora** un *feature* de tipo **Expanding en el Experimento 4** y **evalúa su impacto** a partir de los resultados obtenidos en los **Experimentos 4, 5 y 6**.

### Rúbrica de evaluación

| Nivel | Valor | Descriptor |
|---|---:|---|
| **Bajo** | **0.0** | **No investiga ni incorpora** un *feature* de tipo **Expanding** en el Experimento 4. |
| **Medio** | **3.0** | **Investiga e incorpora** un *feature* de tipo **Expanding** en el Experimento 4, pero **evalúa parcialmente su impacto** a partir de los resultados obtenidos en los Experimentos 4, 5 y 6. |
| **Alto** | **5.0** | **Investiga e incorpora correctamente** un *feature* de tipo **Expanding** en el Experimento 4 y **evalúa de manera completa y correcta su impacto** a partir de los resultados obtenidos en los Experimentos 4, 5 y 6. |

> 📝 **Nota para el consolidado:** La calificación final del proyecto se obtiene mediante la ponderación de los dos criterios de evaluación. El **Criterio 1 – Experimentación (RA 6.1)** corresponde al **80 %** de la calificación y el **Criterio 2 – Autoaprendizaje (RA 7.1)** corresponde al **20 %** restante.



