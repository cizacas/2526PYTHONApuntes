# LIBRERÍAS STANDARD Y DE TERCEROS EN PYTHON
- [LIBRERÍAS STANDARD Y DE TERCEROS EN PYTHON](#librerías-standard-y-de-terceros-en-python)
  - [1. Introducción a las librerías](#1-introducción-a-las-librerías)
    - [¿Qué es una librería y por qué son útiles?](#qué-es-una-librería-y-por-qué-son-útiles)
    - [Cómo instalar librerías usando `pip`](#cómo-instalar-librerías-usando-pip)
  - [2. Librerías estándar de Python](#2-librerías-estándar-de-python)
    - [Uso de `math`](#uso-de-math)
    - [Uso de `datetime`](#uso-de-datetime)
    - [Uso de `os`](#uso-de-os)
    - [Uso de `sys`](#uso-de-sys)
  - [3. Librerías de terceros](#3-librerías-de-terceros)
    - [Introducción a `requests` para hacer solicitudes HTTP](#introducción-a-requests-para-hacer-solicitudes-http)
    - [Uso básico de `NumPy` para cálculos numéricos](#uso-básico-de-numpy-para-cálculos-numéricos)
  - [4. Documentación de librerías](#4-documentación-de-librerías)
    - [Cómo leer la documentación de las librerías](#cómo-leer-la-documentación-de-las-librerías)
  - [5. Comparación y elección de librerías](#5-comparación-y-elección-de-librerías)
    - [Comparar eficiencia y adecuación](#comparar-eficiencia-y-adecuación)
    - [Justificación de la elección](#justificación-de-la-elección)
  - [6. Gestión de dependencias en un proyecto](#6-gestión-de-dependencias-en-un-proyecto)
    - [Uso de `requirements.txt`](#uso-de-requirementstxt)
  - [7. Ejemplos prácticos y limitaciones](#7-ejemplos-prácticos-y-limitaciones)
  - [8. Requisitos para crear y publicar una librería de terceros](#8-requisitos-para-crear-y-publicar-una-librería-de-terceros)

## 1. Introducción a las librerías

### ¿Qué es una librería y por qué son útiles?
Una librería en Python es un conjunto de módulos que contienen funciones y clases reutilizables para resolver problemas comunes. Usar librerías permite ahorrar tiempo, evitar errores y aprovechar el trabajo de la comunidad.
* **Las librerías estándar** son las que vienen incluidas con la instalación oficial de Python, mantenidas y aprobadas por el equipo principal de Python.
* **Las librerías de terceros** pueden ser creadas por cualquier persona o grupo. No necesitan aprobación oficial para existir, pero para que sean fácilmente instalables por otros usuarios, suelen publicarse en el repositorio oficial de paquetes de Python llamado PyPI (Python Package Index): https://pypi.org

### Cómo instalar librerías usando `pip`
`pip` es el gestor de paquetes de Python. Permite instalar librerías externas fácilmente desde la terminal:

```bash
pip install nombre_paquete
```

Ejemplo:
```bash
pip install requests
```
> ⚠️ **IMPORTANTE:** Las librerías de terceros deben instalarse con `pip` antes de poder importarlas en tu código. Si intentas hacer `import` sin haberlas instalado, Python mostrará un error.

## 2. Librerías estándar de Python

### Uso de `math`
Permite realizar operaciones matemáticas avanzadas:
```python
import math
print(math.sqrt(16))      # Raíz cuadrada
print(math.sin(math.pi))  # Seno de pi
```

### Uso de `datetime`
Trabaja con fechas y horas:
```python
from datetime import datetime
ahora = datetime.now()
print(ahora)
print(ahora.strftime('%d/%m/%Y %H:%M'))
```

### Uso de `os`
Permite interactuar con el sistema operativo:
```python
import os
print(os.getcwd())            # Directorio actual
os.mkdir('nueva_carpeta')     # Crear carpeta
```

### Uso de `sys`
Acceso a variables y argumentos del sistema:
```python
import sys
print(sys.argv)               # Argumentos de línea de comandos
print(sys.version)            # Versión de Python
```

## 3. Librerías de terceros

### Introducción a `requests` para hacer solicitudes HTTP
Permite hacer peticiones a páginas web o APIs:


| Función                | Descripción                                         | Ejemplo de uso                                      |
|------------------------|-----------------------------------------------------|-----------------------------------------------------|
| `requests.get()`       | Realiza una petición HTTP GET                       | `requests.get('https://api.example.com')`           |
| `requests.post()`      | Realiza una petición HTTP POST                      | `requests.post('https://api.example.com', data={})` |
| `requests.put()`       | Realiza una petición HTTP PUT                       | `requests.put('https://api.example.com', data={})`  |
| `requests.delete()`    | Realiza una petición HTTP DELETE                    | `requests.delete('https://api.example.com')`        |
| `requests.head()`      | Realiza una petición HTTP HEAD                      | `requests.head('https://api.example.com')`          |
| `requests.patch()`     | Realiza una petición HTTP PATCH                     | `requests.patch('https://api.example.com', data={})`|
| `requests.options()`   | Realiza una petición HTTP OPTIONS                   | `requests.options('https://api.example.com')`       |
| `response.status_code` | Devuelve el código de estado de la respuesta        | `r = requests.get(url); r.status_code`              |
| `response.text`        | Devuelve el contenido de la respuesta como texto    | `r = requests.get(url); r.text`                     |
| `response.json()`      | Devuelve la respuesta en formato JSON (si aplica)   | `r = requests.get(url); r.json()`                   |
| `requests.headers`     | Permite enviar cabeceras personalizadas             | `requests.get(url, headers={'User-Agent': 'my-app'})`|
| `requests.params`      | Permite enviar parámetros en la URL                 | `requests.get(url, params={'q': 'python'})`         |

Los métodos HTTP más comunes y su uso principal:
| Método  | Uso principal                                 | ¿Modifica datos? | Ejemplo típico                        |
|---------|-----------------------------------------------|------------------|---------------------------------------|
| GET     | Obtener datos                                 | No               | Consultar información de un usuario   |
| POST    | Crear un nuevo recurso                        | Sí               | Registrar un nuevo usuario           |
| PUT     | Reemplazar completamente un recurso existente | Sí               | Actualizar todos los datos de un usuario |
| PATCH   | Modificar parcialmente un recurso existente   | Sí               | Cambiar solo el email de un usuario  |
| DELETE  | Eliminar un recurso                           | Sí               | Borrar un usuario                    |
| HEAD    | Obtener solo las cabeceras de la respuesta    | No               | Comprobar si un archivo existe       |
| OPTIONS | Consultar los métodos y opciones permitidos   | No               | Saber qué métodos acepta un recurso  |

```python
# Ejemplo de petición GET
import requests
# suponemos que accedemos a una api a recuperar los datos de un usuario con id igual a 1
url = "https://api.ejemplo.com/usuarios/1"

# Realizamos la petición GET
respuesta = requests.get(url)

# Mostramos el código de estado y el contenido recibido
print("Código de estado:", respuesta.status_code)
print("Contenido:", respuesta.text)
```

```python
import requests
# Ejemplo de petición POST
# enviamos los datos de un usuario para que la api los procese
url = "https://api.ejemplo.com/usuarios"
datos = {"nombre": "Ana", "email": "ana@ejemplo.com"}

# Primero, hacemos una petición OPTIONS
respuesta_options = requests.options(url)

# Mostramos los métodos permitidos por el servidor
print("Métodos permitidos:", respuesta_options.headers.get("Allow"))

# Comprobamos si POST está permitido
if "POST" in respuesta_options.headers.get("Allow", ""):
    # Realizamos la petición POST
    respuesta_post = requests.post(url, json=datos)
    if respuesta_post.status_code == 201:
        print("Usuario creado correctamente.")
    else:
        print("Error al crear usuario:", respuesta_post.status_code)
else:
    print("El método POST no está permitido en este recurso.")

```
[Documentación oficial de la librería](https://requests.readthedocs.io/)

### Uso básico de `NumPy` para cálculos numéricos
Ideal para trabajar con arrays y operaciones matemáticas rápidas:

| Función           | Descripción                                                                                                   | Ejemplo de uso                                  |
|-------------------|---------------------------------------------------------------------------------------------------------------|-------------------------------------------------|
| `np.array()`      | Crea un arreglo de NumPy a partir de una lista                                                                | `np.array([1, 2, 3])`                           |
| `np.arange()`     | Crea un arreglo con valores en un rango                                                                       | `np.arange(0, 10, 2)`                           |
| `np.zeros()`      | Crea un arreglo lleno de ceros                                                                                | `np.zeros((2, 3))`                              |
| `np.ones()`       | Crea un arreglo lleno de unos                                                                                 | `np.ones((3, 2))`                               |
| `np.eye()`        | Crea una matriz identidad (matriz cuadrada con unos en la diagonal principal y ceros en el resto)             | `np.eye(3)`                                     |
| `np.linspace()`   | Crea un arreglo con números espaciados linealmente                                                            | `np.linspace(0, 1, 5)`                          |
| `np.reshape()`    | Cambia la forma de un arreglo                                                                                 | `np.reshape(np.arange(6), (2, 3))`              |
| `np.sum()`        | Suma los elementos de un arreglo                                                                              | `np.sum([1, 2, 3])`                             |
| `np.mean()`       | Calcula la media de los elementos                                                                             | `np.mean([1, 2, 3])`                            |
| `np.var()`        | Calcula la varianza de los elementos                                                                          | `np.var([1, 2, 3])`                             |
| `np.std()`        | Calcula la desviación estándar de los elementos                                                               | `np.std([1, 2, 3])`                             |
| `np.sqrt()`       | Calcula la raíz cuadrada de cada elemento del array                                                           | `np.sqrt([4, 9, 16])`                           |
| `np.max()`        | Devuelve el valor máximo                                                                                      | `np.max([1, 2, 3])`                             |
| `np.min()`        | Devuelve el valor mínimo                                                                                      | `np.min([1, 2, 3])`                             |
| `np.dot()`        | Producto escalar (suma de productos de dos vectores) o producto matricial (multiplicación de dos matrices)    | `np.dot([1, 2], [3, 4])`                        |
| `np.transpose()`  | Transpone una matriz                                                                                          | `np.transpose([[1, 2], [3, 4]])`                |
| `np.random.rand()`| Genera números aleatorios entre 0 y 1                                                                         | `np.random.rand(2, 3)`                          |
| `np.sort()`       | Ordena los elementos de un arreglo                                                                            | `np.sort([3, 1, 2])`                            |
| `np.unique()`     | Devuelve los valores únicos de un array                                                                       | `np.unique([1, 2, 2, 3, 1])`                    |


```python
import numpy as np
arr = np.array([1, 2, 3, 4])
print(np.mean(arr))           # Media
print(np.sqrt(arr))           # Raíz cuadrada de cada elemento

# ejemplo producto Matricial
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])
print(np.dot(A, B))
# Resultado:
# [[19 22]
#  [43 50]]
# cada elemento de la matriz resultado es la suma de productos de filas por columnas.
```

[Documentación oficial de la librería NumPy](https://numpy.org/doc/)

## 4. Documentación de librerías

### Cómo leer la documentación de las librerías

Consultar la documentación oficial es fundamental. [Documentación de librerías Python 3](https://docs.python.org/3/library/)

En Python, puedes usar la función `help()`:
```python
import math
help(math.sqrt)
```

## 5. Comparación y elección de librerías

### Comparar eficiencia y adecuación
Ejemplo: suma de una lista con Python estándar vs. `NumPy`:
```python
import time
import numpy as np

# Suma con listas
lista = list(range(1000000))
start = time.time()
suma = sum(lista)
print('Lista:', time.time() - start)

# Suma con numpy
arr = np.array(lista)
start = time.time()
suma = np.sum(arr)
print('NumPy:', time.time() - start)
```

### Justificación de la elección
`NumPy` es mucho más rápido para operaciones numéricas con grandes volúmenes de datos.

## 6. Gestión de dependencias en un proyecto
El archivo `requirements.txt` se utiliza principalmente para listar las librerías de terceros que necesita tu proyecto, de modo que otros puedan instalarlas fácilmente con pip.
El archivo `requirements.txt` debe ubicarse en la raíz del proyecto, es decir, en la carpeta principal donde está el código fuente y otros archivos importantes (como README.md).  

### Uso de `requirements.txt`
Para gestionar dependencias, se listan en un archivo `requirements.txt`:
```
requests
numpy
```
Instalación:
```bash
pip install -r requirements.txt
```

## 7. Ejemplos prácticos y limitaciones

- Cada ejemplo anterior muestra un caso de uso real.
- **Limitaciones:** Algunas librerías pueden no estar disponibles en todos los sistemas, pueden requerir permisos o tener problemas de compatibilidad.


## 8. Requisitos para crear y publicar una librería de terceros

Para crear y publicar una librería de terceros en Python (por ejemplo, en PyPI), se deben cumplir algunos requisitos básicos:

- El código debe estar en un paquete Python (carpeta con archivo `__init__.py`).
- Debe tener un archivo de configuración (como `setup.py` o `pyproject.toml`) con los metadatos del proyecto: nombre, versión, autor, descripción, dependencias, etc.
- Es recomendable incluir documentación y ejemplos de uso.
- Se debe elegir una licencia (por ejemplo, MIT, GPL).
- El código debe estar libre de errores y preferiblemente con pruebas (tests).
- Para publicar en PyPI, necesitas una cuenta en https://pypi.org y seguir el proceso de subida (usando herramientas como `twine`).

No hay una revisión técnica previa, pero sí hay que cumplir con las normas de empaquetado y publicación de PyPI.

**Recuerda siempre consultar la documentación oficial y probar los ejemplos en tu entorno.**
