
## 🎯 Actividad 1. Análisis de similitud en el proceso de Imitation

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


### 📝 Parte 4. Conclusiones

1. ¿Es posible obtener señales imitadas con alta similitud respecto a una misma señal objetivo utilizando diferentes señales secretas? Sustenta tu respuesta a partir de los resultados experimentales.
2. ¿Existe alguna relación entre la similitud de las señales imitadas y la similitud de sus correspondientes claves? Justifica utilizando los resultados obtenidos.
