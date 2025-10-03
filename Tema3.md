# MÓDULOS Y PAQUETES CON FUNCIONES EN PYTHON

- [MÓDULOS Y PAQUETES CON FUNCIONES EN PYTHON](#módulos-y-paquetes-con-funciones-en-python)
  - [¿QUÉ SON LOS MÓDULOS?](#qué-son-los-módulos)
    - [Definición](#definición)
    - [Ventajas de usar módulos](#ventajas-de-usar-módulos)
  - [IMPORTACIÓN DE MÓDULOS](#importación-de-módulos)
    - [Sintaxis básica de import](#sintaxis-básica-de-import)
    - [Importar funciones específicas](#importar-funciones-específicas)
    - [Importar con alias](#importar-con-alias)
    - [Importar todo (no recomendado)](#importar-todo-no-recomendado)
    - [Importación condicional](#importación-condicional)
  - [CREACIÓN DE MÓDULOS PERSONALIZADOS](#creación-de-módulos-personalizados)
    - [Estructura básica de un módulo](#estructura-básica-de-un-módulo)
    - [Variables especiales en módulos](#variables-especiales-en-módulos)
    - [Ejecutar código solo cuando el módulo es el principal](#ejecutar-código-solo-cuando-el-módulo-es-el-principal)
    - [Documentación de módulos](#documentación-de-módulos)
  - [PAQUETES (PACKAGES)](#paquetes-packages)
    - [¿Qué es un paquete?](#qué-es-un-paquete)
    - [Estructura de directorios](#estructura-de-directorios)
    - [El archivo __init__.py](#el-archivo-initpy)
    - [Importación desde paquetes](#importación-desde-paquetes)
    - [Sub-paquetes](#sub-paquetes)
  - [ALGUNOS MÓDULOS BÁSICOS](#algunos-módulos-básicos)
    - [math - Funciones matemáticas básicas](#math---funciones-matemáticas-básicas)
    - [random - Números aleatorios básicos](#random---números-aleatorios-básicos)
  - [EJEMPLO DE PROYECTO COMPLETO Ejemplo de proyecto completo con funciones](#ejemplo-de-proyecto-completo-ejemplo-de-proyecto-completo-con-funciones)

## ¿QUÉ SON LOS MÓDULOS?

### Definición

Un **módulo** en Python es un archivo que contiene código Python: funciones, variables y sentencias ejecutables. Los módulos permiten organizar y reutilizar código de manera eficiente.

### Ventajas de usar módulos

- **Reutilización**: Evita duplicar código
- **Organización**: Mantiene el código ordenado y estructurado
- **Mantenimiento**: Facilita las actualizaciones y correcciones
- **Colaboración**: Permite trabajar en equipo de forma más eficiente
- **Escalabilidad**: Facilita el crecimiento de proyectos grandes

## IMPORTACIÓN DE MÓDULOS

### Sintaxis básica de import

```python
# Importar un módulo completo
import math
print(math.pi)  # 3.141592653589793
print(math.sqrt(16))  # 4.0

# Importar módulos de la biblioteca estándar
import os
import datetime
import random

# Usar las funciones del módulo
print(os.getcwd())  # Directorio actual
print(datetime.date.today())  # Fecha actual
print(random.randint(1, 10))  # Número aleatorio entre 1 y 10
```

### Importar funciones específicas

```python
# Importar funciones específicas
from math import pi, sqrt, sin, cos
print(pi)  # 3.141592653589793
print(sqrt(25))  # 5.0
print(sin(pi/2))  # 1.0

# Importar múltiples elementos
from datetime import date, datetime, timedelta
hoy = date.today()
ahora = datetime.now()
mañana = hoy + timedelta(days=1)
```

### Importar con alias

```python
# Alias para módulos
import numpy as np  # Convención común
import pandas as pd  # Convención común
import matplotlib.pyplot as plt  # Convención común

# Alias para funciones específicas
from datetime import datetime as dt
from collections import defaultdict as dd

# Ejemplo de uso
fecha_actual = dt.now()
mi_dict = dd(list)
```

### Importar todo (no recomendado)

```python
# ⚠️ NO RECOMENDADO: Importar todo
from math import *

# Problemas:
# 1. Contamina el espacio de nombres
# 2. Puede sobrescribir variables existentes
# 3. Dificulta saber de dónde viene cada función
# 4. Hace el código menos legible

# ✅ MEJOR: Ser específico
from math import pi, sqrt, sin, cos
```

### Importación condicional

```python
# Importación condicional para compatibilidad
try:
    import numpy as np
    NUMPY_AVAILABLE = True
except ImportError:
    NUMPY_AVAILABLE = False
    print("NumPy no está disponible")

# Usar la importación condicional
def procesar_datos(datos):
    if NUMPY_AVAILABLE:
        return np.array(datos).mean()
    else:
        return sum(datos) / len(datos)
```

## CREACIÓN DE MÓDULOS PERSONALIZADOS

### Estructura básica de un módulo

**Archivo: `calculadora.py`**
```python
"""
Módulo de calculadora básica.

Este módulo proporciona funciones básicas de matemáticas.
"""

__author__ = "Tu Nombre"
__version__ = "1.0.0"

# Variables del módulo
PI = 3.141592653589793

# Funciones del módulo
def sumar(a, b):
    """Suma dos números."""
    return a + b

def restar(a, b):
    """Resta dos números."""
    return a - b

def multiplicar(a, b):
    """Multiplica dos números."""
    return a * b

def dividir(a, b):
    """Divide dos números."""
    if b == 0:
        raise ValueError("No se puede dividir por cero")
    return a / b

def area_circulo(radio):
    """Calcula el área de un círculo."""
    return PI * radio ** 2

# Diccionario para almacenar historial de operaciones
historial_operaciones = []

def realizar_operacion(a, b, operador):
    """Realiza una operación y la guarda en el historial."""
    if operador == '+':
        resultado = sumar(a, b)
    elif operador == '-':
        resultado = restar(a, b)
    elif operador == '*':
        resultado = multiplicar(a, b)
    elif operador == '/':
        resultado = dividir(a, b)
    else:
        raise ValueError("Operador no válido")
    
    # Guardar en historial
    operacion_str = f"{a} {operador} {b} = {resultado}"
    historial_operaciones.append(operacion_str)
    return resultado

def mostrar_historial():
    """Muestra todas las operaciones realizadas."""
    print("Historial de operaciones:")
    for operacion in historial_operaciones:
        print(f"  {operacion}")

# Código que se ejecuta al importar
print(f"Módulo calculadora v{__version__} cargado")
```

**Uso del módulo personalizado:**
```python
# Importar el módulo completo
import calculadora

resultado = calculadora.sumar(5, 3)
print(f"5 + 3 = {resultado}")

# Usar las funciones del módulo
resultado = calculadora.realizar_operacion(10, 2, '/')
print(f"10 / 2 = {resultado}")

# Mostrar el historial
calculadora.mostrar_historial()

# Importar funciones específicas
from calculadora import sumar, dividir, realizar_operacion

print(sumar(10, 20))
print(dividir(15, 3))
print(realizar_operacion(8, 4, '*'))
```

### Variables especiales en módulos

```python
# En el módulo
print(f"Nombre del módulo: {__name__}")
print(f"Archivo del módulo: {__file__}")
print(f"Documentación: {__doc__}")

# Variables especiales disponibles
__name__      # Nombre del módulo
__file__      # Ruta del archivo del módulo
__doc__       # Documentación del módulo
__package__   # Paquete al que pertenece
__version__   # Versión (definida por el programador)
__author__    # Autor (definida por el programador)
```

### Ejecutar código solo cuando el módulo es el principal

```python
# En calculadora.py
def sumar(a, b):
    return a + b

def main():
    """Función principal para pruebas."""
    print("Probando el módulo calculadora:")
    print(f"2 + 3 = {sumar(2, 3)}")
    print(f"10 + 5 = {sumar(10, 5)}")

# Este código solo se ejecuta si el archivo se ejecuta directamente
if __name__ == "__main__":
    main()
```

### Documentación de módulos

```python
"""
Módulo de utilidades matemáticas avanzadas.

Este módulo proporciona funciones matemáticas útiles para
cálculos científicos y estadísticos.

Funciones disponibles:
    - factorial(n): Calcula el factorial de n
    - fibonacci(n): Calcula el n-ésimo número de Fibonacci
    - es_primo(n): Verifica si un número es primo

Ejemplo:
    >>> import matematicas_avanzadas
    >>> matematicas_avanzadas.factorial(5)
    120
"""

def factorial(n):
    """
    Calcula el factorial de un número.
    
    Args:
        n (int): Número no negativo
    
    Returns:
        int: Factorial de n
    
    Raises:
        ValueError: Si n es negativo
    
    Example:
        >>> factorial(5)
        120
        >>> factorial(0)
        1
    """
    if n < 0:
        raise ValueError("El factorial no está definido para números negativos")
    if n == 0:
        return 1
    return n * factorial(n - 1)
```

## PAQUETES (PACKAGES)

### ¿Qué es un paquete?

Un **paquete** es una forma de organizar módulos relacionados en una estructura de directorios. Los paquetes permiten crear jerarquías de módulos usando la notación de punto.

### Estructura de directorios

```
mi_proyecto/
│
├── main.py
├── utilidades/
│   ├── __init__.py
│   ├── matematicas.py
│   ├── texto.py
│   └── archivos.py
│
├── modelos/
│   ├── __init__.py
│   ├── usuario.py
│   └── producto.py
│
└── tests/
    ├── __init__.py
    ├── test_matematicas.py
    └── test_usuario.py
```

### El archivo __init__.py

El archivo `__init__.py` convierte un directorio en un paquete Python:

**`utilidades/__init__.py`**
```python
"""
Paquete de utilidades para el proyecto.

Contiene módulos para matemáticas, texto y manejo de archivos.
"""

# Versión del paquete
__version__ = "1.0.0"

# Importar funciones principales para acceso directo
from .matematicas import sumar, multiplicar
from .texto import limpiar_texto, capitalizar_palabras

# Lista de elementos disponibles al usar "from utilidades import *"
__all__ = [
    'sumar', 
    'multiplicar', 
    'limpiar_texto', 
    'capitalizar_palabras'
]

# Inicialización del paquete
print(f"Paquete utilidades v{__version__} inicializado")
```

**`utilidades/matematicas.py`**
```python
"""Módulo de operaciones matemáticas."""

def sumar(a, b):
    """Suma dos números."""
    return a + b

def restar(a, b):
    """Resta dos números."""
    return a - b

def multiplicar(a, b):
    """Multiplica dos números."""
    return a * b

def factorial(n):
    """Calcula el factorial de n."""
    if n <= 1:
        return 1
    return n * factorial(n - 1)
```

**`utilidades/texto.py`**
```python
"""Módulo para procesamiento de texto."""

def limpiar_texto(texto):
    """Elimina espacios extra y normaliza el texto."""
    return " ".join(texto.split())

def capitalizar_palabras(texto):
    """Capitaliza la primera letra de cada palabra."""
    return texto.title()

def contar_palabras(texto):
    """Cuenta el número de palabras en el texto."""
    return len(texto.split())
```

### Importación desde paquetes

```python
# Importar módulo completo del paquete
import utilidades.matematicas
resultado = utilidades.matematicas.sumar(5, 3)

# Importar funciones específicas
from utilidades.matematicas import sumar, factorial
print(sumar(10, 20))
print(factorial(5))

# Importar desde el __init__.py del paquete
from utilidades import sumar, limpiar_texto

# Importar módulo con alias
import utilidades.texto as txt
texto_limpio = txt.limpiar_texto("  hola   mundo  ")

# Importar todo el paquete
import utilidades
resultado = utilidades.sumar(5, 3)  # Disponible por __init__.py
```

### Sub-paquetes

```
proyecto_web/
│
├── main.py
├── backend/
│   ├── __init__.py
│   ├── api/
│   │   ├── __init__.py
│   │   ├── usuarios.py
│   │   └── productos.py
│   ├── database/
│   │   ├── __init__.py
│   │   ├── conexion.py
│   │   └── modelos.py
│   └── utils/
│       ├── __init__.py
│       └── validadores.py
│
└── frontend/
    ├── __init__.py
    ├── static/
    └── templates/
```

```python
# Importación de sub-paquetes
from backend.api.usuarios import obtener_usuario
from backend.database.conexion import conectar_db
from backend.utils.validadores import validar_email

# Importación relativa (desde dentro del paquete)
# En backend/api/usuarios.py
from ..database.modelos import Usuario  # Subir un nivel
from ...utils import helper_function    # Subir dos niveles
from .productos import obtener_producto # Mismo nivel
```

## ALGUNOS MÓDULOS BÁSICOS

Python incluye algunos módulos básicos que son útiles para empezar a trabajar con importaciones y que hemos utilizado en ejercicios anteriores.

### math - Funciones matemáticas básicas

```python
import math

# Constantes matemáticas básicas
print(f"Pi: {math.pi}")
print(f"e: {math.e}")

# Funciones matemáticas básicas
print(f"Raíz cuadrada de 16: {math.sqrt(16)}")
print(f"2 elevado a 3: {math.pow(2, 3)}")
print(f"Valor absoluto de -5: {abs(-5)}")  # abs() es función incorporada

# Funciones de redondeo
print(f"Redondear hacia arriba 4.3: {math.ceil(4.3)}")   # 5
print(f"Redondear hacia abajo 4.7: {math.floor(4.7)}")   # 4

# Importar funciones específicas
from math import sqrt, pi
print(f"Área del círculo (radio 3): {pi * sqrt(9)}")
```

### random - Números aleatorios básicos

```python
import random

# Número aleatorio entre 0 y 1
print(f"Número decimal aleatorio: {random.random()}")

# Número entero aleatorio
print(f"Número entre 1 y 10: {random.randint(1, 10)}")

# Elegir elemento aleatorio de una lista
colores = ['rojo', 'azul', 'verde', 'amarillo']
color_elegido = random.choice(colores)
print(f"Color elegido: {color_elegido}")

# Mezclar una lista
numeros = [1, 2, 3, 4, 5]
random.shuffle(numeros)
print(f"Lista mezclada: {numeros}")

# Usar un alias para el módulo
import random as rnd
print(f"Otro número aleatorio: {rnd.randint(1, 100)}")
```

## EJEMPLO DE PROYECTO COMPLETO Ejemplo de proyecto completo con funciones

**`biblioteca/__init__.py`**
```python
"""
Sistema de gestión de biblioteca.

Un paquete para gestionar libros y operaciones básicas.
"""

__version__ = "1.0.0"
__author__ = "Tu Nombre"

# Importar funciones principales
from .gestion_libros import agregar_libro, buscar_libro, listar_libros
from .operaciones import calcular_multa, dias_prestamo

print(f"Biblioteca v{__version__} cargada")
```

**`biblioteca/gestion_libros.py`**
```python
"""Funciones para gestionar libros."""

# Base de datos simple con listas y diccionarios
biblioteca = []
prestamos = {}

def agregar_libro(id_libro, titulo, autor, categoria):
    """Agrega un libro a la biblioteca."""
    # Verificar que no existe ya
    for libro in biblioteca:
        if libro['id'] == id_libro:
            raise ValueError(f"Ya existe un libro con ID {id_libro}")
    
    libro = {
        'id': id_libro,
        'titulo': titulo,
        'autor': autor,
        'categoria': categoria,
        'disponible': True
    }
    
    biblioteca.append(libro)
    print(f"Libro agregado: {titulo} por {autor}")

def buscar_libro(id_libro):
    """Busca un libro por ID."""
    for libro in biblioteca:
        if libro['id'] == id_libro:
            return libro
    return None

def listar_libros(categoria=None):
    """Lista todos los libros o por categoría."""
    if categoria:
        return [libro for libro in biblioteca if libro['categoria'].lower() == categoria.lower()]
    return biblioteca

def prestar_libro(id_libro, usuario):
    """Registra el préstamo de un libro."""
    libro = buscar_libro(id_libro)
    if not libro:
        raise ValueError("Libro no encontrado")
    
    if not libro['disponible']:
        raise ValueError("Libro no disponible")
    
    libro['disponible'] = False
    prestamos[id_libro] = {
        'usuario': usuario,
        'fecha_prestamo': None  # Se podría usar datetime cuando lo vean
    }
    
    print(f"Libro '{libro['titulo']}' prestado a {usuario}")

def devolver_libro(id_libro):
    """Registra la devolución de un libro."""
    libro = buscar_libro(id_libro)
    if not libro:
        raise ValueError("Libro no encontrado")
    
    if libro['disponible']:
        raise ValueError("El libro no estaba prestado")
    
    libro['disponible'] = True
    usuario = prestamos[id_libro]['usuario']
    del prestamos[id_libro]
    
    print(f"Libro '{libro['titulo']}' devuelto por {usuario}")
```

**`biblioteca/operaciones.py`**
```python
"""Funciones para operaciones y cálculos."""

def calcular_multa(dias_retraso, tarifa_diaria=1.0):
    """Calcula la multa por retraso en devolución."""
    if dias_retraso <= 0:
        return 0.0
    
    return dias_retraso * tarifa_diaria

def dias_prestamo(fecha_prestamo, fecha_actual):
    """Calcula los días de préstamo (simulado con números)."""
    # Para este ejemplo, trabajamos con números simples
    # En un tema posterior usarían datetime
    return abs(fecha_actual - fecha_prestamo)

def generar_reporte():
    """Genera un reporte simple de la biblioteca."""
    from .gestion_libros import biblioteca, prestamos
    
    total_libros = len(biblioteca)
    libros_disponibles = sum(1 for libro in biblioteca if libro['disponible'])
    libros_prestados = total_libros - libros_disponibles
    
    print("=== REPORTE DE BIBLIOTECA ===")
    print(f"Total de libros: {total_libros}")
    print(f"Libros disponibles: {libros_disponibles}")
    print(f"Libros prestados: {libros_prestados}")
    
    if prestamos:
        print("\nLibros prestados actualmente:")
        for id_libro, info in prestamos.items():
            from .gestion_libros import buscar_libro
            libro = buscar_libro(id_libro)
            print(f"  - {libro['titulo']} (prestado a {info['usuario']})")

def estadisticas_por_categoria():
    """Muestra estadísticas por categoría."""
    from .gestion_libros import biblioteca
    
    categorias = {}
    
    for libro in biblioteca:
        categoria = libro['categoria']
        if categoria not in categorias:
            categorias[categoria] = {'total': 0, 'disponibles': 0}
        
        categorias[categoria]['total'] += 1
        if libro['disponible']:
            categorias[categoria]['disponibles'] += 1
    
    print("=== ESTADÍSTICAS POR CATEGORÍA ===")
    for categoria, stats in categorias.items():
        prestados = stats['total'] - stats['disponibles']
        print(f"{categoria}:")
        print(f"  Total: {stats['total']}")
        print(f"  Disponibles: {stats['disponibles']}")
        print(f"  Prestados: {prestados}")
```

**`biblioteca/main.py`**
```python
"""Programa principal de la biblioteca."""

from .gestion_libros import (
    agregar_libro, listar_libros, prestar_libro, 
    devolver_libro, buscar_libro
)
from .operaciones import generar_reporte, estadisticas_por_categoria, calcular_multa

def inicializar_biblioteca():
    """Carga algunos libros de ejemplo."""
    libros_ejemplo = [
        (1, "Aprender Python", "Mark Lutz", "Programación"),
        (2, "El Quijote", "Cervantes", "Literatura"),
        (3, "Algoritmos", "Cormen", "Programación"),
        (4, "Cien años de soledad", "García Márquez", "Literatura"),
    ]
    
    for id_libro, titulo, autor, categoria in libros_ejemplo:
        agregar_libro(id_libro, titulo, autor, categoria)

def main():
    """Función principal del programa."""
    print("=== SISTEMA DE GESTIÓN DE BIBLIOTECA ===")
    
    # Inicializar con datos de ejemplo
    inicializar_biblioteca()
    
    # Mostrar todos los libros
    print("\n--- CATÁLOGO COMPLETO ---")
    todos_los_libros = listar_libros()
    for libro in todos_los_libros:
        estado = "Disponible" if libro['disponible'] else "Prestado"
        print(f"  {libro['id']} - {libro['titulo']} ({libro['autor']}) - {estado}")
    
    # Realizar algunos préstamos
    print("\n--- REALIZANDO PRÉSTAMOS ---")
    try:
        prestar_libro(1, "Ana García")
        prestar_libro(3, "Luis Martín")
    except ValueError as e:
        print(f"Error: {e}")
    
    # Mostrar estado actualizado
    print("\n--- ESTADO DESPUÉS DE PRÉSTAMOS ---")
    generar_reporte()
    
    # Mostrar estadísticas por categoría
    print()
    estadisticas_por_categoria()
    
    # Calcular multa de ejemplo
    print("\n--- EJEMPLO DE CÁLCULO DE MULTA ---")
    dias_retraso = 5
    multa = calcular_multa(dias_retraso, 1.5)
    print(f"Multa por {dias_retraso} días de retraso: ${multa:.2f}")

if __name__ == "__main__":
    main()
```

Este proyecto nos muestras las mejores prácticas:
- ✅ Estructura clara y organizada
- ✅ Separación de responsabilidades en diferentes módulos
- ✅ Documentación completa con docstrings
- ✅ Uso de funciones para organizar el código
- ✅ Trabajo con diccionarios y listas para almacenar datos
- ✅ Manejo de importaciones entre módulos del paquete

:computer: Actividad 1