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

# 🔎 E0 – Comprensión de los datos

Investiga el significado de los códigos de moneda presentes en el dataset:

`AUD`, `BRL`, `CAD`, `CLP`, `COP`, `COU`, `EUR`, `GBP`, `JPY`, `MXN`, `MXV` y `USD`.

Construye una tabla que incluya:

| Código | Moneda / Unidad | País o referencia |
|---|---|---|
| AUD | | |
| BRL | | |
| ... | | |
| USD | | |

A partir de esta información, clasifica las posiciones del portafolio en dos grupos:

- **Nacional**
- **Internacional**

Justifica el criterio utilizado para realizar esta clasificación.

---

# 🧹 E1 – Preparación de los datos

Construye un `DataFrame` con la información suministrada.

Realiza las transformaciones necesarias para que los valores monetarios puedan utilizarse como variables numéricas en Python.

Verifica:

- Tipos de datos.
- Valores faltantes.
- Valores duplicados.
- Consistencia de los valores.

Calcula nuevamente para cada moneda:

$$
\text{Diferencia}
=
\text{Valor}_{31/07/2026}
-
\text{Valor}_{31/03/2026}
$$

y su variación porcentual:

$$
\text{Variación}(\%)
=
\frac{
\text{Valor}_{31/07/2026}
-
\text{Valor}_{31/03/2026}
}{
\text{Valor}_{31/03/2026}
}
\times 100
$$

Compara los resultados obtenidos con los valores suministrados en la tabla original.

---

# 📊 E2 – Análisis del portafolio

Calcula el **valor total del portafolio** para cada una de las dos fechas.

Determina:

- Cambio absoluto del portafolio.
- Cambio porcentual del portafolio.
- Valor de las inversiones nacionales en cada fecha.
- Valor de las inversiones internacionales en cada fecha.
- Variación porcentual de cada uno de estos dos componentes.

Calcula además la participación de la inversión nacional e internacional dentro del portafolio:

$$
\text{Participación}(\%)
=
\frac{\text{Valor del componente}}
{\text{Valor total del portafolio}}
\times 100
$$

Compara cómo cambia la composición del portafolio entre marzo y julio de 2026.

---

# 📈 E3 – ¿Qué explica el cambio del portafolio?

Analiza la contribución de cada moneda al cambio total del portafolio.

Para cada posición calcula:

$$
\text{Contribución}_i(\%)
=
\frac{\text{Diferencia}_i}
{\text{Valor total}_{31/03/2026}}
\times 100
$$

Ordena las monedas de acuerdo con su contribución e identifica cuáles tuvieron el mayor impacto positivo y negativo sobre el portafolio.

Construye al menos **dos visualizaciones** que permitan explicar los resultados.

Una de ellas deberá ser un **gráfico de cascada (*waterfall*)** que muestre:

**Valor inicial del portafolio → contribución de cada moneda → valor final del portafolio**

Selecciona una segunda visualización que consideres apropiada para mostrar el cambio en la composición nacional e internacional del portafolio.

---

# 🧠 E4 – Interpretación de resultados

A partir del análisis realizado, responde:

1. **¿Qué explica el cambio en el valor total del portafolio entre marzo y julio de 2026?** Identifica los componentes que tuvieron mayor influencia en el resultado.

2. **¿Por qué una moneda con una variación porcentual alta no necesariamente produce un impacto importante sobre el portafolio total?** Utiliza los resultados obtenidos para justificar tu respuesta.

3. **¿Cómo cambió la composición del portafolio entre inversión nacional e internacional y qué efecto tuvo este cambio sobre el resultado global?**

Finalmente, redacta una **conclusión general basada en los datos** que sintetice qué ocurrió con el portafolio durante el periodo analizado.

---

# 📓 Entregable

Entrega un **Notebook desarrollado en Python** que documente de manera organizada y reproducible el desarrollo completo del reto.

El Notebook deberá incluir:

- Preparación y validación de los datos.
- Cálculos realizados.
- Tablas de resultados.
- Visualizaciones.
- Desarrollo de los experimentos E0–E4.
- Interpretación de los resultados.
- Conclusión general.
