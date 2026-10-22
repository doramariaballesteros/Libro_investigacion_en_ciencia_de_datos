
# Capítulo 5: Reverse — Recuperación de Señales de Audio Secretas

📖 `Libro: Investigación en Ciencia de Datos`

**Autor: Dora María Ballesteros Larrotta**  
Universidad Militar Nueva Granada (UMNG)

---

## Material complementario del libro

Este notebook acompaña el **Capítulo 5** y presenta un ejemplo de recuperación de señales de audio secretas mediante el proceso **Reverse**, utilizando una señal de audio objetivo (*target*) y las claves generadas previamente mediante **Imitation**.

El procedimiento permite recuperar cinco señales secretas a partir de `audio.wav` y sus correspondientes claves (`key1.csv` hasta `key5.csv`), sin utilizar las señales de audio imitadas (`imitated.wav`).

---

## 🎧 Actividad exploratoria. Recuperación de señales secretas

### 🎯 Propósito

Explorar el funcionamiento del proceso **Reverse**, observando cómo una misma señal de audio, combinada con diferentes claves, permite recuperar distintos mensajes secretos.

### 📂 Archivos suministrados

- 🎵 **audio.wav:** señal de audio objetivo (*target*).
- 🔑 **key1.csv, key2.csv, key3.csv, key4.csv y key5.csv:** claves generadas mediante Imitation.
- 💻 **Código Reverse:** implementación en Python del proceso de recuperación.

### 🧪 Procedimiento

1. Ejecuta el código Reverse utilizando `audio.wav` y cada una de las cinco claves, de manera independiente.
2. Recupera las cinco señales de audio secretas.
3. Reproduce y escucha cada una de las señales recuperadas.
4. Observa cómo una misma señal de audio permite recuperar diferentes mensajes dependiendo de la clave utilizada.

**📌 Nota:** Esta actividad es exclusivamente exploratoria y no hace parte de la evaluación de la asignatura.

