# FUNCIONES EN PYTHON

- [FUNCIONES EN PYTHON](#funciones-en-python)
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
  - [MÓDULOS Y PAQUETES CON FUNCIONES](#módulos-y-paquetes-con-funciones)
    - [¿Qué son los módulos?](#qué-son-los-módulos)
      - [Definición](#definición-1)
      - [Ventajas de usar módulos](#ventajas-de-usar-módulos)
    - [Importación de módulos](#importación-de-módulos)
      - [Sintaxis básica de import](#sintaxis-básica-de-import)
      - [Importar funciones específicas](#importar-funciones-específicas)
      - [Importar con alias](#importar-con-alias)
      - [Importar todo (no recomendado)](#importar-todo-no-recomendado)
      - [Importación condicional](#importación-condicional)
    - [Creación de módulos personalizados](#creación-de-módulos-personalizados)
      - [Estructura básica de un módulo](#estructura-básica-de-un-módulo)
      - [Variables especiales en módulos](#variables-especiales-en-módulos)
      - [Ejecutar código solo cuando el módulo es el principal](#ejecutar-código-solo-cuando-el-módulo-es-el-principal)
      - [Documentación de módulos](#documentación-de-módulos)
    - [Paquetes (packages)](#paquetes-packages)
      - [¿Qué es un paquete?](#qué-es-un-paquete)
      - [Estructura de directorios](#estructura-de-directorios)
      - [El archivo `__init__.py`](#el-archivo-__init__py)
      - [Importación desde paquetes](#importación-desde-paquetes)
      - [Sub-paquetes](#sub-paquetes)
    - [Algunos módulos básicos](#algunos-módulos-básicos)
      - [math - Funciones matemáticas básicas](#math---funciones-matemáticas-básicas)
      - [random - Números aleatorios básicos](#random---números-aleatorios-básicos)
    - [Ejemplo de proyecto completo con funciones](#ejemplo-de-proyecto-completo-con-funciones)
  - [INTRODUCCIÓN A LAS PRUEBAS UNITARIAS](#introducción-a-las-pruebas-unitarias)
    - [¿Qué son las pruebas unitarias?](#qué-son-las-pruebas-unitarias)
    - [Verificación manual vs. automática](#verificación-manual-vs-automática)
      - [Verificación manual (lo que hemos hecho hasta ahora)](#verificación-manual-lo-que-hemos-hecho-hasta-ahora)
      - [Verificación automática (pruebas unitarias)](#verificación-automática-pruebas-unitarias)
    - [Pruebas básicas con assert](#pruebas-básicas-con-assert)
      - [Tipos comunes de verificaciones con assert](#tipos-comunes-de-verificaciones-con-assert)
    - [Organizar las pruebas](#organizar-las-pruebas)
    - [Casos de prueba típicos](#casos-de-prueba-típicos)
      - [1. Casos normales (happy path)](#1-casos-normales-happy-path)
      - [2. Casos límite (edge cases)](#2-casos-límite-edge-cases)
      - [3. Casos de error](#3-casos-de-error)
    - [Ejemplo completo: Probando una calculadora](#ejemplo-completo-probando-una-calculadora)
      - [Estructura recomendada para pruebas](#estructura-recomendada-para-pruebas)


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

## MÓDULOS Y PAQUETES CON FUNCIONES

### ¿Qué son los módulos?

#### Definición

Un **módulo** en Python es un archivo que contiene código Python: funciones, variables y sentencias ejecutables. Los módulos permiten organizar y reutilizar código de manera eficiente.

#### Ventajas de usar módulos

- **Reutilización**: Evita duplicar código
- **Organización**: Mantiene el código ordenado y estructurado
- **Mantenimiento**: Facilita las actualizaciones y correcciones
- **Colaboración**: Permite trabajar en equipo de forma más eficiente
- **Escalabilidad**: Facilita el crecimiento de proyectos grandes

### Importación de módulos

#### Sintaxis básica de import

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

#### Importar funciones específicas

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

#### Importar con alias

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

#### Importar todo (no recomendado)

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

#### Importación condicional

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

### Creación de módulos personalizados

#### Estructura básica de un módulo

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

#### Variables especiales en módulos

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

#### Ejecutar código solo cuando el módulo es el principal

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

#### Documentación de módulos

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

### Paquetes (packages)

#### ¿Qué es un paquete?

Un **paquete** es una forma de organizar módulos relacionados en una estructura de directorios. Los paquetes permiten crear jerarquías de módulos usando la notación de punto.

#### Estructura de directorios

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

#### El archivo `__init__.py`

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
    """Cuenta las palabras en un texto."""
    return len(texto.split())

def es_palindromo(texto):
    """Verifica si un texto es un palíndromo."""
    texto_limpio = texto.replace(" ", "").lower()
    return texto_limpio == texto_limpio[::-1]
```

#### Importación desde paquetes

```python
# Importar el paquete completo
import utilidades

# Usar funciones desde el paquete
resultado = utilidades.sumar(5, 3)
print(resultado)

# Importar módulo específico
from utilidades import matematicas

# Usar funciones del módulo
print(matematicas.multiplicar(4, 7))

# Importar funciones específicas
from utilidades.texto import limpiar_texto, contar_palabras

texto = "  Hola    mundo  "
texto_limpio = limpiar_texto(texto)
print(f"Texto limpio: '{texto_limpio}'")
print(f"Número de palabras: {contar_palabras(texto_limpio)}")
```

#### Sub-paquetes

```python
# Estructura más compleja con sub-paquetes
mi_proyecto/
├── main.py
└── aplicacion/
    ├── __init__.py
    ├── core/
    │   ├── __init__.py
    │   ├── funciones_basicas.py
    │   └── validaciones.py
    └── utils/
        ├── __init__.py
        ├── formateo.py
        └── conversion.py

# Importar desde sub-paquetes
from aplicacion.core.validaciones import validar_email
from aplicacion.utils.formateo import formatear_fecha
```

### Algunos módulos básicos

#### math - Funciones matemáticas básicas

```python
import math

# Constantes matemáticas
print(f"Pi: {math.pi}")
print(f"e: {math.e}")

# Funciones de potencia y logaritmos
print(f"2^3 = {math.pow(2, 3)}")
print(f"√16 = {math.sqrt(16)}")
print(f"log(10) = {math.log10(10)}")

# Funciones trigonométricas
print(f"sin(π/2) = {math.sin(math.pi/2)}")
print(f"cos(0) = {math.cos(0)}")

# Funciones de redondeo
print(f"ceil(4.2) = {math.ceil(4.2)}")  # Redondear hacia arriba
print(f"floor(4.8) = {math.floor(4.8)}")  # Redondear hacia abajo
```

#### random - Números aleatorios básicos

```python
import random

# Número aleatorio entre 0 y 1
print(f"Random: {random.random()}")

# Número entero aleatorio en un rango
print(f"Entre 1 y 10: {random.randint(1, 10)}")

# Elegir elemento aleatorio de una lista
colores = ["rojo", "verde", "azul", "amarillo"]
color_elegido = random.choice(colores)
print(f"Color elegido: {color_elegido}")

# Mezclar una lista
numeros = [1, 2, 3, 4, 5]
random.shuffle(numeros)
print(f"Números mezclados: {numeros}")

# Usar alias
import random as rnd
print(f"Otro número aleatorio: {rnd.randint(1, 100)}")
```

### Ejemplo de proyecto completo con funciones

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
        raise ValueError("El libro ya está disponible")
    
    libro['disponible'] = True
    if id_libro in prestamos:
        del prestamos[id_libro]
    
    print(f"Libro '{libro['titulo']}' devuelto")
```

**`biblioteca/operaciones.py`**
```python
"""Funciones para operaciones y cálculos."""

from .gestion_libros import biblioteca, prestamos

def calcular_multa(dias_retraso, tarifa_dia=1.0):
    """Calcula la multa por días de retraso."""
    if dias_retraso <= 0:
        return 0.0
    return dias_retraso * tarifa_dia

def dias_prestamo():
    """Retorna el número estándar de días de préstamo."""
    return 14

def generar_reporte():
    """Genera un reporte del estado de la biblioteca."""
    total_libros = len(biblioteca)
    libros_prestados = sum(1 for libro in biblioteca if not libro['disponible'])
    libros_disponibles = total_libros - libros_prestados
    
    print("=== REPORTE DE BIBLIOTECA ===")
    print(f"Total de libros: {total_libros}")
    print(f"Libros disponibles: {libros_disponibles}")
    print(f"Libros prestados: {libros_prestados}")
    
    if prestamos:
        print("\nLibros prestados actualmente:")
        for id_libro, info in prestamos.items():
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

Este proyecto nos muestra las mejores prácticas:
- ✅ Estructura clara y organizada
- ✅ Separación de responsabilidades en diferentes módulos
- ✅ Documentación completa con docstrings
- ✅ Uso de funciones para organizar el código
- ✅ Trabajo con diccionarios y listas para almacenar datos
- ✅ Manejo de importaciones entre módulos del paquete

:computer: Actividad 2

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

:computer: Actividad 3
