# Reporte de Datos - *Análisis Exploratorio de Datos (EDA)*

Este reporte presenta los resultados del análisis exploratorio de datos (EDA) sobre el dataset **"House Prices: Advanced Regression Techniques"**. Se exploran diversas características del dataset, incluida la calidad de los datos, las distribuciones de las variables y su relación con la variable objetivo.

## Resumen general de los datos

- **Número total de observaciones (filas)**: 1460 (para el conjunto de entrenamiento)
- **Número total de variables (columnas)**: 81 (incluyendo la variable objetivo `SalePrice`)
- **Tipos de variables**:
  - **Variables numéricas**: 38 variables numéricas (por ejemplo, `LotArea`, `GrLivArea`, `YearBuilt`, etc.)
  - **Variables categóricas**: 43 variables categóricas (por ejemplo, `MSSubClass`, `ExterCond`, `BsmtQual`, etc.)
  
#### **Variables con valores faltantes:**
- A continuación se muestra un resumen de las variables con valores faltantes:

| **Variable**       |
|--------------------|
| `LotFrontage`      |
| `Alley`            | 
| `BsmtQual`         | 
| `BsmtCond`         |
| `BsmtExposure`     |
| `BsmtFinType1`     |
| `BsmtFinType2`     |
| `FireplaceQu`      |
| `GarageType`       |
| `GarageFinish`     |
| `GarageQual`       |
| `GarageCond`       |
| `PoolQC`           |
| `Fence`            |
| `MiscFeature`      |

#### **Acciones tomadas para manejar valores faltantes**:
- **Imputación**: Las variables numéricas con valores faltantes, como `LotFrontage`, son imputadas utilizando la media o la mediana de la columna.
- **Eliminación de columnas**: Las columnas con más del 50% de valores faltantes (como `PoolQC`, `MiscFeature`, y `Alley`) son eliminadas sin perder demasiada información.
- **Imputación para variables categóricas**: Las variables categóricas con pocos valores faltantes, como `BsmtQual` y `GarageType`, son imputadas con el valor más frecuente (moda).

## Resumen de calidad de los datos

#### **Presencia de valores faltantes:**
- En total, el dataset tiene 15 columnas con valores faltantes. A continuación se muestra un resumen de las variables con valores faltantes (y su porcentaje):

| **Variable**       | **Porcentaje de valores faltantes** |
|--------------------|-------------------------------------|
| `LotFrontage`      | 17.74%                              |
| `Alley`            | 93.77%                              |
| `BsmtQual`         | 2.55%                               |
| `BsmtCond`         | 2.55%                               |
| `BsmtExposure`     | 2.52%                               |
| `BsmtFinType1`     | 2.52%                               |
| `BsmtFinType2`     | 2.52%                               |
| `FireplaceQu`      | 47.26%                              |
| `GarageType`       | 5.55%                               |
| `GarageFinish`     | 5.55%                               |
| `GarageQual`       | 5.55%                               |
| `GarageCond`       | 5.55%                               |
| `PoolQC`           | 99.54%                              |
| `Fence`            | 80.49%                              |
| `MiscFeature`      | 96.30%                              |


- **Valores extremos (outliers)**:  
  En el análisis inicial, se han identificado varios valores extremos en variables como `LotArea`, `GrLivArea`, y `SalePrice`. Estos valores son mucho más grandes que el resto de los datos y pueden distorsionar el modelo predictivo.  
  - **Acciones tomadas**: Los valores atípicos son tratados mediante técnicas de transformación (como logaritmos) o pueden ser eliminados si su impacto en el modelo es significativo.

- **Errores y Duplicados**:
  - **Duplicados**: No se encontraron registros duplicados.
  - **Errores de formato**: No se observaron errores significativos en los formatos de las variables (por ejemplo, tipos de datos incorrectos).

## Variable objetivo

La **variable objetivo** es *`SalePrice`*, que representa el precio de venta de la vivienda.

#### **Distribución de la variable `SalePrice`**:
- **Media**: 180,921.195
- **Mediana**: 163,000
- **Desviación estándar**: 79,389.3
- **Rango**: 34,900 a 755,000

#### **Gráficos de distribución**:

- **Histograma**: La distribución de `SalePrice` es asimétrica a la derecha, lo que indica que la mayoría de las viviendas tienen precios más bajos, mientras que un pequeño número de viviendas tiene precios extremadamente altos.
  
  `(Colocar la ImAGEN)`

- **Boxplot**: Se observa una ligera presencia de valores atípicos (outliers) en el rango más alto del precio de venta.

  `(Colocar la ImAGEN)`

## Variables individuales

#### **Análisis de algunas variables clave**:

1. **`OverallQual`** (Calidad general de la vivienda):
   - **Tipo de dato**: Entero (de 1 a 10)
   - **Distribución**: La mayoría de las viviendas tienen una calidad general de 5 a 7.
   - **Relación con `SalePrice`**: Las viviendas con una mejor calidad general tienen precios más altos.
   - **Gráfico**: Diagrama de cajas que muestra cómo los precios aumentan con la calidad.

    `(Colocar la ImAGEN)`

2. **`GrLivArea`** (Área sobre el nivel del suelo):
   - **Tipo de dato**: Entero
   - **Distribución**: La mayoría de las viviendas tienen un área de entre 1,000 y 3,000 pies cuadrados `(medida como figura en el dataset - aplicar transformación)`.
   - **Relación con `SalePrice`**: Hay una relación positiva clara entre el área y el precio de venta. A medida que aumenta el área, también lo hace el precio de la vivienda.

    `(Colocar la ImAGEN)`

3. **`YearBuilt`** (Año de construcción):
   - **Tipo de dato**: Entero
   - **Distribución**: La mayoría de las viviendas fueron construidas entre 1950 y 2000.
   - **Relación con `SalePrice`**: Las viviendas construidas más recientemente tienden a tener precios más altos.
   - **Gráfico**: Utilizamos gráfico de dispersión que muestra que el precio aumenta con la antigüedad de la vivienda, aunque con algunas excepciones.

## Ranking de variables

Se ha utilizado un modelo de **Random Forest** para obtener la importancia de las variables. Las variables más importantes para predecir el `SalePrice` son:

1. `OverallQual` (Calidad general de la vivienda)  
2. `GrLivArea` (Área sobre el nivel del suelo)  
3. `GarageCars` (Número de plazas de garaje)  
4. `TotalBsmtSF` (Área total del sótano)  
5. `1stFlrSF` (Área del primer piso)

#### **Gráfico de importancia de variables**:

- Un gráfico de barras muestra cómo `OverallQual` y `GrLivArea` son las dos variables con mayor impacto en la predicción del precio de venta.

    `(Colocar la ImAGEN)`

## Relación entre variables explicativas y variable objetivo

#### **Matriz de correlación**:
Una matriz de correlación muestra la relación entre las variables numéricas y la variable objetivo `SalePrice`. Las variables más correlacionadas con `SalePrice` son:

- `OverallQual`: Correlación de 0.79 (fuerte relación positiva)
- `GrLivArea`: Correlación de 0.71 (fuerte relación positiva)
- `TotalBsmtSF`: Correlación de 0.61 (moderada relación positiva)

#### **Diagrama de dispersión de `GrLivArea` vs `SalePrice`**:
Este gráfico muestra claramente que, en general, las viviendas con mayor área sobre el nivel del suelo tienden a tener un precio más alto.

    `(Colocar la ImAGEN)`
