
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

Ejecute el código de Imitation utilizando `audio.wav` como señal objetivo y, de manera independiente, cada una de las cinco señales secretas.

Como resultado, debe obtener:

- Cinco señales de audio imitadas: `imitated1.wav` hasta `imitated5.wav`.
- Cinco claves: `key1.csv` hasta `key5.csv`.

### 📊 Parte 2. Similitud entre señales de audio

Compare la señal original `audio.wav` con cada una de las cinco señales imitadas.

Para cada comparación, calcule:

1. **Coeficiente de correlación de Pearson:** para evaluar la similitud entre las formas de onda.
2. **Error cuadrático medio (MSE):** para cuantificar las diferencias entre las muestras.

Presente los resultados en una tabla:


Presente los resultados en una tabla:

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

1. ¿Cuál de las cinco señales imitadas presenta mayor similitud con la señal objetivo? Justifique su respuesta utilizando los valores de correlación de Pearson y MSE obtenidos.
2. ¿Las cinco señales imitadas presentan niveles de similitud comparables? Analice las diferencias observadas y explique si ambas métricas permiten establecer conclusiones consistentes.

### 🔑 Parte 3. Similitud entre claves

Las claves generadas mediante Imitation corresponden a vectores de índices asociados con los coeficientes obtenidos mediante la transformación wavelet `sym4`.

Compare las cinco claves entre sí, considerando todas las parejas posibles (10 comparaciones).

Para cada pareja, calcule:

**Porcentaje de coincidencia:** proporción de posiciones en las que ambas claves contienen exactamente el mismo índice.

$$
\text{Coincidencia (\%)} =
\frac{\sum_{i=1}^{N}\mathbb{1}(K_1[i]=K_2[i])}{N}\times 100
$$

Donde $N$ es la longitud de las claves y $\mathbb{1}$ es la función indicadora, que toma el valor de 1 cuando los índices coinciden y 0 en caso contrario.

Presente los resultados en una tabla:

| Comparación | Coincidencia (%) | 
|---|---|---|
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

1. ¿Qué pareja de claves presenta mayor similitud y cuál presenta menor similitud?
2. ¿Qué indican los porcentajes de coincidencia obtenidos acerca de las diferencias entre las claves?
3. ¿Los resultados de Spearman son consistentes con los porcentajes de coincidencia? Explique.
4. ¿Qué puede concluir acerca de las claves generadas cuando se mantiene la misma señal objetivo y se modifican las señales secretas?

### 📝 Parte 4. Conclusiones

A partir de los resultados obtenidos, responda:

1. ¿Es posible obtener señales imitadas con alta similitud respecto a una misma señal objetivo utilizando diferentes señales secretas?
2. ¿Existe alguna relación entre la similitud de las señales imitadas y la similitud de sus correspondientes claves? Sustente su respuesta con los resultados experimentales.
3. ¿Qué evidencia proporcionan los resultados acerca del comportamiento del proceso de Imitation?
