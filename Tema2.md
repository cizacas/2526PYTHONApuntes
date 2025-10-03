# FUNCIONES EN PYTHON

- [FUNCIONE  - [DOCUMENTACIÓN DE FUNCIONES](#documentación-de-funciones)
    - [Docstrings](#docstrings)
      - [Docstring simple](#docstring-simple)
      - [Docstring detallada](#docstring-detallada)
      - [Acceder a la documentación](#acceder-a-la-documentación)
    - [Anotaciones de tipo (Type Hints)](#anotaciones-de-tipo-type-hints)
    - [Ejemplo: Función con múltiples características](#ejemplo-función-con-múltiples-características)
  - [INTRODUCCIÓN A LAS PRUEBAS UNITARIAS](#introducción-a-las-pruebas-unitarias)
    - [¿Qué son las pruebas unitarias?](#qué-son-las-pruebas-unitarias)
    - [Verificación manual vs. automática](#verificación-manual-vs-automática)
    - [Pruebas básicas con assert](#pruebas-básicas-con-assert)
    - [Organizar las pruebas](#organizar-las-pruebas)
    - [Casos de prueba típicos](#casos-de-prueba-típicos)
    - [Ejemplo completo: Probando una calculadora](#ejemplo-completo-probando-una-calculadora)THON](#funciones-en-python)
  - [DEFINICIÓN Y CREACIÓN DE FUNCIONES CON `def`](#definición-y-creación-de-funciones-con-def)
    - [Sintaxis básica](#sintaxis-básica)
    - [Ejemplo básico](#ejemplo-básico)
    - [Convenciones de nomenclatura](#convenciones-de-nomenclatura)
  - [PARÁMETROS Y ARGUMENTOS](#parámetros-y-argumentos)
    - [Definición](#definición)
    - [Tipos de parámetros](#tipos-de-parámetros)
      - [1. Parámetros posicionales](#1-parámetros-posicionales)
      - [2. Parámetros con valores por defecto](#2-parámetros-con-valores-por-defecto)
      - [3. Argumentos por palabra clave (keyword arguments)](#3-argumentos-por-palabra-clave-keyword-arguments)
      - [4. \*args (argumentos variables posicionales)](#4-args-argumentos-variables-posicionales)
      - [5. \*\*kwargs (argumentos variables por palabra clave)](#5-kwargs-argumentos-variables-por-palabra-clave)
      - [6. Combinando tipos de parámetros](#6-combinando-tipos-de-parámetros)
    - [Paso por valor vs. Paso por referencia](#paso-por-valor-vs-paso-por-referencia)
      - [Objetos inmutables (int, str, tuple)](#objetos-inmutables-int-str-tuple)
      - [Objetos mutables (list, dict, set)](#objetos-mutables-list-dict-set)
        - [**Crear copias explícitas cuando sea necesario:**](#crear-copias-explícitas-cuando-sea-necesario)
  - [VALORES DE RETORNO (`return`)](#valores-de-retorno-return)
    - [Función sin return](#función-sin-return)
    - [Función con return simple](#función-con-return-simple)
    - [Return múltiple](#return-múltiple)
    - [Return condicional](#return-condicional)
  - [ÁMBITO DE LAS VARIABLES](#ámbito-de-las-variables)
    - [Variables locales](#variables-locales)
    - [Variables globales](#variables-globales)
    - [Variables no locales (nonlocal)](#variables-no-locales-nonlocal)
    - [Regla LEGB](#regla-legb)
  - [FUNCIONES INCORPORADAS](#funciones-incorporadas)
    - [Funciones de tipo y conversión](#funciones-de-tipo-y-conversión)
    - [Funciones de secuencias](#funciones-de-secuencias)
    - [Funciones de iteración](#funciones-de-iteración)
    - [Funciones de entrada y salida](#funciones-de-entrada-y-salida)
    - [Funciones matemáticas incorporadas](#funciones-matemáticas-incorporadas)
  - [DOCUMENTACIÓN DE FUNCIONES](#documentación-de-funciones)
    - [Docstrings](#docstrings)
      - [Docstring simple](#docstring-simple)
      - [Docstring detallada](#docstring-detallada)
      - [Acceder a la documentación](#acceder-a-la-documentación)
    - [Anotaciones de tipo (Type Hints)](#anotaciones-de-tipo-type-hints)
    - [Ejemplo: Función con múltiples características](#ejemplo-función-con-múltiples-características)


## DEFINICIÓN Y CREACIÓN DE FUNCIONES CON `def`

Una función es un bloque de código reutilizable que realiza una tarea específica. En Python, las funciones se definen utilizando la palabra clave `def`.

### Sintaxis básica

```python
def nombre_funcion():
    """Documentación de la función (opcional)"""
    # Código de la función
    pass
```

### Ejemplo básico

```python
def saludar():
    """Función que imprime un saludo"""
    print("¡Hola, mundo!")

# Llamada a la función
saludar()  # Salida: ¡Hola, mundo!
```

### Convenciones de nomenclatura

- Usar **snake_case** (palabras separadas por guiones bajos)
- Nombres descriptivos y claros
- Evitar palabras reservadas de Python

```python
def calcular_area_rectangulo():
    pass

def procesar_datos_usuario():
    pass
```

## PARÁMETROS Y ARGUMENTOS

### Definición

- **Parámetro**: Variable definida en la función
- **Argumento**: Valor que se pasa a la función cuando se llama

### Tipos de parámetros

#### 1. Parámetros posicionales

```python
def saludar_persona(nombre, apellido):
    print(f"Hola, {nombre} {apellido}")

# Llamada con argumentos posicionales
saludar_persona("Juan", "Pérez")  # Salida: Hola, Juan Pérez
```

#### 2. Parámetros con valores por defecto

```python
def saludar_con_mensaje(nombre, mensaje="¡Hola!"):
    print(f"{mensaje} {nombre}")

# Llamadas
saludar_con_mensaje("Ana")  # Salida: ¡Hola! Ana
saludar_con_mensaje("Ana", "¡Buenos días!")  # Salida: ¡Buenos días! Ana
```

#### 3. Argumentos por palabra clave (keyword arguments)

```python
def presentar_persona(nombre, edad, ciudad):
    print(f"Me llamo {nombre}, tengo {edad} años y vivo en {ciudad}")

# Llamada con argumentos por palabra clave
presentar_persona(ciudad="Madrid", nombre="Carlos", edad=25)
```

#### 4. *args (argumentos variables posicionales)

```python
def sumar_numeros(*numeros):
    """Suma una cantidad variable de números"""
    total = 0
    for numero in numeros:
        total += numero
    return total

# Ejemplos de uso
print(sumar_numeros(1, 2, 3))        # Salida: 6
print(sumar_numeros(1, 2, 3, 4, 5))  # Salida: 15
```

#### 5. **kwargs (argumentos variables por palabra clave)

```python
def mostrar_informacion(**info):
    """Muestra información variable del usuario"""
    for clave, valor in info.items():
        print(f"{clave}: {valor}")

# Ejemplo de uso
mostrar_informacion(nombre="Luis", edad=30, profesion="Programador")
# Salida:
# nombre: Luis
# edad: 30
# profesion: Programador
```

#### 6. Combinando tipos de parámetros

```python
def funcion_completa(pos1, pos2, defecto="valor", *args, **kwargs):
    print(f"Posicional 1: {pos1}")
    print(f"Posicional 2: {pos2}")
    print(f"Por defecto: {defecto}")
    print(f"Args adicionales: {args}")
    print(f"Kwargs: {kwargs}")

# Ejemplo de uso
funcion_completa("a", "b", "c", "d", "e", nombre="Juan", edad=25)
```

### Paso por valor vs. Paso por referencia

En Python, todo se pasa por **referencia de objeto**. Esto significa que no se crea una copia del objeto, sino que se pasa una referencia (dirección de memoria) al objeto original.

**La diferencia clave está en la mutabilidad del objeto, no en cómo se pasa:**

#### Objetos inmutables (int, str, tuple)

📌IMPORTANTE: Los objetos inmutables **NO se copian** cuando se pasan como parámetros. Se pasa la misma referencia, pero como el objeto no puede cambiar, el efecto es como si fuera una copia.

```python
def modificar_numero(x):
    # INMUTABLES: Efecto "copia" (pero no es copia real)
    print(f"ID dentro (antes): {id(x)}")  # Mismo ID que fuera
    x = x + 10  # Esto crea un NUEVO objeto, no modifica el original
    print(f"ID dentro (después): {id(x)}")  # ID diferente (nuevo objeto)
    print(f"Dentro de la función: {x}")

numero = 5
print(f"ID fuera (original): {id(numero)}")
modificar_numero(numero)
print(f"Fuera de la función: {numero}")
print(f"ID fuera (después): {id(numero)}")  # Mismo ID original

# Salida:
# ID fuera (original): 140712345678976
# ID dentro (antes): 140712345678976    <- MISMO ID
# ID dentro (después): 140712345679296  <- NUEVO ID
# Dentro de la función: 15
# Fuera de la función: 5
# ID fuera (después): 140712345678976   <- ID original sin cambios
```

**Lo que realmente sucede:**
1. Se pasa la **misma referencia** al objeto `5`
2. `x = x + 10` crea un **nuevo objeto** `15` y hace que `x` apunte a él
3. La variable original `numero` sigue apuntando al objeto original `5`
4. **No hay copia**, pero el efecto es como si la hubiera

```python
def demostrar_referencias_inmutables():
    # Ejemplo con strings
    # INMUTABLES: Efecto "copia" (pero no es copia real)
    def modificar_texto(cadena):
        print(f"Cadena recibida ID: {id(cadena)}")
        cadena = cadena + " modificada"  # Nuevo objeto string
        print(f"Cadena nueva ID: {id(cadena)}")
        return cadena
    
    texto_original = "Hola"
    print(f"Texto original ID: {id(texto_original)}")
    texto_modificado = modificar_texto(texto_original)
    print(f"Después de función - Original: '{texto_original}' ID: {id(texto_original)}")
    print(f"Después de función - Modificado: '{texto_modificado}' ID: {id(texto_modificado)}")

demostrar_referencias_inmutables()

# Salida esperada:
# Texto original ID: 140712345678123
# Cadena recibida ID: 140712345678123    <- MISMO ID (misma referencia)
# Cadena nueva ID: 140712345679456       <- NUEVO ID (nuevo objeto)
# Después de función - Original: 'Hola' ID: 140712345678123     <- Original sin cambios
# Después de función - Modificado: 'Hola modificada' ID: 140712345679456  <- Nuevo objeto
```

#### Objetos mutables (list, dict, set)

**Con objetos mutables, la referencia apunta al mismo objeto y SÍ se puede modificar directamente:**

```python
def modificar_lista(lista):
    # MUTABLES: Modificación directa
    print(f"Lista recibida ID: {id(lista)}")
    lista.append(4)  # Modifica el objeto original directamente
    print(f"Lista después ID: {id(lista)}")  # Mismo ID
    print(f"Dentro de la función: {lista}")

# Ejemplo de uso de la función modificar_lista
mi_lista = [1, 2, 3]
print(f"Lista original ID: {id(mi_lista)}")
modificar_lista(mi_lista)
print(f"Fuera de la función: {mi_lista}")
print(f"Lista final ID: {id(mi_lista)}")  # Mismo ID original

# Salida:
# Lista original ID: 2234567891234
# Lista recibida ID: 2234567891234    <- MISMO ID
# Lista después ID: 2234567891234     <- MISMO ID
# Dentro de la función: [1, 2, 3, 4]
# Fuera de la función: [1, 2, 3, 4]   <- ¡MODIFICADA!
# Lista final ID: 2234567891234       <- MISMO ID
```

##### **Crear copias explícitas cuando sea necesario:**
En Python, tiene dos tipos de copia:

1️⃣ **Copia Superficial (Shallow Copy)**
* **Métodos**: .copy(), list(), [:], copy.copy()
* **Comportamiento**: Crea un nuevo contenedor, pero comparte los objetos internos

2️⃣ **Copia Profunda (Deep Copy)**
* **Método**: copy.deepcopy()
* **Comportamiento**: Crea objetos completamente independientes en todos los niveles

```python
import copy

def no_modificar_original(lista_original):
    # Copia superficial (shallow copy)
    lista_copia = lista_original.copy()  # o list(lista_original) o [:]
    lista_copia.append(99)
    print(f"Original: {lista_original}")
    print(f"Copia modificada: {lista_copia}")

# Ejemplo de uso de la función no_modificar_original
print("=== EJEMPLO: Función no_modificar_original ===")
mi_lista = [1, 2, 3]
print(f"Lista antes de llamar la función: {mi_lista}")
no_modificar_original(mi_lista)
print(f"Lista después de llamar la función: {mi_lista}")

# Salida esperada:
# Lista antes de llamar la función: [1, 2, 3]
# Original: [1, 2, 3]
# Copia modificada: [1, 2, 3, 99]
# Lista después de llamar la función: [1, 2, 3]  <- ¡No se modificó!

```

```python
import copy

def no_modificar_original_profundo(matriz_original):
    # Copia profunda (deep copy)
    matriz_copia = copy.deepcopy(matriz_original)
    matriz_copia[0].append(99)  # Modifica la primera sublista de la copia
    print(f"Original: {matriz_original}")
    print(f"Copia modificada: {matriz_copia}")

# Ejemplo de uso de la función no_modificar_original_profundo
print("\n=== EJEMPLO: Función no_modificar_original_profundo ===")
mi_matriz = [[1, 2], [3, 4]]
print(f"Matriz antes de llamar la función: {mi_matriz}")
no_modificar_original_profundo(mi_matriz)
print(f"Matriz después de llamar la función: {mi_matriz}")

# Salida esperada:
# Matriz antes de llamar la función: [[1, 2], [3, 4]]
# Original: [[1, 2], [3, 4]]
# Copia modificada: [[1, 2, 99], [3, 4]]
# Matriz después de llamar la función: [[1, 2], [3, 4]]  <- ¡No se modificó!

```
🎯 Estructura paralela lograda:

|Copia Superficial |Copia Profunda|
|------------------|--------------|
|lista.copy() |copy.deepcopy() |
|Elementos simples ✅|Estructuras anidadas ✅|
|Lista [1, 2, 3]|Matriz `[[1, 2], [3, 4]]`|
|Original no cambia|Original no cambia|

⚠️ Comparación con el problema de copia superficial:

```python
import copy
# COMPARACIÓN: Si hubiéramos usado copia superficial con matriz anidada
def ejemplo_problema_copia_superficial():
    print("\n=== PROBLEMA: Si usáramos copia superficial con matriz ===")
    mi_matriz2 = [[1, 2], [3, 4]]
    matriz_shallow = mi_matriz2.copy()  # Copia superficial
    matriz_shallow[0].append(99)        # ¡Modifica también el original!    
    print(f"Original después de shallow: {mi_matriz2}")      # ¡CAMBIÓ!
    print(f"Copia shallow: {matriz_shallow}")

ejemplo_problema_copia_superficial()

# Salida del problema:
# Original después de shallow: [[1, 2, 99], [3, 4]]  <- ¡Se modificó sin querer!
# Copia shallow: [[1, 2, 99], [3, 4]]
```
🎯 La diferencia fundamental:
* **Copia Superficial (.copy())**:
✅ Crea una nueva lista principal
❌ Comparte los objetos internos (sublistas, diccionarios)
🔄 Si modificas una sublista, afecta ambas copias
* **Copia Profunda (copy.deepcopy())**:
✅ Crea una nueva lista principal
✅ Crea copias de todos los objetos internos
🔒 Modificar una copia no afecta la otra


🎯 Cuándo usar cada una:
**Superficial**: Listas con elementos inmutables (números, strings)
**Profunda**: Estructuras anidadas (listas de listas, diccionarios complejos)

💡 Regla práctica:
✅ Usa superficial cuando:
  * Elementos son inmutables (números, strings, tuplas)
  * No necesitas modificar objetos internos
  * Quieres eficiencia

⚠️ Usa profunda cuando:
  * Tienes estructuras anidadas complejas
  * Vas a modificar objetos internos
  * Necesitas independencia total

📊 TABLA COMPARATIVA:

|ASPECTO |COPIA SUPERFICIAL |COPIA PROFUNDA |
|-----------|------------------|---------------|
|Contenedor |✅ Nuevo objeto |✅ Nuevo objeto |
|Objetos internos|❌ Compartidos |✅ Nuevos objetos |
|Velocidad |⚡ Rápida |🐌 Más lenta |
|Memoria |💾 Menos uso |🗄️  Más uso |
|Independencia |⚠️  Parcial |✅ Total |
|Uso típico|📝 Listas simples|🏗️  Estructuras complejas|


## VALORES DE RETORNO (`return`)

### Función sin return

```python
def imprimir_mensaje():
    print("Este mensaje se imprime")
    # return None (implícito)

resultado = imprimir_mensaje()
print(resultado)  # Salida: None
```

### Función con return simple

```python
def calcular_cuadrado(numero):
    return numero ** 2

resultado = calcular_cuadrado(5)
print(resultado)  # Salida: 25
```

### Return múltiple

```python
def operaciones_basicas(a, b):
    suma = a + b
    resta = a - b
    multiplicacion = a * b
    division = a / b if b != 0 else None
    
    return suma, resta, multiplicacion, division

# Desempaquetado de valores
s, r, m, d = operaciones_basicas(10, 3)
print(f"Suma: {s}, Resta: {r}, Multiplicación: {m}, División: {d}")
```

### Return condicional

```python
def es_par(numero):
    if numero % 2 == 0:
        return True
    return False

# Versión más concisa
def es_par_conciso(numero):
    return numero % 2 == 0
```

## ÁMBITO DE LAS VARIABLES

### Variables locales

```python
def funcion_local():
    variable_local = "Solo existe dentro de la función"
    print(variable_local)

funcion_local()
# print(variable_local)  # Error: NameError
```

### Variables globales

```python
variable_global = "Soy global"

def usar_variable_global():
    print(variable_global)  # Lectura de variable global

def modificar_global():
    global variable_global
    variable_global = "He sido modificada"

print(variable_global)  # Salida: Soy global
usar_variable_global()  # Salida: Soy global
modificar_global()
print(variable_global)  # Salida: He sido modificada
```

### Variables no locales (nonlocal)

```python
def funcion_externa():
    variable_externa = "Desde función externa"
    
    def funcion_interna():
        nonlocal variable_externa
        variable_externa = "Modificada desde función interna"
        print(variable_externa)
    
    print(f"Antes: {variable_externa}")
    funcion_interna()
    print(f"Después: {variable_externa}")

funcion_externa()
# Salida:
# Antes: Desde función externa
# Modificada desde función interna
# Después: Modificada desde función interna

```

### Regla LEGB

Python busca variables en el siguiente orden:
1. **L**ocal - En la función actual
2. **E**nclosing - En funciones que contienen a la actual
3. **G**lobal - En el nivel del módulo
4. **B**uilt-in - En el espacio de nombres incorporado

```python
nombre = "Global"  # Global

def funcion_externa():
    nombre = "Enclosing"  # Enclosing
    
    def funcion_interna():
        nombre = "Local"  # Local
        print(f"Local: {nombre}")
    
    funcion_interna()
    print(f"Enclosing: {nombre}")

funcion_externa()
print(f"Global: {nombre}")
```

## FUNCIONES INCORPORADAS

Python proporciona muchas funciones incorporadas útiles:

### Funciones de tipo y conversión

```python
# type() - Obtener el tipo de un objeto
print(type(42))        # <class 'int'>
print(type("texto"))   # <class 'str'>
print(type([1, 2, 3])) # <class 'list'>

# isinstance() - Verificar si un objeto es de un tipo específico
print(isinstance(42, int))        # True
print(isinstance("texto", str))   # True
print(isinstance([1, 2, 3], list)) # True

# Conversiones de tipo
print(int("123"))      # 123
print(float("3.14"))   # 3.14
print(str(42))         # "42"
print(list("python"))  # ['p', 'y', 't', 'h', 'o', 'n']
```

### Funciones de secuencias

```python
# len() - Longitud de una secuencia
print(len("Python"))     # 6
print(len([1, 2, 3, 4])) # 4
print(len({"a": 1, "b": 2})) # 2

# min() y max() - Valores mínimo y máximo
numeros = [3, 1, 4, 1, 5, 9, 2, 6]
print(min(numeros))  # 1
print(max(numeros))  # 9
print(min("python")) # 'h'
print(max("python")) # 'y'

# sum() - Suma de elementos
print(sum(numeros))  # 31
print(sum([1, 2, 3, 4, 5]))  # 15

# sorted() - Lista ordenada
print(sorted(numeros))  # [1, 1, 2, 3, 4, 5, 6, 9]
print(sorted("python")) # ['h', 'n', 'o', 'p', 't', 'y']
```

### Funciones de iteración

```python
# range() - Generar secuencias numéricas
print(list(range(5)))        # [0, 1, 2, 3, 4]
print(list(range(2, 8)))     # [2, 3, 4, 5, 6, 7]
print(list(range(0, 10, 2))) # [0, 2, 4, 6, 8]

# enumerate() - Enumerar elementos con índice, que es muy útil cuando necesitas tanto el índice como el valor de cada elemento en una lista.
frutas = ["manzana", "banana", "naranja"]
for indice, fruta in enumerate(frutas):
    print(f"{indice}: {fruta}")

# zip() - Combinar iterables
nombres = ["Ana", "Juan", "Luis"]
edades = [25, 30, 35]
for nombre, edad in zip(nombres, edades):
    print(f"{nombre} tiene {edad} años")
```

### Funciones de entrada y salida

```python
# input() - Leer entrada del usuario
# nombre = input("¿Cuál es tu nombre? ")
# print(f"Hola, {nombre}")

# print() - Mostrar salida
print("Hola", "mundo", sep="-")  # Hola-mundo
print("Python", end=" ")
print("es genial")  # Python es genial
```

### Funciones matemáticas incorporadas

```python
# abs() - Valor absoluto
print(abs(-5))    # 5
print(abs(3.14))  # 3.14

# round() - Redondear
print(round(3.14159))     # 3
print(round(3.14159, 2))  # 3.14

# pow() - Potencia
print(pow(2, 3))     # 8
print(pow(2, 3, 5))  # 3 (2^3 mod 5)

# divmod() - División y módulo
print(divmod(17, 5))  # (3, 2)
```

## DOCUMENTACIÓN DE FUNCIONES
### Docstrings

Las docstrings son cadenas de documentación que describen qué hace una función:

#### Docstring simple

```python
def calcular_area_circulo(radio):
    """Calcula el área de un círculo dado su radio."""
    import math
    return math.pi * radio ** 2
```

#### Docstring detallada

```python
def calcular_imc(peso, altura):
    """
    Calcula el Índice de Masa Corporal (IMC).
    
    Args:
        peso (float): Peso en kilogramos
        altura (float): Altura en metros
    
    Returns:
        float: El IMC calculado
    
    Raises:
        ValueError: Si el peso o la altura son negativos o cero
    
    Example:
        >>> calcular_imc(70, 1.75)
        22.857142857142858
    """
    if peso <= 0 or altura <= 0:
        raise ValueError("El peso y la altura deben ser positivos")
    
    return peso / (altura ** 2)
```

#### Acceder a la documentación

```python
# Usando help()
help(calcular_imc)

# Usando __doc__
print(calcular_imc.__doc__)

# En Jupyter/IPython usando ?
# calcular_imc?
```

### Anotaciones de tipo (Type Hints)

```python
def saludar(nombre: str) -> str:
    """
    Genera un saludo personalizado.
    
    Args:
        nombre: El nombre de la persona a saludar
    
    Returns:
        Un mensaje de saludo
    """
    return f"¡Hola, {nombre}!"

def sumar(a: int, b: int) -> int:
    """Suma dos números enteros."""
    return a + b

# Con tipos más complejos
from typing import List, Dict, Optional

def procesar_lista(numeros: List[int]) -> Dict[str, int]:
    """
    Procesa una lista de números y devuelve estadísticas.
    
    Args:
        numeros: Lista de números enteros
    
    Returns:
        Diccionario con estadísticas básicas
    """
    return {
        "suma": sum(numeros),
        "minimo": min(numeros),
        "maximo": max(numeros),
        "longitud": len(numeros)
    }
```

### Ejemplo: Función con múltiples características

```python
def procesar_datos(datos: List[float], 
                   operacion: str = "suma", 
                   filtrar_negativos: bool = False,
                   **opciones) -> Dict[str, float]:
    """
    Procesa una lista de datos numéricos aplicando diferentes operaciones.
    
    Args:
        datos: Lista de números flotantes a procesar
        operacion: Tipo de operación ('suma', 'promedio', 'maximo', 'minimo')
        filtrar_negativos: Si True, excluye los números negativos
        **opciones: Opciones adicionales para el procesamiento
    
    Returns:
        Diccionario con el resultado de la operación y metadatos
    
    Raises:
        ValueError: Si la operación no es válida o si no hay datos
    """
    if not datos:
        raise ValueError("La lista de datos no puede estar vacía")
    
    # Filtrar datos si es necesario
    datos_procesados = [x for x in datos if x >= 0] if filtrar_negativos else datos
    
    if not datos_procesados:
        raise ValueError("No hay datos válidos después del filtrado")
    
    # Realizar operación
    operaciones = {
        "suma": sum(datos_procesados),
        "promedio": sum(datos_procesados) / len(datos_procesados),
        "maximo": max(datos_procesados),
        "minimo": min(datos_procesados)
    }
    
    if operacion not in operaciones:
        raise ValueError(f"Operación '{operacion}' no válida")
    
    return {
        "resultado": operaciones[operacion],
        "cantidad_datos": len(datos_procesados),
        "datos_filtrados": len(datos) - len(datos_procesados)
    }

# Ejemplo de uso
datos = [1.5, -2.3, 4.7, -1.2, 3.8, 0.5]
resultado = procesar_datos(datos, "promedio", filtrar_negativos=True)
print(resultado)
```
:computer: Actividad 1

## INTRODUCCIÓN A LAS PRUEBAS UNITARIAS

### ¿Qué son las pruebas unitarias?

Las **pruebas unitarias** son pequeños programas que verifican que nuestras funciones funcionen correctamente. Son como "exámenes" para nuestro código que nos ayudan a:

- **Detectar errores** antes de que los usuarios los encuentren
- **Verificar** que las funciones hacen lo que esperamos
- **Facilitar cambios** sin romper el código existente
- **Documentar** cómo se espera que funcione cada función

### Verificación manual vs. automática

#### Verificación manual (lo que hemos hecho hasta ahora)

```python
def sumar(a, b):
    """Suma dos números."""
    return a + b

# Probar manualmente
print(sumar(2, 3))  # Esperamos 5
print(sumar(-1, 1))  # Esperamos 0
print(sumar(0, 0))   # Esperamos 0
```

**Problemas de la verificación manual:**
- Hay que ejecutar y revisar cada resultado
- Es fácil olvidar probar casos importantes
- No se puede repetir automáticamente
- Toma mucho tiempo cuando hay muchas funciones

#### Verificación automática (pruebas unitarias)

```python
def sumar(a, b):
    """Suma dos números."""
    return a + b

def probar_sumar():
    """Prueba automática de la función sumar."""
    # Caso 1: números positivos
    resultado = sumar(2, 3)
    assert resultado == 5, f"Esperaba 5, pero obtuve {resultado}"
    
    # Caso 2: números con signo
    resultado = sumar(-1, 1)
    assert resultado == 0, f"Esperaba 0, pero obtuve {resultado}"
    
    # Caso 3: ceros
    resultado = sumar(0, 0)
    assert resultado == 0, f"Esperaba 0, pero obtuve {resultado}"
    
    print("✅ Todas las pruebas de sumar() pasaron correctamente")

# Ejecutar las pruebas
probar_sumar()
```

### Pruebas básicas con assert

La palabra clave `assert` es fundamental para las pruebas. Funciona así:

```python
# Sintaxis básica
assert condicion, "mensaje de error si falla"

# Ejemplos
assert 2 + 2 == 4, "La suma básica falló"
assert "python" == "python", "Las cadenas deberían ser iguales"
assert len([1, 2, 3]) == 3, "La lista debería tener 3 elementos"

# Si la condición es False, se lanza una excepción
try:
    assert 2 + 2 == 5, "Esto va a fallar"
except AssertionError as e:
    print(f"Error en la prueba: {e}")
```

#### Tipos comunes de verificaciones con assert

```python
def ejemplos_de_assert():
    """Ejemplos de verificaciones comunes en pruebas."""
    
    # Verificar igualdad
    assert 2 + 3 == 5
    assert "hola".upper() == "HOLA"
    
    # Verificar desigualdad
    assert 3 != 4
    assert "python" != "java"
    
    # Verificar mayor/menor
    assert 5 > 3
    assert 2 < 10
    assert 5 >= 5
    assert 3 <= 3
    
    # Verificar tipos
    assert isinstance(42, int)
    assert isinstance("texto", str)
    assert isinstance([1, 2, 3], list)
    
    # Verificar pertenencia
    assert 3 in [1, 2, 3, 4]
    assert "a" in "palabra"
    
    # Verificar longitud
    assert len("python") == 6
    assert len([1, 2, 3]) == 3
    
    # Verificar valores booleanos
    assert True
    assert not False
    assert bool([1, 2, 3])  # Lista no vacía es True
    assert not bool([])     # Lista vacía es False

ejemplos_de_assert()
print("✅ Todas las verificaciones pasaron")
```

### Organizar las pruebas

Es importante organizar las pruebas de forma clara y sistemática:

```python
def calcular_area_rectangulo(base, altura):
    """Calcula el área de un rectángulo."""
    if base < 0 or altura < 0:
        raise ValueError("Base y altura deben ser positivas")
    return base * altura

def calcular_perimetro_rectangulo(base, altura):
    """Calcula el perímetro de un rectángulo."""
    if base < 0 or altura < 0:
        raise ValueError("Base y altura deben ser positivas")
    return 2 * (base + altura)

def probar_area_rectangulo():
    """Pruebas para la función calcular_area_rectangulo."""
    print("Probando calcular_area_rectangulo...")
    
    # Caso normal
    assert calcular_area_rectangulo(5, 3) == 15
    
    # Caso con ceros
    assert calcular_area_rectangulo(0, 5) == 0
    assert calcular_area_rectangulo(4, 0) == 0
    
    # Caso con decimales
    assert calcular_area_rectangulo(2.5, 4) == 10.0
    
    # Caso de error (valores negativos)
    try:
        calcular_area_rectangulo(-1, 5)
        assert False, "Debería haber lanzado ValueError"
    except ValueError:
        pass  # Es lo esperado
    
    print("  ✅ Todas las pruebas de área pasaron")

def probar_perimetro_rectangulo():
    """Pruebas para la función calcular_perimetro_rectangulo."""
    print("Probando calcular_perimetro_rectangulo...")
    
    # Caso normal
    assert calcular_perimetro_rectangulo(5, 3) == 16
    
    # Caso cuadrado
    assert calcular_perimetro_rectangulo(4, 4) == 16
    
    # Caso con decimales
    assert calcular_perimetro_rectangulo(2.5, 1.5) == 8.0
    
    print("  ✅ Todas las pruebas de perímetro pasaron")

def ejecutar_todas_las_pruebas():
    """Ejecuta todas las pruebas del módulo."""
    print("🧪 Ejecutando pruebas unitarias...")
    print("-" * 40)
    
    probar_area_rectangulo()
    probar_perimetro_rectangulo()
    
    print("-" * 40)
    print("🎉 ¡Todas las pruebas pasaron exitosamente!")

# Ejecutar las pruebas
ejecutar_todas_las_pruebas()
```

### Casos de prueba típicos

Para cada función, deberíamos probar:

#### 1. Casos normales (happy path)
```python
def dividir(a, b):
    """Divide dos números."""
    if b == 0:
        raise ValueError("No se puede dividir por cero")
    return a / b

def probar_casos_normales():
    """Probar casos típicos de uso."""
    assert dividir(10, 2) == 5.0
    assert dividir(9, 3) == 3.0
    assert dividir(1, 4) == 0.25
```

#### 2. Casos límite (edge cases)
```python
def probar_casos_limite():
    """Probar casos en los límites."""
    assert dividir(0, 1) == 0.0    # Dividendo cero
    assert dividir(1, 1) == 1.0    # Números iguales
    assert dividir(-10, 2) == -5.0  # Números negativos
    assert dividir(10, -2) == -5.0  # Divisor negativo
```

#### 3. Casos de error
```python
def probar_casos_error():
    """Probar casos que deben producir errores."""
    try:
        dividir(5, 0)
        assert False, "Debería haber lanzado ValueError"
    except ValueError as e:
        assert "No se puede dividir por cero" in str(e)
```

### Ejemplo completo: Probando una calculadora

```python
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

def potencia(base, exponente):
    """Calcula base elevado a exponente."""
    if exponente < 0:
        raise ValueError("Exponente debe ser positivo")
    return base ** exponente

def es_par(numero):
    """Verifica si un número es par."""
    return numero % 2 == 0

# PRUEBAS UNITARIAS

def probar_operaciones_basicas():
    """Prueba las operaciones matemáticas básicas."""
    print("Probando operaciones básicas...")
    
    # Sumar
    assert sumar(2, 3) == 5
    assert sumar(-1, 1) == 0
    assert sumar(0, 0) == 0
    
    # Restar
    assert restar(5, 3) == 2
    assert restar(3, 5) == -2
    assert restar(0, 0) == 0
    
    # Multiplicar
    assert multiplicar(4, 3) == 12
    assert multiplicar(-2, 3) == -6
    assert multiplicar(0, 100) == 0
    
    print("  ✅ Operaciones básicas correctas")

def probar_division():
    """Prueba la función de división."""
    print("Probando división...")
    
    # Casos normales
    assert dividir(10, 2) == 5.0
    assert dividir(7, 2) == 3.5
    assert dividir(-10, 2) == -5.0
    
    # Casos límite
    assert dividir(0, 5) == 0.0
    assert dividir(1, 1) == 1.0
    
    # Caso de error
    try:
        dividir(5, 0)
        assert False, "Debería lanzar ValueError por división por cero"
    except ValueError as e:
        assert "No se puede dividir por cero" in str(e)
    
    print("  ✅ División funciona correctamente")

def probar_potencia():
    """Prueba la función de potencia."""
    print("Probando potencia...")
    
    # Casos normales
    assert potencia(2, 3) == 8
    assert potencia(5, 2) == 25
    assert potencia(10, 0) == 1
    assert potencia(0, 5) == 0
    
    # Caso de error
    try:
        potencia(2, -1)
        assert False, "Debería lanzar ValueError por exponente negativo"
    except ValueError:
        pass  # Es lo esperado
    
    print("  ✅ Potencia funciona correctamente")

def probar_es_par():
    """Prueba la función es_par."""
    print("Probando es_par...")
    
    # Números pares
    assert es_par(2) == True
    assert es_par(0) == True
    assert es_par(-4) == True
    assert es_par(100) == True
    
    # Números impares
    assert es_par(1) == False
    assert es_par(3) == False
    assert es_par(-5) == False
    assert es_par(99) == False
    
    print("  ✅ es_par funciona correctamente")

def ejecutar_suite_completa():
    """Ejecuta todas las pruebas de la calculadora."""
    print("🧪 SUITE DE PRUEBAS - CALCULADORA")
    print("=" * 50)
    
    # Ejecutar todas las pruebas
    probar_operaciones_basicas()
    probar_division()
    probar_potencia()
    probar_es_par()
    
    print("=" * 50)
    print("🎉 ¡TODAS LAS PRUEBAS PASARON EXITOSAMENTE!")
    print("   Tu calculadora funciona correctamente.")

# Ejecutar las pruebas
if __name__ == "__main__":
    ejecutar_suite_completa()
```

#### Estructura recomendada para pruebas

```python
def probar_mi_funcion():
    """
    Template para crear pruebas unitarias.
    
    1. Casos normales (funcionamiento típico)
    2. Casos límite (valores extremos)
    3. Casos de error (situaciones inválidas)
    """
    print("Probando mi_funcion...")
    
    # 1. CASOS NORMALES
    # assert mi_funcion(entrada_normal) == resultado_esperado
    
    # 2. CASOS LÍMITE
    # assert mi_funcion(entrada_limite) == resultado_limite
    
    # 3. CASOS DE ERROR
    # try:
    #     mi_funcion(entrada_invalida)
    #     assert False, "Debería haber dado error"
    # except TipoDeError:
    #     pass  # Es lo esperado
    
    print("  ✅ mi_funcion funciona correctamente")
```

Las pruebas unitarias son una herramienta fundamental para escribir código correcto. En temas posteriores veremos herramientas más avanzadas como `pytest`, pero con `assert` ya podemos verificar que nuestras funciones funcionen correctamente.

:computer: Actividad 2

