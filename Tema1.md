# INTRODUCCIÓN A PYTHON: INSTALACIÓN,TIPOS DE DATOS Y ESTRUCTURAS DE CONTROL
- [INTRODUCCIÓN A PYTHON: INSTALACIÓN,TIPOS DE DATOS Y ESTRUCTURAS DE CONTROL](#introducción-a-python-instalacióntipos-de-datos-y-estructuras-de-control)
  - [INTRODUCCIÓN](#introducción)
  - [INSTALACIÓN EN EL ENTORNO WINDOWS](#instalación-en-el-entorno-windows)
    - [Ventajas de esta instalación:](#ventajas-de-esta-instalación)
  - [CONFIGURACIÓN DEL ENTORNO DE DESARROLLO (IDE)](#configuración-del-entorno-de-desarrollo-ide)
    - [Ventajas de VS Code para Python:](#ventajas-de-vs-code-para-python)
    - [Extensiones recomendadas de Python en VS Code:](#extensiones-recomendadas-de-python-en-vs-code)
    - [¿Qué es Pylint?](#qué-es-pylint)
    - [¿Qué es Jupyter?](#qué-es-jupyter)
    - [Configurar el VSCode: Detecta la versión de Python y configura el intérprete](#configurar-el-vscode-detecta-la-versión-de-python-y-configura-el-intérprete)
  - [MODO INTERACTIVO](#modo-interactivo)
  - [UTILIZAR COMENTARIOS](#utilizar-comentarios)
    - [Documentar el código](#documentar-el-código)
      - [Ejemplo de uso de la función help()](#ejemplo-de-uso-de-la-función-help)
  - [INDENTACIÓN DEL CÓDIGO](#indentación-del-código)
  - [DEFINICIÓN DE VARIABLES](#definición-de-variables)
  - [TIPOS DE DATOS](#tipos-de-datos)
    - [1. **Numéricos**: `int`, `float`, `complex`](#1-numéricos-int-float-complex)
    - [2. **Texto**](#2-texto)
    - [Métodos de strings](#métodos-de-strings)
      - [Tabla de los métodos de strings más comunes](#tabla-de-los-métodos-de-strings-más-comunes)
    - [Formateo de cadenas](#formateo-de-cadenas)
      - [Tipos de formato en strings](#tipos-de-formato-en-strings)
    - [Casting de tipos de datos](#casting-de-tipos-de-datos)
  - [OPERADORES](#operadores)
    - [Operadores de asignación](#operadores-de-asignación)
    - [Operadores bit a bit](#operadores-bit-a-bit)
  - [ENTRADA DE DATOS DEL USUARIO](#entrada-de-datos-del-usuario)
    - [Entradas múltiples](#entradas-múltiples)
    - [Convertir la entrada a otros tipos de datos](#convertir-la-entrada-a-otros-tipos-de-datos)
    - [Manejo de errores en la entrada](#manejo-de-errores-en-la-entrada)
  - [ESTRUCTURAS DE CONTROL](#estructuras-de-control)
    - [Estructuras condicionales](#estructuras-condicionales)
      - [Estructura if](#estructura-if)
      - [Estructura if-elif](#estructura-if-elif)
      - [Estructura if-elif-else](#estructura-if-elif-else)
      - [Anidamiento de estructuras if](#anidamiento-de-estructuras-if)
    - [Estructura match (Python 3.10+)](#estructura-match-python-310)
    - [Estructuras de control repetitivas](#estructuras-de-control-repetitivas)
      - [Estructura while](#estructura-while)
      - [Estructura for](#estructura-for)
      - [Uso de range() en for](#uso-de-range-en-for)
      - [Uso de break y continue](#uso-de-break-y-continue)
    - [Uso de la instrucción pass](#uso-de-la-instrucción-pass)
  - [COLECCIONES](#colecciones)
    - [Mutabilidad e inmutabilidad](#mutabilidad-e-inmutabilidad)
    - [Listas](#listas)
      - [Métodos de listas](#métodos-de-listas)
      - [Más sobre listas](#más-sobre-listas)
    - [Tuplas](#tuplas)
      - [Añadir elementos](#añadir-elementos)
      - [Métodos de tuplas](#métodos-de-tuplas)
    - [Conjuntos](#conjuntos)
      - [Operaciones con conjuntos](#operaciones-con-conjuntos)
      - [Métodos de conjuntos](#métodos-de-conjuntos)
    - [Diccionarios](#diccionarios)

## INTRODUCCIÓN
`Python` es un lenguaje de programación potente y fácil de aprender. Tiene estructuras de datos de alto nivel eficientes y un simple pero efectivo sistema de programación orientado a objetos. La elegante sintaxis de Python y su tipado dinámico, junto a su naturaleza interpretada lo convierten en un lenguaje ideal para scripting y desarrollo rápido de aplicaciones en muchas áreas, para la mayoría de plataformas.

`El intérprete de Python` y la extensa librería estándar se encuentran disponibles libremente en código fuente y de forma binaria para la mayoría de las plataformas desde [la Web de Python](https://www.python.org/)y se pueden distribuir libremente. El mismo sitio también contiene distribuciones y referencias a muchos módulos libres de Python de terceros, programas, herramientas y documentación adicional.

`El intérprete de Python` es fácilmente extensible con funciones y tipos de datos implementados en C o C++ (u otros lenguajes que permitan ser llamados desde C). Python también es apropiado como un lenguaje para extender aplicaciones modificables.

`Python` es un lenguaje interpretado, lo cual puede ahorrarte mucho tiempo durante el desarrollo ya que no es necesario compilar ni enlazar. El intérprete puede usarse interactivamente, lo que facilita experimentar con características del lenguaje, escribir programas desechables o probar funciones cuando se hace desarrollo de programas de abajo hacia arriba. Es también **una calculadora** de escritorio práctica.

`Python` permite escribir programas compactos y legibles. Los programas en Python son típicamente más cortos que sus programas equivalentes en C, C++ o Java por varios motivos:

* Los tipos de datos de alto nivel permiten expresar operaciones complejas en una sola instrucción.
* La agrupación de instrucciones se hace mediante indentación en vez de llaves de apertura y cierre.
* No es necesario declarar variables ni argumentos.

Por cierto, el lenguaje recibe su nombre del programa de televisión de la BBC «Monty Python’s Flying Circus» y no tiene nada que ver con reptiles. Hacer referencias sobre Monty Python en la documentación no sólo esta permitido, ¡sino que también está bien visto!

## INSTALACIÓN EN EL ENTORNO WINDOWS

1. **Ir a la página oficial:**
   - Visita: https://python.org
   - Haz clic en "Downloads"
   - Descarga la versión más reciente (Python 3.13.x)

2. **Durante la instalación:**
   - ✅ **MUY IMPORTANTE:** Marca "Add Python to PATH"
   - ✅ Marca "Install launcher for all users"
   - Haz clic en "Install Now

3. **Verificar la instalación:**
   - Abre "Símbolo del sistema" o "PowerShell"
   - Escribe: `python --version`
   - Deberías ver algo como: `Python 3.13.x`

4. **Configurar VS Code:**
   - Abre VS Code en Windows
   - Instala la extensión de Python
   - VS Code detectará automáticamente tu instalación

### Ventajas de esta instalación:
- ✅ Más simple y directa
- ✅ Mejor integración con Windows
- ✅ Acceso a todas las librerías
- ✅ Mejor rendimiento

## CONFIGURACIÓN DEL ENTORNO DE DESARROLLO (IDE)

Para comenzar a aprender Python, instalaremos **Visual Studio Code** (VS Code) como IDE. Es una excelente opción por estas razones:

### Ventajas de VS Code para Python:

1. **Gratuito y de código abierto**
2. **Excelente soporte para Python** con extensiones oficiales
3. **IntelliSense** (autocompletado inteligente)
4. **Depurador integrado**
5. **Terminal integrado**
6. **Soporte para Jupyter Notebooks**
7. **Control de versiones Git integrado**
8. **Gran cantidad de extensiones útiles**

### Extensiones recomendadas de Python en VS Code:

Instalar las extensiones esenciales: 
* Python
* Pylint , **Pylint** es una herramienta muy útil para principiantes en Python. 
* Jupiter
### ¿Qué es Pylint?
Pylint es un **analizador de código estático** que te ayuda a:

 1. Detecta errores antes de ejecutar
- Encuentra errores de sintaxis
- Detecta variables no definidas
- Identifica importaciones incorrectas

2. Mejora la calidad del código
- Te sugiere mejores prácticas de programación
- Detecta código redundante o innecesario
- Identifica funciones o variables no utilizadas

3. Sigue las convenciones de Python (PEP 8)
- Te ayuda a escribir código más legible
- Sugiere nombres de variables más claros
- Corrige problemas de formato y espaciado

4. Aprende mientras programas
- Te da consejos sobre cómo mejorar tu código
- Explica por qué algo puede ser problemático
- Te enseña buenas prácticas de Python

**Ejemplo práctico**:

Si escribes esto:
```python
def miFuncion():  # Pylint sugiere usar snake_case: mi_funcion
    x=1+2         # Pylint sugiere espacios: x = 1 + 2
    return x
```

Pylint te mostrará:
- ⚠️ "Function name should be in snake_case"
- ⚠️ "Missing whitespace around operator"

**¿Es necesario para empezar?**
No es **esencial**, pero es **muy recomendado** porque:
- Te ayuda a aprender las mejores prácticas desde el inicio
- Evita que desarrolles malos hábitos
- Hace tu código más profesional y legible

### ¿Qué es Jupyter?
Jupyter te permite crear **notebooks interactivos** donde puedes:

1. Experimentar paso a paso
- Ejecutas código en pequeñas celdas
- Ves el resultado inmediatamente
- Puedes modificar y volver a ejecutar fácilmente

2. Combinar código con explicaciones
- Mezclas código Python con texto explicativo
- Documentas lo que haces mientras aprendes
- Creas "cuadernos de notas" de programación

3. Ideal para aprendizaje
- Perfecto para tutoriales y ejercicios
- Puedes probar conceptos sin crear archivos completos
- Visualizas datos y gráficos directamente

4. Muy usado en ciencia de datos
- Análisis de datos
- Machine Learning
- Visualización de gráficos

**Ejemplo de uso:**

**Celda 1:**
```python
# Mi primera variable
nombre = "Ana"
edad = 25
print(f"Hola {nombre}, tienes {edad} años")
```
**Resultado:** `Hola Ana, tienes 25 años`

**Celda 2:**
```python
# Probemos una lista
numeros = [1, 2, 3, 4, 5]
suma = sum(numeros)
print(f"La suma es: {suma}")
```
**Resultado:** `La suma es: 15`

**¿Es esencial para empezar?**
- **No es obligatorio**, puedes aprender Python con archivos `.py` normales
- **Pero es muy recomendado** porque hace el aprendizaje más interactivo y visual
- Es **estándar** en cursos de Python y ciencia de datos

### Configurar el VSCode: Detecta la versión de Python y configura el intérprete
- Encuentra qué versión de Python tienes instalada
- Se asegura de que VS Code use la correcta
- Le dice a VS Code dónde encontrar Python
- Permite que el autocompletado funcione correctamente
- Cuando instalas Python en Windows usando el instalador oficial, por defecto lo instala en una de estas rutas:
    - Para todos los usuarios:  
  `C:\Program Files\Python3x\`  
  (por ejemplo, `C:\Program Files\Python313\`)
    - Solo para el usuario actual:  
  `C:\Users\<tu_usuario>\AppData\Local\Programs\Python\Python3x\`  
  (por ejemplo, Python313)
El ejecutable principal es `python.exe` dentro de esa carpeta. 
- Si usas una versión específica o un entorno virtual, debes apuntar a esa ruta
Sí, existe una configuración de intérprete de Python a nivel de usuario en VS Code, normalmente en el archivo `settings.json` ubicado en %APPDATA%/Code/User/settings.json en Windows.

En ese archivo puedes encontrar (o agregar) el parámetro:
```json
{
  "python.defaultInterpreterPath": "C:\\ruta\\a\\tu\\python.exe"
}
```
Asegúrate de reemplazar `"C:\\ruta\\a\\tu\\python.exe"` con la ruta correcta a tu instalación de Python.

## MODO INTERACTIVO
Cuando se leen los comandos desde un terminal, se dice que el intérprete está en modo interactivo. En este modo, espera el siguiente comando con el prompt primario, generalmente tres signos de mayor que `(>>>)`; para las líneas de continuación, aparece el prompt secundario, por defecto tres puntos `(...)`. El intérprete imprime un mensaje de bienvenida que indica su número de versión y un aviso de copyright antes de imprimir el primer prompt primario:

```python
$py 
Python 3.13.7 (tags/v3.13.7:bcee1c3, Aug 14 2025, 14:15:11) [MSC v.1944 64 bit (AMD64)] on win32
Type  "help", "copyright", "credits" or "license" for more information.

>>> print("Hola, Mundo!")
... 
Hola, Mundo! 
>>>
```
## UTILIZAR COMENTARIOS
Los comentarios en Python comienzan con el carácter numeral,**#**, y se extienden hasta el final visible de la línea. Un comentario quizás aparezca al comienzo de la línea o seguido de espacios en blanco o código, pero no dentro de una cadena de caracteres.

```python
# este es el primer comentario
spam = 1  # este es el segundo comentario
          # ... este es el tercer comentario!
text = "# este no es un comentario porque está entre comillas dobles."
```
Para comentar en varias líneas puedes usar una cadena multilínea.

Como Python ignora las cadenas literales que no están asignadas a una variable, puedes añadir una cadena multilínea (entre comillas triples) a tu código y colocar tu comentario dentro:
```python
"""
Este es un comentario
escrito en más de una
línea
"""
```
### Documentar el código
**Un docstring (document string)** es una cadena de texto especial que se coloca al inicio de un módulo, función, clase o método en Python, encerrada entre triple comillas `(""" ... """)`. Sirve para documentar el propósito y uso del bloque de código.

```python
def suma(a, b):
    """Devuelve la suma de a y b."""
    return a + b
```
Los docstrings permiten que herramientas y editores muestren ayuda y documentación automáticamente. No son comentarios normales, sino documentación accesible desde el propio código con **la función help()**.

#### Ejemplo de uso de la función help()

La función `help()` nos permite acceder a la documentación de cualquier objeto en Python:

```python
# Definimos una función con docstring
def calcular_area_rectangulo(base, altura):
    """
    Calcula el área de un rectángulo.
    
    Parámetros:
    base (float): La base del rectángulo
    altura (float): La altura del rectángulo
    
    Retorna:
    float: El área del rectángulo (base * altura)
    """
    return base * altura

# Usamos help() para ver la documentación
help(calcular_area_rectangulo)
```

**Salida:**
```
Help on function calcular_area_rectangulo in module __main__:

calcular_area_rectangulo(base, altura)
    Calcula el área de un rectángulo.
    
    Parámetros:
    base (float): La base del rectángulo
    altura (float): La altura del rectángulo
    
    Retorna:
    float: El área del rectángulo (base * altura)
```

**Otros ejemplos de uso de help():**

```python
# Ayuda sobre tipos de datos
help(str)           # Información sobre strings
help(list)          # Información sobre listas
help(int)           # Información sobre enteros

# Ayuda sobre funciones incorporadas
help(print)         # Información sobre la función print
help(len)           # Información sobre la función len
help(input)         # Información sobre la función input

# Ayuda sobre métodos específicos
help(str.upper)     # Método upper de strings
help(list.append)   # Método append de listas

# Ayuda sobre módulos
import math
help(math)          # Información sobre el módulo math
help(math.sqrt)     # Información sobre la función sqrt
```

La extension de visual studio **Pylint**, nos obliga a documentar el programa

```python
"""Este ejercicio imprime un saludo."""
# la primera línea de comentario la obliga a utilizar la extensión Pylint
print("Hola, Mundo!")
```
## INDENTACIÓN DEL CÓDIGO
La sangría se refiere a los espacios al principio de una línea de código.
Mientras que en otros lenguajes de programación la sangría solo se utiliza para facilitar la lectura, en Python es muy importante.

Python utiliza la sangría para indicar un bloque de código.
Por ejemplo, en otros lenguajes de programación, podrías escribir algo como esto:

```c
if (x > 0) {
    printf("x es positivo\n");
}
```
En Python, la misma estructura se escribiría así:

```python
if x > 0:
    print("x es positivo")
```
La cantidad de espacios en la sangría es variable, pero todos los comandos en un bloque deben tener la misma cantidad de espacios. La convención es usar cuatro espacios por nivel de sangría.

```python
if x > 0:
    print("x es positivo")
    if x > 10:
        print("x es mayor que 10")
    else:
        print("x es 10 o menor")
else:
    print("x no es positivo")
```

## DEFINICIÓN DE VARIABLES
Una variable es un nombre que se refiere a un valor. En Python, no es necesario declarar una variable antes de usarla o declarar su tipo. Una variable se crea en el momento en que se le asigna un valor por primera vez.

```python  
contador = 100          # un número entero
kilometros = 1000.0     # un número decimal
nombre = "Juan"        # una cadena de texto
print(contador)
print(kilometros)
print(nombre)
```
## TIPOS DE DATOS
Python tiene varios tipos de datos integrados, algunos de los más comunes son:

### 1. **Numéricos**: `int`, `float`, `complex`
Podemos utilizar python como una calculadora. El intérprete funciona como una simple calculadora: puedes introducir una expresión en él y este escribirá los valores. La sintaxis es sencilla: los operadores `+`, `-`, `*` y `/` se pueden usar para realizar operaciones aritméticas; los paréntesis `()` pueden ser usados para agrupar. Por ejemplo:

```python
>>> 2 + 2
4
>>> 50 - 5*6
20
>>> (50 - 5*6) / 4
5.0
>>> 8 / 5  # división siempre devuelve un flotante
1.6
>>> 5 * 3 + 2  # combina ambos
17
```
El operador // (división entera) trunca el resultado a un número entero:
```python
>>> 17 / 3  # división normal devuelve un flotante
5.666666666666667
>>> 17 // 3  # división entera trunca el resultado
5
```
El operador %  devuelve el resto
```python
>>> 17 % 3  # el operador módulo devuelve el resto de la división
2
```
El operador ** eleva a la potencia
```python
>>> 5 ** 2  # 5 al cuadrado
25
>>> 2 ** 7  # 2 a la séptima potencia
128
```
**Crear variables y asignar valor**
El signo igual `(=)` se usa para asignar un valor a una variable. Después, no se muestra ningún resultado antes del siguiente prompt interactivo

```python
>>> ancho = 20
>>> alto = 5 * 9
>>> ancho * alto
900
```
Si una variable no está «definida» (no se le ha asignado un valor), al intentar usarla dará un error:
```python
>>> n  # intenta usar una variable no definida
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>  
NameError: name 'n' is not defined
```
**Operadores de comparación**
Los operadores de comparación son muy útiles en las expresiones condicionales. Devuelven un valor booleano: `True` o `False`. Por ejemplo:

```python
>>> 3 < 4  # menor que
True
>>> 3 > 4  # mayor que
False
>>> 3 == 4  # igual a
False
>>> 3 != 4  # diferente de
True

>>> n = 17
>>> n % 2  # el resto de la división por 2
1
>>> n % 2 == 0  # ¿es n par?
False
>>> n % 2 == 1  # ¿es n impar?
True
```
En el modo interactivo, la última expresión impresa se asigna a la variable `_`. Esto significa que cuando se está utilizando Python como calculadora, es más fácil seguir calculando, por ejemplo:

```python
>>> impuesto = 12.5 / 100
>>> precio = 100.50
>>> precio * impuesto
12.5625
>>> precio + _  # añade el impuesto al precio
113.0625
>>> round(_, 2)  # redondea a 2 decimales
113.06
```
Esta variable debe ser tratada como de sólo lectura por el usuario. No le asignes explícitamente un valor porque crearás una variable local independiente con el mismo nombre enmascarando la variable con el comportamiento mágico.
Además de `int` y `float`, Python admite otros tipos de números, como `Decimal` y `Fraction`. Python también tiene soporte incorporado para `complex` números complejos, y usa el sufijo j o J para indicar la parte imaginaria (por ejemplo, 3+5j).

### 2. **Texto**
Python puede manipular texto (representado por el tipo `str`, conocido como «cadenas de caracteres») al igual que números. Esto incluye caracteres `«!»`, palabras `«conejo»`, nombres `«París»`, oraciones `«¡te cubre las espaldas! »`, etc. `«¡Genial!»`. Se pueden encerrar en comillas simples `('...')` o comillas dobles `("...")` con el mismo resultado

```python
>>> "manzana"  # comillas simples
'manzana'
>>> "¡La manzana de Madrid te cubre las espaldas! ¡Genial!"  # Comillas dobles
'¡La manzana de Madrid te cubre las espaldas! ¡Genial!'
>>> '1975'  # Los dígitos y números entre comillas también son cadenas
'1975'
>>> "2025"  # Los dígitos y números entre comillas también son cadenas
'2025'
```
**Caracteres de escape**
Para insertar caracteres no permitidos en una cadena se utiliza el caracter de escape.
El carácter de escape consiste en una barra diagonal inversa `(\)` seguida del carácter que desea insertar.
Un ejemplo de carácter no permitido es una comilla simple dentro de una cadena delimitada por comillas simples. Alternativamente, podemos usar el otro tipo de comillas:

```python
>>> 'doesn\'t'  # usa la barra invertida para escapar la comilla simple
"doesn't"
>>> "doesn't"  # o usa comillas dobles en su lugar
"doesn't"
>>> '"Yes," he said.'
'"Yes," he said.'
>>> "\"Yes,\" he said."
'"Yes," he said.'
>>> '"Isn\'t," she said.'
'"Isn\'t," she said.'   
```
**Tabla de los caracteres de escape más comunes**

| Código  | Resultado           |
|---------|---------------------|
| `\'`      | Comilla simple      |
| `\\`      | Barra invertida     |
| `\n`      | Nueva línea         |
| `\r`      | Retorno de carro    |
| `\t`      | Tabulación          |
| `\b`      | Retroceso           |
| `\f`      | Avance de página    |
| `\ooo`    | Valor octal         |
| `\xhh`    | Valor hexadecimal   |


En el intérprete de Python, la definición de cadena y la cadena de salida pueden verse diferentes. La **función print()** produce una salida más legible, omitiendo las comillas de encuadre e imprimiendo caracteres escapados y especiales:

```python
>>> cadena = 'Primera línea.\nSegunda línea.'  # \n significa nueva línea
>>> cadena  # muestra la representación «oficial»
'Primera línea.\nSegunda línea.'
>>> print(cadena)  # muestra la cadena en forma legible
Primera línea.
Segunda línea.
```
* Cuando escribes solo el nombre de la variable (cadena), Python muestra la representación oficial, incluyendo el carácter especial \n.
* Cuando usas print(cadena), Python imprime el texto en varias líneas,
Las cadenas pueden ser concatenadas (unidas) con el operador +, y repetidas con *:

```python
>>> 'Hola' + 'Mundo'
'HolaMundo'
>>> 'Hola ' + 'Mundo'
'Hola Mundo'
>>> 'Hola ' * 3
'Hola Hola Hola '
>>> 'Hola ' * 3 + '!'
'Hola Hola Hola !'
>>> 'Hola ' * (3 + 1)
'Hola Hola Hola Hola '
>>> 'Hola ' * 3.0
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can't multiply sequence by non-int of type 'float'
```
Dos o más cadenas literales (es decir, las encerradas entre comillas) una al lado de la otra se concatenan automáticamente.

```python
>>> 'Hola' 'Mundo'
'HolaMundo'
>>> 'Hola'     'Mundo'
'HolaMundo'
>>> ('Hola'
... 'Mundo')
'HolaMundo'
```
Esta característica es particularmente útil cuando quieres dividir cadenas largas

```python
>>> text = ('Este es un texto muy largo y no quiero '
... 'escribirlo todo en una sola línea')
>>> text
'Este es un texto muy largo y no quiero escribirlo todo en una sola línea'
>>> print(text)
Este es un texto muy largo y no quiero escribirlo todo en una sola línea
```
Esto solo funciona con dos literales, no con variables ni expresiones:

```python
>>> prefijo = 'Hola'
>>> prefijo 'Mundo'
  File "<stdin>", line 1
    prefijo 'Mundo'
           ^
SyntaxError: invalid syntax
>>> (prefijo + ' ') 'Mundo'
  File "<stdin>", line 1
    (prefijo + ' ') 'Mundo'
                   ^ 
SyntaxError: invalid syntax
```
Si quieres concatenar variables o una variable y un literal, usa +:

```python
>>> prefijo + ' ' + 'Mundo'
'Hola Mundo'
>>> (prefijo + ' ') + 'Mundo'
'Hola Mundo'
```
Las cadenas de texto se pueden indexar (subíndices), el primer carácter de la cadena tiene el índice 0. No hay un tipo de dato diferente para los caracteres; un carácter es simplemente una cadena de longitud uno:

```python
>>> palabra = 'Python'
>>> palabra[0]  # primer carácter
'P'
>>> palabra[5]  # sexto carácter
'n'
```
Los índices también pueden ser números negativos, para empezar a contar desde la derecha:

```python
>>> palabra[-1]  # último carácter
'n'
>>> palabra[-2]  # penúltimo carácter
'o'
>>> palabra[-6]  # primer carácter
'P'
```
Los índices fuera del rango válido generan un error:

```python
>>> palabra[6]  # error, el índice está fuera del rango
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: string index out of range
>>> palabra[-7]  # error, el índice está fuera del rango
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: string index out of range
```
Nótese que -0 es lo mismo que 0, los índice negativos comienzan desde -1.

Además de los índices, las rebanadas (slicing) también están soportadas. Mientras que la indexación se utiliza para obtener caracteres individuales, rebanar te permite obtener una subcadena:

```python
>>> palabra[0:2]  # caracteres desde el índice 0 hasta (pero sin incluir) el 2
'Py'
>>> palabra[2:5]  # caracteres desde el índice 2 hasta (pero sin incluir) el 5
'tho'
```
Los índices de las rebanadas tienen valores por defecto útiles; el valor por defecto para el primer índice es cero, el valor por defecto para el segundo índice es la longitud de la cadena a rebanar.

```python
>>> palabra[:2]   # los dos primeros caracteres
'Py'
>>> palabra[4:]   # desde el quinto carácter hasta el final
'on'
>>> palabra[-2:]  # los dos últimos caracteres
'on'
>>> palabra[:-2]  # todos menos los dos últimos caracteres
'Pyth'
>>> palabra[:]    # una copia de toda la cadena
'Python'
```
Resumiendo:
El primer índice es inclusivo, el segundo no. Si el primer índice es omitido, se asume que es 0; si el segundo índice es omitido, se asume que es la longitud de la cadena (es decir, hasta el final de la cadena). Si ambos índices son omitidos, se obtiene una copia de toda la cadena.

Ten en cuenta que los índices negativos pueden ser usados en las rebanadas:

```python
>>> palabra[-4:-2]  # los dos caracteres antes de los dos últimos
'th'
>>> palabra[-2:]    # los dos últimos caracteres
'on'
'on'
```
Las rebanadas pueden tener un tercer índice, llamado paso (step), que especifica el incremento entre cada índice para la rebanada:

```python
>>> palabra[::2]  # toma cada segundo carácter
'Pto' 
>>> palabra[1::2]  # toma cada segundo carácter, empezando desde el segundo
'yhn'
>>> palabra[::-1]  # toma todos los caracteres, pero en orden inverso
'nohtyP'
```
El paso puede ser negativo, lo que significa que la rebanada se hace de derecha a izquierda:

```python
>>> palabra[::-2]  # toma cada segundo carácter, pero en orden inverso
'nhy'
>>> palabra[5:1:-1]  # rebanada desde el índice 5 hasta (pero sin incluir) el 1, en orden inverso
'noht'
>>> palabra[5:1:-2]  # rebanada desde el índice 5 hasta (pero sin incluir) el 1, tomando cada segundo carácter
'nt'
>>> palabra[1:5:-1]  # no hay caracteres en esta rebanada
''
>>> palabra[5:1]  # no hay caracteres en esta rebanada
''
```
Una forma de recordar cómo funcionan las rebanadas es pensar que los índices apuntan entre caracteres, con el borde izquierdo del primer carácter numerado 0. Luego, el punto derecho del último carácter de una cadena de n caracteres tiene un índice n, por ejemplo
```python
 +---+---+---+---+---+---+
 | P | y | t | h | o | n |
 +---+---+---+---+---+---+
 0   1   2   3   4   5   6
   -6  -5  -4  -3  -2  -1
```
La primera fila de números da la posición de los índices 0…6 en la cadena; La segunda fila da los correspondientes indices negativos. La rebanada desde i hasta j consta de todos los caracteres entre los bordes etiquetados i y j, respectivamente.

Para índices no negativos, la longitud de la rebanada es la diferencia de los índices, si ambos están dentro de los límites. Por ejemplo, la longitud de palabra[1:3] es 2.

```python
>>> len(palabra[1:3])
2
>>> len(palabra[1:100])  # el segundo índice está fuera del rango
5
>>> len(palabra[1:1])  # los índices son iguales
0
>>> len(palabra[3:1])  # el primer índice es mayor que el segundo
0
```
Si el paso es n, entonces se toman cada n-ésimo carácter. Por ejemplo, la longitud de palabra[1:5:2] es 2:

```python
>>> len(palabra[1:5:2])
2
>>> palabra[1:5:2]
'yt'
>>> len(palabra[::3])
2
>>> palabra[::3]
'Ph'
>>> len(palabra[1::3])
2
>>> palabra[1::3]
'yo'
>>> len(palabra[::-1])
6
>>> palabra[::-1]
'nohtyP'
>>> len(palabra[::-2])
3
>>> palabra[::-2]
'nyh'
>>> len(palabra[5:1:-1])
4
>>> palabra[5:1:-1]
'noht'
>>> len(palabra[5:1:-2])
2
>>> palabra[5:1:-2]
'nt'
>>> len(palabra[1:5:-1])  # no hay caracteres en esta rebanada
0
>>> palabra[1:5:-1]
''
>>> len(palabra[5:1])  # no hay caracteres en esta rebanada
0
>>> palabra[5:1]
''
```
Las cadenas son inmutables, lo que significa que no pueden ser cambiadas después de ser creadas. Por ejemplo, la asignación de un carácter individual en una cadena produce un error:

```python
>>> palabra[0] = 'J'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module> 
TypeError: 'str' object does not support item assignment
```

### Métodos de strings
Los métodos son funciones que están asociadas a un objeto. Por ejemplo, los strings tienen varios métodos integrados que pueden ser usados para realizar operaciones en la cadena. Aquí hay algunos ejemplos comunes:

```python
>>> cadena = "hola mundo"
>>> cadena.upper()  # convierte a mayúsculas
'HOLA MUNDO'
>>> cadena.lower()  # convierte a minúsculas
'hola mundo'
>>> cadena.capitalize()  # convierte el primer carácter a mayúscula
'Hola mundo'
>>> cadena.title()  # convierte el primer carácter de cada palabra a mayúscula
'Hola Mundo'
>>> cadena.strip()  # elimina espacios en blanco al inicio y al final
'hola mundo'
>>> cadena.replace("mundo", "Python")  # reemplaza una subcadena
'hola Python'
>>> cadena.split()  # divide la cadena en una lista de palabras
['hola', 'mundo']
>>> ' '.join(['hola', 'Python'])  # une una lista de palabras en una cadena
'hola Python'
>>> cadena.find("mundo")  # encuentra la posición de una subcadena
5
>>> cadena.find("Python")  # devuelve -1 si no se encuentra la subcadena
-1
>>> s.startswith("hello")  # verifica si la cadena empieza con un prefijo
True
>>> s.endswith("world")  # verifica si la cadena termina con un sufijo
True
>>> len(s)  # obtiene la longitud de la cadena
11
```
#### Tabla de los métodos de strings más comunes

| Método         | Descripción                                                                 |
|----------------|-----------------------------------------------------------------------------|
| capitalize()   | Convierte el primer carácter en mayúscula                                   |
| casefold()     | Convierte la cadena en minúsculas                                           |
| center()       | Devuelve una cadena centrada                                                |
| count()        | Devuelve el número de veces que un valor especificado aparece en la cadena  |
| encode()       | Devuelve una versión codificada de la cadena                                |
| endswith()     | Devuelve True si la cadena termina con el valor especificado                |
| expandtabs()   | Establece el tamaño de la tabulación de la cadena                          |
| find()         | Busca un valor especificado y devuelve la posición donde se encontró        |
| format()       | Formatea valores especificados en una cadena                                |
| format_map()   | Formatea valores especificados en una cadena                                |
| index()        | Busca un valor especificado y devuelve la posición donde se encontró        |
| isalnum()      | Devuelve True si todos los caracteres son alfanuméricos                     |
| isalpha()      | Devuelve True si todos los caracteres están en el alfabeto                  |
| isascii()      | Devuelve True si todos los caracteres son ASCII                             |
| isdecimal()    | Devuelve True si todos los caracteres son decimales                         |
| isdigit()      | Devuelve True si todos los caracteres son dígitos                           |
| isidentifier() | Devuelve True si la cadena es un identificador                             |
| islower()      | Devuelve True si todos los caracteres están en minúsculas                   |
| isnumeric()    | Devuelve True si todos los caracteres son numéricos                         |
| isprintable()  | Devuelve True si todos los caracteres son imprimibles                       |
| isspace()      | Devuelve True si todos los caracteres son espacios en blanco                |
| istitle()      | Devuelve True si la cadena sigue las reglas de un título                    |
| isupper()      | Devuelve True si todos los caracteres están en mayúsculas                   |
| join()         | Une los elementos de un iterable al final de la cadena                      |
| ljust()        | Devuelve una versión justificada a la izquierda de la cadena                |
| lower()        | Convierte la cadena en minúsculas                                           |
| lstrip()       | Devuelve una versión recortada a la izquierda de la cadena                  |
| maketrans()    | Devuelve una tabla de traducción para usar en traducciones                  |
| partition()    | Devuelve una tupla donde la cadena se divide en tres partes                 |
| replace()      | Devuelve una cadena donde un valor especificado es reemplazado              |
| rfind()        | Busca un valor especificado y devuelve la última posición donde se encontró |
| rindex()       | Busca un valor especificado y devuelve la última posición donde se encontró |
| rjust()        | Devuelve una versión justificada a la derecha de la cadena                  |
| rpartition()   | Devuelve una tupla donde la cadena se divide en tres partes                 |
| rsplit()       | Divide la cadena en el separador especificado y devuelve una lista          |
| rstrip()       | Devuelve una versión recortada a la derecha de la cadena                    |
| split()        | Divide la cadena en el separador especificado y devuelve una lista          |
| splitlines()   | Divide la cadena en saltos de línea y devuelve una lista                    |
| startswith()   | Devuelve True si la cadena comienza con el valor especificado               |
| strip()        | Devuelve una versión recortada de la cadena                                 |
| swapcase()     | Intercambia mayúsculas y minúsculas                                         |
| title()        | Convierte el primer carácter de cada palabra en mayúscula                   |
| translate()    | Devuelve una cadena traducida                                               |
| upper()        | Convierte la cadena en mayúsculas                                           |
| zfill()        | Rellena la cadena con ceros al principio                                    |

### Formateo de cadenas
Las cadenas de formato (**f-strings**) se introdujeron en Python 3.6 y actualmente son el método preferido para formatear cadenas de texto.Antes de Python 3.6, teníamos que usar **el método format()**.
**Marcadores de posición y modificadores**
Para definir una cadena como f-string, simplemente coloque una `"f"` delante del literal de la cadena y utilice llaves `{}` como marcadores de posición para las variables y otras operaciones.

```python
>>> nombre = "Ana"
>>> edad = 25
>>> f"Hola, {nombre}. Tienes {edad} años."
'Hola, Ana. Tienes 25 años.'
>>> f"El próximo año tendrás {edad + 1} años."
'El próximo año tendrás 26 años.'
>>> f"{2 * 37}"
'74'
>>> f"{3.14159:.2f}"  # formatea el número a 2 decimales
'3.14'
```
Las f-strings también soportan expresiones más complejas dentro de las llaves, como llamadas a funciones y métodos:

```python
>>> nombre = "Ana"
>>> f"Hola, {nombre.upper()}."  # llama al método upper() en la variable nombre
'Hola, ANA.'
>>> f"El número de caracteres en tu nombre es {len(nombre)}."  # llama a la función len()
'El número de caracteres en tu nombre es 3.'
```
Las f-strings pueden abarcar múltiples líneas utilizando comillas triples:

```python
>>> nombre = "Ana"
>>> edad = 25
>>> f"""Hola, {nombre}.
... Tienes {edad} años."""
'Hola, Ana.\nTienes 25 años.'
>>> print(f"""Hola, {nombre}.
... Tienes {edad} años.""")
Hola, Ana.
Tienes 25 años.
```
Un marcador de posición también puede incluir un modificador para dar formato al valor.
```python
>>> precio = 49.99
>>> f"El precio es ${precio:.2f}"  # formatea el número a 2 decimales
'El precio es $49.99'
>>> f"El precio es ${precio:,.2f}"  # formatea el número con coma como separador de miles
'El precio es $49.99'
>>> f"El precio es ${precio:*>10.2f}"  # formatea el número con relleno de asteriscos
'El precio es $****49.99'
```
#### Tipos de formato en strings

| Formato | Descripción                                                                 |
|---------|-----------------------------------------------------------------------------|
| :<      | Alinea a la izquierda el resultado (en el espacio disponible)               |
| :>      | Alinea a la derecha el resultado (en el espacio disponible)                 |
| :^      | Centra el resultado (en el espacio disponible)                              |
| :=      | Coloca el signo en la posición más a la izquierda                           |
| :+      | Usa un signo más para indicar si el resultado es positivo o negativo        |
| :-      | Usa un signo menos solo para valores negativos                              |
| :       | Inserta un espacio extra antes de números positivos (y un menos si negativo)|
| :,      | Usa una coma como separador de miles                                        |
| :_      | Usa un guion bajo como separador de miles                                   |
| :b      | Formato binario                                                             |
| :c      | Convierte el valor en el carácter Unicode correspondiente                   |
| :d      | Formato decimal                                                             |
| :e      | Formato científico, con una e minúscula                                     |
| :E      | Formato científico, con una E mayúscula                                     |
| :f      | Formato de número de punto fijo                                             |
| :F      | Formato de número de punto fijo, en mayúsculas (INF y NAN)                  |
| :g      | Formato general                                                             |
| :G      | Formato general (usa E mayúscula para notación científica)                  |
| :o      | Formato octal                                                               |
| :x      | Formato hexadecimal, minúsculas                                             |
| :X      | Formato hexadecimal, mayúsculas                                             |
| :n      | Formato de número                                                           |
| :%      | Formato de porcentaje                                                       |

### Casting de tipos de datos
Puedes convertir entre diferentes tipos de datos usando las funciones integradas `int()`, `float()`, y `str()`:

```python
>>> int('123')  # convierte una cadena a un entero
123
>>> int(12.34)  # convierte un flotante a un entero (trunca el decimal)
12
>>> float('12.34')  # convierte una cadena a un flotante
12.34
>>> float(123)  # convierte un entero a un flotante
123.0
>>> str(123)  # convierte un entero a una cadena
'123'
>>> str(12.34)  # convierte un flotante a una cadena
'12.34'
```

## OPERADORES
Los operadores se utilizan para realizar operaciones con variables y valores.

| Operador | Descripción               | Ejemplo       | Resultado |
|----------|---------------------------|---------------|-----------|
| +        | Suma                      | x + y         | 5         |
| -        | Resta                     | x - y         | -1        |
| *        | Multiplicación            | x * y         | 6         |
| /        | División                  | x / y         | 0.66666667|
| //       | División entera           | x // y        | 0         |
| %        | Módulo (resto de división) | x % y         | 2         |
| **       | Exponenciación            | x ** y        | 9         |
| ==       | Igualdad                  | x == y        | False     |
| !=       | Desigualdad               | x != y        | True      |
| >        | Mayor que                 | x > y         | False
| <        | Menor que                 | x < y         | True      |
| >=       | Mayor o igual que         | x >= y        | False
| <=       | Menor o igual que         | x <= y        | True      |
| and      | Lógico Y                  | x and y       | False     |
| or       | Lógico O                  | x or y        | True      |
| not      | Lógico NO                 | not x         | False     |
| is       | Identidad                 | x is y        | False     |
| is not   | No identidad              | x is not y    | True      |
| in       | Pertenencia               | x in y        | True      |
| not in   | No pertenencia            | x not in y    | False     |

### Operadores de asignación

| Operador | Descripción               | Ejemplo       | Resultado |
|----------|---------------------------|---------------|-----------|
| =        | Asignación                | x = 5         | x = 5     |
| +=       | Suma y asignación         | x += 3        | x = x + 3 |
| -=       | Resta y asignación        | x -= 2        | x = x - 2 |
| *=       | Multiplicación y asignación | x *= 4      | x = x * 4 |
| /=       | División y asignación     | x /= 2        | x = x / 2 |
| //=      | División entera y asignación | x //= 3    | x = x // 3|
| %=       | Módulo y asignación       | x %= 2        | x = x % 2 |
| **=      | Exponenciación y asignación | x **= 2     | x = x ** 2|
| &=       | AND bit a bit y asignación   | x &= 3    | x = x & 3 |
| \|=       | OR bit a bit y asignación    | x \|= 3     | x = x \| 3 |
| ^=       | XOR bit a bit y asignación   | x ^= 3     | x = x ^ 3 |
| >>=      | Desplazamiento derecha y asignación | x >>= 3 | x = x >> 3|
| <<=      | Desplazamiento izquierda y asignación | x <<= 3 | x = x << 3|
| :=       | Asignación por expresión     | print(x := 3) | x = 3 |
|          |                              |               |print(x)|

### Operadores bit a bit
Los operadores bit a bit se utilizan para comparar números (en formato binario):

| Operador | Descripción               | Ejemplo       | Resultado |
|----------|---------------------------|---------------|-----------|
| &        | AND bit a bit             | x & y         | 0         |
| \|       | OR bit a bit              | x \| y        | 7         |
| ^        | XOR bit a bit             | x ^ y         | 7         |
| ~        | NOT bit a bit             | ~x            | -4        |
| <<       | Desplazamiento a la izquierda | x << 2        | 20        |
| >>       | Desplazamiento a la derecha | x >> 2        | 1         |


## ENTRADA DE DATOS DEL USUARIO

Python permite la entrada de datos por parte del usuario.
Esto significa que podemos solicitar información al usuario.
El siguiente ejemplo solicita su nombre; una vez que lo ingresa, se muestra en pantalla:

```python
print("Introduce tu nombre:")
nombre = input()
print(f"Hola {nombre}")
```
La función **input()** permite al usuario ingresar datos. El programa se detiene y espera a que el usuario ingrese algo. Cuando el usuario presiona Enter, la función **input()** devuelve lo que el usuario escribió como una cadena (string).
Si deseas mostrar un mensaje antes de la entrada, puedes pasarlo como argumento a la función **input()**:

```python
nombre = input("Introduce tu nombre: ")
print(f"Hola {nombre}")
```
### Entradas múltiples
Puedes añadir tantas entradas como quieras; Python pausará la ejecución en cada una de ellas, esperando la entrada del usuario:

```python
nombre = input("Introduce tu nombre: ")
edad = input("Introduce tu edad: ")
print(f"Hola {nombre}, tienes {edad} años.")
```
### Convertir la entrada a otros tipos de datos
La función **input()** siempre devuelve una cadena (string). Si necesitas otro tipo de dato, como un número entero o un número decimal, debes convertirlo usando las funciones **int()** o **float()**:

```python
edad = int(input("Introduce tu edad: "))
altura = float(input("Introduce tu altura en metros: "))
print(f"Tienes {edad} años y mides {altura} metros.")
```
### Manejo de errores en la entrada
Es importante manejar posibles errores al convertir la entrada del usuario. Por ejemplo, si el usuario ingresa algo que no puede convertirse a un entero, el programa generará un error. Puedes usar un bloque **try-except** para manejar estos errores:

```python
try:
    edad = int(input("Introduce tu edad: "))
    print(f"Tienes {edad} años.")
except ValueError:
    print("Por favor, introduce un número válido para la edad.")
```
**Ejemplo completo:**

```python
try:
    nombre = input("Introduce tu nombre: ")
    edad = int(input("Introduce tu edad: "))
    altura = float(input("Introduce tu altura en metros: "))
    print(f"Hola {nombre}, tienes {edad} años y mides {altura} metros.")
except ValueError:
    print("Por favor, introduce valores válidos.")
``` 

:computer: Actividad 1

## ESTRUCTURAS DE CONTROL

En las estructuras de control de python es muy importante hablar tanto de la identación como de **encoding**. El encoding no es más que una **directiva que se coloca al inicio de un archivo Python, a fin de indicar al sistema, la codificación de caracteres utilizada en el archivo.**
El encoding más común es UTF-8, que soporta una amplia gama de caracteres, incluyendo letras acentuadas y símbolos especiales. La línea de código para especificar el encoding UTF-8 es la siguiente:

```python
# -*- coding: utf-8 -*-
```
Esta línea debe colocarse al inicio del archivo Python, antes de cualquier otro código. Es especialmente útil cuando el código contiene caracteres especiales o acentuados, ya que garantiza que estos caracteres se interpreten correctamente.
La identación es crucial en Python, ya que define la estructura del código y determina qué bloques de código pertenecen a qué estructuras de control. A diferencia de otros lenguajes de programación que utilizan llaves `{}` o palabras clave para delimitar bloques de código, Python utiliza la identación (espacios o tabulaciones) para este propósito. Una identación incorrecta puede llevar a errores de sintaxis o a un comportamiento inesperado del programa.

### Estructuras condicionales
Nos permiten evaluar si una o más condiciones se cumplen, para decir qué acción vamos a ejecutar. La evaluación de condiciones, solo puede arrojar 1 de 2 resultados: **verdadero o falso** (True o False).

Para evaluar las condiciones se utilizan **operadores relacionales o de comparación** y para unir distintas condiciones **operadores lógicos**.

Las estructuras de control de flujo condicionales mas conocida es el **if**, se define mediante el uso de tres palabras claves reservadas, del lenguaje: **if** (si), **elif** (sino, si) y **else** (sino).

#### Estructura if
La estructura if evalúa una condición y si esta es verdadera, ejecuta un bloque de código. Si la condición es falsa, el bloque de código se omite.

```python
# -*- coding: utf-8 -*-
x = 10
if x > 0:
    print("x es un número positivo")
```
#### Estructura if-elif
La estructura if-elif permite evaluar múltiples condiciones. Si la primera condición es falsa, se evalúa la siguiente, y así sucesivamente. Si ninguna condición es verdadera, se puede ejecutar un bloque de código alternativo con else.

```python
# -*- coding: utf-8 -*-
x = 10
if x > 0:
    print("x es un número positivo")
elif x == 0:
    print("x es cero")
```
#### Estructura if-elif-else
La estructura if-elif-else es una extensión de if-elif que incluye un bloque else. Este bloque se ejecuta si ninguna de las condiciones anteriores es verdadera.

```python
# -*- coding: utf-8 -*-
x = 10
if x > 0:
    print("x es un número positivo")
elif x == 0:
    print("x es cero")
else:
    print("x es un número negativo")
```
En este ejemplo, se verifica si `x` es mayor que 0, igual a 0 o menor que 0, y se imprime un mensaje correspondiente.

#### Anidamiento de estructuras if
Las estructuras if pueden anidarse dentro de otras estructuras if para evaluar condiciones más complejas.

```python
# -*- coding: utf-8 -*-
x = 10
if x > 0:
    if x % 2 == 0:
        print("x es un número positivo y par")
    else:
        print("x es un número positivo y impar")
elif x == 0:
    print("x es cero")
else:
    print("x es un número negativo")
```
En este ejemplo, se verifica si `x` es positivo y luego se evalúa si es par o impar.

### Estructura match (Python 3.10+)
Para la comprobación de un valor con muchas constantes se utiliza la sentencia **match**. Esta estructura recibe una expresión y compara su valor con patrones sucesivos, de forma similar al switch de Java.

```python
# -*- coding: utf-8 -*-
valor = 2
match valor:
    case 1:
        print("El valor es uno")
    case 2:
        print("El valor es dos")
    case 3:
        print("El valor es tres")
    case _:
        print("El valor no es uno, dos ni tres")
```
En este ejemplo, se verifica el valor de la variable `valor` y se imprime un mensaje correspondiente según el caso que coincida. El caso `_` actúa como un caso por defecto si ninguno de los casos anteriores coincide.
Se pueden unir varios literales en un case usando `|` equivale a un `o`

```python
# -*- coding: utf-8 -*-
valor = 2
match valor:
    case 1 | 2 | 3:
        print("El valor es uno, dos o tres")
    case _:
        print("El valor no es uno, dos ni tres")
```
En este ejemplo, si `valor` es 1, 2 o 3, se imprimirá el mismo mensaje.
Sentencias if como condiciones adicionales

Puede añadir sentencias if en la evaluación de casos para realizar una comprobación de condiciones adicional:

```python
# -*- coding: utf-8 -*-
valor = 2
match valor:
    case x if x < 0:
        print("El valor es negativo")
    case x if x == 0:
        print("El valor es cero")
    case x if x > 0:
        print("El valor es positivo")
```
En este ejemplo, se utiliza una sentencia if dentro de cada case para evaluar si el valor es negativo, cero o positivo.

:computer: Actividad 2

### Estructuras de control repetitivas
Las estructuras de control repetitivas permiten ejecutar un bloque de código varias veces, dependiendo de una condición o un rango de valores. Las estructuras más comunes en Python son **while** y **for**.

#### Estructura while
La estructura while ejecuta un bloque de código mientras una condición sea verdadera. Si la condición es falsa, el bloque de código se omite y el programa continúa con la siguiente instrucción después del bloque while.

```python
# -*- coding: utf-8 -*-
contador = 0
while contador < 5:
    print("Contador:", contador)
    contador += 1
```
En este ejemplo, el bloque de código dentro del while se ejecuta mientras el valor de `contador` sea menor que 5. En cada iteración, se imprime el valor de `contador` y luego se incrementa en 1.

#### Estructura for
La estructura for itera sobre una secuencia (como una lista, una tupla, un diccionario, un conjunto o una cadena) y ejecuta un bloque de código para cada elemento en la secuencia.

```python
# -*- coding: utf-8 -*-
frutas = ["manzana", "banana", "cereza"]
for fruta in frutas:
    print("Fruta:", fruta)
```
En este ejemplo, el bloque de código dentro del for se ejecuta para cada elemento en la lista `frutas`. En cada iteración, se imprime el nombre de la fruta actual.

#### Uso de range() en for
La función `range()` se utiliza comúnmente con la estructura for para generar una secuencia de números. Puedes especificar el inicio, el final y el paso de la secuencia.

```python
# -*- coding: utf-8 -*-
for i in range(5):  # Desde 0 hasta 4
    print("Número:", i)
for i in range(1, 6):  # Desde 1 hasta 5
    print("Número:", i)
for i in range(1, 10, 2):  # Desde 1 hasta 9, con paso de 2
    print("Número:", i)
```
En este ejemplo, se utilizan diferentes variantes de `range()` para generar secuencias de números y se imprime cada número en la secuencia.

#### Uso de break y continue
Dentro de los bucles, puedes usar las palabras clave `break` y `continue` para controlar el flujo de ejecución.
- `break` se utiliza para salir completamente del bucle cuando se cumple una condición específica.
- `continue` se utiliza para saltar el resto del código en la iteración actual y pasar directamente a la siguiente vuelta del bucle.
Ejemplo:

```python
# -*- coding: utf-8 -*-
for i in range(10):
    if i == 5:
        break  # Sale del bucle cuando i es igual a 5
    print("Número:", i)
# Salida: 0, 1, 2, 3, 4
for i in range(10):
    if i % 2 == 0:
        continue  # Salta los números pares
    print("Número impar:", i)
# Salida: 1, 3, 5, 7, 9
```
### Uso de la instrucción pass
La instrucción `pass` se utiliza como un marcador de posición en bloques de código donde se requiere una sintaxis pero no se desea ejecutar ninguna acción. Es útil en situaciones donde el código aún no está implementado o cuando se desea crear una estructura vacía.

```python
# -*- coding: utf-8 -*-
x = 10
if x > 0:
    pass  # Aquí no se realiza ninguna acción
else:
    print("x es un número negativo o cero")
```
En este ejemplo, si `x` es mayor que 0, no se realiza ninguna acción debido a la instrucción `pass`. Si `x` no es mayor que 0, se imprime un mensaje indicando que `x` es negativo o cero.

```python
for numero in range(5):
    if numero == 3:
        pass  # No hace nada cuando el número es 3
    else:
        print(numero)
# Salida: 0, 1, 2, 4
```
En este ejemplo, cuando el número es 3, la instrucción `pass` se ejecuta y no se realiza ninguna acción. Para los demás números, se imprime el número correspondiente.

:computer: Actividad 3

## COLECCIONES
En el lenguaje de programación Python existen cuatro tipos de datos de colección:

* **Lista**: es una colección ordenada y **mutable**. Permite elementos duplicados. 
* **Tupla**: es una colección ordenada e **inmutable**. Permite elementos duplicados. 
* **Conjunto**: es una colección no ordenada, **mutable** y sin índice. No permite elementos duplicados. 
* **Diccionario**: es una colección ordenada² y **mutable**. No permite claves duplicadas.

² Ordenada: A partir de la versión 3.7 de Python, los diccionarios tienen un orden definido. En las versiones anteriores de Python (3.6 y anteriores), los diccionarios no tenían un orden definido.

### Mutabilidad e inmutabilidad
🔍 **ACLARACIÓN IMPORTANTE: Mutabilidad del contenedor vs elementos**

**La mutabilidad se refiere al CONTENEDOR, no a los elementos:**

```python
# EJEMPLOS PARA ENTENDER LA DIFERENCIA:

# 1. LISTA = MUTABLE (siempre puedes cambiar la lista)
lista_numeros = [1, 2, 3]           # Lista mutable con números inmutables
lista_listas = [[1, 2], [3, 4]]     # Lista mutable con listas mutables

# Ambas listas son MUTABLES:
lista_numeros.append(4)              # ✅ Funciona
lista_listas.append([5, 6])          # ✅ Funciona

# 2. TUPLA = INMUTABLE (nunca puedes cambiar la tupla)
tupla_numeros = (1, 2, 3)           # Tupla inmutable con números inmutables
tupla_listas = ([1, 2], [3, 4])     # Tupla inmutable con listas mutables

# La tupla es INMUTABLE:
# tupla_numeros.append(4)            # ❌ Error - tuplas no tienen append()
# tupla_listas[0] = [99]             # ❌ Error - no puedes reasignar elementos

# PERO puedes modificar las listas DENTRO de la tupla:
tupla_listas[0].append(99)          # ✅ Funciona - modificas la lista, no la tupla
print(tupla_listas)                 # ([1, 2, 99], [3, 4])
```

**Regla de oro:** La mutabilidad es del TIPO (lista, tupla, conjunto, etc.), no depende del contenido. 

📋 RESUMEN :
|Tipo	|Ordenado	|Mutable	|Duplicados|	Indexado|
|-------|-----------|-----------|----------|---------|
|Lista	|✅ Sí |	✅ Sí	|✅ Sí	|✅ Sí|
|Tupla	|✅ Sí	|❌ No	|✅ Sí	|✅ Sí|
|Conjunto	|❌ No	|✅ Sí	|❌ No	|❌ No|
|Diccionario |✅ Sí*	|✅ Sí	|❌ No (claves)	|✅ Sí (por clave)|


### Listas
Python tiene varios tipos de datos _compuestos_, utilizados para agrupar otros valores. El más versátil es la _lista_, la cual puede ser escrita como una lista de valores separados por coma (ítems) entre corchetes. Las listas pueden contener ítems de diferentes tipos, pero usualmente los ítems son del mismo tipo.

```python
>>> cuadrados = [1, 4, 9, 16, 25]
>>> cuadrados
[1, 4, 9, 16, 25]
```
Al igual que las cadenas (y todas las demás tipos integrados sequence), las listas se pueden indexar y segmentar:

```python
>>> cuadrados[0]  # primer elemento
1
>>> cuadrados[-1]  # último elemento
25
>>> cuadrados[-3:]  # los últimos tres elementos
[9, 16, 25]
>>> cuadrados[:]
[1, 4, 9, 16, 25]
```
Las listas también admiten operaciones como **concatenación**:

```python
>>> cuadrados + [36, 49, 64, 81, 100]  # concatenación de listas
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
>>> cuadrados * 2  # repetición de listas
[1, 4, 9, 16, 25, 1, 4, 9, 16, 25]
```
Las listas son mutables, y sus elementos pueden ser cambiados en su lugar:

```python
>>> len(cuadrados)  # longitud de la lista
5
>>> cuadrados[0] = 36  # asignación de un nuevo valor
>>> cuadrados
[36, 4, 9, 16, 25]
```
También puedes agregar nuevos elementos al final de la lista, utilizando el método **list.append()** (veremos más sobre los métodos más adelante):

```python
>>> cuadrados.append(49)  # añade un nuevo ítem al final
>>> cuadrados
[36, 4, 9, 16, 25, 49]
```
**La asignación simple en Python nunca copia datos**. Al asignar una lista a una variable, esta hace referencia a la lista existente. Cualquier cambio que se realice en la lista mediante una variable se reflejará en todas las demás variables que hagan referencia a ella.

```python
>>> lista1 = lista2 = [1, 2, 3]  # ambas variables hacen referencia a la misma lista
>>> lista1 is lista2  # ambas variables apuntan al mismo objeto
True
>>> lista1[0] = 4  # cambia el primer elemento de la lista
>>> lista2  # el cambio es visible a través de ambas variables
[4, 2, 3]
>>> lista1 is lista2  # ambas variables siguen apuntando al mismo objeto
True
>>> lista1 = [1, 2, 3]  # ahora lista1 apunta a una nueva lista
>>> lista1 is lista2  # ahora lista1 y lista2 apuntan a diferentes objetos
False
>>> lista1
[1, 2, 3]
>>> lista2
[4, 2, 3]
>>> lista1[0] = 5  # cambia el primer elemento de la lista lista1
>>> lista1
[5, 2, 3]
>>> lista2  # la lista lista2 no se ve afectada
[4, 2, 3]
>>> lista1 is lista2  # ambas variables siguen apuntando al mismo objeto
False
```

Todas las operaciones de rebanado retornan una nueva lista que contiene los elementos pedidos. Esto significa que la siguiente rebanada retorna una **shallow copy (copia superficial)** de la lista:

`Una copia superficial`construye un nuevo objeto compuesto y luego (en la medida de lo posible) inserta references en él a los objetos encontrados en el original.

```python
>>> cuadrados = [1, 4, 9, 16, 25]
>>> cuadrados_copia = cuadrados[:]  # crea una copia superficial de la lista
>>> cuadrados_copia is cuadrados  # ambas variables apuntan a diferentes objetos
False
>>> cuadrados_copia == cuadrados  # pero tienen el mismo contenido
True
>>> cuadrados_copia[0] = 36  # cambia el primer elemento de la copia
>>> cuadrados_copia
[36, 4, 9, 16, 25]
>>> cuadrados  # la lista original no se ve afectada, porque es una lista con elementos inmutables-numeros
[1, 4, 9, 16, 25]
>>> cuadrados_copia is cuadrados  # ambas variables siguen apuntando a diferentes objetos
False
>>> cuadrados_copia == cuadrados  # y ahora tienen diferente contenido
False
>>> cuadrados_copia = list(cuadrados)  # otra forma de crear una copia superficial
```

También es posible asignar a una rebanada, y esto incluso puede cambiar la longitud de la lista o vaciarla totalmente:

```python
>>> cuadrados = [1, 4, 9, 16, 25]
>>> cuadrados[2:4] = [8, 27]  # cambia los elementos en las posiciones 2 y 3
>>> cuadrados
[1, 4, 8, 27, 25]
>>> cuadrados[2:4] = []  # elimina los elementos en las posiciones 2 y 3
>>> cuadrados
[1, 4, 25]
>>> cuadrados[:] = []  # elimina todos los elementos de la lista
>>> cuadrados
[]
>>> del cuadrados  # elimina la variable que referencia a la lista
>>> cuadrados
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'cuadrados' is not defined
```
La función predefinida **len()** también sirve para las listas

```python
>>> len(cuadrados)
0
>>> cuadrados = [1, 4, 9, 16, 25]
>>> len(cuadrados)
5
```
Y el método **list.append()** puede ser usado para añadir nuevos elementos al final de la lista:

```python
>>> cuadrados.append(36)
>>> len(cuadrados)
6
```
Para insertar un elemento en una lista en una posición específica, utilice el **método insert()**:

```python
milista = ["manzana", "banana", "cereza"]
milista.insert(1, "naranja")
print(milista)
# Salida: ['manzana', 'naranja', 'banana', 'cereza']
```
**El método remove()** elimina el elemento especificado:

```python
milista = ["manzana", "banana", "cereza"]
milista.remove("banana")
print(milista)
# Salida: ['manzana', 'cereza']
```
Si hay más de un elemento con el valor especificado, **el método remove() elimina la primera aparición**:

```python
milista = ["manzana", "banana", "cereza", "banana"]
milista.remove("banana")
print(milista)
# Salida: ['manzana', 'cereza', 'banana']
```
**El método pop()** elimina el elemento en la posición indicada:

```python
milista = ["manzana", "banana", "cereza"]
milista.pop(1)
print(milista)
# Salida: ['manzana', 'cereza']
```
Si no se especifica ningún índice, el método pop() elimina el último elemento:

```python
milista = ["manzana", "banana", "cereza"]
milista.pop()
print(milista)
# Salida: ['manzana', 'banana']
```
La palabra clave **"del"** también elimina el índice especificado:

```python
milista = ["manzana", "banana", "cereza"]
del milista[0]
print(milista)
# Salida: ['banana', 'cereza']
```
El **método clear()** vacía la lista. La lista sigue existiendo, pero no contiene ningún elemento:

```python
milista = ["manzana", "banana", "cereza"]
milista.clear()
print(milista)
# Salida: []
```
**Listas de bucles**
Puedes recorrer los elementos de una lista utilizando un bucle for:

```python
milista = ["manzana", "banana", "cereza"]
for x in milista:
  print(x)
# Salida:
# manzana
# banana
# cereza
```
**Recorrer la lista mediante los índices**
También se puede recorrer los elementos de la lista haciendo referencia a su índice.
Para ello, utilizamos las funciones **range()** y **len()** para crear un objeto iterable adecuado.

```python
milista = ["manzana", "banana", "cereza"]
for i in range(len(milista)):
  print(milista[i])
# Salida:
# manzana
# banana
# cereza
```
**Comprensión de listas**
La comprensión de listas ofrece una sintaxis más compacta para crear una nueva lista a partir de los valores de una lista existente.

Ejemplo:Partiendo de una lista de frutas, queremos crear una nueva lista que contenga solo las frutas cuyo nombre incluya la letra "a".

Sin la comprensión de listas, tendríamos que escribir una sentencia for con una condición dentro:

```python
frutas = ["manzana", "banana", "cereza", "kiwi", "mango"]
nuevalista = []
for x in frutas:
  if "a" in x:
    nuevalista.append(x)
print(nuevalista)
# Salida: ['manzana', 'banana', 'mango']
```
Con la comprensión de listas, podemos lograr lo mismo en una sola línea:

```python
frutas = ["manzana", "banana", "cereza", "kiwi", "mango"]
nuevalista = [x for x in frutas if "a" in x]
print(nuevalista)
# Salida: ['manzana', 'banana', 'mango']
```
**Ordenar listas alfanuméricamente**
Los objetos de tipo lista tienen un método llamado **sort()** que, por defecto, ordena la lista alfabéticamente de forma ascendente:

```python
esta_lista = ["naranja", "mango", "kiwi", "piña", "banana"]
esta_lista.sort()
print(esta_lista)
# Salida: ['banana', 'kiwi', 'mango', 'naranja', 'piña']
```
Para ordenar la lista en orden descendente, utiliza el parámetro opcional `reverse = True`:

```python
esta_lista = ["naranja", "mango", "kiwi", "piña", "banana"]
esta_lista.sort(reverse=True)
print(esta_lista)
# Salida: ['piña', 'naranja', 'mango', 'kiwi', 'banana']
```
**Copiar una lista**
No se puede copiar una lista simplemente escribiendo `list2 = list1`, ya que `list2` solo será una referencia a `list1`, y cualquier cambio realizado en `list1` se reflejará automáticamente en `list2`.

Utilizar **el método copy()**. Para copiar una lista, que está integrado en la clase List.

```python
esta_lista = ["manzana", "banana", "cereza"]
milista = esta_lista.copy()
print(milista)
# Salida: ['manzana', 'banana', 'cereza']
```
O utilizar **la función built-in list()** para hacer una copia de la lista:

```python
esta_lista = ["manzana", "banana", "cereza"]
milista = list(esta_lista)
print(milista)
# Salida: ['manzana', 'banana', 'cereza']
```
**Uso del operador de segmentación**
También puedes crear una copia de una lista utilizando el operador `:`

```python
esta_lista = ["manzana", "banana", "cereza"]
milista = esta_lista[:]
print(milista)
# Salida: ['manzana', 'banana', 'cereza']
```
**El método extend()**, el propósito es añadir elementos de una lista a otra:

```python
esta_lista = ["manzana", "banana", "cereza"]
otra_lista = ["kiwi", "mango", "piña"]
esta_lista.extend(otra_lista)
print(esta_lista)
# Salida: ['manzana', 'banana', 'cereza', 'kiwi', 'mango', 'piña']
```
#### Métodos de listas
Python dispone de una serie de métodos integrados que se pueden utilizar con las listas:

| Método      | Descripción                                                        |
|-------------|--------------------------------------------------------------------|
| append()    | Añade un elemento al final de la lista                             |
| clear()     | Elimina todos los elementos de la lista                            |
| copy()      | Devuelve una copia de la lista                                     |
| count()     | Devuelve el número de elementos con el valor especificado          |
| extend()    | Añade los elementos de otra lista (o iterable) al final de la lista|
| index()     | Devuelve el índice del primer elemento con el valor especificado   |
| insert()    | Inserta un elemento en la posición especificada                    |
| pop()       | Elimina el elemento en la posición especificada                    |
| remove()    | Elimina el elemento con el valor especificado                      |
| reverse()   | Invierte el orden de los elementos de la lista                     |
| sort()      | Ordena los elementos de la lista                                   |

#### Más sobre listas
Las listas pueden contener elementos de diferentes tipos:

```python
>>> a = [1, 2, 3, 4]
>>> a
[1, 2, 3, 4]
>>> a.append('Hola')
>>> a
[1, 2, 3, 4, 'Hola']
>>> a.append(5.0)
>>> a
[1, 2, 3, 4, 'Hola', 5.0]
>>> a.append([6, 7, 8])
>>> a
[1, 2, 3, 4, 'Hola', 5.0, [6, 7, 8]]
>>> len(a)
7
>>> a[6]
[6, 7, 8]
>>> a[6][0]
6
>>> a[6][1]
7
>>> a[6][2]
8
>>> a[6].append(9)
>>> a
[1, 2, 3, 4, 'Hola', 5.0, [6, 7, 8, 9]]
>>> len(a)
7
>>> a[6]
[6, 7, 8, 9]
>>> a[6][3]
9
>>> a[6][3] = 10
>>> a
[1, 2, 3, 4, 'Hola', 5.0, [6, 7, 8, 10]]
```
Es posible anidar listas (crear listas que contengan otras listas), por ejemplo:

```python
>>> matriz = [
...     [1, 2, 3, 4],
...     [5, 6, 7, 8],
...     [9, 10, 11, 12],
... ]
>>> matriz
[[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12]]
>>> matriz[0]  # primer fila
[1, 2, 3, 4]
>>> matriz[1]  # segunda fila
[5, 6, 7, 8]
>>> matriz[2]  # tercera fila
[9, 10, 11, 12]
>>> matriz[0][0]  # primer elemento de la primera fila
1
>>> matriz[1][0]  # primer elemento de la segunda fila
5
>>> matriz[2][0]  # primer elemento de la tercera fila
9
>>> matriz[1][2]  # tercer elemento de la segunda fila
7
>>> matriz[2][3]  # cuarto elemento de la tercera fila
12
>>> matriz[2][3] = 13  # cambia el cuarto elemento de la tercera fila
>>> matriz
[[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 13]]
>>> len(matriz)  # número de filas
3
>>> len(matriz[0])  # número de columnas en la primera fila
4
```
### Tuplas
Una tupla es una colección ordenada e inmutable de elementos. Las tuplas son similares a las listas, pero no pueden ser modificadas después de su creación. Las tuplas se definen utilizando paréntesis `()` y los elementos están separados por comas.

```python
>>> mi_tupla = (1, 2, 3, 4, 5)
>>> mi_tupla
(1, 2, 3, 4, 5)
>>> mi_tupla[0]  # primer elemento
1
>>> mi_tupla[-1]  # último elemento
5
>>> mi_tupla[1:4]  # elementos desde el índice 1 hasta el 3
(2, 3, 4)
>>> len(mi_tupla)  # longitud de la tupla
5
>>> mi_tupla[0] = 10  # intenta cambiar el primer elemento (esto producirá un error)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
>>> otra_tupla = (6, 7, 8)
>>> nueva_tupla = mi_tupla + otra_tupla  # concatenación de tuplas
>>> nueva_tupla
(1, 2, 3, 4, 5, 6, 7, 8)
>>> mi_tupla * 2  # repetición de tuplas
(1, 2, 3, 4, 5, 1, 2, 3, 4, 5)
```
#### Añadir elementos
Dado que las tuplas son inmutables, no disponen de un método append() integrado, pero existen otras maneras de añadir elementos a una tupla.

1. Convertir a lista: Al igual que para modificar una tupla, puedes convertirla en una lista, añadir el/los elemento/s y volver a convertirla en tupla.

```python
>>> mi_tupla = (1, 2, 3)
>>> lista = list(mi_tupla)  # convierte la tupla en una lista
>>> lista.append(4)  # añade un nuevo elemento a la lista
>>> mi_tupla = tuple(lista)  # convierte la lista de nuevo en una tupla
>>> mi_tupla
(1, 2, 3, 4)
```
2. Concatenación: Puedes crear una nueva tupla que contenga los elementos de la tupla original más los nuevos elementos.

```python
>>> mi_tupla = (1, 2, 3)
>>> mi_tupla = mi_tupla + (4,)  # añade un nuevo elemento mediante concatenación
>>> mi_tupla
(1, 2, 3, 4)
>>> mi_tupla = mi_tupla + (5, 6)  # añade varios elementos mediante concatenación
>>> mi_tupla
(1, 2, 3, 4, 5, 6)
```
#### Métodos de tuplas
Las tuplas tienen dos métodos integrados para realizar operaciones comunes:

| Método      | Descripción                                                        |
|-------------|--------------------------------------------------------------------|
| count()     | Devuelve el número de veces que un valor especificado aparece en la tupla |
| index()     | Devuelve el índice del primer elemento con el valor especificado   |


### Conjuntos
Un conjunto es una colección no ordenada, mutable y sin índice de elementos únicos. Los conjuntos se definen utilizando llaves `{}` o la función `set()`.

```python
>>> mi_conjunto = {1, 2, 3, 4, 5}
>>> mi_conjunto
{1, 2, 3, 4, 5}
>>> mi_conjunto = set([1, 2, 3, 4, 5])  # usando la función set()
>>> mi_conjunto
{1, 2, 3, 4, 5}
>>> mi_conjunto.add(6)  # añade un nuevo elemento
>>> mi_conjunto
{1, 2, 3, 4, 5, 6}
>>> mi_conjunto.add(3)  # intenta añadir un elemento duplicado (no tendrá efecto)
>>> mi_conjunto
{1, 2, 3, 4, 5, 6}
>>> mi_conjunto.remove(4)  # elimina un elemento
>>> mi_conjunto
{1, 2, 3, 5, 6}
>>> len(mi_conjunto)  # longitud del conjunto
5
>>> 3 in mi_conjunto  # verifica si un elemento está en el conjunto
True
>>> 4 in mi_conjunto  # verifica si un elemento está en el conjunto
False
>>> mi_conjunto.clear()  # elimina todos los elementos del conjunto
>>> mi_conjunto
set()
>>> del mi_conjunto  # elimina la variable que referencia al conjunto
>>> mi_conjunto
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'mi_conjunto' is not defined
```
#### Operaciones con conjuntos
Los conjuntos soportan operaciones matemáticas como unión, intersección, diferencia y diferencia simétrica.

```python
>>> A = {1, 2, 3, 4}
>>> B = {3, 4, 5, 6}
>>> A | B  # unión
{1, 2, 3, 4, 5, 6}
>>> A & B  # intersección
{3, 4}
>>> A - B  # diferencia
{1, 2}
>>> A ^ B  # diferencia simétrica. Es como la operación "O exclusivo" (XOR) en lógica: devuelve los elementos que están en uno u otro conjunto, pero no en ambos
{1, 2, 5, 6}
```
#### Métodos de conjuntos
Los conjuntos tienen varios métodos integrados para realizar operaciones comunes:

| Método        | Descripción                                                        |
|---------------|--------------------------------------------------------------------|
| add()         | Añade un elemento al conjunto                                      |
| clear()       | Elimina todos los elementos del conjunto                           |
| copy()        | Devuelve una copia del conjunto                                    |
| difference() | Devuelve la diferencia entre dos conjuntos                         |
| discard()     | Elimina un elemento del conjunto si está presente                  |
| intersection()| Devuelve la intersección de dos conjuntos                         |
| isdisjoint()  | Devuelve True si dos conjuntos no tienen elementos en común        |
| issubset()    | Devuelve True si un conjunto es subconjunto de otro                |
| issuperset()  | Devuelve True si un conjunto es superconjunto de otro              |
| pop()         | Elimina y devuelve un elemento arbitrario del conjunto             |
| remove()      | Elimina un elemento del conjunto; genera un error si no está presente |
| symmetric_difference() | Devuelve la diferencia simétrica entre dos conjuntos     |
| union()       | Devuelve la unión de dos conjuntos                                 |
| update()      | Actualiza el conjunto con la unión de sí mismo y otro conjunto     |

### Diccionarios
Un diccionario es una colección ordenada y mutable de pares clave-valor. Los diccionarios se definen utilizando llaves `{}` y los pares clave-valor están separados por comas. Cada clave está separada de su valor por dos puntos `:`.

```python
>>> mi_diccionario = {'nombre': 'Juan', 'edad': 30, 'ciudad': 'Madrid'}
>>> mi_diccionario
{'nombre': 'Juan', 'edad': 30, 'ciudad': 'Madrid'}
>>> mi_diccionario['nombre']  # acceso al valor mediante la clave
'Juan'
>>> mi_diccionario['edad']  # acceso al valor mediante la clave
30
>>> mi_diccionario['ciudad']  # acceso al valor mediante la clave
'Madrid'
>>> mi_diccionario['edad'] = 31  # modifica el valor asociado a la clave 'edad'
>>> mi_diccionario
{'nombre': 'Juan', 'edad': 31, 'ciudad': 'Madrid'}
>>> mi_diccionario['pais'] = 'España'  # añade un nuevo par clave-valor
>>> mi_diccionario
{'nombre': 'Juan', 'edad': 31, 'ciudad': 'Madrid', 'pais': 'España'}
>>> del mi_diccionario['ciudad']  # elimina el par clave-valor con clave 'ciudad'
>>> mi_diccionario
{'nombre': 'Juan', 'edad': 31, 'pais': 'España'}
>>> len(mi_diccionario)  # longitud del diccionario
3
>>> 'nombre' in mi_diccionario  # verifica si una clave está en el diccionario
True
>>> 'ciudad' in mi_diccionario  # verifica si una clave está en el diccionario
False
>>> mi_diccionario.clear()  # elimina todos los pares clave-valor del diccionario
>>> mi_diccionario
{}
>>> del mi_diccionario  # elimina la variable que referencia al diccionario
>>> mi_diccionario
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'mi_diccionario' is not defined
```

:computer: Actividad 4







 





  















 








