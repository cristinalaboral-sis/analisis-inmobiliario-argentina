# Análisis Exploratorio del Mercado Inmobiliario Argentino

## Propósito

El objetivo de este proyecto es realizar un análisis exploratorio de datos (EDA) sobre un conjunto de publicaciones inmobiliarias de Argentina, con el propósito de estudiar la distribución de precios, superficies y características de las propiedades.

A través de Python y sus principales bibliotecas de análisis de datos, se busca identificar patrones, relaciones, valores faltantes, posibles inconsistencias y valores atípicos que permitan comprender mejor la información disponible.

El análisis incluye técnicas de estadística descriptiva, evaluación de distribuciones y visualización de datos, con el fin de obtener información relevante sobre el mercado inmobiliario y documentar los criterios aplicados durante el procesamiento.

## Tecnologías y Herramientas Utilizadas

- **Python:** lenguaje utilizado para el procesamiento y análisis de los datos.
- **Pandas:** lectura, selección, limpieza y manipulación del conjunto de datos.
- **NumPy:** operaciones numéricas y tratamiento de valores inválidos.
- **Matplotlib:** construcción y personalización de gráficos.
- **Seaborn:** visualización estadística mediante distintos tipos de gráficos.
- **Jupyter Notebook:** entorno interactivo utilizado para desarrollar y documentar el análisis.

## Descripción del Análisis

El proyecto se organiza en las siguientes etapas:

### 1. Carga y exploración inicial

Se utiliza Pandas para leer el archivo `venta.csv`, que contiene publicaciones de propiedades inmobiliarias.

El conjunto de datos original cuenta con:

- **Registros:** 519.792.
- **Variables:** 35.

Se realiza una revisión inicial de las dimensiones, los tipos de datos, los primeros registros y la estructura general del conjunto de datos.

### 2. Selección de variables

Para el análisis se seleccionan 26 variables relacionadas con:

- Identificación de las publicaciones.
- Precios en dólares y pesos.
- Cantidad de ambientes y antigüedad.
- Superficie total y cubierta.
- Ubicación geográfica y barrio.
- Características y servicios de las propiedades.
- Fecha y mes de publicación.

Se genera un conjunto de trabajo independiente del dataset original para conservar los datos de origen.

### 3. Análisis exploratorio de datos (EDA)

Se analizan las principales variables para identificar patrones, distribuciones e inconsistencias.

Las operaciones incluyen:

- Análisis de precios y monedas.
- Comparación de variables de precios.
- Evaluación de la relación entre precios expresados en pesos y dólares.
- Análisis de superficies totales y cubiertas.
- Identificación de superficies iguales a cero y valores extremos.
- Revisión de características de las propiedades.
- Análisis de antigüedad y cantidad de ambientes.
- Identificación de posibles valores inconsistentes.

### 4. Limpieza y tratamiento de datos

Se aplican criterios de limpieza sobre las variables de antigüedad y ambientes.

Las operaciones incluyen:

- Tratamiento de valores negativos en antigüedad.
- Identificación de posibles años de construcción registrados incorrectamente como antigüedad.
- Tratamiento de antigüedades superiores a 100 años.
- Reemplazo de valores iguales a cero en cantidad de ambientes.
- Tratamiento de cantidades de ambientes superiores a 50.

Los valores identificados como inválidos o poco confiables se reemplazan por valores faltantes (`NaN`), sin eliminar automáticamente los registros completos.

### 5. Medidas resumen y análisis de distribución

Se calculan medidas estadísticas para las principales variables numéricas:

- Precio en dólares.
- Cantidad de ambientes.
- Antigüedad.
- Superficie total.
- Superficie cubierta.

También se calculan la asimetría (skewness) y la curtosis (kurtosis) para evaluar la forma y el comportamiento de las distribuciones.

### 6. Detección y clasificación de valores atípicos

Se utiliza el método del rango intercuartílico (IQR) para identificar valores atípicos en las principales variables numéricas.

El procedimiento contempla:

- Cálculo del primer y tercer cuartil.
- Obtención del rango intercuartílico.
- Determinación de los límites inferior y superior.
- Identificación y cuantificación de valores atípicos.
- Clasificación de los registros como habituales, outliers o sin datos.

Los valores atípicos identificados se conservan para su posterior interpretación y no se eliminan automáticamente.

## Visualizaciones

Se utilizan distintos tipos de gráficos para complementar el análisis estadístico:

- **Boxplot:** permite observar la distribución de las variables numéricas y detectar valores extremos.
- **Barplot:** permite identificar los barrios con mayor cantidad de publicaciones.
- **Violin Plot:** permite comparar la distribución de precios según la cantidad de ambientes.

Se utiliza una paleta de colores consistente para facilitar la lectura y mantener la identidad visual del análisis.

## Decisiones sobre Inconsistencias en Superficies

Durante el análisis se identificaron publicaciones cuya superficie cubierta supera la superficie total, superficies iguales a cero y valores considerablemente superiores a los habituales.

Como no es posible determinar con certeza cuáles son los valores correctos, se decidió conservar estos registros sin modificarlos ni eliminarlos automáticamente.

Estas observaciones se consideran al interpretar los resultados y la detección de valores atípicos.

## Resultados del Análisis

El análisis permitió:

- Identificar valores faltantes en las variables seleccionadas.
- Reconocer posibles inconsistencias en superficies, antigüedad y cantidad de ambientes.
- Aplicar criterios de limpieza sobre los valores de antigüedad y ambientes.
- Evaluar la distribución de las principales variables numéricas mediante medidas estadísticas.
- Detectar y clasificar valores atípicos utilizando el método IQR.
- Representar gráficamente las principales características del conjunto de datos.

## Estructura del Repositorio

- `data/`: contiene el archivo original `venta.csv`.
- `notebooks/`: contiene el notebook Jupyter con el análisis exploratorio y las visualizaciones.
- `requirements.txt`: contiene las bibliotecas necesarias para ejecutar el proyecto.
- `.gitignore`: permite excluir archivos temporales, entornos virtuales y otros elementos que no deben incluirse en el repositorio.
- `README.md`: documentación general del proyecto.

## Dataset

El conjunto de datos utilizado en este proyecto corresponde a publicaciones de propiedades en venta en la Ciudad Autónoma de Buenos Aires (CABA).

**Fuente:** [Dataset de mercado inmobiliario en CABA. Venta y alquiler – Zenodo](https://zenodo.org/records/13826379)

**Autor:** Sergio Rosanovich – Universidad Nacional de San Martín.

Para ejecutar el proyecto:

1. Descargar el archivo `venta.csv` desde Zenodo.
2. Colocarlo dentro de la carpeta `data/`.
3. Ejecutar el notebook siguiendo los pasos indicados a continuación.
## Requisitos

- Python 3.10 o superior.
- Pandas.
- NumPy.
- Matplotlib.
- Seaborn.
- Jupyter Notebook.

## Pasos para Ejecutar

1. Clonar el repositorio desde GitHub.
2. Ubicar el archivo `venta.csv` dentro de la carpeta `data/`.
3. Instalar las dependencias:

   `python -m pip install -r requirements.txt`

4. Abrir el proyecto en Visual Studio Code.
5. Abrir el notebook `analisis_inmobiliario_ordenado.ipynb`.
6. Seleccionar un entorno de Python con las dependencias instaladas.
7. Ejecutar las celdas del notebook en orden.

## Autor

Proyecto académico de análisis exploratorio de datos aplicado al mercado inmobiliario argentino, utilizando Python y herramientas de análisis y visualización de datos.