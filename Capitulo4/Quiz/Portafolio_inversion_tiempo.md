# 💰 Reto de Ciencia de Datos – ¿Qué pasó con el portafolio?

## 📌 Contexto

Se dispone de información sobre el valor de un portafolio de inversiones expresado en pesos colombianos (COP) para dos fechas:

- **31/03/2026**
- **31/07/2026**

El portafolio contiene inversiones registradas en diferentes monedas:

`AUD`, `BRL`, `CAD`, `CLP`, `COP`, `COU`, `EUR`, `GBP`, `JPY`, `MXN`, `MXV` y `USD`.

A primera vista, la tabla permite observar cuáles posiciones aumentaron o disminuyeron. Sin embargo, analizar únicamente la variación porcentual de cada moneda puede conducir a conclusiones incompletas, ya que cada posición tiene un peso diferente dentro del portafolio.

El objetivo del reto será utilizar **Python y técnicas de análisis de datos** para descubrir qué ocurrió con el portafolio entre las dos fechas y cuáles componentes explican principalmente su variación.

---

# 📂 Datos del portafolio

La siguiente tabla presenta el valor del portafolio, expresado en **pesos colombianos (COP)**, para cada moneda en dos fechas diferentes.

| Moneda original | 31/03/2026 | 31/07/2026 | Diferencia | Variación |
|---|---:|---:|---:|---:|
| AUD | 2.305.959.381 | 1.981.632.950 | -324.326.432 | -14,1 % |
| BRL | 1.586.894.701.090 | 1.862.288.677.034 | 275.393.975.944 | 17,4 % |
| CAD | 7.365.033.354 | 6.282.031.659 | -1.083.001.695 | -14,7 % |
| CLP | 6.408.113.225 | 6.197.693.757 | -210.419.468 | -3,3 % |
| COP | 200.824.503.058.034 | 220.424.221.846.983 | 19.599.718.788.949 | 9,8 % |
| COU | 69.345.836.754.232 | 87.596.593.935.495 | 18.250.757.181.263 | 26,3 % |
| EUR | 14.051.157.737.441 | 11.467.106.071.043 | -2.584.051.666.398 | -18,4 % |
| GBP | 5.127.546.284.243 | 5.061.357.629.687 | -66.188.654.555 | -1,3 % |
| JPY | 1.997.011.828.563 | 1.895.846.846.426 | -101.164.982.137 | -5,1 % |
| MXN | 231.856.075.346 | 172.154.197.663 | -59.701.877.683 | -25,7 % |
| MXV | 342.493.565 | 298.717.322 | -43.776.243 | -12,8 % |
| USD | 243.116.623.090.348 | 227.972.996.228.466 | -15.143.626.861.882 | -6,2 % |

> **Nota:** Los valores de las columnas `31/03/2026`, `31/07/2026` y `Diferencia` están expresados en pesos colombianos (COP).
---

# 🔎 E0 – Preparación de los datos

Investiga el significado de los códigos:

`AUD`, `BRL`, `CAD`, `CLP`, `COP`, `COU`, `EUR`, `GBP`, `JPY`, `MXN`, `MXV` y `USD`.

Construye un `DataFrame` con la información suministrada y agrega una nueva columna que clasifique cada posición como:

- **Nacional**
- **Internacional**

---

# 📊 E1 – Análisis del portafolio

Calcula el **valor total del portafolio** para cada fecha y determina:

- Cambio absoluto y porcentual del portafolio total.
- Valor de la inversión nacional e internacional en cada fecha.
- Variación porcentual de la inversión nacional e internacional.

Calcula además la participación de cada componente:

$$
\text{Participación}(\%) =
\frac{\text{Valor del componente}}
{\text{Valor total del portafolio}}
\times 100
$$

Construye una **visualización** que permita comparar la participación de la inversión nacional e internacional en las dos fechas.

---

# 🧠 E2 – Interpretación de resultados

A partir de los resultados obtenidos, responde:

1. **¿Cómo cambió el portafolio entre marzo y julio de 2026?** Analiza tanto su valor total como la participación de la inversión nacional e internacional.

2. **¿Qué componente explica principalmente el resultado global del portafolio: nacional o internacional?** Justifica tu respuesta utilizando los valores obtenidos.

Finalmente, redacta una **conclusión general basada en los datos** que sintetice qué ocurrió con el portafolio durante el periodo analizado..

---
# 💬 Entregable – Discusión en clase

Al finalizar la actividad, cada grupo participará en una **discusión de resultados en clase**.

Utilizando los cálculos y la visualización obtenida, el grupo deberá presentar brevemente:

- El cambio observado en el valor total del portafolio.
- El comportamiento de la inversión nacional e internacional.
- La principal conclusión que puede obtenerse a partir de los datos.

La discusión deberá estar **sustentada en los resultados obtenidos durante el análisis**.




