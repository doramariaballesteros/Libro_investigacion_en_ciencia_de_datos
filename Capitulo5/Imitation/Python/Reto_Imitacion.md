
# 🔐 Reto: Análisis de Similitud en el Proceso de Imitación

### 📌 Propósito

Analizar el comportamiento del proceso de **Imitation** mediante la generación de diferentes señales de audio imitadas y sus correspondientes claves, evaluando la similitud entre las señales de audio y entre las claves obtenidas.

La actividad busca determinar cómo cambia el resultado del proceso de imitación cuando se utiliza una misma señal objetivo (*target*) y diferentes señales secretas (*secret*).

### 📂 Archivos suministrados

Para el desarrollo de la actividad se proporcionan:

- 🎵 **audio.wav:** señal de audio objetivo (*target*).
- 🔐 **secret1.wav, secret2.wav, secret3.wav, secret4.wav y secret5.wav:** cinco señales secretas.
- 💻 **Imitation_GitHub.ipynb:** código Python que implementa el proceso de Imitation.

### 🧪 Parte 1. Ejecución de Imitation

Ejecuta el código de Imitation utilizando `audio.wav` como señal objetivo y, de manera independiente, cada una de las cinco señales secretas.

Como resultado, debes obtener:

- Cinco señales de audio imitadas: `imitated1.wav` hasta `imitated5.wav`.
- Cinco claves: `key1.csv` hasta `key5.csv`.

### 📊 Parte 2. Similitud entre señales de audio

Compara la señal original `audio.wav` con cada una de las cinco señales imitadas.

Para cada comparación, calcula:

1. **Coeficiente de correlación de Pearson:** para evaluar la similitud entre las formas de onda.
2. **Error cuadrático medio (MSE):** para cuantificar las diferencias entre las muestras.

Presenta los resultados en una tabla:

| Comparación | Correlación de Pearson | MSE |
|:---|:---:|:---:|
| audio vs. imitated1 | | |
| audio vs. imitated2 | | |
| audio vs. imitated3 | | |
| audio vs. imitated4 | | |
| audio vs. imitated5 | | |

**Preguntas de análisis:**

1. ¿Cuál de las cinco señales imitadas presenta mayor similitud con la señal audio.wav? Justifica tu respuesta utilizando los valores de correlación de Pearson y MSE obtenidos.
2. ¿Las cinco señales imitadas presentan niveles de similitud comparables? Analiza las diferencias observadas y explica si ambas métricas permiten establecer conclusiones consistentes.

### 🔑 Parte 3. Similitud entre claves

Las claves generadas mediante Imitation corresponden a vectores de índices asociados con los coeficientes obtenidos mediante la transformación wavelet `sym4`.

Compara las cinco claves entre sí, considerando todas las parejas posibles (10 comparaciones).

Para cada pareja, calcula:

**Porcentaje de coincidencia:** proporción de posiciones en las que ambas claves contienen exactamente el mismo índice.

$$
\text{Coincidencia (\%)} =
\frac{\sum_{i=1}^{N}\mathbb{1}(K_1[i]=K_2[i])}{N}\times 100
$$

Donde $N$ es la longitud de las claves y $\mathbb{1}$ es la función indicadora, que toma el valor de 1 cuando los índices coinciden y 0 en caso contrario.

Presenta los resultados en una tabla:

| Comparación | Coincidencia (%) |
|:---|:---:|
| key1 vs. key2 | |
| key1 vs. key3 | |
| key1 vs. key4 | |
| key1 vs. key5 | |
| key2 vs. key3 | |
| key2 vs. key4 | |
| key2 vs. key5 | |
| key3 vs. key4 | |
| key3 vs. key5 | |
| key4 vs. key5 | |

**Preguntas de análisis:**

1. ¿Qué parejas de claves presentan la mayor y la menor similitud? Justifica tu respuesta utilizando los porcentajes de coincidencia obtenidos.
2. ¿Qué puedes concluir acerca de las claves generadas cuando se mantiene la misma señal objetivo y se utilizan diferentes señales secretas?

## 📋 Rúbrica de evaluación — Actividad 1. Imitation

### 🎯 Resultado de Aprendizaje

Implementa soluciones de ingeniería de datos para datos estructurados, series de tiempo y señales de voz, integrando procesos de exploración, transformación, ingeniería de características y análisis sobre un conjunto de datos, utilizando Python y tomando como referencia los casos de estudio desarrollados en la asignatura.

### 📊 Niveles de desempeño

| Nivel | Desempeño | Nota |
|:---:|---|:---:|
| 1 | Sin evidencia | **0.0** |
| 2 | Inicial | **2.0** |
| 3 | Satisfactorio | **3.5** |
| 4 | Sobresaliente | **5.0** |

### 🔵 Criterio 1. Similitud entre señales imitadas (50 %)

**Implementa en Python métricas de similitud entre señales imitadas y compara sus resultados.**

| Nivel | Descriptor | Nota |
|:---:|---|:---:|
| 1 | No implementa las métricas de similitud ni compara los resultados. | 0.0 |
| 2 | Implementa parcialmente las métricas de similitud y compara parcialmente los resultados. | 2.0 |
| 3 | Implementa completamente y de forma correcta las métricas de similitud, pero compara parcialmente los resultados. | 3.5 |
| 4 | Implementa completamente y de forma correcta las métricas de similitud y compara completamente y de forma correcta los resultados. | 5.0 |

### 🟣 Criterio 2. Similitud entre claves (50 %)

**Implementa en Python una métrica de similitud entre claves generadas mediante Imitation y compara sus resultados.**

| Nivel | Descriptor | Nota |
|:---:|---|:---:|
| 1 | No implementa la métrica de similitud ni compara los resultados. | 0.0 |
| 2 | Implementa parcialmente la métrica de similitud y compara parcialmente los resultados. | 2.0 |
| 3 | Implementa completamente y de forma correcta la métrica de similitud, pero compara parcialmente los resultados. | 3.5 |
| 4 | Implementa completamente y de forma correcta la métrica de similitud y compara completamente y de forma correcta los resultados. | 5.0 |

### 🧮 Cálculo de la nota final

Los dos criterios tienen la misma ponderación:

- **Criterio 1:** 50 %
- **Criterio 2:** 50 %

La nota final de la actividad se calcula mediante:

$$
\boxed{N_f=0.5N_{C1}+0.5N_{C2}}
$$

Donde:

- $N_{C1}$: nota obtenida en el criterio 1.
- $N_{C2}$: nota obtenida en el criterio 2.
- $N_f$: nota final de la actividad.

