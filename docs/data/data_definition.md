# Definición de los datos

## Origen de los datos

- [ ] **Fuente de los datos**:  
  Los datos provienen del conjunto de datos de Kaggle llamado "House Prices: Advanced Regression Techniques". Este conjunto de datos es proporcionado por **Kaggle**, una plataforma de competiciones y datasets que conecta a analistas de datos y científicos de datos.  
  El dataset está disponible en formato **CSV** y es utilizado comúnmente en competiciones de Machine Learning, como un caso clásico de predicción de precios inmobiliarios.

- [ ] **Forma en que se obtuvieron**:  
  Los datos fueron descargados directamente desde el sitio web de Kaggle mediante una cuenta de Kaggle y utilizando la interfaz de descarga proporcionada en el siguiente enlace:
  [Kaggle Dataset - House Prices](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data).  
  La descarga puede hacerse manualmente desde la página o utilizando la **Kaggle API** para descargar los archivos directamente desde la terminal o un script en Python hacia el repositorio de la organización DataMinds-ISPC-2024 en GitHub. 

## Especificación de los scripts para la carga de datos

- [ ] Los scripts utilizados para cargar los datos pueden variar dependiendo del entorno de desarrollo utilizado (local, servidor, entorno en la nube, etc.). A continuación se describe el script utilizado en Python para cargar de los datos a Google Colab:

**Script para la cargar de los datos en Python**:

`# Importar las librerías necesarias
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns`

`import ydata_profiling
import sweetviz
import fairlearn
import raiwidgets
import raiutils`

`from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder`

`import requests`

`from pandas_profiling import ProfileReport
from ydata_profiling import ProfileReport
from google.colab import files`

`from IPython.display import IFrame`

`from sklearn.ensemble import RandomForestRegressor
from fairlearn.metrics import MetricFrame
from sklearn.metrics import mean_absolute_error`
`# from fairlearn.widget import FairlearnDashboard`

`import warnings
warnings.simplefilter('ignore')`

`print("Todas las bibliotecas se importaron correctamente.")
print("✅ Entorno listo y sin conflictos")`


`# URL del archivo en GitHub
url_train = 'https://raw.githubusercontent.com/DataMinds-ISPC-2024/DataMinds-PP2-Proyecto/93777d37ba8fd3026305262171b0ff95034c9796/docs/data/house-prices-advanced-regression-techniques/train.csv'
url_test = 'https://raw.githubusercontent.com/DataMinds-ISPC-2024/DataMinds-PP2-Proyecto/93777d37ba8fd3026305262171b0ff95034c9796/docs/data/house-prices-advanced-regression-techniques/test.csv'`

`# Descargar el archivo train
response = requests.get(url_train)
response.raise_for_status()  # Verifica si la descarga fue exitosa (código 200)`

`# Guardar el contenido en un archivo local
with open('train.csv', 'wb') as f:
    f.write(response.content)`

`# Leer el archivo CSV descargado
train_data = pd.read_csv('train.csv')`

`# Descargar el archivo test
response = requests.get(url_test)
response.raise_for_status()`

`# Guardar el contenido en un archivo local
with open('test.csv', 'wb') as f:
    f.write(response.content)`

`# Leer el archivo CSV descargado
test_data = pd.read_csv('test.csv') # Assign the DataFrame to test_data`

`print("Cargando datasets.")
print(f"Training data shape: {train_data.shape}")
print(f"Testing data shape: {test_data.shape}")`


- [ ] **Consideraciones**: Este script carga el archivo `train.csv`, que contiene la información de las viviendas (incluyendo el precio). El archivo `test.csv` puede usarse para las predicciones en una fase posterior del proyecto. También se puede usar un archivo adicional `sample_submission.csv` para el formato de salida esperado en competiciones. 

## Referencias a rutas o bases de datos origen y destino

Especificamos las rutas o bases de datos de origen únicamente, porque las de destino de los datos `no se implementó aun`.

### Rutas de origen de datos

- [ ] **Ubicación de los archivos de origen**:
  Los archivos de datos de origen se encuentran localmente en la máquina después de ser descargados de Kaggle. Las rutas típicas a los archivos descargados son:
  - **Ruta local**: `C:/Users/Usuario/Downloads/house-prices-advanced-regression-techniques/train.csv`
  - O si se está trabajando en un entorno como Google Colab, se puede cargar desde Google Drive o una URL pública.
    
- [ ] **Estructura de los archivos de origen**:
  Los archivos de datos descargados de Kaggle se encuentran en formato **CSV**. En el caso del archivo `train.csv`, la estructura típica es:
  - **Columnas**: Variables relacionadas con las características de las viviendas, como el número de habitaciones, el tamaño del lote, el año de construcción, la ubicación (vecindario), el precio de venta (variable dependiente), entre otras.
  - **Ejemplo de columnas**: `Id`, `MSSubClass`, `LotFrontage`, `LotArea`, `OverallQual`, `YearBuilt`, `ExterCond`, `BsmtQual`, `GrLivArea`, `SalePrice`, etc.
  
  En términos generales, cada fila del archivo CSV representa una vivienda y sus respectivas características, mientras que la última columna `SalePrice` es la variable objetivo que se busca predecir.

- [ ] **Procedimientos de transformación y limpieza de los datos**:
  - **Manejo de valores faltantes**: Se identifican y manejan los valores faltantes mediante imputación o eliminación de filas/columnas, según corresponda.
  - **Eliminación de columnas irrelevantes**: Algunas columnas pueden ser innecesarias para el análisis, como el `Id` que es solo un identificador único de cada vivienda.
  - **Conversión de tipos de datos**: Se asegura de que las columnas numéricas se manejen correctamente como variables continuas, mientras que las variables categóricas se convierten en tipos adecuados para su análisis (por ejemplo, `One-Hot Encoding` para las variables categóricas).
  - **Detección de valores atípicos**: Los valores extremos (outliers) en las variables continuas pueden ser tratados, ya sea recortándolos o transformándolos.

### Base de datos de destino

- [ ] **Base de datos de destino**:
  Para fines de análisis y modelado, no es estrictamente necesario cargar los datos en una base de datos relacional por tal motivo `no se implementó aun`. Sin embargo, si se desea utilizar una base de datos SQL o similar, se puede optar por almacenar los datos en una base de datos **MySQL**, **PostgreSQL**, **SQLite**, o incluso en una base de datos NoSQL como **MongoDB** si fuera necesario para escalabilidad.

- [ ] **Estructura de la base de datos de destino**:
  La base de datos de destino debe reflejar la estructura de los datos originales en el archivo CSV. Para almacenar estos datos en una tabla, se debe crear una tabla con columnas que coincidan con las variables del conjunto de datos. Cada columna en el archivo CSV se mapea a una columna en la tabla SQL:
  - **Ejemplo de columnas en la tabla**: `Id INT`, `MSSubClass INT`, `LotFrontage FLOAT`, `LotArea INT`, `OverallQual INT`, `YearBuilt INT`, `ExterCond VARCHAR(255)`, etc.
      
- [ ] **Procedimientos de carga y transformación de los datos en la base de datos de destino**:
  - **Carga**: Usariamos un script Python con `Pandas` y `SQLAlchemy` o `mysql.connector` para cargar los datos en la base de datos de destino.
  - **Transformación**: Durante la carga de los datos en la base de datos, se podrían realizar transformaciones adicionales, como la conversión de tipos de datos, creación de índices, normalización de ciertas columnas, o particionado de tablas si los datos se almacenan en una base de datos relacional de gran tamaño.
