# Análisis Estadístico y Exploratorio de Datos (EDA) - Impacto del COVID-19

Este repositorio contiene el análisis exploratorio y la validación estadística de un conjunto de datos sobre la evolución de la pandemia de COVID-19. El objetivo principal del proyecto fue analizar la relación entre el incremento diario de casos positivos y el incremento de muertes, así como evaluar los cambios de comportamiento de la pandemia a través del tiempo.

---

## 👥 Autores
* Elena Suárez Serrano
* Rita Romero
* Daniel Luque Gallardo

---

## 🛠️ Tecnologías Usadas
* **Pandas** (Estructuración y manipulación de series de datos)
* **Statsmodels** (Regresión OLS y diagnósticos)
* **Scipy.stats** (Pruebas de Levene, Shapiro-Wilk, T-Test y Mann-Whitney U)
* **Matplotlib & Seaborn** (Visualización de datos avanzada)
* **missingno** (Visualización de valores nulos)
* **sklearn.impute** (Imputación de valores nulos)

---

## 🎯 Objetivo del proyecto
El objetivo principal del proyecto es realizar un EDA (Exploration Data Analysis) del dataset de `The COVID Tracking Project National Data`. En el hemos :
1. **Carga y Vsisualización rápidad de los datos:** Obtener los datos provenientes del dataset y realizar un análisis rápido de la composición del dataset.
2. **Conversiones Necesarias:** Realizar las conversiones necesarias para conseguir tener un dataset con el formato de las variables deseado.
3. **Dsitribuciones:** Comprender como son nuestros datos y poder identificar patrones, tendencias, valores outliers de forma visual.
4. **Correlaciones y ScatterPlot:** Indentificar como de correlacionadas están nuestras variables del dataset.
5. **Detección y Tratamiento de Valores Outliers y Nulos :** Indentificar y tratar de valores outliers y nulos.
6. **Correlaciones y ScatterPlot:** Indentificar como de correlacionadas están nuestras variables del dataset.
7. **Feature Engineering:** Creación de variables derivadas de las variables ya presentes en el dataset.
8. **Regresión Lineal y Test estadísticos:** Visualización de las correlaciones entre dos variables mediante la regresión y uso de pruebas estadísticas para comprobar la normalidad de los datos y correlaciones.
8. **Gráficas Interesantes:** Creación de diferentes gráficas para visualizar patrones, tendencias y evidencias durante la pandemia.


---

## 📋 Decisiones Tomadas

### 1. Tratamiento de valores nulos y outliers
* **Decisión:** Los valores outliers no se trataron y los valores nulos hemos usado el `SimpleImputer` para las variables `death', `negative`. Para el nulo de `positive` se ha eliminaod el registro y para el resto se ha imputado con 0.


### 2. Modelado Inicial: Regresión Lineal OLS
* **Decisión:** Se entrenó un modelo de Mínimos Cuadrados Ordinarios (OLS) para predecir `hospitalizedIncrease` ~ `positiveIncrease`,  `deathIncrease` ~ `positiveIncrease` y `positiveIncrease` ~ `totalTestResultsIncrease`.

### 3. Prueba de Hipótesis
* **Decisión:** Ver si los incrementos diarios siguen uan distribución normal.


*
El análisis demuestra que existe una correlación de muertes y incrementos de contagios, pero al ser datos temporales en los que la variable `tiempo` esta vinculada directamente necesitamos de un modelo más complejo para poder realizar una inferencia correcta y obtener conclusiones cientificamente más validadas.
*