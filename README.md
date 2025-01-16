# Análisis Exploratorio y Regresión para Predicción de Costos Médicos

## Descripción del Proyecto

Este proyecto realiza un **análisis exploratorio de datos (EDA)** y utiliza diferentes técnicas de **regresión** para predecir el costo médico de los pacientes, con base en un conjunto de datos que incluye información como edad, sexo, índice de masa corporal (BMI), número de hijos, región y si el paciente es fumador. 

El análisis y la predicción están inspirados en el trabajo realizado en [este notebook de Kaggle](https://www.kaggle.com/code/hely333/eda-regression/notebook).

---

## Objetivos Principales

1. **Explorar los datos para identificar patrones y relaciones clave entre las variables.**
2. **Implementar modelos de regresión** para predecir los costos médicos.
3. **Evaluar el desempeño de los modelos** mediante métricas como MSE y R².

---

## Análisis Exploratorio de Datos (EDA)

Se realizaron los siguientes pasos para explorar los datos:

- **Transformación de datos categóricos**: Se aplicó codificación (`LabelEncoder`) a variables como `sex`, `smoker` y `region`.
- **Análisis de correlación**:
  - Las variables más correlacionadas con los costos (`charges`) son:
    - `smoker` (fumador): Mayor impacto en los costos.
    - `bmi` (índice de masa corporal).
    - `age` (edad).
  - Se generó un mapa de calor para visualizar estas relaciones.
- **Distribución de costos**:
  - Los fumadores tienen costos médicos significativamente más altos que los no fumadores.
  - Los pacientes con un BMI mayor a 30 (sobrepeso/obesidad) también presentan costos más elevados.
- **Relaciones específicas**:
  - Se analizaron distribuciones y relaciones entre variables como `age`, `bmi`, `children` y `charges` mediante gráficos de dispersión, histogramas y diagramas de caja.

---

## Modelos de Regresión

Se implementaron tres enfoques para predecir los costos médicos:

1. **Regresión Lineal Simple**:
   - Modelo básico para evaluar las relaciones lineales entre las variables independientes y el costo (`charges`).
   - **Desempeño**:
     - \( R^2 \): Resultado moderado, mostrando que las relaciones lineales explican parcialmente los costos.

2. **Regresión Polinomial**:
   - Se agregó un término cuadrático (grado 2) para capturar relaciones no lineales.
   - **Desempeño**:
     - \( R^2 \) mejorado en comparación con la regresión lineal simple.

3. **Regresión con Bosques Aleatorios**:
   - Modelo basado en árboles de decisión para capturar relaciones complejas entre las variables.
   - **Desempeño**:
     - Error cuadrático medio (MSE) bajo y \( R^2 \) alto, demostrando que este modelo tiene el mejor ajuste para los datos.

---

## Insights Clave

1. **Impacto de ser fumador**:
   - Ser fumador es el factor más determinante en los costos médicos. Esto se refleja en distribuciones significativamente diferentes para fumadores y no fumadores.
2. **Relación con el BMI**:
   - Un BMI alto incrementa los costos, especialmente en fumadores.
3. **Edad y costos**:
   - Los costos aumentan progresivamente con la edad, reflejando el incremento en necesidades médicas.
4. **Familia y costos**:
   - Aunque el número de hijos tiene menor impacto, sigue siendo un factor relevante.

---

## Evaluación del Modelo
<!-- 

| Modelo                    | MSE (entrenamiento) | MSE (prueba) | \( R^2 \) (entrenamiento) | \( R^2 \) (prueba) |
|---------------------------|---------------------|--------------|---------------------------|--------------------|
| Regresión Lineal Simple   | -                   | -            | -                         | -                  |
| Regresión Polinomial      | -                   | -            | -                         | -                  |
| Bosques Aleatorios        | **Bajo**            | **Bajo**     | **Alto**                  | **Alto**           | -->

- El modelo de **bosques aleatorios** tuvo el mejor desempeño, capturando relaciones no lineales y complejas en los datos.

---

## Cómo Ejecutar el Proyecto

1. Clonar el repositorio y asegurarse de tener los datos en el directorio especificado (`data/kaggle/insurance.csv`).
2. Instalar las dependencias:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn bokeh


## Contribuciones
	•	Basado en el trabajo de hely333 en Kaggle.# medical-cost-eda-regression
