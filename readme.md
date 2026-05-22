# 📊 Análisis Estadístico y Exploratorio de Datos (EDA) - Impacto del COVID-19

Este repositorio contiene un análisis exploratorio de datos (EDA) y validación estadística sobre la evolución de la pandemia de COVID-19 en Estados Unidos. El objetivo principal es analizar la relación entre el incremento diario de casos positivos y el incremento de muertes, así como estudiar la evolución temporal de la pandemia y sus patrones estadísticos.

---

## 👥 Autores
- Elena Suárez Serrano  
- Rita Romero  
- Daniel Luque Gallardo  

---

## 📂 Dataset

El dataset utilizado se ha obtenido de:

https://covidtracking.com/data/download

Este proyecto trabaja con el archivo:

```
national_history.csv
```

---

## 📁 Estructura del proyecto

Para ejecutar correctamente el proyecto, la estructura debe ser la siguiente:

```
/data
    national_history.csv
/notebooks
    (notebook principal del análisis)
/report
    Reporte Covid-19.pdf
/.venv
requirements.txt
README.md
```

---

## ⚙️ Requisitos de ejecución

### 1. Crear entorno virtual
```bash
python -m venv .venv
```

### 2. Activar entorno virtual

**Windows:**
```bash
.venv\Scripts\activate
```

**Mac/Linux:**
```bash
source .venv/bin/activate
```

### 3. Instalar dependencias
```bash
pip install -r requirements.txt
```

### 4. Ejecutar el notebook
Abrir y ejecutar el notebook dentro del entorno virtual.

---

## 🛠️ Tecnologías usadas

- Pandas → Manipulación y análisis de datos  
- NumPy → Operaciones numéricas  
- Matplotlib & Seaborn → Visualización de datos  
- Statsmodels → Modelos de regresión OLS  
- SciPy.stats → Tests estadísticos (Shapiro, Levene, T-test, Mann-Whitney U)  
- missingno → Visualización de valores nulos  
- sklearn.impute → Imputación de valores faltantes  

---

## 🎯 Objetivo del proyecto

El objetivo principal es realizar un análisis exploratorio completo del dataset *The COVID Tracking Project National Data*, con el fin de comprender la evolución de la pandemia y la relación entre variables clave.

### Etapas del análisis:

1. Carga y exploración inicial de datos  
2. Transformación y limpieza del dataset  
3. Análisis de distribuciones y outliers  
4. Análisis de correlaciones y visualización  
5. Tratamiento de valores nulos  
6. Feature Engineering  
7. Modelado estadístico (regresión lineal OLS)  
8. Pruebas de hipótesis  
9. Visualización de patrones temporales  

---

## 📌 Decisiones tomadas

### 1. Tratamiento de valores nulos y outliers
Se decidió mantener los outliers para conservar la naturaleza real de la pandemia.  
Los valores nulos se trataron de la siguiente forma:
- `death` y `negative` → imputación con técnicas de relleno  
- `positive` → eliminación de registros nulos  
- resto de variables → imputación con 0 cuando fue necesario  

---

### 2. Modelado estadístico (OLS)
Se aplicaron modelos de regresión lineal para estudiar relaciones entre variables:

- `hospitalizedIncrease ~ positiveIncrease`  
- `deathIncrease ~ positiveIncrease`  
- `positiveIncrease ~ totalTestResultsIncrease`  

---

### 3. Pruebas de hipótesis
Se evaluó la normalidad de las variables mediante:
- Shapiro-Wilk  
- Levene  
- T-test  
- Mann-Whitney U  

---

### 4. Conclusión analítica
El análisis muestra una correlación clara entre el aumento de contagios y el incremento de muertes. Sin embargo, al tratarse de datos temporales dependientes del tiempo, un modelo lineal simple no es suficiente para capturar completamente la dinámica del fenómeno, siendo necesario un enfoque estadístico más avanzado para inferencias más robustas.

---

## 📄 Informe final

El informe completo se encuentra en:

```
/report/Reporte Covid-19.pdf
```