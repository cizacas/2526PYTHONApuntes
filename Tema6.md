# MANIPULACIÓN Y ANÁLISIS DE DATOS (PANDAS)
- [MANIPULACIÓN Y ANÁLISIS DE DATOS (PANDAS)](#manipulación-y-análisis-de-datos-pandas)
  - [1. Introducción a la manipulación de datos en Python](#1-introducción-a-la-manipulación-de-datos-en-python)
    - [Listas](#listas)
    - [Diccionarios](#diccionarios)
    - [Conjuntos](#conjuntos)
  - [2. Introducción a Pandas](#2-introducción-a-pandas)
    - [Instalación y configuración de Pandas](#instalación-y-configuración-de-pandas)
    - [Conceptos básicos: Series y DataFrames](#conceptos-básicos-series-y-dataframes)
  - [3. Creación de DataFrames](#3-creación-de-dataframes)
    - [Desde diccionarios](#desde-diccionarios)
    - [Desde listas de listas](#desde-listas-de-listas)
    - [Desde arrays de NumPy](#desde-arrays-de-numpy)
    - [Desde archivos externos](#desde-archivos-externos)
      - [CSV](#csv)
      - [Excel](#excel)
      - [JSON](#json)
  - [4. Manipulación de datos con Pandas](#4-manipulación-de-datos-con-pandas)
    - [Selección y filtrado de datos](#selección-y-filtrado-de-datos)
    - [Modificación de columnas y filas](#modificación-de-columnas-y-filas)
    - [Operaciones de agregación y agrupamiento](#operaciones-de-agregación-y-agrupamiento)
    - [Transformaciones y operaciones vectorizadas](#transformaciones-y-operaciones-vectorizadas)
  - [5. Importación y exportación de datos](#5-importación-y-exportación-de-datos)
    - [Guardar datos](#guardar-datos)
      - [A CSV](#a-csv)
      - [A Excel](#a-excel)
      - [A JSON](#a-json)
  - [6. Limpieza y depuración de datos](#6-limpieza-y-depuración-de-datos)
    - [Manejo de valores NaN y datos faltantes](#manejo-de-valores-nan-y-datos-faltantes)
    - [Eliminación de duplicados](#eliminación-de-duplicados)
    - [Filtrado de datos no válidos](#filtrado-de-datos-no-válidos)
    - [Técnicas para asegurar la coherencia y calidad de los datos](#técnicas-para-asegurar-la-coherencia-y-calidad-de-los-datos)
  - [7. Optimización y eficiencia en el manejo de datos](#7-optimización-y-eficiencia-en-el-manejo-de-datos)
    - [Procesamiento por lotes](#procesamiento-por-lotes)
    - [Comparación de eficiencia: listas vs. Pandas](#comparación-de-eficiencia-listas-vs-pandas)
    - [Comparativa: NumPy vs Pandas](#comparativa-numpy-vs-pandas)
      - [Ejemplo práctico: suma de una columna](#ejemplo-práctico-suma-de-una-columna)
  - [8. Visualización de datos](#8-visualización-de-datos)
    - [Introducción a Matplotlib](#introducción-a-matplotlib)
    - [Introducción a Seaborn](#introducción-a-seaborn)
    - [Otros tipos de gráficos útiles](#otros-tipos-de-gráficos-útiles)
  - [Resumen final: Importancia de NumPy y Pandas en IA](#resumen-final-importancia-de-numpy-y-pandas-en-ia)

## 1. Introducción a la manipulación de datos en Python

La manipulación de datos es fundamental en la programación, ya que permite transformar, analizar y extraer información útil a partir de datos en bruto. Python ofrece varias estructuras de datos básicas para este propósito:

### Listas
Permiten almacenar colecciones ordenadas y modificables de elementos.

**Ejemplo de operaciones básicas con listas:**
```python
numeros = [1, 2, 3, 4, 5]
numeros.append(6)           # Añadir elemento
numeros.remove(3)           # Eliminar elemento
pares = [x for x in numeros if x % 2 == 0]  # Filtrar pares
cuadrados = [x**2 for x in numeros]         # Transformar: elevar al cuadrado
print(numeros)
print(pares)
print(cuadrados)
```

### Diccionarios
Permiten almacenar pares clave-valor.

**Ejemplo de operaciones básicas con diccionarios:**
```python
persona = {'nombre': 'Ana', 'edad': 25}
persona['ciudad'] = 'Madrid'   # Añadir clave-valor
del persona['edad']            # Eliminar clave
for clave, valor in persona.items():
	print(clave, valor)
```

### Conjuntos
Permiten almacenar elementos únicos y realizar operaciones de conjuntos.

**Ejemplo de operaciones básicas con conjuntos:**
```python
conjunto1 = {1, 2, 3, 4}
conjunto2 = {3, 4, 5, 6}
union = conjunto1 | conjunto2         # Unión
interseccion = conjunto1 & conjunto2  # Intersección
conjunto1.add(7)                      # Añadir elemento
conjunto1.discard(2)                  # Eliminar elemento
print(union)
print(interseccion)
print(conjunto1)
```

## 2. Introducción a Pandas

`Pandas` es una librería de Python especializada en la manipulación y análisis de datos, especialmente datos tabulares (similares a hojas de cálculo o bases de datos). Permite trabajar de forma eficiente con grandes volúmenes de datos y realizar operaciones complejas de manera sencilla.

### Instalación y configuración de Pandas
Para instalar Pandas, utiliza el siguiente comando en la terminal:
```bash
pip install pandas
```
Luego, puedes importarla en tu código:
```python
import pandas as pd
```

### Conceptos básicos: Series y DataFrames

- **Series:** Estructura unidimensional similar a un array o una columna de una tabla.
- **DataFrame:** Estructura bidimensional (tabla) con filas y columnas, similar a una hoja de cálculo.

**Ejemplo de Series:**
```python
import pandas as pd
serie = pd.Series([10, 20, 30, 40])
print(serie)
```

**Ejemplo de DataFrame:**
```python
import pandas as pd
datos = {'Nombre': ['Ana', 'Luis', 'Marta'], 'Edad': [23, 34, 29]}
df = pd.DataFrame(datos)
print(df)
```

## 3. Creación de DataFrames

Pandas permite crear DataFrames de diferentes fuentes de datos:

### Desde diccionarios
```python
import pandas as pd
datos = {'Nombre': ['Ana', 'Luis', 'Marta'], 'Edad': [23, 34, 29]}
df = pd.DataFrame(datos)
print(df)
```

### Desde listas de listas
```python
import pandas as pd
datos = [['Ana', 23], ['Luis', 34], ['Marta', 29]]
df = pd.DataFrame(datos, columns=['Nombre', 'Edad'])
print(df)
```

### Desde arrays de NumPy
```python
import numpy as np
import pandas as pd
arr = np.array([[1, 2], [3, 4]])
df = pd.DataFrame(arr, columns=['Col1', 'Col2'])
print(df)
```

### Desde archivos externos
#### CSV
Supón que tienes un archivo llamado `archivo.csv` con el siguiente contenido:

```
Nombre,Edad,Ciudad
Ana,23,Madrid
Luis,34,Sevilla
Marta,29,Valencia
```

El siguiente código carga el archivo CSV en un DataFrame:
```python
import pandas as pd
df = pd.read_csv('archivo.csv')
print(df.head())
```

**¿Qué transformación hace?**

El método `pd.read_csv` lee el archivo CSV y convierte cada fila en una fila del DataFrame, y cada columna del CSV en una columna del DataFrame. El resultado es una tabla en memoria que puedes manipular fácilmente con pandas:

|   | Nombre | Edad | Ciudad   |
|---|--------|------|----------|
| 0 | Ana    | 23   | Madrid   |
| 1 | Luis   | 34   | Sevilla  |
| 2 | Marta  | 29   | Valencia |

Puedes acceder, filtrar y transformar estos datos usando las funciones de pandas.
#### Excel
Supón que tienes un archivo llamado `archivo.xlsx` con una hoja que contiene:

| Nombre | Edad | Ciudad   |
|--------|------|----------|
| Ana    | 23   | Madrid   |
| Luis   | 34   | Sevilla  |
| Marta  | 29   | Valencia |

El siguiente código carga el archivo Excel en un DataFrame:
```python
import pandas as pd
df = pd.read_excel('archivo.xlsx')
print(df.head())
```

**¿Qué transformación hace?**

El método `pd.read_excel` lee la hoja del archivo Excel y convierte cada fila en una fila del DataFrame, y cada columna en una columna del DataFrame. El resultado es una tabla en memoria igual a la que ves en Excel, pero lista para manipular con pandas.
#### JSON
Supón que tienes un archivo llamado `archivo.json` con el siguiente contenido:

```json
[
	{"Nombre": "Ana", "Edad": 23, "Ciudad": "Madrid"},
	{"Nombre": "Luis", "Edad": 34, "Ciudad": "Sevilla"},
	{"Nombre": "Marta", "Edad": 29, "Ciudad": "Valencia"}
]
```

El siguiente código carga el archivo JSON en un DataFrame:
```python
import pandas as pd
df = pd.read_json('archivo.json')
print(df.head())
```

**¿Qué transformación hace?**

El método `pd.read_json` lee el archivo JSON y convierte cada objeto del array en una fila del DataFrame, y cada clave en una columna. El resultado es una tabla en memoria igual a la estructura del JSON, lista para manipular con pandas.

> ℹ️ **Nota:** Lo ideal es que los archivos CSV, Excel y JSON tengan una cabecera o claves que identifiquen los campos (nombres de columnas). Pandas usará automáticamente la primera fila (CSV/Excel) o las claves (JSON) como nombres de las columnas del DataFrame. Si no hay cabecera, puedes usar el parámetro `header=None` en CSV/Excel y pandas asignará nombres genéricos. En JSON, si las claves no son uniformes, pandas rellenará con NaN los valores que falten.

## 4. Manipulación de datos con Pandas

Pandas facilita la manipulación de datos tabulares mediante operaciones sencillas y potentes:

### Selección y filtrado de datos

| Acción                        | Sintaxis/Ejemplo                        | Descripción                                      |
|------------------------------|------------------------------------------|--------------------------------------------------|
| Seleccionar columna          | df['Edad']                               | Devuelve la columna 'Edad' como Series           |
| Seleccionar varias columnas  | df[['Nombre', 'Edad']]                   | Devuelve un DataFrame con esas columnas          |
| Seleccionar por índice       | df.iloc[0]                               | Devuelve la primera fila                         |
| Seleccionar por etiqueta     | df.loc[1]                                | Devuelve la fila con índice 1                    |
| Filtrar filas por condición  | df[df['Edad'] > 30]                      | Filas donde la edad es mayor que 30              |
| Selección múltiple           | df.loc[0:2, ['Nombre', 'Edad']]          | Filas 0 a 2 y columnas 'Nombre' y 'Edad'         |

**Ejemplo práctico:**
```python
import pandas as pd
df = pd.DataFrame({'Nombre': ['Ana', 'Luis', 'Marta'], 'Edad': [23, 34, 29]})
# Seleccionar columna
print(df['Edad'])
# Filtrar filas
mayores_30 = df[df['Edad'] > 30]
print(mayores_30)
```

### Modificación de columnas y filas

| Acción                        | Sintaxis/Ejemplo                        | Descripción                                      |
|------------------------------|------------------------------------------|--------------------------------------------------|
| Añadir columna               | df['Ciudad'] = ['Madrid', ...]           | Añade una nueva columna                          |
| Modificar valor              | df.loc[1, 'Edad'] = 35                   | Cambia el valor de la fila 1, columna 'Edad'     |
| Eliminar columna             | df = df.drop('Ciudad', axis=1)           | Elimina la columna 'Ciudad'                      |
| Eliminar fila                | df = df.drop(2, axis=0)                  | Elimina la fila con índice 2                     |
| Renombrar columnas           | df.rename(columns={'Edad':'Años'})       | Cambia el nombre de la columna 'Edad' a 'Años'   |

**Ejemplo práctico:**
```python
# Añadir nueva columna
df['Ciudad'] = ['Madrid', 'Sevilla', 'Valencia']
# Modificar valores
# Luis pasa a tener 35 años
df.loc[1, 'Edad'] = 35
# Eliminar columna
#En Pandas, el parámetro axis indica la dirección de la operación:
#axis=0 significa operar sobre filas (vertical).
#axis=1 significa operar sobre columnas (horizontal).
df = df.drop('Ciudad', axis=1)
print(df)
```

### Operaciones de agregación y agrupamiento

| Acción                        | Sintaxis/Ejemplo                        | Descripción                                      |
|------------------------------|------------------------------------------|--------------------------------------------------|
| Suma de columna              | df['Edad'].sum()                         | Suma todos los valores de la columna 'Edad'      |
| Media de columna             | df['Edad'].mean()                        | Calcula la media de la columna 'Edad'            |
| Agrupar por columna          | df.groupby('Ciudad')['Edad'].mean()      | Media de 'Edad' agrupada por 'Ciudad'            |
| Contar valores               | df['Ciudad'].value_counts()              | Cuenta ocurrencias de cada valor en 'Ciudad'     |

**Ejemplo práctico:**
```python
df = pd.DataFrame({
	'Nombre': ['Ana', 'Luis', 'Marta', 'Luis'],
	'Edad': [23, 34, 29, 34],
	'Ciudad': ['Madrid', 'Sevilla', 'Valencia', 'Sevilla']
})
# Agrupar por ciudad y calcular media de edad
agrupado = df.groupby('Ciudad')['Edad'].mean()
print(agrupado)
```

### Transformaciones y operaciones vectorizadas

| Acción                        | Sintaxis/Ejemplo                        | Descripción                                      |
|------------------------------|------------------------------------------|--------------------------------------------------|
| Sumar a columna              | df['Edad'] = df['Edad'] + 1              | Suma 1 a todos los valores de 'Edad'             |
| Aplicar función personalizada| df['Edad2'] = df['Edad'].apply(lambda x: x*2) | Aplica una función a cada elemento de 'Edad' |
| Redondear valores            | df['Edad'] = df['Edad'].round(0)         | Redondea los valores de la columna 'Edad'        |

**Ejemplo práctico:**
```python
# Sumar 1 a todas las edades
df['Edad'] = df['Edad'] + 1
# Aplicar función personalizada
df['Edad_doble'] = df['Edad'].apply(lambda x: x * 2)
print(df)
```

## 5. Importación y exportación de datos

La importación de datos en Pandas consiste en cargar información desde archivos externos (CSV, Excel, JSON, etc.) a un DataFrame. Este proceso ya se ha explicado en el apartado "Creación de DataFrames desde archivos externos". Consulta ese apartado para ver ejemplos y detalles de cómo importar datos.

### Guardar datos

Supón que tienes el siguiente DataFrame:

```python
import pandas as pd
df = pd.DataFrame({
	'Nombre': ['Ana', 'Luis', 'Marta'],
	'Edad': [23, 34, 29],
	'Ciudad': ['Madrid', 'Sevilla', 'Valencia']
})
print(df)
```

|   | Nombre | Edad | Ciudad   |
|---|--------|------|----------|
| 0 | Ana    | 23   | Madrid   |
| 1 | Luis   | 34   | Sevilla  |
| 2 | Marta  | 29   | Valencia |

Puedes guardar este DataFrame en diferentes formatos:

#### A CSV
```python
df.to_csv('salida.csv', index=False)
```
Esto crea un archivo `salida.csv` con el siguiente contenido:
```
Nombre,Edad,Ciudad
Ana,23,Madrid
Luis,34,Sevilla
Marta,29,Valencia
```

#### A Excel
```python
df.to_excel('salida.xlsx', index=False)
```
Esto crea un archivo Excel con una hoja que contiene la misma tabla.

#### A JSON
```python
df.to_json('salida.json')
```
Esto crea un archivo JSON con el siguiente contenido:
```json
[{"Nombre":"Ana","Edad":23,"Ciudad":"Madrid"},
 {"Nombre":"Luis","Edad":34,"Ciudad":"Sevilla"},
 {"Nombre":"Marta","Edad":29,"Ciudad":"Valencia"}]
```

## 6. Limpieza y depuración de datos

| Función              | Ejemplo de uso                        | Descripción                                      |
|----------------------|---------------------------------------|--------------------------------------------------|
| dropna()             | df.dropna()                           | Elimina filas con valores NaN                    |
| fillna()             | df.fillna(0)                          | Rellena valores NaN con el valor indicado        |
| isna(), notna()      | df['A'].isna()                        | Devuelve True donde hay (o no hay) NaN           |
| drop_duplicates()    | df.drop_duplicates()                   | Elimina filas duplicadas                         |
| replace()            | df.replace('?', np.nan)               | Reemplaza valores específicos                    |
| astype()             | df['Edad'].astype(int)                | Cambia el tipo de datos de una columna           |
| apply()              | df['A'].apply(lambda x: x*2)          | Aplica una función a cada elemento de la columna |
| str.lower()          | df['Nombre'].str.lower()              | Convierte texto a minúsculas                     |
| clip()               | df['A'].clip(0, 100)                  | Limita valores a un rango                        |
| round()              | df['A'].round(1)                      | Redondea valores numéricos                       |
| query()              | df.query('Edad > 30')                 | Filtra filas usando una expresión                |


La limpieza de datos es esencial para garantizar la calidad y coherencia de los resultados. Pandas ofrece herramientas para:

### Manejo de valores NaN y datos faltantes
```python
import pandas as pd
import numpy as np
df = pd.DataFrame({'A': [1, 2, np.nan], 'B': [4, np.nan, 6]})
print(df)
# Eliminar filas con NaN
df_sin_nan = df.dropna()
print(df_sin_nan)
# Rellenar NaN con un valor
df_relleno = df.fillna(0)
print(df_relleno)
```

### Eliminación de duplicados
```python
df = pd.DataFrame({'A': [1, 2, 2, 3], 'B': [4, 5, 5, 6]})
df_sin_duplicados = df.drop_duplicates()
print(df_sin_duplicados)
```

### Filtrado de datos no válidos
```python
df = pd.DataFrame({'A': [1, -2, 3, -4]})
df_filtrado = df[df['A'] > 0]  # Solo valores positivos
print(df_filtrado)
```

### Técnicas para asegurar la coherencia y calidad de los datos

- **Revisar tipos de datos:** `dtypes`
	```python
	print(df.dtypes)  # Muestra el tipo de cada columna
	```
- **Comprobar valores únicos:** `unique()`
	```python
	print(df['Ciudad'].unique())  # Lista los valores únicos de la columna 'Ciudad'
	```
- **Usar descripciones estadísticas:** `describe()`
	```python
	import pandas as pd
	df = pd.DataFrame({'Edad': [23, 34, 29, 40, 31]})
	print(df.describe())  # Estadísticas básicas de la columna 'Edad'
	```
	Resultado:
	```
			   Edad
	count   5.000000
	mean   31.400000
	std     6.658328
	min    23.000000
	25%    29.000000
	50%    31.000000
	75%    34.000000
	max    40.000000
	```
Esto te da información sobre:

* cuántos datos hay (count)
* media (mean)
* desviación estándar (std)
* mínimo y máximo
* percentiles (25%, 50%, 75%)
Sirve para detectar valores atípicos, errores o comprobar la distribución de los datos.

## 7. Optimización y eficiencia en el manejo de datos

Cuando se trabaja con grandes volúmenes de datos, es importante optimizar las operaciones para mejorar el rendimiento.

### Procesamiento por lotes
Pandas permite leer archivos grandes por partes usando el parámetro `chunksize`:
* Si usas chunksize=10000, pandas leerá el archivo en bloques de 10.000 filas cada vez.
* Cada bloque (chunk) se procesa como un DataFrame independiente.
* Es útil para trabajar con archivos muy grandes que no caben en memoria, o para procesar datos por lotes.
```python
import pandas as pd
for chunk in pd.read_csv('datos_grandes.csv', chunksize=10000):
	print(chunk.shape)# Muestra el tamaño del bloque leído
    # Aquí puedes procesar cada chunk por separado
```

### Comparación de eficiencia: listas vs. Pandas
```python
import time
import pandas as pd

# Suma de una columna con listas
datos = list(range(1000000))
start = time.time()
suma = sum(datos)
print('Suma con listas:', time.time() - start)

# Suma con Pandas
df = pd.DataFrame({'A': datos})
start = time.time()
suma = df['A'].sum()
print('Suma con Pandas:', time.time() - start)
```

Pandas suele ser más eficiente y permite operaciones vectorizadas, lo que mejora el rendimiento en grandes conjuntos de datos.

### Comparativa: NumPy vs Pandas

| Característica                | NumPy                                 | Pandas                                      |
|-------------------------------|---------------------------------------|---------------------------------------------|
| Tipo de datos                 | Arrays homogéneos (mismo tipo)        | Tablas (DataFrames) con columnas de distinto tipo |
| Velocidad en cálculos         | Muy alta                              | Alta, pero algo menor que NumPy             |
| Funciones matemáticas         | Muy completas                         | Usa internamente NumPy para cálculos        |
| Manipulación de datos         | Limitada                              | Muy flexible (filtrado, agrupación, limpieza, etc.) |
| Manejo de datos faltantes     | No                                    | Sí (NaN, fillna, dropna, etc.)              |
| Indexación avanzada           | Limitada                              | Muy avanzada (por etiquetas, booleanos, etc.)|

#### Ejemplo práctico: suma de una columna

```python
import numpy as np
import pandas as pd
import time

# Con NumPy
arr = np.random.randint(0, 100, size=1000000)
start = time.time()
suma_np = np.sum(arr)
print('NumPy:', time.time() - start)

# Con Pandas
df = pd.DataFrame({'A': arr})
start = time.time()
suma_pd = df['A'].sum()
print('Pandas:', time.time() - start)
```

NumPy suele ser más rápido para operaciones puramente numéricas, pero Pandas es más versátil para análisis y manipulación de datos tabulares.


## 8. Visualización de datos

La visualización de datos permite interpretar y comunicar resultados de forma clara. Pandas se integra fácilmente con librerías como `Matplotlib` y `Seaborn`.

### Introducción a Matplotlib
Matplotlib es la librería más utilizada para crear gráficos en Python.
```python
import pandas as pd
import matplotlib.pyplot as plt
df = pd.DataFrame({'A': [1, 2, 3, 4], 'B': [10, 20, 25, 30]})
df.plot(kind='bar', x='A', y='B')
plt.title('Gráfico de barras')
plt.xlabel('A')
plt.ylabel('B')
plt.show()
```

### Introducción a Seaborn
Seaborn facilita la creación de gráficos estadísticos atractivos.
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.DataFrame({'A': [1, 2, 3, 4], 'B': [10, 20, 25, 30]})
sns.lineplot(data=df, x='A', y='B')
plt.title('Gráfico de líneas con Seaborn')
plt.show()
```

### Otros tipos de gráficos útiles
- Histogramas: `df['columna'].plot(kind='hist')`
- Gráficos de dispersión: `df.plot(kind='scatter', x='A', y='B')`

## Resumen final: Importancia de NumPy y Pandas en IA

El manejo de NumPy (tema 5) y Pandas (tema 6) es fundamental para trabajar con Python en el ámbito de la inteligencia artificial y el análisis de datos.

Ambas librerías son la base para tareas de procesamiento, limpieza y manipulación de datos, que son pasos previos imprescindibles antes de aplicar técnicas de machine learning, deep learning o cualquier algoritmo de IA.

Además, muchas librerías avanzadas de IA (como scikit-learn, TensorFlow o PyTorch) utilizan internamente estructuras de NumPy y Pandas. Por eso, dominar estos temas es esencial para avanzar en inteligencia artificial con Python.
