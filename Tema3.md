# GESTION DE ARCHIVOS EN PYTHON

- [GESTION DE ARCHIVOS EN PYTHON](#gestion-de-archivos-en-python)
  - [INTRODUCCIÓN](#introducción)
  - [MODOS DE APERTURA DE ARCHIVOS](#modos-de-apertura-de-archivos)
  - [ABRIR Y CERRAR ARCHIVOS](#abrir-y-cerrar-archivos)
    - [Método tradicional](#método-tradicional)
    - [Uso de `with` (Recomendado)](#uso-de-with-recomendado)
  - [LECTURA DE ARCHIVOS](#lectura-de-archivos)
    - [Método `read()`](#método-read)
    - [Método `readline()`](#método-readline)
      - [Variantes del método `strip()`:](#variantes-del-método-strip)
      - [También puedes especificar qué caracteres eliminar:](#también-puedes-especificar-qué-caracteres-eliminar)
    - [Método `readlines()`](#método-readlines)
    - [Lectura línea por línea con bucle](#lectura-línea-por-línea-con-bucle)
    - [¿Cómo detecta Python el final de un archivo?](#cómo-detecta-python-el-final-de-un-archivo)
      - [1. **Los archivos son objetos iterables**](#1-los-archivos-son-objetos-iterables)
      - [2. **Protocolo de iteración**](#2-protocolo-de-iteración)
      - [3. **La excepción `StopIteration`**](#3-la-excepción-stopiteration)
      - [4. **Comparación con otros métodos**](#4-comparación-con-otros-métodos)
      - [5. **Ventajas de este sistema automático**](#5-ventajas-de-este-sistema-automático)
      - [6. **Comparación con `readlines()`**](#6-comparación-con-readlines)
  - [ESCRITURA EN ARCHIVOS](#escritura-en-archivos)
    - [Método `write()`](#método-write)
    - [Método `writelines()`](#método-writelines)
    - [Añadir contenido a un archivo](#añadir-contenido-a-un-archivo)
  - [MANEJO DE ERRORES](#manejo-de-errores)
    - [Excepciones comunes](#excepciones-comunes)
    - [Uso de `try-except`](#uso-de-try-except)
    - [Múltiples excepciones](#múltiples-excepciones)
    - [Bloque `finally`](#bloque-finally)
  - [FORMATOS ESPECÍFICOS DE ARCHIVOS](#formatos-específicos-de-archivos)
    - [Archivos CSV](#archivos-csv)
      - [Lectura de archivos CSV](#lectura-de-archivos-csv)
      - [Escritura de archivos CSV](#escritura-de-archivos-csv)
        - [Escritura con delimitador personalizado](#escritura-con-delimitador-personalizado)
      - [CSV con DictReader y DictWriter](#csv-con-dictreader-y-dictwriter)
    - [Archivos JSON](#archivos-json)
      - [Lectura de archivos JSON](#lectura-de-archivos-json)
      - [Escritura de archivos JSON](#escritura-de-archivos-json)
      - [Manipulación de datos JSON](#manipulación-de-datos-json)
  - [EJEMPLOS PRÁCTICOS](#ejemplos-prácticos)
    - [Ejemplo 1: Contador de palabras](#ejemplo-1-contador-de-palabras)
    - [Ejemplo 2: Registro de logs](#ejemplo-2-registro-de-logs)
    - [Ejemplo 3: Procesamiento de datos CSV](#ejemplo-3-procesamiento-de-datos-csv)
    - [Ejemplo 4: Configuración JSON](#ejemplo-4-configuración-json)
  - [BUENAS PRÁCTICAS](#buenas-prácticas)

## INTRODUCCIÓN

El manejo de archivos es una funcionalidad fundamental en Python que permite leer, escribir y manipular archivos del sistema. Python proporciona funciones incorporadas y bibliotecas especializadas para trabajar con diferentes formatos de archivo.

## MODOS DE APERTURA DE ARCHIVOS

Python ofrece varios modos para abrir archivos:

| Modo | Descripción | Comportamiento |
|------|-------------|----------------|
| `'r'` | Lectura (solo lectura) | Abre el archivo para lectura. Error si no existe |
| `'w'` | Escritura | Crea un archivo nuevo o sobrescribe si existe |
| `'a'` | Añade | Abre para escritura, añade al final del archivo |
| `'x'` | Creación exclusiva | Crea un archivo nuevo, error si ya existe |
| `'r+'` | Lectura y escritura | Abre para lectura y escritura |
| `'w+'` | Escritura y lectura | Crea/sobrescribe para lectura y escritura |
| `'a+'` | Añade y lectura | Abre para lectura y añade al final del archivo |

**Modificadores adicionales:**
- `'t'`: Modo texto (por defecto)
- `'b'`: Modo binario (para imágenes, videos, etc.)

```python
# Ejemplos de modos
archivo_lectura = open('datos.txt', 'r')        # Solo lectura
archivo_escritura = open('salida.txt', 'w')     # Solo escritura
archivo_binario = open('imagen.jpg', 'rb')      # Lectura binaria
archivo_texto = open('documento.txt', 'rt')     # Lectura texto (equivale a 'r')
```

## ABRIR Y CERRAR ARCHIVOS

### Método tradicional

```python
# Apertura manual (requiere cerrar explícitamente)
archivo = open('ejemplo.txt', 'r')
contenido = archivo.read()
print(contenido)
archivo.close()  # ¡Importante cerrar el archivo!
```

### Uso de `with` (Recomendado)

El uso de `with` garantiza que el archivo se cierre automáticamente, incluso si ocurre un error:

```python
# Método recomendado con context manager
with open('ejemplo.txt', 'r') as archivo:
    contenido = archivo.read()
    print(contenido)
# El archivo se cierra automáticamente al salir del bloque
```

**Ventajas del `with`:**
- Cierre automático del archivo
- Manejo automático de recursos
- Código más limpio y seguro

## LECTURA DE ARCHIVOS

### Método `read()`

Lee todo el contenido del archivo como una sola cadena:

```python
# Leer todo el archivo
with open('documento.txt', 'r', encoding='utf-8') as archivo:
    contenido_completo = archivo.read()
    print(contenido_completo)

# Leer un número específico de caracteres
with open('documento.txt', 'r', encoding='utf-8') as archivo:
    primeros_100_chars = archivo.read(100)
    print(primeros_100_chars)
```

### Método `readline()`

Lee una línea a la vez:

```python
with open('documento.txt', 'r', encoding='utf-8') as archivo:
    primera_linea = archivo.readline()
    segunda_linea = archivo.readline()
    print("Primera línea:", primera_linea.strip())
    print("Segunda línea:", segunda_linea.strip())
```
El método `strip()` es un método de las cadenas (strings) en Python que **elimina espacios en blanco y caracteres de nueva línea** `(\n)` del **inicio y final** de una cadena.
Cuando lees una línea de un archivo con `readline()`, la cadena que obtienes incluye el carácter de nueva línea `(\n)` al final.

#### Variantes del método `strip()`:

- **`strip()`**: Elimina espacios y `\n` del inicio Y final
- **`lstrip()`**: Elimina solo del lado **izquierdo** (left)
- **`rstrip()`**: Elimina solo del lado **derecho** (right)

#### También puedes especificar qué caracteres eliminar:

```python
texto = "...Hola mundo..."
print(texto.strip('.'))  # 'Hola mundo'

texto = "xxxHola mundoxxx"
print(texto.strip('x'))  # 'Hola mundo'
```

### Método `readlines()`

Lee todas las líneas y las devuelve como una lista:

```python
with open('documento.txt', 'r', encoding='utf-8') as archivo:
    todas_las_lineas = archivo.readlines()
    for i, linea in enumerate(todas_las_lineas, 1):
        print(f"Línea {i}: {linea.strip()}")
```
Este bucle for utiliza la función `enumerate()`, que es muy útil cuando necesitas tanto el **índice** como el **valor** de cada elemento en una lista.
Explicación:
1. `todas_las_lineas`: Es una lista que contiene todas las líneas del archivo
2. `enumerate(todas_las_lineas, 1)`: Crea pares de (índice, valor) empezando desde 1
3. `i`, `linea`: Desempaqueta cada par en dos variables separadas

```python
# Sin enumerate (forma tradicional)
todas_las_lineas = ["Hola\n", "Mundo\n", "Python\n"]
for i in range(len(todas_las_lineas)):
    print(f"Línea {i+1}: {todas_las_lineas[i].strip()}")

# Con enumerate (forma moderna y limpia)
for i, linea in enumerate(todas_las_lineas, 1):
    print(f"Línea {i}: {linea.strip()}")

```
Ventajas:

✅ Más legible 
✅ Evita errores de índice
✅ No necesitas calcular range(len(lista))
✅ Más eficiente

### Lectura línea por línea con bucle

La forma más eficiente para archivos grandes:

```python
with open('documento.txt', 'r', encoding='utf-8') as archivo:
    for numero_linea, linea in enumerate(archivo, 1):
        print(f"Línea {numero_linea}: {linea.strip()}")
```

**Ejemplo práctico de lectura:**

```python
def mostrar_archivo_numerado(nombre_archivo):
    """Muestra el contenido de un archivo con números de línea."""
    try:
        with open(nombre_archivo, 'r', encoding='utf-8') as archivo:
            for num, linea in enumerate(archivo, 1):
                print(f"{num:3d}: {linea.rstrip()}")
    except FileNotFoundError:
        print(f"Error: El archivo '{nombre_archivo}' no existe.")

# Uso
mostrar_archivo_numerado('mi_documento.txt')
```

### ¿Cómo detecta Python el final de un archivo?

#### 1. **Los archivos son objetos iterables**

En Python, cuando abres un archivo, se convierte en un **objeto iterable**. Esto significa que puedes usar `for` directamente sobre él:

```python
with open('archivo.txt', 'r') as archivo:
    for linea in archivo:  # ¡Python maneja automáticamente el final!
        print(linea.strip())
```

#### 2. **Protocolo de iteración**

Python utiliza el **protocolo de iteración** que funciona así internamente:

```python
# Lo que Python hace internamente (simplificado):
archivo = open('archivo.txt', 'r')
iterador = iter(archivo)

try:
    while True:
        linea = next(iterador)  # Obtiene la siguiente línea
        print(linea.strip())    # Procesa la línea
except StopIteration:           # ¡Aquí detecta el final!
    pass                        # Sale del bucle automáticamente

archivo.close()
```

#### 3. **La excepción `StopIteration`**

Cuando Python llega al final del archivo:
- El método `next()` lanza una excepción `StopIteration`
- El bucle `for` **captura automáticamente** esta excepción
- **Termina el bucle sin error**

#### 4. **Comparación con otros métodos**

```python
# Método manual (MÁS PROPENSO A ERRORES)
with open('archivo.txt', 'r') as archivo:
    while True:
        linea = archivo.readline()
        if not linea:  # ¿Cómo sabemos si llegamos al final?
            break      # Tenemos que verificar manualmente
        print(linea.strip())

# Método automático (RECOMENDADO)
with open('archivo.txt', 'r') as archivo:
    for linea in archivo:  # Python detecta automáticamente el final
        print(linea.strip())
```

#### 5. **Ventajas de este sistema automático**

✅ **Sin errores de índice**: No necesitas saber cuántas líneas tiene el archivo
✅ **Eficiente en memoria**: Lee línea por línea, no todo el archivo de una vez
✅ **Código limpio**: No necesitas verificar manualmente el final
✅ **Robusto**: Funciona con archivos de cualquier tamaño

#### 6. **Comparación con `readlines()`**

```python
# readlines() - Carga TODO en memoria de una vez
with open('archivo.txt', 'r') as archivo:
    todas_las_lineas = archivo.readlines()  # ¡Carga todo!
    for linea in todas_las_lineas:
        print(linea.strip())

# Iteración directa - Lee línea por línea
with open('archivo.txt', 'r') as archivo:
    for linea in archivo:  # ¡Solo una línea en memoria!
        print(linea.strip())
```

**En resumen**: Python detecta automáticamente el final del archivo usando el protocolo de iteración. Cuando no hay más líneas que leer, se lanza internamente una excepción `StopIteration` que el bucle `for` captura y maneja automáticamente, terminando el bucle sin errores. ¡Es parte de la "magia" de Python que hace el código más simple y robusto!

## ESCRITURA EN ARCHIVOS

### Método `write()`

Escribe una cadena en el archivo:

```python
# Crear un nuevo archivo y escribir contenido
with open('nuevo_archivo.txt', 'w', encoding='utf-8') as archivo:
    archivo.write("Hola, mundo!\n")
    archivo.write("Esta es la segunda línea.\n")
    
# Escribir variables
nombre = "Python"
version = 3.9
with open('info.txt', 'w', encoding='utf-8') as archivo:
    archivo.write(f"Lenguaje: {nombre}\n")
    archivo.write(f"Versión: {version}\n")
```

### Método `writelines()`

Escribe una lista de cadenas:

```python
lineas = [
    "Primera línea\n",
    "Segunda línea\n",
    "Tercera línea\n"
]

with open('multiple_lines.txt', 'w', encoding='utf-8') as archivo:
    archivo.writelines(lineas)

# También se puede usar con cualquier iterable
datos = ['apple', 'banana', 'cherry']
with open('frutas.txt', 'w', encoding='utf-8') as archivo:
    archivo.writelines(f"{fruta}\n" for fruta in datos)
```

### Añadir contenido a un archivo

```python
# Añadir al final del archivo existente
with open('log.txt', 'a', encoding='utf-8') as archivo:
    archivo.write("Nueva entrada de log\n")
    
# Diferentes formas de importar la librería datetime:

# 1. Importar solo la clase datetime del módulo datetime
# from datetime import datetime

# 2. Importar todo el módulo datetime
# import datetime

# 3. Importar el módulo con un alias
# import datetime as dt

# 4. Importar múltiples clases del módulo datetime
# from datetime import datetime, date, time

# 5. Importar todo del módulo datetime (no recomendado)
# from datetime import *

# Ejemplo usando cada forma de importación:

# Forma 1: from datetime import datetime
def registrar_evento_forma1(evento):
    from datetime import datetime
    timestamp = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    with open('eventos.log', 'a', encoding='utf-8') as archivo:
        archivo.write(f"[{timestamp}] {evento}\n")

# Forma 2: import datetime
def registrar_evento_forma2(evento):
    import datetime
    timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    with open('eventos.log', 'a', encoding='utf-8') as archivo:
        archivo.write(f"[{timestamp}] {evento}\n")

# Forma 3: import datetime as dt
def registrar_evento_forma3(evento):
    import datetime as dt
    timestamp = dt.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    with open('eventos.log', 'a', encoding='utf-8') as archivo:
        archivo.write(f"[{timestamp}] {evento}\n")

# Uso de las diferentes formas
registrar_evento_forma1("Aplicación iniciada - Forma 1")
registrar_evento_forma2("Aplicación iniciada - Forma 2")
registrar_evento_forma3("Aplicación iniciada - Forma 3")

## Comparación de las diferentes formas de importar datetime:

### 1. `from datetime import datetime`
**Ventajas:**
- Más conciso en el código
- No necesitas prefijo para usar la clase
- Más legible cuando solo usas datetime

**Desventajas:**
- Puede crear conflictos de nombres si tienes otra variable llamada `datetime`
- Menos claro de dónde viene la clase

### 2. `import datetime`
**Ventajas:**
- Más explícito sobre el origen del módulo
- Evita conflictos de nombres
- Acceso a todas las clases del módulo (datetime, date, time, etc.)

**Desventajas:**
- Código más largo: `datetime.datetime.now()`
- Puede ser confuso tener que escribir `datetime.datetime`

### 3. `import datetime as dt`
**Ventajas:**
- Más corto que `datetime.datetime`
- Mantiene la claridad del origen
- Convención común en la comunidad Python

**Desventajas:**
- Requiere recordar el alias
- Sigue siendo más largo que la forma 1

### 4. `from datetime import datetime, date, time`
**Ventajas:**
- Importa múltiples clases de una vez
- Código conciso para cada clase

**Desventajas:**
- La línea de importación puede volverse muy larga
- Posibles conflictos de nombres

### 5. `from datetime import *` (NO RECOMENDADO)
**Por qué NO es recomendado:**
- Contamina el namespace global
- Puede sobrescribir funciones existentes
- Hace el código menos legible
- Dificulta el debugging

## ✅ RECOMENDACIONES DE USO:

### **FORMA 1**: `from datetime import datetime` 
**✅ Recomendada cuando:**
- Solo necesitas la clase `datetime`
- Escribes código simple o scripts pequeños
- No hay riesgo de conflictos de nombres

### **FORMA 3**: `import datetime as dt`
**✅ Recomendada cuando:**
- Trabajas en proyectos grandes
- Necesitas claridad sobre el origen del módulo
- Quieres evitar conflictos de nombres
- Sigues convenciones de la comunidad Python

### **MENOS RECOMENDADAS:**
- **Forma 2** (`import datetime`): Muy extensa (`datetime.datetime.now()`)
- **Forma 4** (`from datetime import datetime, date, time`): Solo si necesitas múltiples clases
- **Forma 5** (`from datetime import *`): ❌ **NUNCA recomendada**

### **CONCLUSIÓN:**
En la práctica, **la Forma 1 y la Forma 3 son las más utilizadas** por los desarrolladores Python. La elección entre ellas depende del contexto y preferencias del proyecto.
```

## MANEJO DE ERRORES

### Excepciones comunes

| Excepción | Descripción |
|-----------|-------------|
| `FileNotFoundError` | El archivo no existe |
| `PermissionError` | Sin permisos para acceder al archivo |
| `IsADirectoryError` | Se intentó abrir un directorio como archivo |
| `UnicodeDecodeError` | Error de codificación al leer |
| `IOError` | Error general de entrada/salida |

### Uso de `try-except`

```python
def leer_archivo_seguro(nombre_archivo):
    """Lee un archivo de forma segura manejando errores."""
    try:
        with open(nombre_archivo, 'r', encoding='utf-8') as archivo:
            return archivo.read()
    except FileNotFoundError:
        print(f"Error: El archivo '{nombre_archivo}' no fue encontrado.")
        return None
    except PermissionError:
        print(f"Error: Sin permisos para leer '{nombre_archivo}'.")
        return None
    except UnicodeDecodeError:
        print(f"Error: Problemas de codificación en '{nombre_archivo}'.")
        return None

# Uso
contenido = leer_archivo_seguro('mi_archivo.txt')
if contenido:
    print(contenido)
```

### Múltiples excepciones

```python
def escribir_archivo_seguro(nombre_archivo, contenido):
    """Escribe un archivo manejando múltiples errores."""
    try:
        with open(nombre_archivo, 'w', encoding='utf-8') as archivo:
            archivo.write(contenido)
        print(f"Archivo '{nombre_archivo}' creado exitosamente.")
        return True
    except (PermissionError, OSError) as e:
        print(f"Error al crear el archivo: {e}")
        return False
    except Exception as e:
        print(f"Error inesperado: {e}")
        return False
```

### Bloque `finally`

```python
def procesar_archivo(nombre_archivo):
    """Ejemplo de uso de finally."""
    archivo = None
    try:
        archivo = open(nombre_archivo, 'r')
        # Procesar archivo
        contenido = archivo.read()
        return contenido
    except FileNotFoundError:
        print("Archivo no encontrado")
        return None
    finally:
        # Este bloque SIEMPRE se ejecuta
        if archivo:
            archivo.close()
            print("Archivo cerrado")
```

## FORMATOS ESPECÍFICOS DE ARCHIVOS

### Archivos CSV

CSV (Comma-Separated Values) es un formato común para datos tabulares.
Vamos a utilizar la librería estándar de Python `csv`, este módulo viene incluido en Python, es parte del núcleo del lenguaje. 
* Facilita la lectura y escritura de archivos CSV(Comma Separated Values).
* Maneja automáticamente aspectos complejos como:
    * Comillas en los datos
    * Comas dentro de los campos
    * Diferentes delimitadores
    * Saltos de línea en los datos

#### Lectura de archivos CSV

```python
import csv

# Lectura básica
def leer_csv_basico(nombre_archivo):
    """Lee un archivo CSV de forma básica."""
    with open(nombre_archivo, 'r', encoding='utf-8') as archivo:
        lector = csv.reader(archivo)
        for fila in lector:
            print(fila)

# Ejemplo de uso
# leer_csv_basico('datos.csv')

# Lectura con cabeceras
def leer_csv_con_cabeceras(nombre_archivo):
    """Lee un CSV mostrando cabeceras y datos."""
    with open(nombre_archivo, 'r', encoding='utf-8') as archivo:
        lector = csv.reader(archivo)
        cabeceras = next(lector)  # Primera fila como cabeceras
        print("Cabeceras:", cabeceras)
        
        for i, fila in enumerate(lector, 1):
            print(f"Fila {i}: {fila}")

# Ejemplo con diferentes delimitadores
def leer_csv_personalizado(nombre_archivo, delimitador=','):
    """Lee CSV con delimitador personalizado."""
    with open(nombre_archivo, 'r', encoding='utf-8') as archivo:
        lector = csv.reader(archivo, delimiter=delimitador)
```
📌 IMPORTANTE: Delimitadores en CSV

**Delimitador por defecto: `,` (coma)**
El módulo `csv` de Python usa la **coma (`,`)** como delimitador por defecto.

```python
# Esto es equivalente:
csv.reader(archivo)
csv.reader(archivo, delimiter=',')
```

#### Escritura de archivos CSV

```python
import csv

# Escritura básica
def escribir_csv_basico(nombre_archivo, datos):
    """Escribe datos en formato CSV."""
    with open(nombre_archivo, 'w', newline='', encoding='utf-8') as archivo:
        escritor = csv.writer(archivo)
        escritor.writerows(datos)

# Ejemplo de uso
datos_ejemplo = [
    ['Nombre', 'Edad', 'Ciudad'],
    ['Juan', 25, 'Madrid'],
    ['Ana', 30, 'Barcelona'],
    ['Carlos', 22, 'Valencia']
]
escribir_csv_basico('personas.csv', datos_ejemplo)
```

📌 IMPORTANTE: Uso de `newline=''` en archivos CSV

El parámetro `newline=''` es específico y muy importante cuando trabajas con archivos CSV en Python. Su función es:

**¿Qué hace `newline=''`?**

Evita líneas en blanco extra: Sin este parámetro, Python puede agregar líneas vacías adicionales entre las filas del CSV, especialmente en Windows.

Permite al módulo csv controlar los saltos de línea: El módulo csv está diseñado para manejar los saltos de línea por sí mismo, y newline='' le da control total sobre esto.

**¿Por qué es importante?**

* **Compatibilidad multiplataforma**: Funciona correctamente en Windows, macOS y Linux
* **Formato CSV estándar**: Mantiene el formato CSV limpio y sin líneas vacías inesperadas
* **Mejores prácticas**: Es la forma recomendada oficialmente por Python

##### Escritura con delimitador personalizado

```python
def escribir_csv_personalizado(nombre_archivo, datos, delimitador=';'):
    """Escribe CSV con delimitador personalizado."""
    with open(nombre_archivo, 'w', newline='', encoding='utf-8') as archivo:
        escritor = csv.writer(archivo, delimiter=delimitador)
        escritor.writerows(datos)
```

#### CSV con DictReader y DictWriter

* **csv.DictReader**: Lee archivos CSV y convierte cada fila en un diccionario, donde las claves son los nombres de las columnas (cabeceras) y los valores son los datos de cada celda.

* **csv.DictWriter**: Escribe archivos CSV desde diccionarios, donde especificas qué claves del diccionario corresponden a qué columnas.

**Principales ventajas de DictReader/DictWriter**:

1. 📌 **Legibilidad**: El código es mucho más claro porque usas nombres de columnas en lugar de índices numéricos.
2. 🔧 **Mantenibilidad**: Si cambia el orden de las columnas en el CSV, tu código sigue funcionando.
3. 🚫 **Menos errores**: No hay riesgo de confundir posiciones (¿era la edad la columna 1 o 2?).
4. 📝 **Autoexplicativo**: fila['nombre'] es más descriptivo que fila[0].
5. 🔄 **Flexibilidad**: Puedes trabajar directamente con estructuras de datos más complejas.

```python
import csv

# Lectura como diccionario
def leer_csv_como_dict(nombre_archivo):
    """Lee CSV y devuelve lista de diccionarios."""
    personas = []
    with open(nombre_archivo, 'r', encoding='utf-8') as archivo:
        lector = csv.DictReader(archivo)
        for fila in lector:
            personas.append(fila)
    return personas

# Escritura desde diccionarios
def escribir_csv_desde_dict(nombre_archivo, datos, campos):
    """
    Escribe CSV desde lista de diccionarios.
    
    Parámetros:
    - nombre_archivo: string - Nombre del archivo CSV a crear
    - datos: list - Lista de diccionarios con la información a escribir
    - campos: list - Lista con los nombres de las columnas (cabeceras del CSV)
    """
    with open(nombre_archivo, 'w', newline='', encoding='utf-8') as archivo:
        # DictWriter necesita saber cuáles son las columnas (fieldnames)
        escritor = csv.DictWriter(archivo, fieldnames=campos)
        escritor.writeheader()  # Escribir cabeceras (primera fila)
        escritor.writerows(datos)  # Escribir todas las filas de datos
```
📌 EXPLICACIÓN DE PARÁMETROS:

**`datos`** = Lista de diccionarios con la información
Es una lista donde cada elemento es un diccionario que representa una fila:

```python
datos = [
    {'nombre': 'Laura', 'edad': 28, 'profesion': 'Ingeniera'},    # Fila 1
    {'nombre': 'Miguel', 'edad': 35, 'profesion': 'Doctor'},      # Fila 2  
    {'nombre': 'Sofia', 'edad': 24, 'profesion': 'Diseñadora'}   # Fila 3
]
```

**`campos`** = Lista de nombres de columnas (cabeceras)
Es una lista con los nombres que aparecerán como cabeceras del CSV:

```python
campos = ['nombre', 'edad', 'profesion']
```

**Resultado final en el CSV:**
```
nombre,edad,profesion
Laura,28,Ingeniera
Miguel,35,Doctor
Sofia,24,Diseñadora
```

### Archivos JSON

JSON (JavaScript Object Notation) es un formato popular para intercambio de datos.

#### Lectura de archivos JSON

```python
import json

# Lectura básica
def leer_json(nombre_archivo):
    """Lee y devuelve datos de un archivo JSON."""
    try:
        with open(nombre_archivo, 'r', encoding='utf-8') as archivo:
            datos = json.load(archivo)
            return datos
    except json.JSONDecodeError:
        print("Error: Formato JSON inválido")
        return None
    except FileNotFoundError:
        print(f"Error: Archivo '{nombre_archivo}' no encontrado")
        return None

# Ejemplo de uso
datos = leer_json('configuracion.json')
if datos:
    print("Datos cargados:", datos)
```

#### Escritura de archivos JSON

```python
import json

# Escritura básica
def escribir_json(nombre_archivo, datos):
    """Escribe datos en formato JSON."""
    try:
        with open(nombre_archivo, 'w', encoding='utf-8') as archivo:
            json.dump(datos, archivo, ensure_ascii=False, indent=4)
        print(f"Archivo JSON '{nombre_archivo}' creado exitosamente.")
    except Exception as e:
        print(f"Error al escribir JSON: {e}")

# Ejemplo de uso
configuracion = {
    "aplicacion": "Mi App",
    "version": "1.0.0",
    "configuracion": {
        "debug": True,
        "puerto": 8080,
        "base_datos": {
            "host": "localhost",
            "puerto": 5432,
            "nombre": "mi_db"
        }
    },
    "usuarios": [
        {"nombre": "admin", "rol": "administrador"},
        {"nombre": "usuario1", "rol": "usuario"}
    ]
}

escribir_json('config.json', configuracion)
```

#### Manipulación de datos JSON

```python
import json

def actualizar_configuracion(archivo, nueva_config):
    """Actualiza parcialmente un archivo de configuración JSON."""
    # Leer configuración actual
    try:
        with open(archivo, 'r', encoding='utf-8') as f:
            config_actual = json.load(f)
    except FileNotFoundError:
        config_actual = {}
    
    # Actualizar con nueva configuración
    config_actual.update(nueva_config)
    
    # Guardar configuración actualizada
    with open(archivo, 'w', encoding='utf-8') as f:
        json.dump(config_actual, f, ensure_ascii=False, indent=4)

# Ejemplo de uso
nueva_configuracion = {
    "puerto": 9000,
    "debug": False
}
actualizar_configuracion('config.json', nueva_configuracion)
```

## EJEMPLOS PRÁCTICOS

### Ejemplo 1: Contador de palabras

```python
def contar_palabras(nombre_archivo):
    """Cuenta palabras, líneas y caracteres de un archivo."""
    try:
        with open(nombre_archivo, 'r', encoding='utf-8') as archivo:
            contenido = archivo.read()
            
        # Contar elementos
        caracteres = len(contenido)
        palabras = len(contenido.split())
        lineas = contenido.count('\n') + 1
        
        # Mostrar estadísticas
        print(f"Estadísticas de '{nombre_archivo}':")
        print(f"  Caracteres: {caracteres}")
        print(f"  Palabras: {palabras}")
        print(f"  Líneas: {lineas}")
        
        return {'caracteres': caracteres, 'palabras': palabras, 'lineas': lineas}
        
    except FileNotFoundError:
        print(f"Error: El archivo '{nombre_archivo}' no existe.")
        return None

# Uso
estadisticas = contar_palabras('documento.txt')
```

### Ejemplo 2: Registro de logs

```python
from datetime import datetime
import os

class Logger:
    """Clase para manejar registros de log."""
    
    def __init__(self, archivo_log='aplicacion.log'):
        self.archivo_log = archivo_log
    
    def escribir_log(self, nivel, mensaje):
        """Escribe una entrada de log."""
        timestamp = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
        entrada = f"[{timestamp}] {nivel.upper()}: {mensaje}\n"
        
        try:
            with open(self.archivo_log, 'a', encoding='utf-8') as archivo:
                archivo.write(entrada)
        except Exception as e:
            print(f"Error al escribir log: {e}")
    
    def info(self, mensaje):
        """Registra un mensaje informativo."""
        self.escribir_log('INFO', mensaje)
    
    def error(self, mensaje):
        """Registra un mensaje de error."""
        self.escribir_log('ERROR', mensaje)
    
    def warning(self, mensaje):
        """Registra un mensaje de advertencia."""
        self.escribir_log('WARNING', mensaje)
    
    def leer_logs(self, ultimas_lineas=10):
        """Lee las últimas líneas del log."""
        try:
            with open(self.archivo_log, 'r', encoding='utf-8') as archivo:
                lineas = archivo.readlines()
                return lineas[-ultimas_lineas:]
        except FileNotFoundError:
            return []

# Ejemplo de uso
logger = Logger('mi_app.log')
logger.info('Aplicación iniciada')
logger.warning('Memoria baja')
logger.error('Error de conexión')

# Leer últimos logs
ultimos_logs = logger.leer_logs(5)
for log in ultimos_logs:
    print(log.strip())
```

### Ejemplo 3: Procesamiento de datos CSV

```python
import csv
from collections import defaultdict

def analizar_ventas(archivo_csv):
    """Analiza datos de ventas desde un archivo CSV."""
    ventas_por_producto = defaultdict(float)
    ventas_por_mes = defaultdict(float)
    total_ventas = 0
    
    try:
        with open(archivo_csv, 'r', encoding='utf-8') as archivo:
            lector = csv.DictReader(archivo)
            
            for fila in lector:
                producto = fila['producto']
                mes = fila['mes']
                venta = float(fila['venta'])
                
                ventas_por_producto[producto] += venta
                ventas_por_mes[mes] += venta
                total_ventas += venta
        
        # Generar reporte
        with open('reporte_ventas.txt', 'w', encoding='utf-8') as reporte:
            reporte.write("REPORTE DE VENTAS\n")
            reporte.write("=" * 50 + "\n\n")
            
            reporte.write(f"Total de ventas: ${total_ventas:.2f}\n\n")
            
            reporte.write("Ventas por producto:\n")
            for producto, venta in sorted(ventas_por_producto.items()):
                reporte.write(f"  {producto}: ${venta:.2f}\n")
            
            reporte.write("\nVentas por mes:\n")
            for mes, venta in sorted(ventas_por_mes.items()):
                reporte.write(f"  {mes}: ${venta:.2f}\n")
        
        print("Reporte generado: reporte_ventas.txt")
        
    except FileNotFoundError:
        print(f"Error: Archivo '{archivo_csv}' no encontrado.")
    except KeyError as e:
        print(f"Error: Columna faltante en CSV: {e}")
    except ValueError as e:
        print(f"Error: Valor inválido en CSV: {e}")

# Crear archivo de ejemplo
datos_ventas = [
    ['producto', 'mes', 'venta'],
    ['Laptop', 'Enero', '1500.00'],
    ['Mouse', 'Enero', '25.50'],
    ['Laptop', 'Febrero', '1800.00'],
    ['Teclado', 'Febrero', '75.00'],
    ['Mouse', 'Marzo', '30.00']
]

with open('ventas.csv', 'w', newline='', encoding='utf-8') as f:
    escritor = csv.writer(f)
    escritor.writerows(datos_ventas)

# Analizar ventas
analizar_ventas('ventas.csv')
```

### Ejemplo 4: Configuración JSON

```python
import json
import os

class ConfiguracionApp:
    """Maneja la configuración de la aplicación."""
    
    def __init__(self, archivo_config='config.json'):
        self.archivo_config = archivo_config
        self.config_default = {
            'app': {
                'nombre': 'Mi Aplicación',
                'version': '1.0.0',
                'debug': False
            },
            'base_datos': {
                'host': 'localhost',
                'puerto': 5432,
                'nombre': 'mi_db',
                'usuario': 'admin'
            },
            'servidor': {
                'puerto': 8080,
                'host': '0.0.0.0'
            }
        }
        self.config = self.cargar_configuracion()
    
    def cargar_configuracion(self):
        """Carga la configuración desde archivo o crea una por defecto."""
        if os.path.exists(self.archivo_config):
            try:
                with open(self.archivo_config, 'r', encoding='utf-8') as archivo:
                    return json.load(archivo)
            except json.JSONDecodeError:
                print("Error: Archivo de configuración inválido. Usando valores por defecto.")
                return self.config_default.copy()
        else:
            print("Archivo de configuración no encontrado. Creando uno por defecto.")
            self.guardar_configuracion(self.config_default)
            return self.config_default.copy()
    
    def guardar_configuracion(self, config=None):
        """Guarda la configuración actual."""
        if config is None:
            config = self.config
        
        try:
            with open(self.archivo_config, 'w', encoding='utf-8') as archivo:
                json.dump(config, archivo, ensure_ascii=False, indent=4)
            print(f"Configuración guardada en '{self.archivo_config}'")
        except Exception as e:
            print(f"Error al guardar configuración: {e}")
    
    def obtener(self, clave, valor_defecto=None):
        """Obtiene un valor de configuración usando notación de punto."""
        claves = clave.split('.')
        valor = self.config
        
        try:
            for k in claves:
                valor = valor[k]
            return valor
        except KeyError:
            return valor_defecto
    
    def establecer(self, clave, valor):
        """Establece un valor de configuración usando notación de punto."""
        claves = clave.split('.')
        config_ref = self.config
        
        # Navegar hasta el penúltimo nivel
        for k in claves[:-1]:
            if k not in config_ref:
                config_ref[k] = {}
            config_ref = config_ref[k]
        
        # Establecer el valor
        config_ref[claves[-1]] = valor
        self.guardar_configuracion()

# Ejemplo de uso
config = ConfiguracionApp()

# Obtener valores
print("Nombre de la app:", config.obtener('app.nombre'))
print("Puerto del servidor:", config.obtener('servidor.puerto'))

# Cambiar valores
config.establecer('app.debug', True)
config.establecer('servidor.puerto', 9000)

# Obtener valor con defecto
timeout = config.obtener('servidor.timeout', 30)
print("Timeout:", timeout)
```

## BUENAS PRÁCTICAS

1. **Siempre usar `with` para manejar archivos:**
   ```python
   # ✅ Correcto
   with open('archivo.txt', 'r') as f:
       contenido = f.read()
   
   # ❌ Incorrecto (puede dejar archivos abiertos)
   f = open('archivo.txt', 'r')
   contenido = f.read()
   # f.close() # Podría no ejecutarse si hay error
   ```

2. **Especificar la codificación explícitamente:**
   ```python
   with open('archivo.txt', 'r', encoding='utf-8') as f:
       contenido = f.read()
   ```

3. **Manejar errores apropiadamente:**
   ```python
   try:
       with open('archivo.txt', 'r', encoding='utf-8') as f:
           contenido = f.read()
   except FileNotFoundError:
       print("Archivo no encontrado")
   except PermissionError:
       print("Sin permisos para leer el archivo")
   ```

4. **Para archivos grandes, procesar línea por línea:**
   ```python
   # ✅ Eficiente en memoria
   with open('archivo_grande.txt', 'r') as f:
       for linea in f:
           procesar(linea)
   
   # ❌ Carga todo en memoria
   with open('archivo_grande.txt', 'r') as f:
       lineas = f.readlines()
       for linea in lineas:
           procesar(linea)
   ```

5. **Usar rutas absolutas o relativas consistentes:**
   ```python
   import os
   
   # Ruta relativa al directorio del script
   ruta_archivo = os.path.join(os.path.dirname(__file__), 'datos', 'archivo.txt')
   ```

6. **Para CSV, usar `newline=''` en modo escritura:**
   ```python
   with open('datos.csv', 'w', newline='', encoding='utf-8') as f:
       writer = csv.writer(f)
       writer.writerows(datos)
   ```

7. **Para JSON, usar `ensure_ascii=False` para caracteres Unicode:**
   ```python
   with open('datos.json', 'w', encoding='utf-8') as f:
       json.dump(datos, f, ensure_ascii=False, indent=4)
   ```

8. **Validar datos antes de procesarlos:**
   ```python
   def procesar_csv_seguro(archivo):
       required_columns = ['nombre', 'edad', 'email']
       
       with open(archivo, 'r', encoding='utf-8') as f:
           reader = csv.DictReader(f)
           
           # Validar columnas
           if not all(col in reader.fieldnames for col in required_columns):
               raise ValueError("Columnas requeridas faltantes")
           
           for row in reader:
               # Validar datos de la fila
               if not row['email'] or '@' not in row['email']:
                   continue  # Saltar fila inválida
               
               procesar_fila(row)
   ```