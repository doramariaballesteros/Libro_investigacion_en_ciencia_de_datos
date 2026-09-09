# Caso de Estudio 1: Clima

Este directorio contiene los notebooks utilizados en el **Caso de Estudio 1: Clima** del Capítulo 4 del libro *Investigación en Ciencia de Datos*.

> Dora María Ballesteros  
> Primera edición, 2026  
> ISBN: 978-1-957395-63-0

> 🔗 **[Consultar el libro en Editorial REDIPE](https://editorial.redipe.org/index.php/1/catalog/book/245)**

>💡 **Nota:** Los códigos disponibles en este repositorio han sido **actualizados y complementados** con respecto a los presentados en la primera edición del libro. Estas actualizaciones conservan la **esencia y propósito de los códigos originales**, incorporando ajustes orientados a mejorar su desarrollo, explicación y aplicación.

## Orden recomendado de ejecución

1. `Capitulo4_EDA_clima.ipynb`  
   Realiza el **Análisis Exploratorio de Datos (EDA)** aplicado a Series de Tiempo.

   **Dataset de entrada:**  
   `clima.csv`

   **Dataset generado:**  
   `clima_eda.csv`

2. `Capitulo4_FE_1_(rolling)_Clima.ipynb`  
   Aplica **Feature Engineering mediante Rolling** a partir de los patrones identificados durante el EDA y realiza el modelamiento con el nuevo dataset.

   **Dataset de entrada:**  
   `clima_eda.csv`

3. `Capitulo4_FE_2_(temporal+lag)_Clima.ipynb`  
   Genera **features temporales y Lags** a partir de los patrones identificados durante el EDA y realiza el modelamiento con el nuevo dataset.

   **Dataset de entrada:**  
   `clima_eda.csv`

   **Dataset de entrada:**  
   `clima_eda.csv`

4. `Capitulo4_FE_3_(junto)_Clima.ipynb`  
   Integra los mejores *features* obtenidos mediante **Rolling y Lags**, junto con **hora** y **día de la semana**, para entrenar y comparar nuevos modelos.

   **Dataset de entrada:**  
   `clima_eda.csv`

## Importante

Los notebooks deben ejecutarse respetando el orden indicado si se desea reproducir todo el proceso desde el dataset original.

El archivo `clima_eda.csv` corresponde al dataset resultante del proceso de preparación y EDA y se utiliza como punto de partida para los experimentos de Feature Engineering.
