# 📊 Análisis Exploratorio de Datos (EDA) - Challenge Alura Store LATAM

## Introducción al Proyecto

Este repositorio contiene un Análisis Exploratorio de Datos (EDA) realizado sobre un conjunto de datos simulado de ventas de la **Alura Store LATAM**, distribuido en cuatro tiendas diferentes. El objetivo principal es identificar patrones de rendimiento, satisfacción del cliente y eficiencia logística para proponer estrategias de mejora basadas en evidencia.

---

## 🛠 Herramientas y Librerías Utilizadas

El análisis se desarrolló íntegramente en un entorno de **Jupyter Notebook** utilizando las siguientes bibliotecas clave de Python para la manipulación y visualización de datos:

### 1. Pandas (`pandas`) 🐼

**Propósito:** Es la herramienta fundamental para la manipulación y limpieza de datos estructurados (DataFrames).
**Uso Detallado:**
* **Carga y Concatenación de Datos:** Se utilizó `pd.read_csv()` para cargar los cuatro archivos de datos de las tiendas (`tienda_1.csv` a `tienda_4.csv`) directamente desde URLs de GitHub. Posteriormente, la función clave **`pd.concat()`** fue esencial para unificar las cuatro fuentes de datos en un único DataFrame (`listas`), permitiendo el análisis global de la operación.
* **Limpieza y Preprocesamiento:**
    * Corrección de `KeyError`: Se identificó y resolvió un error de clave (espacios invisibles o tildes) en los nombres de columna, un paso crucial en la limpieza.
    * Creación de `Tienda_ID`: Se añadió una columna identificadora (`Tienda_ID`) a cada DataFrame antes de la concatenación para permitir el **análisis comparativo por tienda**.
    * Conversión de Tipos: Se utilizó **`pd.to_datetime()`** y `.dt.to_period('M')` para convertir la columna `Fecha de Compra` en un formato de fecha usable para el análisis de tendencias temporales.
* **Agregación de Datos:** Se empleó la función **`.groupby()`** combinada con `.sum()` y `.mean()` para resumir métricas clave como la facturación por categoría, el promedio de calificación y el costo de envío promedio por tienda.

### 2. Matplotlib (`matplotlib.pyplot`) 📊

**Propósito:** Biblioteca base para la creación de gráficos estáticos y personalización avanzada.
**Uso Detallado:**
* **Control del Gráfico:** Se usó para definir el tamaño de las figuras (`plt.figure(figsize=...)`), añadir títulos (`plt.title()`, `plt.xlabel()`), ajustar ejes (`plt.ylim()`) y mostrar el resultado (`plt.show()`).
* **Anotaciones:** Se utilizó `plt.text()` para añadir los valores numéricos exactos sobre las barras de los gráficos, mejorando la legibilidad.

### 3. Seaborn (`seaborn`) 🎨

**Propósito:** Biblioteca de alto nivel que simplifica la creación de visualizaciones estadísticas más atractivas y complejas.
**Uso Detallado:**
* **Gráfico de Barras (`sns.barplot`):** Ideal para comparar métricas discretas como la calificación o el costo de envío entre las cuatro tiendas, así como para visualizar el Top y Bottom 10 de productos vendidos.
* **Gráfico Circular (`plt.pie`):** Se utilizó para mostrar la distribución porcentual de la Facturación Total por Categoría.
* **Gráfico de Dispersión (`sns.scatterplot`):** Se empleó para analizar la **tendencia de desempeño** (Costo de Envío Promedio Mensual), diferenciando cada tienda por color (`hue`) y forma (`style`) para evaluar la variabilidad logística en el tiempo.

---

## 📈 Análisis Realizados y Visualizaciones Clave

1.  **Facturación por Categoría:** Cálculo de la suma total de la columna `Precio` agrupada por `Categoría del Producto` para identificar las categorías de mayor y menor rendimiento.
2.  **Rendimiento Logístico y Satisfacción (por Tienda):**
    * **Calificación Promedio por Tienda:** Cálculo de la media de la columna `Calificación` agrupada por `Tienda_ID`.
    * **Costo de Envío Promedio por Tienda:** Cálculo de la media de la columna `Costo de envío` agrupada por `Tienda_ID`.
3.  **Productos Más y Menos Vendidos:** Uso de **`.value_counts().head(10)`** y **`.tail(10)`** sobre la columna `Producto` para identificar el Top 10 y el Bottom 10 de artículos vendidos por frecuencia de transacción.
4.  **Tendencia Temporal del Desempeño Logístico:** Visualización del **Costo de Envío Promedio Mensual** de cada tienda mediante un gráfico de dispersión, crucial para identificar si los costos logísticos están bajo control o si están aumentando con el tiempo.

---

## 📚 Bibliografía y Fuentes

El análisis se basa en datos y recursos proporcionados por el ecosistema de Alura Latam, complementados con la documentación oficial de las bibliotecas de Python.

| Elemento | Descripción | Enlace / Referencia |
| :--- | :--- | :--- |
| **Fuente de Datos** | Datos de ventas simulados para el Challenge Data Science Latam. | Repositorio de datos proporcionado por Alura Latam. |
| **Documentación Pandas** | Referencia principal para funciones como `groupby`, `concat`, `read_csv`, `to_datetime`, y métodos de limpieza de datos. | [https://pandas.pydata.org/docs/](https://pandas.pydata.org/docs/) |
| **Documentación Seaborn** | Referencia para la creación de gráficos de barras y dispersión. | [https://seaborn.pydata.org/](https://seaborn.pydata.org/) |
| **Lenguaje de Programación** | Python 3 | [https://www.python.org/](https://www.python.org/) |