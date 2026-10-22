
# 🔐 Actividad experimental: Recuperación de mensajes secretos mediante DWT

## 🎯 Objetivo

Recuperar diferentes mensajes de voz a partir de una señal de audio común y cinco claves de permutación, utilizando el algoritmo **Reverse**, basado en la Transformada Discreta Wavelet (DWT).

---

## 🎵 Parte 1. Recuperación de mensajes secretos

### 📂 Archivos proporcionados

| Archivo | Descripción |
|---|---|
| `Reverse_GitHub.ipynb` | Código para recuperar los mensajes secretos. |
| `audio.wav` | Señal de audio utilizada como entrada común. |
| `key1.csv` a `key5.csv` | Cinco claves de permutación, cada una con **383.197 índices**. |

### ⚙️ Procedimiento

1. Abra el notebook `Reverse_GitHub.ipynb` en Google Colab.
2. Cargue el archivo `audio.wav` y las cinco claves (`key1.csv` a `key5.csv`) en el directorio `/content`.
3. Ejecute el código para recuperar los cinco mensajes secretos.
4. Reproduzca y escuche atentamente los archivos recuperados (`raudio1.wav` a `raudio5.wav`).

---

## 🔎 Parte 2. Análisis de los mensajes recuperados

A partir de la inspección de las claves y la escucha de los audios, responda:

**a)** ¿Existe alguna relación o similitud entre las cinco claves proporcionadas y los mensajes recuperados? Explique su respuesta.

**b)** ¿Qué similitudes y diferencias identifica entre los cinco mensajes recuperados? Considere características como el contenido, las voces y la calidad perceptual.

**c)** ¿El género de la voz de cada mensaje recuperado coincide con el género de la voz presente en `audio.wav`?

**d)** ¿El idioma de los mensajes recuperados coincide con el idioma de `audio.wav`?

**e)** Teniendo en cuenta que los cinco mensajes fueron recuperados utilizando un mismo archivo de audio, ¿qué papel considera que desempeñan las claves en el proceso de recuperación?

---

📌 **Importante:** En esta primera etapa no debe modificar las claves ni el código del algoritmo Reverse. Los resultados obtenidos serán utilizados como referencia para los experimentos posteriores.
