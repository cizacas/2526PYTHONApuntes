# FUNCIONES EN PYTHON

- [FUNCIONES EN PYTHON](#funciones-en-python)
  - [Definición y creación de funciones con `def`](#definición-y-creación-de-funciones-con-def)
    - [Sintaxis básica](#sintaxis-básica)
    - [Ejemplo básico](#ejemplo-básico)
    - [Convenciones de nomenclatura](#convenciones-de-nomenclatura)
  - [Parámetros y argumentos](#parámetros-y-argumentos)
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
    - [Función con return simple](#función-con-return-simple)
    - [Return múltiple](#return-múltiple)
    - [Return condicional](#return-condicional)
  - [Ámbito de las variables](#ámbito-de-las-variables)
    - [Variables locales](#variables-locales)
    - [Variables globales](#variables-globales)
    - [Variables no locales (nonlocal)](#variables-no-locales-nonlocal)
    - [Regla LEGB](#regla-legb)
  - [Funciones incorporadas](#funciones-incorporadas)
    - [Funciones de tipo y conversión](#funciones-de-tipo-y-conversión)
    - [Funciones de secuencias](#funciones-de-secuencias)
    - [Funciones de iteración](#funciones-de-iteración)
    - [Funciones de entrada y salida](#funciones-de-entrada-y-salida)
    - [Funciones matemáticas incorporadas](#funciones-matemáticas-incorporadas)
  - [Documentación de funciones](#documentación-de-funciones)
    - [Docstrings](#docstrings)
      - [Docstring simple](#docstring-simple)
      - [Docstring detallada](#docstring-detallada)
      - [Acceder a la documentación](#acceder-a-la-documentación)
    - [Anotaciones de tipo (Type Hints)](#anotaciones-de-tipo-type-hints)
    - [Ejemplos completos](#ejemplos-completos)
      - [Función con documentación completa](#función-con-documentación-completa)
      - [Función con múltiples características](#función-con-múltiples-características)
  - [Ejercicios prácticos](#ejercicios-prácticos)
    - [Ejercicio 1: Calculadora básica](#ejercicio-1-calculadora-básica)
    - [Ejercicio 2: Validador de contraseña](#ejercicio-2-validador-de-contraseña)
  - [Pruebas unitarias](#pruebas-unitarias)
    - [¿Qué son las pruebas unitarias?](#qué-son-las-pruebas-unitarias)
    - [Introducción al módulo unittest](#introducción-al-módulo-unittest)
    - [Métodos de verificación (assertions)](#métodos-de-verificación-assertions)
      - [Assertions básicas](#assertions-básicas)
    - [Ejemplos prácticos de pruebas](#ejemplos-prácticos-de-pruebas)
      - [Función para validar email](#función-para-validar-email)
      - [Función calculadora con pruebas completas](#función-calculadora-con-pruebas-completas)
    - [Técnicas avanzadas de testing](#técnicas-avanzadas-de-testing)
      - [Mock y patching (simulación)](#mock-y-patching-simulación)
      - [Fixtures y datos de prueba](#fixtures-y-datos-de-prueba)
    - [Organizando y ejecutando pruebas](#organizando-y-ejecutando-pruebas)
      - [Estructura de archivos de prueba](#estructura-de-archivos-de-prueba)
      - [Script para ejecutar pruebas](#script-para-ejecutar-pruebas)
    - [Mejores prácticas para pruebas unitarias](#mejores-prácticas-para-pruebas-unitarias)
      - [1. Nomenclatura clara](#1-nomenclatura-clara)
      - [2. Principio AAA (Arrange, Act, Assert)](#2-principio-aaa-arrange-act-assert)
      - [3. Una sola cosa por prueba](#3-una-sola-cosa-por-prueba)
      - [4. Cobertura de casos extremos](#4-cobertura-de-casos-extremos)
    - [Ejemplo completo: Sistema de gestión de estudiantes](#ejemplo-completo-sistema-de-gestión-de-estudiantes)
    - [Herramientas adicionales para testing](#herramientas-adicionales-para-testing)
      - [Coverage (cobertura de código)](#coverage-cobertura-de-código)
      - [pytest (alternativa a unittest)](#pytest-alternativa-a-unittest)
    - [Integración con VS Code](#integración-con-vs-code)
  - [Ejercicios prácticos](#ejercicios-prácticos-1)
    - [Ejercicio 1: Crear pruebas para una función de validación](#ejercicio-1-crear-pruebas-para-una-función-de-validación)
    - [Ejercicio 2: Testing de una clase completa](#ejercicio-2-testing-de-una-clase-completa)
  - [Resumen](#resumen)


## Definición y creación de funciones con `def`

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

## Parámetros y argumentos

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
```

#### Objetos mutables (list, dict, set)

**Con objetos mutables, la referencia apunta al mismo objeto y SÍ se puede modificar directamente:**

```python
def modificar_lista(lista):
    print(f"Lista recibida ID: {id(lista)}")
    lista.append(4)  # Modifica el objeto original directamente
    print(f"Lista después ID: {id(lista)}")  # Mismo ID
    print(f"Dentro de la función: {lista}")

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

**Comparación visual del comportamiento:**

```python
def ejemplo_completo():
    # INMUTABLES: Efecto "copia" (pero no es copia real)
    def probar_inmutable(valor):
        print(f"  Inmutable - ID recibido: {id(valor)}")
        valor = valor * 2  # Crea nuevo objeto
        print(f"  Inmutable - ID después: {id(valor)}")
        return valor
    
    # MUTABLES: Modificación directa
    def probar_mutable(lista):
        print(f"  Mutable - ID recibido: {id(lista)}")
        lista.extend([4, 5])  # Modifica el objeto original
        print(f"  Mutable - ID después: {id(lista)}")
        return lista
    
    # Prueba con inmutable
    numero = 10
    print(f"INMUTABLE - Número original: {numero}, ID: {id(numero)}")
    numero_modificado = probar_inmutable(numero)
    print(f"INMUTABLE - Original: {numero}, Modificado: {numero_modificado}")
    print(f"INMUTABLE - IDs diferentes: {id(numero)} vs {id(numero_modificado)}")
    
    print("\n" + "="*50 + "\n")
    
    # Prueba con mutable
    lista = [1, 2, 3]
    print(f"MUTABLE - Lista original: {lista}, ID: {id(lista)}")
    lista_modificada = probar_mutable(lista)
    print(f"MUTABLE - Original: {lista}, Retornada: {lista_modificada}")
    print(f"MUTABLE - Mismo ID: {id(lista)} == {id(lista_modificada)}")
    print(f"MUTABLE - Son el mismo objeto: {lista is lista_modificada}")

ejemplo_completo()
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

def ejemplo_diferencias_copia():
    """Demuestra la diferencia clave entre copia superficial y profunda."""
    
    print("=== COPIA SUPERFICIAL vs PROFUNDA ===\n")
    
    # Estructura anidada para demostrar la diferencia
    lista_anidada = [[1, 2], [3, 4], {"a": 5}]
    print(f"Lista original: {lista_anidada}")
    print(f"IDs originales: lista={id(lista_anidada)}, sublista1={id(lista_anidada[0])}, dict={id(lista_anidada[2])}\n")
    
    # 1. COPIA SUPERFICIAL (.copy() o copy.copy())
    print("1. COPIA SUPERFICIAL:")
    copia_superficial = lista_anidada.copy()  # También: copy.copy(lista_anidada)
    
    print(f"   Lista copia: {copia_superficial}")
    print(f"   IDs copia: lista={id(copia_superficial)}, sublista1={id(copia_superficial[0])}, dict={id(copia_superficial[2])}")
    print(f"   ¿Misma lista? {lista_anidada is copia_superficial}")  # False
    print(f"   ¿Misma sublista[0]? {lista_anidada[0] is copia_superficial[0]}")  # True ← PROBLEMA
    print(f"   ¿Mismo diccionario? {lista_anidada[2] is copia_superficial[2]}")  # True ← PROBLEMA
    
    # Modificar la copia superficial
    copia_superficial[0].append(99)  # Modifica la sublista compartida
    copia_superficial[2]["b"] = 6    # Modifica el diccionario compartido
    
    print(f"\n   Después de modificar copia superficial:")
    print(f"   Original: {lista_anidada}")  # ¡CAMBIÓ! porque comparten objetos internos
    print(f"   Copia: {copia_superficial}")
    
    print("\n" + "-"*60 + "\n")
    
    # 2. COPIA PROFUNDA (copy.deepcopy())
    print("2. COPIA PROFUNDA:")
    lista_anidada2 = [[1, 2], [3, 4], {"a": 5}]  # Nueva lista para la prueba
    copia_profunda = copy.deepcopy(lista_anidada2)
    
    print(f"   Lista original: {lista_anidada2}")
    print(f"   Lista copia: {copia_profunda}")
    print(f"   IDs original: lista={id(lista_anidada2)}, sublista1={id(lista_anidada2[0])}, dict={id(lista_anidada2[2])}")
    print(f"   IDs copia: lista={id(copia_profunda)}, sublista1={id(copia_profunda[0])}, dict={id(copia_profunda[2])}")
    print(f"   ¿Misma lista? {lista_anidada2 is copia_profunda}")  # False
    print(f"   ¿Misma sublista[0]? {lista_anidada2[0] is copia_profunda[0]}")  # False ← BUENO
    print(f"   ¿Mismo diccionario? {lista_anidada2[2] is copia_profunda[2]}")  # False ← BUENO
    
    # Modificar la copia profunda
    copia_profunda[0].append(99)  # Solo modifica la copia
    copia_profunda[2]["b"] = 6    # Solo modifica la copia
    
    print(f"\n   Después de modificar copia profunda:")
    print(f"   Original: {lista_anidada2}")  # ¡NO CAMBIÓ! objetos completamente separados
    print(f"   Copia: {copia_profunda}")

def comparacion_visual_copias():
    """Visualización clara de las diferencias."""
    print("\n=== RESUMEN VISUAL ===")
    print("""
    ESTRUCTURA ORIGINAL: [sublista1, sublista2, diccionario]
                        ↓
    
    COPIA SUPERFICIAL (.copy()):
    ✓ Crea nueva lista principal
    ✗ Comparte objetos internos (sublistas, diccionarios)
    
    Original:  [sublista1] ──┐
                            ├── Misma sublista en memoria
    Copia:     [sublista1] ──┘
    
    COPIA PROFUNDA (copy.deepcopy()):
    ✓ Crea nueva lista principal  
    ✓ Crea copias de todos los objetos internos
    
    Original:  [sublista1] ── sublista independiente
    Copia:     [sublista1'] ── sublista independiente (diferente)
    """)

# Ejecutar ejemplos
ejemplo_diferencias_copia()
comparacion_visual_copias()

# Ejemplo práctico: cuándo usar cada una
def cuando_usar_cada_copia():
    print("\n=== CUÁNDO USAR CADA TIPO ===")
    
    # Copia superficial: suficiente para listas simples
    numeros = [1, 2, 3, 4, 5]
    numeros_copia = numeros.copy()  # Suficiente, son inmutables
    numeros_copia.append(6)
    print(f"Lista simple - Original: {numeros}, Copia: {numeros_copia}")
    
    # Copia profunda: necesaria para estructuras complejas
    matriz = [[1, 2], [3, 4]]
    matriz_shallow = matriz.copy()
    matriz_deep = copy.deepcopy(matriz)
    
    matriz_shallow[0].append(99)  # Afecta original
    matriz_deep[0].append(88)     # No afecta original
    
    print(f"Matriz - Original: {matriz}")
    print(f"Matriz - Shallow: {matriz_shallow}")  
    print(f"Matriz - Deep: {matriz_deep}")

cuando_usar_cada_copia()

### ⚠️ **ACLARACIÓN IMPORTANTE: Mutabilidad vs Tipo de Copia**

**¡NO confundir!** El tipo de copia (superficial/profunda) **NO depende automáticamente** de si los elementos son mutables o inmutables. **Tú decides qué método usar:**

```python
def aclaracion_mutabilidad_vs_copia():
    print("=== ACLARACIÓN: MUTABILIDAD vs TIPO DE COPIA ===\n")
    
    # CASO 1: Lista con elementos INMUTABLES
    lista_numeros = [1, 2, 3, 4, 5]  # Números son inmutables
    
    # Puedes hacer AMBOS tipos de copia:
    shallow_numeros = lista_numeros.copy()        # Copia superficial
    deep_numeros = copy.deepcopy(lista_numeros)   # Copia profunda
    
    print("Lista con elementos inmutables:")
    print(f"Original: {lista_numeros}")
    print(f"Shallow:  {shallow_numeros}")
    print(f"Deep:     {deep_numeros}")
    print(f"¿Son iguales las copias? {shallow_numeros == deep_numeros}")  # True
    print(f"¿Mismo objeto shallow? {lista_numeros is shallow_numeros}")    # False
    print(f"¿Mismo objeto deep? {lista_numeros is deep_numeros}")          # False
    
    # Para elementos inmutables, AMBAS copias son funcionalmente equivalentes
    # porque no puedes modificar los elementos internos de ninguna manera
    
    print("\n" + "-"*50 + "\n")
    
    # CASO 2: Lista con elementos MUTABLES  
    lista_listas = [[1, 2], [3, 4]]  # Sublistas son mutables
    
    # Puedes hacer AMBOS tipos de copia, pero con diferente comportamiento:
    shallow_listas = lista_listas.copy()        # Copia superficial - COMPARTE sublistas
    deep_listas = copy.deepcopy(lista_listas)   # Copia profunda - INDEPENDIZA sublistas
    
    print("Lista con elementos mutables ANTES de modificar:")
    print(f"Original: {lista_listas}")
    print(f"Shallow:  {shallow_listas}")  
    print(f"Deep:     {deep_listas}")
    
    # Modificar para ver la diferencia
    shallow_listas[0].append(99)  # Afecta también al original
    deep_listas[0].append(88)     # NO afecta al original
    
    print("\nDESPUÉS de modificar:")
    print(f"Original: {lista_listas}")    # ¡Cambió por shallow!
    print(f"Shallow:  {shallow_listas}")  # Cambió (comparte con original)
    print(f"Deep:     {deep_listas}")     # Solo cambió esta copia
    
    print("\n" + "="*60 + "\n")

def regla_practica():
    """Regla práctica para decidir qué tipo de copia usar."""
    print("🎯 REGLA PRÁCTICA:")
    print("""
    ┌─────────────────────────────────────────────────────────┐
    │  DECIDE TÚ qué tipo de copia usar según tu NECESIDAD:   │
    ├─────────────────────────────────────────────────────────┤
    │                                                         │
    │  🔸 COPIA SUPERFICIAL (.copy()):                       │
    │     ✓ Lista simple con elementos inmutables             │
    │     ✓ Quieres compartir objetos internos                │
    │     ✓ Más rápida y usa menos memoria                    │
    │                                                         │
    │  🔸 COPIA PROFUNDA (copy.deepcopy()):                  │
    │     ✓ Estructuras anidadas complejas                    │ 
    │     ✓ Necesitas independencia total                     │
    │     ✓ Vas a modificar objetos internos                  │
    │                                                         │
    └─────────────────────────────────────────────────────────┘
    """)
    
    # Ejemplos prácticos
    print("EJEMPLOS PRÁCTICOS:")
    
    # Cuando shallow es suficiente
    print("\n✅ SHALLOW SUFICIENTE:")
    coordenadas = [(1, 2), (3, 4), (5, 6)]  # Tuplas son inmutables
    coord_copia = coordenadas.copy()
    coord_copia.append((7, 8))  # Solo modifica la lista, no las tuplas
    print(f"Original: {coordenadas}")
    print(f"Copia:    {coord_copia}")
    
    # Cuando necesitas deep
    print("\n⚠️  DEEP NECESARIO:")
    estudiantes = [
        {"nombre": "Ana", "notas": [8, 9]},
        {"nombre": "Juan", "notas": [7, 6]}
    ]
    
    est_shallow = estudiantes.copy()
    est_deep = copy.deepcopy(estudiantes)
    
    # Modificar notas
    est_shallow[0]["notas"].append(10)  # ¡Afecta original!
    est_deep[0]["notas"].append(5)      # No afecta original
    
    print(f"Original: {estudiantes}")
    print(f"Shallow:  {est_shallow}")
    print(f"Deep:     {est_deep}")

# Ejecutar aclaraciones
aclaracion_mutabilidad_vs_copia()
regla_practica()

### 📋 **RESUMEN: Los DOS tipos de copia en Python**

**✅ CORRECTO: Python maneja DOS tipos principales de copia:**

```python
def resumen_tipos_copia():
    """Resumen definitivo de los dos tipos de copia en Python."""
    
    print("🐍 PYTHON: DOS TIPOS DE COPIA")
    print("="*50)
    
    lista_ejemplo = [1, [2, 3], {"a": 4}]
    
    print(f"📊 Lista original: {lista_ejemplo}")
    print(f"    ID original: {id(lista_ejemplo)}")
    print(f"    ID sublista: {id(lista_ejemplo[1])}")
    print(f"    ID diccionario: {id(lista_ejemplo[2])}")
    
    print("\n1️⃣ COPIA SUPERFICIAL (Shallow Copy):")
    print("   Métodos: .copy(), list(), [:], copy.copy()")
    
    copia_superficial = lista_ejemplo.copy()
    print(f"   Resultado: {copia_superficial}")
    print(f"   ID nueva lista: {id(copia_superficial)}")
    print(f"   ID sublista: {id(copia_superficial[1])}")      # ¡MISMO!
    print(f"   ID diccionario: {id(copia_superficial[2])}")   # ¡MISMO!
    print("   ⚠️  Comparte objetos internos con el original")
    
    print("\n2️⃣ COPIA PROFUNDA (Deep Copy):")
    print("   Método: copy.deepcopy()")
    
    copia_profunda = copy.deepcopy(lista_ejemplo)
    print(f"   Resultado: {copia_profunda}")
    print(f"   ID nueva lista: {id(copia_profunda)}")
    print(f"   ID sublista: {id(copia_profunda[1])}")       # DIFERENTE
    print(f"   ID diccionario: {id(copia_profunda[2])}")    # DIFERENTE  
    print("   ✅ Crea objetos completamente independientes")

def tabla_comparativa():
    """Tabla comparativa de los dos tipos de copia."""
    
    print("\n📊 TABLA COMPARATIVA:")
    print("""
    ┌────────────────┬─────────────────────┬──────────────────────┐
    │   ASPECTO      │   COPIA SUPERFICIAL │    COPIA PROFUNDA    │
    ├────────────────┼─────────────────────┼──────────────────────┤
    │ Contenedor     │ ✅ Nuevo objeto     │ ✅ Nuevo objeto      │
    │ Objetos internos│ ❌ Compartidos     │ ✅ Nuevos objetos    │
    │ Velocidad      │ ⚡ Rápida          │ 🐌 Más lenta        │
    │ Memoria        │ 💾 Menos uso       │ 🗄️  Más uso          │
    │ Independencia  │ ⚠️  Parcial        │ ✅ Total             │
    │ Uso típico     │ 📝 Listas simples  │ 🏗️  Estructuras      │
    │                │                     │    complejas         │
    └────────────────┴─────────────────────┴──────────────────────┘
    """)

def metodos_disponibles():
    """Muestra todos los métodos disponibles para cada tipo."""
    
    print("🔧 MÉTODOS DISPONIBLES:")
    print("\n🔹 PARA COPIA SUPERFICIAL:")
    lista = [1, 2, [3, 4]]
    
    metodo1 = lista.copy()           # Método .copy()
    metodo2 = list(lista)            # Constructor list()
    metodo3 = lista[:]               # Slicing completo
    metodo4 = copy.copy(lista)       # Función copy.copy()
    
    print("   • lista.copy()")
    print("   • list(lista)")
    print("   • lista[:]") 
    print("   • copy.copy(lista)")
    print("   ➡️ Todos producen el MISMO resultado")
    
    print("\n🔹 PARA COPIA PROFUNDA:")
    metodo5 = copy.deepcopy(lista)   # Único método
    
    print("   • copy.deepcopy(lista)")
    print("   ➡️ Único método disponible")
    
    # Verificar que shallow son iguales
    print(f"\n✅ Verificación - Todas las copias superficiales son iguales:")
    print(f"   .copy() == list(): {metodo1 == metodo2}")
    print(f"   .copy() == [:]: {metodo1 == metodo3}")
    print(f"   .copy() == copy.copy(): {metodo1 == metodo4}")
    
    print(f"\n🔍 Pero los objetos internos son los mismos (shallow):")
    print(f"   Original sublista ID: {id(lista[2])}")
    print(f"   Shallow sublista ID:  {id(metodo1[2])}")
    print(f"   Deep sublista ID:     {id(metodo5[2])}")
    print(f"   Shallow == Original: {lista[2] is metodo1[2]}")  # True
    print(f"   Deep == Original: {lista[2] is metodo5[2]}")     # False

# Ejecutar resumen completo
resumen_tipos_copia()
tabla_comparativa() 
metodos_disponibles()
```
```

---

## Valores de retorno (`return`)

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

---

## Ámbito de las variables

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

---

## Funciones incorporadas

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

# enumerate() - Enumerar elementos con índice
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

---

## Documentación de funciones

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

### Ejemplos completos

#### Función con documentación completa

```python
def factorial(n: int) -> int:
    """
    Calcula el factorial de un número entero no negativo.
    
    El factorial de n (n!) es el producto de todos los enteros 
    positivos menores o iguales a n.
    
    Args:
        n (int): Número entero no negativo
    
    Returns:
        int: El factorial de n
    
    Raises:
        ValueError: Si n es negativo
        TypeError: Si n no es un entero
    
    Examples:
        >>> factorial(0)
        1
        >>> factorial(5)
        120
        >>> factorial(-1)
        ValueError: El número debe ser no negativo
    """
    if not isinstance(n, int):
        raise TypeError("El argumento debe ser un entero")
    
    if n < 0:
        raise ValueError("El número debe ser no negativo")
    
    if n == 0 or n == 1:
        return 1
    
    resultado = 1
    for i in range(2, n + 1):
        resultado *= i
    
    return resultado

# Ejemplo de uso con manejo de errores
try:
    print(factorial(5))  # 120
    print(factorial(-1)) # Lanza ValueError
except ValueError as e:
    print(f"Error: {e}")
```

#### Función con múltiples características

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

## Ejercicios prácticos

### Ejercicio 1: Calculadora básica

```python
def calculadora(a: float, b: float, operacion: str) -> float:
    """
    Realiza operaciones matemáticas básicas.
    
    Args:
        a: Primer número
        b: Segundo número
        operacion: Tipo de operación ('+', '-', '*', '/')
    
    Returns:
        Resultado de la operación
    """
    if operacion == '+':
        return a + b
    elif operacion == '-':
        return a - b
    elif operacion == '*':
        return a * b
    elif operacion == '/':
        if b == 0:
            raise ValueError("No se puede dividir por cero")
        return a / b
    else:
        raise ValueError("Operación no válida")
```

### Ejercicio 2: Validador de contraseña

```python
def validar_contraseña(contraseña: str) -> Dict[str, bool]:
    """
    Valida una contraseña según criterios de seguridad.
    
    Args:
        contraseña: La contraseña a validar
    
    Returns:
        Diccionario con los resultados de validación
    """
    import string
    
    criterios = {
        "longitud_minima": len(contraseña) >= 8,
        "tiene_mayuscula": any(c.isupper() for c in contraseña),
        "tiene_minuscula": any(c.islower() for c in contraseña),
        "tiene_numero": any(c.isdigit() for c in contraseña),
        "tiene_especial": any(c in string.punctuation for c in contraseña)
    }
    
    criterios["es_valida"] = all(criterios.values())
    
    return criterios
```

---

## Pruebas unitarias

Las pruebas unitarias son fundamentales para verificar que nuestras funciones funcionan correctamente. Python proporciona el módulo `unittest` incorporado para crear y ejecutar pruebas.

### ¿Qué son las pruebas unitarias?

Las pruebas unitarias son pequeños fragmentos de código que verifican el comportamiento de una unidad específica de código (generalmente una función o método). Su objetivo es:

- **Verificar** que el código funciona como se espera
- **Detectar errores** temprano en el desarrollo
- **Facilitar refactoring** con confianza
- **Documentar** el comportamiento esperado del código

### Introducción al módulo unittest

```python
import unittest

def sumar(a, b):
    """Suma dos números."""
    return a + b

def dividir(a, b):
    """Divide dos números."""
    if b == 0:
        raise ValueError("No se puede dividir por cero")
    return a / b

class TestOperacionesMatematicas(unittest.TestCase):
    
    def test_sumar_numeros_positivos(self):
        """Prueba suma de números positivos."""
        resultado = sumar(3, 4)
        self.assertEqual(resultado, 7)
    
    def test_sumar_numeros_negativos(self):
        """Prueba suma con números negativos."""
        resultado = sumar(-2, -3)
        self.assertEqual(resultado, -5)
    
    def test_dividir_numeros_normales(self):
        """Prueba división normal."""
        resultado = dividir(10, 2)
        self.assertEqual(resultado, 5.0)
    
    def test_dividir_por_cero(self):
        """Prueba que dividir por cero lance excepción."""
        with self.assertRaises(ValueError):
            dividir(10, 0)

# Ejecutar las pruebas
if __name__ == '__main__':
    unittest.main()
```

### Métodos de verificación (assertions)

#### Assertions básicas

```python
import unittest

class TestAssertions(unittest.TestCase):
    
    def test_assertions_basicas(self):
        # Igualdad
        self.assertEqual(2 + 2, 4)
        self.assertNotEqual(2 + 2, 5)
        
        # Verdadero/Falso
        self.assertTrue(True)
        self.assertFalse(False)
        
        # None
        self.assertIsNone(None)
        self.assertIsNotNone("algo")
        
        # Tipos
        self.assertIsInstance(42, int)
        
        # Contenido en secuencias
        self.assertIn(3, [1, 2, 3, 4])
        self.assertNotIn(5, [1, 2, 3, 4])
        
        # Aproximación para flotantes
        self.assertAlmostEqual(3.14159, 3.14, places=2)
```

### Ejemplos prácticos de pruebas

#### Función para validar email

```python
import re

def validar_email(email):
    """
    Valida si un email tiene formato correcto.
    
    Args:
        email (str): Email a validar
    
    Returns:
        bool: True si el email es válido, False en caso contrario
    """
    if not isinstance(email, str):
        return False
    
    patron = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    return bool(re.match(patron, email))

# Pruebas para la función validar_email
class TestValidarEmail(unittest.TestCase):
    
    def test_email_valido(self):
        """Prueba emails válidos."""
        emails_validos = [
            "usuario@ejemplo.com",
            "test.email@dominio.org",
            "usuario123@ejemplo.es",
            "mi.email+tag@dominio.co.uk"
        ]
        
        for email in emails_validos:
            with self.subTest(email=email):
                self.assertTrue(validar_email(email))
    
    def test_email_invalido(self):
        """Prueba emails inválidos."""
        emails_invalidos = [
            "usuario@",
            "@dominio.com",
            "usuario.dominio.com",
            "usuario@",
            "",
            "usuario@dominio",
            "usuario@@dominio.com"
        ]
        
        for email in emails_invalidos:
            with self.subTest(email=email):
                self.assertFalse(validar_email(email))
    
    def test_tipo_incorrecto(self):
        """Prueba con tipos que no son string."""
        self.assertFalse(validar_email(123))
        self.assertFalse(validar_email(None))
        self.assertFalse(validar_email(['email']))
```

#### Función calculadora con pruebas completas

```python
def calculadora_avanzada(operacion, *numeros):
    """
    Calculadora que puede realizar diferentes operaciones con múltiples números.
    
    Args:
        operacion (str): Tipo de operación ('suma', 'multiplicacion', 'promedio')
        *numeros: Números sobre los que realizar la operación
    
    Returns:
        float: Resultado de la operación
    
    Raises:
        ValueError: Si la operación no es válida o no hay números
        TypeError: Si algún número no es numérico
    """
    if not numeros:
        raise ValueError("Debe proporcionar al menos un número")
    
    # Verificar que todos los argumentos sean números
    for num in numeros:
        if not isinstance(num, (int, float)):
            raise TypeError(f"Todos los argumentos deben ser números, recibido: {type(num)}")
    
    if operacion == "suma":
        return sum(numeros)
    elif operacion == "multiplicacion":
        resultado = 1
        for num in numeros:
            resultado *= num
        return resultado
    elif operacion == "promedio":
        return sum(numeros) / len(numeros)
    else:
        raise ValueError(f"Operación '{operacion}' no soportada")

# Pruebas completas
class TestCalculadoraAvanzada(unittest.TestCase):
    
    def setUp(self):
        """Configuración que se ejecuta antes de cada prueba."""
        self.numeros_prueba = [2, 4, 6, 8]
        self.numeros_flotante = [1.5, 2.5, 3.0]
    
    def test_suma(self):
        """Prueba operación de suma."""
        resultado = calculadora_avanzada("suma", *self.numeros_prueba)
        self.assertEqual(resultado, 20)
        
        resultado_float = calculadora_avanzada("suma", *self.numeros_flotante)
        self.assertAlmostEqual(resultado_float, 7.0)
    
    def test_multiplicacion(self):
        """Prueba operación de multiplicación."""
        resultado = calculadora_avanzada("multiplicacion", 2, 3, 4)
        self.assertEqual(resultado, 24)
        
        resultado_con_cero = calculadora_avanzada("multiplicacion", 5, 0, 3)
        self.assertEqual(resultado_con_cero, 0)
    
    def test_promedio(self):
        """Prueba operación de promedio."""
        resultado = calculadora_avanzada("promedio", *self.numeros_prueba)
        self.assertEqual(resultado, 5.0)
        
        resultado_impar = calculadora_avanzada("promedio", 1, 2, 3)
        self.assertAlmostEqual(resultado_impar, 2.0)
    
    def test_operacion_invalida(self):
        """Prueba que operación inválida lance excepción."""
        with self.assertRaises(ValueError) as cm:
            calculadora_avanzada("division", 10, 2)
        
        self.assertIn("no soportada", str(cm.exception))
    
    def test_sin_numeros(self):
        """Prueba que sin números lance excepción."""
        with self.assertRaises(ValueError):
            calculadora_avanzada("suma")
    
    def test_tipos_incorrectos(self):
        """Prueba que tipos incorrectos lancen excepción."""
        with self.assertRaises(TypeError):
            calculadora_avanzada("suma", 1, "2", 3)
        
        with self.assertRaises(TypeError):
            calculadora_avanzada("suma", 1, None, 3)
    
    def tearDown(self):
        """Limpieza que se ejecuta después de cada prueba."""
        # En este caso no necesitamos limpiar nada
        pass

# Ejecutar solo estas pruebas
if __name__ == '__main__':
    # Crear suite de pruebas
    suite = unittest.TestSuite()
    suite.addTest(unittest.makeSuite(TestCalculadoraAvanzada))
    
    # Ejecutar con más información
    runner = unittest.TextTestRunner(verbosity=2)
    runner.run(suite)
```

### Técnicas avanzadas de testing

#### Mock y patching (simulación)

```python
from unittest.mock import patch, Mock
import requests

def obtener_clima(ciudad):
    """
    Obtiene información del clima de una ciudad usando una API externa.
    
    Args:
        ciudad (str): Nombre de la ciudad
    
    Returns:
        dict: Información del clima
    """
    url = f"http://api.clima.com/v1/weather?city={ciudad}"
    response = requests.get(url)
    
    if response.status_code == 200:
        return response.json()
    else:
        raise Exception(f"Error al obtener clima: {response.status_code}")

class TestObtenerClima(unittest.TestCase):
    
    @patch('requests.get')
    def test_clima_exitoso(self, mock_get):
        """Prueba obtención exitosa del clima."""
        # Configurar el mock
        mock_response = Mock()
        mock_response.status_code = 200
        mock_response.json.return_value = {
            "ciudad": "Madrid",
            "temperatura": 25,
            "descripcion": "Soleado"
        }
        mock_get.return_value = mock_response
        
        # Ejecutar función
        resultado = obtener_clima("Madrid")
        
        # Verificar resultado
        self.assertEqual(resultado["ciudad"], "Madrid")
        self.assertEqual(resultado["temperatura"], 25)
        
        # Verificar que se llamó correctamente
        mock_get.assert_called_once_with("http://api.clima.com/v1/weather?city=Madrid")
    
    @patch('requests.get')
    def test_clima_error(self, mock_get):
        """Prueba manejo de error en API."""
        mock_response = Mock()
        mock_response.status_code = 404
        mock_get.return_value = mock_response
        
        with self.assertRaises(Exception) as cm:
            obtener_clima("CiudadInexistente")
        
        self.assertIn("404", str(cm.exception))
```

#### Fixtures y datos de prueba

```python
class TestConDatos(unittest.TestCase):
    
    @classmethod
    def setUpClass(cls):
        """Se ejecuta una vez al inicio de todas las pruebas de la clase."""
        print("Configurando datos para toda la clase")
        cls.datos_grandes = list(range(1000000))  # Datos costosos de crear
    
    def setUp(self):
        """Se ejecuta antes de cada prueba individual."""
        self.datos_prueba = {
            "usuarios": [
                {"id": 1, "nombre": "Ana", "edad": 25},
                {"id": 2, "nombre": "Juan", "edad": 30},
                {"id": 3, "nombre": "Luis", "edad": 35}
            ]
        }
    
    def test_buscar_usuario_existente(self):
        """Prueba búsqueda de usuario existente."""
        def buscar_usuario_por_id(usuarios, user_id):
            return next((u for u in usuarios if u["id"] == user_id), None)
        
        usuario = buscar_usuario_por_id(self.datos_prueba["usuarios"], 2)
        self.assertIsNotNone(usuario)
        self.assertEqual(usuario["nombre"], "Juan")
    
    def test_buscar_usuario_inexistente(self):
        """Prueba búsqueda de usuario inexistente."""
        def buscar_usuario_por_id(usuarios, user_id):
            return next((u for u in usuarios if u["id"] == user_id), None)
        
        usuario = buscar_usuario_por_id(self.datos_prueba["usuarios"], 999)
        self.assertIsNone(usuario)
    
    @classmethod
    def tearDownClass(cls):
        """Se ejecuta una vez al final de todas las pruebas de la clase."""
        print("Limpiando datos de la clase")
        del cls.datos_grandes
```

### Organizando y ejecutando pruebas

#### Estructura de archivos de prueba

```
mi_proyecto/
├── src/
│   ├── __init__.py
│   ├── calculadora.py
│   └── utils.py
├── tests/
│   ├── __init__.py
│   ├── test_calculadora.py
│   ├── test_utils.py
│   └── test_integracion.py
└── run_tests.py
```

#### Script para ejecutar pruebas

```python
# run_tests.py
import unittest
import sys
import os

# Agregar src al path para importar módulos
sys.path.insert(0, os.path.join(os.path.dirname(__file__), 'src'))

def ejecutar_todas_las_pruebas():
    """Ejecuta todas las pruebas del proyecto."""
    # Descubrir y ejecutar todas las pruebas
    loader = unittest.TestLoader()
    suite = loader.discover('tests', pattern='test_*.py')
    
    runner = unittest.TextTestRunner(verbosity=2)
    result = runner.run(suite)
    
    # Retornar código de salida apropiado
    return 0 if result.wasSuccessful() else 1

def ejecutar_pruebas_especificas(modulo):
    """Ejecuta pruebas de un módulo específico."""
    suite = unittest.TestLoader().loadTestsFromName(f'tests.{modulo}')
    runner = unittest.TextTestRunner(verbosity=2)
    result = runner.run(suite)
    
    return 0 if result.wasSuccessful() else 1

if __name__ == '__main__':
    if len(sys.argv) > 1:
        # Ejecutar pruebas específicas
        modulo = sys.argv[1]
        exit_code = ejecutar_pruebas_especificas(modulo)
    else:
        # Ejecutar todas las pruebas
        exit_code = ejecutar_todas_las_pruebas()
    
    sys.exit(exit_code)
```

### Mejores prácticas para pruebas unitarias

#### 1. Nomenclatura clara

```python
class TestValidadorContrasena(unittest.TestCase):
    
    def test_contraseña_valida_con_todos_los_criterios_debe_pasar_validacion(self):
        """Nombre descriptivo que explica qué se está probando."""
        pass
    
    def test_contraseña_sin_mayusculas_debe_fallar_validacion(self):
        pass
    
    def test_contraseña_muy_corta_debe_fallar_validacion(self):
        pass
```

#### 2. Principio AAA (Arrange, Act, Assert)

```python
def test_calcular_descuento_con_porcentaje_valido(self):
    # Arrange (Preparar)
    precio_original = 100.0
    porcentaje_descuento = 20
    descuento_esperado = 20.0
    
    # Act (Actuar)
    descuento_calculado = calcular_descuento(precio_original, porcentaje_descuento)
    
    # Assert (Verificar)
    self.assertEqual(descuento_calculado, descuento_esperado)
```

#### 3. Una sola cosa por prueba

```python
# ❌ Mal - prueba múltiples cosas
def test_operaciones_matematicas(self):
    self.assertEqual(sumar(2, 3), 5)
    self.assertEqual(restar(5, 2), 3)
    self.assertEqual(multiplicar(3, 4), 12)

# ✅ Bien - una prueba por operación
def test_sumar_dos_numeros_positivos(self):
    self.assertEqual(sumar(2, 3), 5)

def test_restar_dos_numeros_positivos(self):
    self.assertEqual(restar(5, 2), 3)

def test_multiplicar_dos_numeros_positivos(self):
    self.assertEqual(multiplicar(3, 4), 12)
```

#### 4. Cobertura de casos extremos

```python
def dividir_seguro(dividendo, divisor):
    """División segura que maneja casos extremos."""
    if divisor == 0:
        return None
    return dividendo / divisor

class TestDividirSeguro(unittest.TestCase):
    
    def test_division_normal(self):
        """Caso normal."""
        self.assertEqual(dividir_seguro(10, 2), 5.0)
    
    def test_division_por_cero(self):
        """Caso extremo: división por cero."""
        self.assertIsNone(dividir_seguro(10, 0))
    
    def test_division_de_cero(self):
        """Caso extremo: dividendo cero."""
        self.assertEqual(dividir_seguro(0, 5), 0.0)
    
    def test_division_numeros_negativos(self):
        """Caso extremo: números negativos."""
        self.assertEqual(dividir_seguro(-10, 2), -5.0)
        self.assertEqual(dividir_seguro(10, -2), -5.0)
        self.assertEqual(dividir_seguro(-10, -2), 5.0)
    
    def test_division_numeros_flotantes(self):
        """Caso extremo: números flotantes."""
        resultado = dividir_seguro(7.5, 2.5)
        self.assertAlmostEqual(resultado, 3.0)
```

### Ejemplo completo: Sistema de gestión de estudiantes

```python
# estudiantes.py
class Estudiante:
    def __init__(self, nombre, edad, notas=None):
        if not nombre or not isinstance(nombre, str):
            raise ValueError("El nombre debe ser una cadena no vacía")
        if not isinstance(edad, int) or edad < 0:
            raise ValueError("La edad debe ser un entero positivo")
        
        self.nombre = nombre
        self.edad = edad
        self.notas = notas if notas is not None else []
    
    def agregar_nota(self, nota):
        if not isinstance(nota, (int, float)) or not (0 <= nota <= 10):
            raise ValueError("La nota debe ser un número entre 0 y 10")
        self.notas.append(nota)
    
    def calcular_promedio(self):
        if not self.notas:
            return 0
        return sum(self.notas) / len(self.notas)
    
    def aprobo(self):
        return self.calcular_promedio() >= 5.0

# test_estudiantes.py
class TestEstudiante(unittest.TestCase):
    
    def setUp(self):
        """Configurar datos para cada prueba."""
        self.estudiante = Estudiante("Ana García", 20)
    
    def test_crear_estudiante_valido(self):
        """Prueba creación de estudiante válido."""
        estudiante = Estudiante("Juan Pérez", 19, [7.5, 8.0, 6.5])
        
        self.assertEqual(estudiante.nombre, "Juan Pérez")
        self.assertEqual(estudiante.edad, 19)
        self.assertEqual(len(estudiante.notas), 3)
    
    def test_crear_estudiante_nombre_invalido(self):
        """Prueba validación de nombre inválido."""
        with self.assertRaises(ValueError):
            Estudiante("", 20)
        
        with self.assertRaises(ValueError):
            Estudiante(None, 20)
        
        with self.assertRaises(ValueError):
            Estudiante(123, 20)
    
    def test_crear_estudiante_edad_invalida(self):
        """Prueba validación de edad inválida."""
        with self.assertRaises(ValueError):
            Estudiante("Juan", -1)
        
        with self.assertRaises(ValueError):
            Estudiante("Juan", "veinte")
    
    def test_agregar_nota_valida(self):
        """Prueba agregar nota válida."""
        self.estudiante.agregar_nota(8.5)
        self.assertIn(8.5, self.estudiante.notas)
        self.assertEqual(len(self.estudiante.notas), 1)
    
    def test_agregar_nota_invalida(self):
        """Prueba validación de nota inválida."""
        with self.assertRaises(ValueError):
            self.estudiante.agregar_nota(11)
        
        with self.assertRaises(ValueError):
            self.estudiante.agregar_nota(-1)
        
        with self.assertRaises(ValueError):
            self.estudiante.agregar_nota("ocho")
    
    def test_calcular_promedio_sin_notas(self):
        """Prueba promedio sin notas."""
        promedio = self.estudiante.calcular_promedio()
        self.assertEqual(promedio, 0)
    
    def test_calcular_promedio_con_notas(self):
        """Prueba cálculo de promedio con notas."""
        notas = [7.0, 8.0, 9.0]
        for nota in notas:
            self.estudiante.agregar_nota(nota)
        
        promedio = self.estudiante.calcular_promedio()
        self.assertAlmostEqual(promedio, 8.0)
    
    def test_aprobo_con_promedio_aprobatorio(self):
        """Prueba aprobación con promedio >= 5.0."""
        for nota in [6.0, 7.0, 8.0]:
            self.estudiante.agregar_nota(nota)
        
        self.assertTrue(self.estudiante.aprobo())
    
    def test_no_aprobo_con_promedio_reprobatorio(self):
        """Prueba reprobación con promedio < 5.0."""
        for nota in [3.0, 4.0, 2.0]:
            self.estudiante.agregar_nota(nota)
        
        self.assertFalse(self.estudiante.aprobo())
    
    def test_no_aprobo_sin_notas(self):
        """Prueba reprobación sin notas."""
        self.assertFalse(self.estudiante.aprobo())

# Ejecutar las pruebas
if __name__ == '__main__':
    unittest.main()
```

### Herramientas adicionales para testing

#### Coverage (cobertura de código)

```bash
# Instalar coverage
pip install coverage

# Ejecutar pruebas con coverage
coverage run -m unittest discover
coverage report
coverage html  # Genera reporte HTML
```

#### pytest (alternativa a unittest)

```bash
# Instalar pytest
pip install pytest

# Ejecutar pruebas con pytest
pytest tests/
pytest tests/test_calculadora.py
pytest -v  # Modo verbose
```

### Integración con VS Code

Para ejecutar pruebas directamente en VS Code:

1. **Configurar Python Test Discovery**:
   - Abrir Command Palette (Ctrl+Shift+P)
   - Buscar "Python: Configure Tests"
   - Seleccionar "unittest"
   - Especificar directorio de pruebas

2. **Ejecutar pruebas**:
   - Usar el explorador de pruebas
   - Ejecutar pruebas individuales o en lote
   - Ver resultados y fallos directamente

## Ejercicios prácticos

### Ejercicio 1: Crear pruebas para una función de validación

```python
def validar_telefono(telefono):
    """
    Valida un número de teléfono español.
    Formato válido: +34XXXXXXXXX o 6XXXXXXXX o 9XXXXXXXX
    """
    import re
    
    # Eliminar espacios y guiones
    telefono_limpio = re.sub(r'[\s\-]', '', telefono)
    
    # Patrones válidos
    patron_internacional = r'^\+34[679]\d{8}$'
    patron_nacional = r'^[679]\d{8}$'
    
    return bool(re.match(patron_internacional, telefono_limpio) or 
                re.match(patron_nacional, telefono_limpio))

# TODO: Crear clase TestValidarTelefono con pruebas para:
# - Teléfonos válidos (varios formatos)
# - Teléfonos inválidos
# - Casos extremos (None, cadena vacía, etc.)
```

### Ejercicio 2: Testing de una clase completa

```python
class CuentaBancaria:
    def __init__(self, titular, saldo_inicial=0):
        self.titular = titular
        self.saldo = saldo_inicial
        self.historial = []
    
    def depositar(self, cantidad):
        # TODO: Implementar validaciones y lógica
        pass
    
    def retirar(self, cantidad):
        # TODO: Implementar validaciones y lógica
        pass
    
    def obtener_saldo(self):
        return self.saldo
    
    def obtener_historial(self):
        return self.historial.copy()

# TODO: Crear pruebas completas para CuentaBancaria
```

---

## Resumen

Las funciones en Python son fundamentales para escribir código modular, reutilizable y mantenible. Los conceptos clave incluyen:

- **Definición**: Usar `def` para crear funciones
- **Parámetros**: Diferentes tipos (posicionales, por defecto, *args, **kwargs)
- **Return**: Devolver valores desde las funciones
- **Ámbito**: Variables locales, globales y regla LEGB
- **Funciones incorporadas**: Aprovechar las funciones que Python ofrece
- **Documentación**: Usar docstrings y type hints para código claro y mantenible
- **Pruebas unitarias**: Verificar que las funciones funcionan correctamente mediante testing

El dominio de las funciones y su testing es esencial para convertirse en un programador Python competente y profesional.