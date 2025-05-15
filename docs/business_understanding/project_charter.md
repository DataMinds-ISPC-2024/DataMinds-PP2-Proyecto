# Project Charter - Entendimiento del Negocio

## Nombre del Proyecto

### ***Predicción y análisis de precios de viviendas en el mercado inmobiliario***

## Objetivo del Proyecto

### **Objetivo general**

Desarrollar un modelo predictivo que permita estimar de manera precisa el precio de venta de viviendas en base a diversas  características de las propiedades (tamaño, ubicación, calidad de construcción, entre otras), optimizando la precisión y la equidad del modelo para asegurar que las predicciones sean justas y no presenten sesgos e identificando factores clave que afectan el valor de las propiedades como las variables que tienen mayor influencia en la determinación del precio de las viviendas.

### **¿Por qué es importante?**

Este proyecto es crucial porque proporciona a los stakeholders (desarrolladores inmobiliarios, agentes de bienes raíces, compradores y vendedores de viviendas) herramientas basadas en datos para tomar decisiones más informadas y eficaces en el mercado inmobiliario. La capacidad de predecir con precisión el precio de una vivienda no solo optimiza las estrategias de inversión, sino que también mejora la transparencia y la equidad del mercado, evitando discriminaciones basadas en factores como ubicación, género o clase social, asegurando que el mercado de viviendas sea accesible para todos.

## Alcance del Proyecto

### Incluye:

- **Datos disponibles**: el dataset cuenta con cuatro archivos: train.csv (la base de datos); test.csv (para hacer pruebas); data_description.txt (descripción completa de cada columna); y sample_submission.csv (una presentación de referencia a partir de una regresión lineal sobre el año y mes de venta, los metros cuadrados del lote y el número de habitaciones).
dataset "House Prices: Advanced Regression Techniques"  que contiene una serie de variables que describen las características de diversas viviendas, así como el precio de venta de cada una. Estas variables incluyen:

   - **Características de la vivienda**: por ejemplo, el número de habitaciones, superficie habitable, tamaño del lote, calidad de la construcción, entre otros.
     
   - **Características geográficas y vecindario**: tales como, el tipo de vecindario y la proximidad a servicios o carreteras principales.
     
   - **Datos temporales**: como el año de construcción y de renovación de las viviendas.
     
   - **Otras características**: como la presencia de sótano, piscina, garaje, etc.

   El objetivo es analizar estas variables para construir modelos predictivos que estimen el precio de venta de las viviendas basándose en sus características.
- **Resultados esperados**:
   - **Modelo predictivo**: un modelo robusto y preciso para predecir el precio de venta de una vivienda basado en las características proporcionadas. Se evaluará el desempeño del modelo usando métricas como **RMSE (Root Mean Squared Error)** y **R² (Coeficiente de determinación)**.
   
   - **Identificación de factores clave**: un análisis de las variables que tienen mayor impacto en el precio de las viviendas, proporcionando una visión detallada de qué características son las más determinantes para la fijación de precios.
   
   - **Segmentación del mercado inmobiliario**: la segmentación de las viviendas en grupos según sus características y precios, lo cual podría ser útil para desarrolladores inmobiliarios y agentes de bienes raíces.
   
   - **Análisis de equidad**: evaluación de si el modelo es justo para diferentes grupos de usuarios, sin mostrar sesgos hacia ciertas variables como género, ubicación geográfica o clase social.
   
   - **Recomendaciones**: propuestas sobre cómo optimizar el valor de las viviendas mediante la modificación de ciertas características o la selección de ubicaciones que potencialmente incrementen su valor.
     
- **Criterios de éxito del proyecto:**
   - **Éxito en la precisión del modelo**: el modelo de predicción de precios debe lograr un bajo **RMSE** y un **R²** cercano a 1, demostrando una capacidad adecuada para predecir el precio de las viviendas.
     
   - **Identificación clara de factores clave**: Ee análisis debe identificar las características que tienen mayor influencia en el precio, proporcionando insights valiosos para los stakeholders.
     
   - **Equidad del modelo**: el modelo debe ser evaluado para asegurar que no esté sesgado contra ningún grupo demográfico o ubicación geográfica.
     
   - **Segmentación efectiva**: la segmentación del mercado debe ser clara y útil, permitiendo a los stakeholders identificar grupos con patrones de precio similares.
     
   - **Valor práctico y utilidad**: las recomendaciones sobre cómo mejorar el valor de una vivienda deben ser implementables y útiles para los desarrolladores y agentes inmobiliarios.

### Excluye:

- **Análisis de aspectos legales o regulatorios**: el proyecto no abordará ni examinará ninguna normativa legal relacionada con el mercado inmobiliario o las regulaciones locales que puedan afectar el precio de las viviendas.
  
- **Análisis de factores macroeconómicos**: el análisis no tomará en cuenta factores macroeconómicos más amplios como tasas de interés, inflación o cambios en la política económica que puedan influir en el mercado inmobiliario.
  
- **Desarrollo de nuevas características del dataset**: el proyecto no se enfocará en la creación de nuevas características (como la combinación de variables) que no estén presentes en el dataset original. El análisis se basa exclusivamente en las variables proporcionadas en el conjunto de datos.
  
- **Análisis fuera del conjunto de datos proporcionado**: el proyecto no incluye la integración de otros datasets externos (por ejemplo, datos de tendencias del mercado inmobiliario en otras ciudades o países).
  
- **Evaluación de estrategias comerciales o de marketing**: el proyecto no se centrará en la creación de estrategias comerciales o de marketing para la venta de viviendas basadas en los resultados del análisis, sino solo en la predicción y análisis de precios basados en datos históricos de las viviendas.

## Metodología

La metodología para llevar a cabo este proyecto se basa en una combinación de análisis exploratorio de datos, desarrollo de modelos predictivos, evaluación de la equidad, y segmentación del mercado inmobiliario. A continuación, se detalla el enfoque que se seguirá:

### **Análisis Exploratorio de Datos (EDA):**
   - **Objetivo**: comprender la distribución y las relaciones entre las variables del dataset.
   - **Actividades**:
     - Inspección y limpieza de los datos: manejo de valores faltantes, valores atípicos, y consistencia de los datos.
     - Visualización de las distribuciones de las variables principales (como el precio de la vivienda) y la correlación entre las características y el precio.
     - Identificación de patrones y tendencias en los datos, así como posibles transformaciones necesarias (e.g., escalado, codificación de variables categóricas).

### **Preprocesamiento de los datos:**
   - **Objetivo**: preparar los datos para el desarrollo del modelo predictivo.
   - **Actividades**:
     - Imputación de datos faltantes.
     - Transformación de variables categóricas (usando técnicas como **One-Hot Encoding** o **Label Encoding**).
     - Normalización o estandarización de variables numéricas para mejorar la convergencia de ciertos modelos (por ejemplo, regresión lineal o redes neuronales).
     - Creación de nuevas características si es necesario (por ejemplo, combinando variables existentes para extraer nuevas relaciones).

### **Selección de Modelos Predictivos:**
   - **Objetivo**: desarrollar un modelo que prediga el precio de las viviendas.
   - **Actividades**:
     - Probar varios algoritmos de modelado, tales como:
       - **Regresión Lineal**: basada en la suposición de relaciones lineales entre las variables.
       - **Árboles de Decisión y Random Forest**: para capturar interacciones no lineales entre las variables.
       - **XGBoost o LightGBM**: modelos basados en boosting, que han demostrado ser efectivos para este tipo de problemas.
       - **Redes Neuronales**: si se dispone de suficiente tiempo y capacidad computacional y datos, se pueden probar modelos más complejos como redes neuronales profundas.
     - Evaluar los modelos utilizando métricas como **RMSE (Root Mean Squared Error)** y **R² (Coeficiente de Determinación)**.

### **Evaluación de la Equidad:**
   - **Objetivo**: asegurar que el modelo no tenga sesgos en cuanto a género, ubicación, o cualquier otro factor relevante.
   - **Actividad**: evaluar si los resultados muestran diferencias significativas en el precio de las viviendas predicho para diferentes géneros, razas, o ubicaciones geográficas.

### **Segmentación del Mercado:**
   - **Objetivo**: agrupar las viviendas en segmentos según características comunes.
   - **Actividades**:
     - Usar técnicas de **clustering**, como **K-means** o **DBSCAN**, para segmentar el mercado inmobiliario en grupos basados en características similares.
     - Analizar cómo las características clave (tamaño, ubicación, calidad de construcción, etc.) afectan los precios dentro de cada segmento.

### **Optimización del Modelo:**
   - **Objetivo**: mejorar la precisión del modelo a través de técnicas de optimización.
   - **Actividades**:
     - Realizar **tuning de hiperparámetros** (ajustar parámetros del modelo como la profundidad de los árboles en Random Forest o el número de estimadores en XGBoost).
     - Usar técnicas como **Validación Cruzada** para asegurar que el modelo generalice bien a nuevos datos y evitar el sobreajuste.

### **Presentación de Resultados y Recomendaciones:**
   - **Objetivo**: presentar los hallazgos del proyecto de forma clara y accesible.
   - **Actividades**:
     - Visualización de los resultados clave: como las distribuciones de precios, la importancia de las características y la segmentación del mercado.
     - Proporcionar recomendaciones prácticas para optimizar las inversiones en bienes raíces, mejorar la precisión de las predicciones, y mitigar posibles sesgos.
---
## Cronograma

| Etapa | Duración Estimada | Fechas |
|------|---------|-------|
| Entendimiento del negocio y carga de datos | 1 semana | del 28 de abril al 02 de mayo |
| Preprocesamiento, análisis exploratorio | 1 semana | del 05 de mayo al 09 de mayo |
| Modelamiento y extracción de características | 2 semanas | del 12 de mayo al 23 de mayo |
| Despliegue | 2 semanas | del 26 de mayo al 06 de junio |
| Evaluación y entrega final | 2 semanas | del 09 de junio al 13 de junio |

##### Hay que tener en cuenta que estas fechas se irán ajustando de acuerdo avance del proyecto.
---
## Equipo del Proyecto

| Apellido | Nombre | Usuario de GitHub | Rol |
|:---------|:-------|:------------------|:----|
| Ayán | María Trinidad | https://github.com/triniayan | Project Manager |
| Giordano | Ariel Eduardo | https://github.com/GIORDIAR | Data Engineer |
| Herrera | Edgar Fabián | https://github.com/dgarherrera2023 | Data Scientist |
| Quiroga | Fernanda Micaela | https://github.com/Fernanda63 | Ethical Reviewer |
| Siccardi | Luis | https://github.com/luissiccardi | Data Scientist |
---
## Presupuesto

| Concepto | Detalle | Valor estimado (ARS) |
|----------|---------|---------------------:|
| Recursos Humanos | Análisis de datos, modelado, evaluación de equidad y documentación | 6.300.000 |
| Herramientas y servicios en la nube | Espacios de almacenamiento y procesamiento de datos | 330.000 |
| Comunicaciones y gestión | Herramientas de colaboración y reuniones virtuales | 90.000 |
| Costos administrativos | Insumos, presentaciones y documentación final | 75.000 |
| **Total Estimado** |  | **6.795.000** |


##### El presupuesto en Recursos Humanos fue obtenido del portal Talently Argentina. Este consiste en cinco sueldos mínimos por media jornada en el sector tecnológico.
---
## Stakeholders

| Stakeholder | Relación con el proyecto | Expectativas |
|:------------|:--------------------------|:-------------|
| Desarrolladores inmobiliarios | Uso del modelo para definir precios de venta y compra de propiedades | Precios realistas y rentabilidad en operaciones |
| Agentes de bienes raíces | Asistencia en tasaciones y estrategias de venta | Modelos confiables que reflejen el valor de mercado |
| Compradores de viviendas | Herramientas para evaluar propiedades y negociar precios justos | Predicciones confiables sin sesgos de ubicación o calidad |
| Vendedores de viviendas | Optimización del valor de venta de sus propiedades | Información clara sobre factores que aumentan el precio |
| Instituto Superior Politécnico Córdoba | Supervisión y evaluación del proyecto | Aplicación correcta de análisis de datos y metodologías de Machine Learning |
---
## Aprobaciones

| Nombre | Cargo | Rol | Firma | Fecha de Aprobación |
|:-------|:------|:----|:------|:--------------------|
|Tatiana Manzanelli | Coordinadora de la Tecnicatura en Ciencia de Datos e Inteligencia Artificial | Chief Data Officer (CDO) | ____________________ | ____ / ____ / 2025 |
| Carlos Ignacio Charletti | Profesor de la asignatura Práctica Profesionalizante II | Supervisor | ____________________ | ____ / ____ / 2025 |
| María Trinidad Ayán | Estudiante de la Tecnicatura de Ciencia de Datos e Inteligencia Artificial | Project Manager | ____________________ | ____ / ____ / 2025 |
---
