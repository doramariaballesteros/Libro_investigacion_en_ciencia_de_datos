# 📚 Guía del Laboratorio (quiz1)
## Análisis de un artículo científico

### 🎯 Objetivo

Analizar críticamente un artículo científico desde la perspectiva de un científico de datos, identificando las decisiones relacionadas con los datos, el modelado, la evaluación y la selección del modelo final.

---

### 📄 Artículo

**Chavarro, A. F., Renza, D., & Ballesteros, D. M. (2023).**  
*Influence of Hyperparameters in Deep Learning Models for Coffee Rust Detection.*  
Applied Sciences, 13(7), 4565.  
https://doi.org/10.3390/app13074565

---

### 👥 Modalidad

**Trabajo en parejas**

### ⏱️ Tiempo

**2 horas**

### 📤 Entregable

Un único documento en formato **PDF** con las respuestas argumentadas.

---

# Actividad

## 1. Datos

**1.** ¿Cuál es el problema de clasificación abordado en el artículo y cuáles son las clases utilizadas?

**2.** ¿Por qué los autores construyeron un nuevo conjunto de datos a partir de cinco bases de datos diferentes? Mencione al menos dos ventajas de esta decisión.

**3.** Describa dos tareas de preprocesamiento realizadas antes del entrenamiento y explique por qué eran necesarias.

---

## 2. Modelos

**4.** ¿Qué cinco hiperparámetros fueron evaluados durante la investigación?

**5.** Ordénelos desde el de mayor impacto hasta el de menor impacto sobre el desempeño de los modelos.

**6.** ¿Cuántos modelos fueron entrenados y cuál fue el propósito de realizar un experimentación tan ampli?

---

## 3. Evaluación

**7.** Explique brevemente qué mide cada una de las siguientes métricas:

- Accuracy
- Precision
- Recall
- F1-score

**8.** A partir de la Tabla 5:

- ¿Cuál fue el modelo con mejor desempeño?
- ¿Qué diferencias observa entre Accuracy y F1-score en los mejores modelos?

**9.** Los autores afirman que los mejores modelos no presentan un sesgo importante hacia alguna de las clases. ¿Qué evidencia utilizan para sustentar esta afirmación?

**10.** Imagine que usted es el líder del proyecto y debe seleccionar un único modelo para implementar en producción. Justifique su decisión utilizando las Tablas 5 y 6, considerando simultáneamente:

- desempeño,
- costo computacional,
- tiempo de entrenamiento,
- tamaño del modelo.

No existe una única respuesta correcta; se evaluará la calidad de la argumentación.

---

# 📊 Rúbrica

| Nivel | Descripción | Calificación |
|:------|:------------|:------------:|
| 🟢 **Sobresaliente** | Analiza correctamente el artículo, interpreta los resultados experimentales y sustenta sus respuestas con evidencia técnica. Argumenta adecuadamente la selección del modelo. | **4.4 – 5.0** |
| 🟡 **Competente** | Comprende la metodología y los principales resultados, aunque algunas respuestas presentan justificaciones parciales o poco profundas. | **3.4 – 4.3** |
| 🔴 **En desarrollo** | Presenta dificultades para interpretar los datos, los modelos o las métricas. Las respuestas son principalmente descriptivas y con escasa argumentación técnica. | **2.5 – 3.3** |

---

> **Reflexión:** En Ciencia de Datos no basta con obtener el modelo con mayor desempeño; es igualmente importante comprender cómo fueron preparados los datos, cómo se diseñó el experimento y por qué un modelo resulta más adecuado que otro para un escenario de aplicación determinado.
