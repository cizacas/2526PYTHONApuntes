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
    - [Uso básico de `numpy` para cálculos numéricos](#uso-básico-de-numpy-para-cálculos-numéricos)
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
```python
import requests
respuesta = requests.get('https://api.github.com')
print(respuesta.status_code)
print(respuesta.json())
```

### Uso básico de `numpy` para cálculos numéricos
Ideal para trabajar con arrays y operaciones matemáticas rápidas:
```python
import numpy as np
arr = np.array([1, 2, 3, 4])
print(np.mean(arr))           # Media
print(np.sqrt(arr))           # Raíz cuadrada de cada elemento
```

## 4. Documentación de librerías

### Cómo leer la documentación de las librerías
Consultar la documentación oficial es fundamental. Ejemplo: https://docs.python.org/3/library/

En Python, puedes usar la función `help()`:
```python
import math
help(math.sqrt)
```

## 5. Comparación y elección de librerías

### Comparar eficiencia y adecuación
Ejemplo: suma de una lista con Python estándar vs. `numpy`:
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
print('Numpy:', time.time() - start)
```

### Justificación de la elección
`numpy` es mucho más rápido para operaciones numéricas con grandes volúmenes de datos.

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
