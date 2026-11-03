# Proyecto de Ciencia de Datos: Fusión de modelos para la detección de audios sintéticos

## 🎯 1. Contexto del proyecto

🎙️ La **detección de audios sintéticos (*audio deepfake detection*)** es un problema de clasificación binaria cuyo propósito es distinguir entre grabaciones de voz naturales y aquellas generadas o modificadas mediante técnicas de Inteligencia Artificial (IA).

🧠 Una estrategia para abordar este problema consiste en utilizar modelos de aprendizaje profundo (*Deep Learning*) entrenados sobre diferentes representaciones de una misma señal de voz. Aunque estos modelos realizan predicciones de manera independiente, **sus resultados pueden contener información complementaria que, al combinarse, permita mejorar el desempeño de la clasificación**.

🔬 En este proyecto trabajaremos con las predicciones de **cuatro modelos basados en la arquitectura DenseNet121**, cada uno entrenado con una representación diferente del audio:

- 📊 **LOG:** espectrograma logarítmico.
- 🎼 **MEL:** espectrograma en escala Mel.
- 🌊 **DWT:** transformada discreta Wavelet.
- 📈 **CQT:** transformada de Q constante.

⚙️ **¿Cuál es el reto?**

Diseñar e implementar un método de fusión basado en *Machine Learning* que aproveche las predicciones de los cuatro modelos para obtener **una única decisión por audio: natural (0) o sintético (1)**.

🏆 **La pregunta que guiará nuestro desafío es:**

**¿Podemos superar el desempeño de los modelos individuales mediante una estrategia inteligente de fusión y alcanzar el mayor F1 de la clase?**

## 2. Objetivo

Diseñar, implementar y evaluar un método de fusión basado en Machine Learning que combine las predicciones de cuatro modelos DenseNet121, correspondientes a las representaciones LOG, MEL, DWT y CQT, con el propósito de **maximizar el F1 de clasificación binaria** sobre un conjunto de validación interna.

## 3. Descripción del dataset

El archivo `fake_densenet121.csv` contiene las predicciones generadas por cuatro modelos DenseNet121 sobre un conjunto de audios.

Cada audio aparece en cuatro registros, uno por representación, con las siguientes columnas de interés:

| Campo | Descripción |
|---|---|
| Identificador del audio | Nombre del archivo WAV al que corresponde la predicción. |
| Representación | LOG, MEL, DWT o CQT. |
| `prediction` | Valor entre 0 y 100 generado por el modelo de clasificación. |
| `ground_truth` | Etiqueta verdadera del audio. |

### Interpretación de los valores

La columna `prediction` contiene valores en el intervalo de 0 a 100:

- Valores inferiores a 50: predicción de audio natural.
- Valores iguales o superiores a 50: predicción de audio sintético (*fake*).

La columna `ground_truth` contiene las etiquetas verdaderas:

- **0:** audio natural.
- **1:** audio sintético (*fake*).

**Importante:** los cuatro registros correspondientes a un mismo audio tienen el mismo valor de `ground_truth`, aunque sus valores de `prediction` pueden ser diferentes.

## 4. Metodología

### 4.1. Organización de los datos

El primer paso consiste en transformar la estructura original del dataset para obtener una única fila por audio.

Cada fila debe contener las cuatro predicciones correspondientes a LOG, MEL, DWT y CQT, además de su etiqueta verdadera.

De esta manera, el problema de fusión se transforma en una tarea de clasificación supervisada con cuatro variables de entrada y una variable de salida.

### 4.2. División del dataset

La división será fija y estará determinada por la numeración de los archivos de audio.

| Conjunto | Archivos | Propósito |
|---|---|---|
| Entrenamiento | `1.wav` hasta `450.wav` | Entrenar el método de fusión. |
| Validación interna | `451.wav` en adelante | Evaluar el desempeño mediante F1. |

Se deben cumplir las siguientes condiciones:

1. Los cuatro registros de cada audio deben permanecer agrupados.
2. Ningún audio puede aparecer simultáneamente en entrenamiento y validación.
3. Todos los grupos deben utilizar exactamente la misma partición.
4. El conjunto de validación interna no debe utilizarse para ajustar el modelo.

### 4.3. Selección del método de fusión

Cada grupo deberá investigar y seleccionar de manera autónoma un algoritmo de Machine Learning capaz de combinar las cuatro predicciones.

La elección del algoritmo es libre, siempre que permita realizar clasificación binaria y se justifique su aplicación al problema.

La entrada al método de fusión estará formada por las cuatro predicciones de cada audio:

\[
\mathbf{x}_i =
[p_{LOG},p_{MEL},p_{DWT},p_{CQT}]
\]

La salida será una única etiqueta:

\[
\hat{y}_i\in\{0,1\}
\]

Donde:

- **0:** audio natural.
- **1:** audio sintético.

Los estudiantes podrán investigar diferentes algoritmos, estrategias de preprocesamiento, selección de hiperparámetros y mecanismos de clasificación.

### 4.4. Evaluación del método de fusión

El desempeño se evaluará mediante el **F1-score**, calculado sobre el conjunto de validación interna.

\[
F1=\frac{2PR}{P+R}
\]

Donde:

- \(P\): precisión (*Precision*).
- \(R\): sensibilidad (*Recall*).

La clase positiva será la correspondiente a los audios sintéticos (`ground_truth = 1`).

Cada audio debe producir una única predicción fusionada, que se comparará con su etiqueta verdadera.

**El grupo ganador será aquel que obtenga el mayor F1 en el conjunto de validación interna.**

## 5. Resultados de aprendizaje

**RA 6.1.** Diseña y ejecuta experimentos computacionales sobre datos estructurados, series de tiempo y señales de voz, comparando distintas estrategias de análisis, preprocesamiento, ingeniería de características o modelado, interpretando los resultados mediante métricas apropiadas y proponiendo mejoras a partir de la evidencia obtenida.

**RA 7.1.** Investiga, selecciona e incorpora de manera autónoma una técnica, herramienta o estrategia relacionada con Ciencia de Datos que no haya sido desarrollada explícitamente en clase, justificando su integración dentro de la solución de un problema basado en datos estructurados, series de tiempo o señales de voz mediante Python.

## 6. Rúbrica de evaluación

### Criterio 1. Desempeño del método de fusión (RA 6.1)

**Peso: 65 %**

| Nota | Descripción |
|---|---|
| **0.0** | No obtiene un F1, dado que el código presentado no permite realizar la fusión de modelos. |
| **3.0** | Obtiene un F1, aunque muy inferior al alcanzado por el mejor grupo de la clase. |
| **4.0** | Obtiene un F1 ligeramente inferior al alcanzado por el mejor grupo de la clase. |
| **5.0** | Obtiene un F1 y alcanza el mejor resultado entre los grupos de la clase. |

### Criterio 2. Selección y justificación del método de clasificación (RA 7.1)

**Peso: 35 %**

| Nota | Descripción |
|---|---|
| **0.0** | No justifica la selección ni el funcionamiento del método de clasificación basado en Machine Learning. |
| **3.0** | Justifica parcialmente la selección y el funcionamiento del método de clasificación basado en Machine Learning. |
| **5.0** | Justifica correctamente la selección y el funcionamiento del método de clasificación basado en Machine Learning. |

### Calificación definitiva

\[
\text{Nota final}=0.65C_1+0.35C_2
\]

Donde \(C_1\) y \(C_2\) son las calificaciones de los criterios 1 y 2, respectivamente.

## 7. Entregables

Cada grupo deberá presentar un archivo Jupyter Notebook (`.ipynb`) que contenga:

1. Lectura y organización del dataset.
2. Construcción de las cuatro variables de entrada por audio.
3. División de los datos en entrenamiento y validación interna.
4. Investigación y justificación del algoritmo de fusión seleccionado.
5. Implementación y entrenamiento del método de clasificación.
6. Obtención de las predicciones fusionadas.
7. Cálculo del F1 sobre el conjunto de validación interna.
8. Análisis e interpretación de los resultados obtenidos.

El código debe ser ejecutable y permitir reproducir los resultados presentados.

**Uso de Inteligencia Artificial:** se permite utilizar herramientas de IA como apoyo para la programación y la investigación. Sin embargo, la selección del método, las decisiones de diseño y la interpretación de los resultados son responsabilidad exclusiva de los estudiantes.

## 8. Duración

**Tiempo disponible: dos semanas a partir de la asignación del proyecto.**

El objetivo no es únicamente obtener un F1 elevado, sino demostrar la capacidad de investigar, seleccionar, implementar y justificar una solución de Ciencia de Datos basada en evidencia experimental.
