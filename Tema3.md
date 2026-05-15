# PROGRAMACIÓN ORIENTADA A OBJETOS EN PYTHON

- [PROGRAMACIÓN ORIENTADA A OBJETOS EN PYTHON](#programación-orientada-a-objetos-en-python)
  - [INTRODUCCIÓN A LA POO](#introducción-a-la-poo)
    - [¿Qué es la Programación Orientada a Objetos?](#qué-es-la-programación-orientada-a-objetos)
    - [Principios fundamentales de la POO](#principios-fundamentales-de-la-poo)
    - [Ventajas de la POO](#ventajas-de-la-poo)
  - [CONCEPTOS BÁSICOS DE POO](#conceptos-básicos-de-poo)
    - [Clases y objetos: definición y características](#clases-y-objetos-definición-y-características)
      - [¿Qué es una clase?](#qué-es-una-clase)
      - [¿Qué es un objeto?](#qué-es-un-objeto)
      - [Sintaxis para crear una clase](#sintaxis-para-crear-una-clase)
      - [Creación de objetos (instanciación)](#creación-de-objetos-instanciación)
      - [Ejemplo básico](#ejemplo-básico)
    - [Atributos y métodos](#atributos-y-métodos)
      - [Atributos de instancia](#atributos-de-instancia)
      - [Atributos de clase](#atributos-de-clase)
      - [Métodos](#métodos)
      - [El método constructor `__init__()`](#el-método-constructor-__init__)
      - [Métodos de clase](#métodos-de-clase)
      - [Métodos estáticos](#métodos-estáticos)
      - [Ejemplo completo: Clase Persona](#ejemplo-completo-clase-persona)
  - [ENCAPSULAMIENTO](#encapsulamiento)
    - [Concepto de encapsulamiento](#concepto-de-encapsulamiento)
    - [Uso de modificadores de acceso (público, privado)](#uso-de-modificadores-de-acceso-público-privado)
      - [Atributos y métodos públicos](#atributos-y-métodos-públicos)
      - [Atributos y métodos protegidos](#atributos-y-métodos-protegidos)
      - [Atributos y métodos privados](#atributos-y-métodos-privados)
    - [Métodos getters y setters](#métodos-getters-y-setters)
      - [Getters y setters tradicionales](#getters-y-setters-tradicionales)
      - [Propiedades con `@property`](#propiedades-con-property)
      - [Ejemplo completo con encapsulamiento](#ejemplo-completo-con-encapsulamiento)
  - [HERENCIA](#herencia)
    - [Concepto de herencia y creación de clases derivadas](#concepto-de-herencia-y-creación-de-clases-derivadas)
      - [¿Qué es la herencia?](#qué-es-la-herencia)
      - [Sintaxis de herencia](#sintaxis-de-herencia)
      - [Ejemplo básico de herencia](#ejemplo-básico-de-herencia)
    - [Uso de `super()` para llamar métodos de la clase base](#uso-de-super-para-llamar-métodos-de-la-clase-base)
      - [¿Qué es `super()`?](#qué-es-super)
      - [Usar `super()` en el constructor](#usar-super-en-el-constructor)
      - [Usar `super()` en métodos](#usar-super-en-métodos)
      - [Ejemplo completo con `super()`](#ejemplo-completo-con-super)
  - [CLASES ABSTRACTAS E INTERFACES](#clases-abstractas-e-interfaces)
    - [Concepto de clases abstractas](#concepto-de-clases-abstractas)
      - [Crear clases abstractas con `abc`](#crear-clases-abstractas-con-abc)
      - [Métodos abstractos con implementación parcial](#métodos-abstractos-con-implementación-parcial)
    - [Interfaces en Python](#interfaces-en-python)
      - [Interfaces mediante clases abstractas](#interfaces-mediante-clases-abstractas)
      - [Protocolos (Python 3.8+)](#protocolos-python-38)
      - [Ejemplo completo: Sistema de pagos](#ejemplo-completo-sistema-de-pagos)
  - [POLIMORFISMO](#polimorfismo)
    - [Concepto de polimorfismo](#concepto-de-polimorfismo)
    - [Uso de métodos sobrescritos en clases derivadas](#uso-de-métodos-sobrescritos-en-clases-derivadas)
      - [Sobrescritura de métodos](#sobrescritura-de-métodos)
      - [Utilización del Polimorfismo](#utilización-del-polimorfismo)
      - [Ejemplo completo de polimorfismo](#ejemplo-completo-de-polimorfismo)
  - [MÉTODOS ESPECIALES](#métodos-especiales)
    - [¿Qué son los métodos mágicos?](#qué-son-los-métodos-mágicos)
    - [Uso de métodos mágicos como `__init__()`, `__str__()`, y `__repr__()`](#uso-de-métodos-mágicos-como-__init__-__str__-y-__repr__)
      - [El método `__init__()`](#el-método-__init__)
      - [El método `__str__()`](#el-método-__str__)
      - [El método `__repr__()`](#el-método-__repr__)
      - [Otros métodos especiales importantes](#otros-métodos-especiales-importantes)
    - [Ejemplo completo con métodos especiales](#ejemplo-completo-con-métodos-especiales)
  - [MÓDULOS Y PAQUETES EN POO](#módulos-y-paquetes-en-poo)
    - [Organización de clases en módulos](#organización-de-clases-en-módulos)
      - [¿Por qué usar módulos?](#por-qué-usar-módulos)
      - [Crear un módulo con clases](#crear-un-módulo-con-clases)
      - [Importar clases desde módulos](#importar-clases-desde-módulos)
    - [Creación y estructura de paquetes](#creación-y-estructura-de-paquetes)
      - [¿Qué es un paquete?](#qué-es-un-paquete)
      - [El archivo `__init__.py`](#el-archivo-__init__py)
      - [Estructura de directorios](#estructura-de-directorios)
    - [Importación avanzada de clases](#importación-avanzada-de-clases)
      - [Diferentes formas de importar](#diferentes-formas-de-importar)
      - [Alias y nombres personalizados](#alias-y-nombres-personalizados)
      - [Importación condicional](#importación-condicional)
    - [Buenas prácticas y organización](#buenas-prácticas-y-organización)
      - [Convenciones de nomenclatura](#convenciones-de-nomenclatura)
      - [Organización por funcionalidad](#organización-por-funcionalidad)
      - [Evitar importaciones circulares](#evitar-importaciones-circulares)
      - [Ejemplo de proyecto estructurado](#ejemplo-de-proyecto-estructurado)
  - [PRUEBAS UNITARIAS PARA CLASES](#pruebas-unitarias-para-clases)
    - [Importancia de probar clases](#importancia-de-probar-clases)
    - [Configuración de pruebas con `unittest`](#configuración-de-pruebas-con-unittest)
      - [Estructura básica de pruebas para clases](#estructura-básica-de-pruebas-para-clases)
      - [Métodos `setUp()` y `tearDown()`](#métodos-setup-y-teardown)
    - [Pruebas de atributos y métodos](#pruebas-de-atributos-y-métodos)
      - [Probar inicialización de objetos](#probar-inicialización-de-objetos)
      - [Probar métodos públicos](#probar-métodos-públicos)
      - [Pruebas de herencia y polimorfismo](#pruebas-de-herencia-y-polimorfismo)
    - [Pruebas de métodos especiales](#pruebas-de-métodos-especiales)
      - [Probar métodos mágicos](#probar-métodos-mágicos)
      - [Probar operadores sobrecargados](#probar-operadores-sobrecargados)
    - [Ejemplo completo de pruebas para el sistema de biblioteca](#ejemplo-completo-de-pruebas-para-el-sistema-de-biblioteca)
    - [Ejecutar las pruebas](#ejecutar-las-pruebas)
    - [Cobertura de código](#cobertura-de-código)

## INTRODUCCIÓN A LA POO

### ¿Qué es la Programación Orientada a Objetos?

La **Programación Orientada a Objetos (POO)** es un paradigma de programación que organiza el código en **clases** y **objetos**, permitiendo modelar problemas del mundo real de manera más natural e intuitiva.

```python
# Ejemplo conceptual: modelar un coche
class Coche:
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo
        self.velocidad = 0
    
    def acelerar(self):
        self.velocidad += 10
    
    def frenar(self):
        self.velocidad = max(0, self.velocidad - 10)

# Crear objetos (instancias)
mi_coche = Coche("Toyota", "Corolla")
tu_coche = Coche("Ford", "Focus")
```

### Principios fundamentales de la POO

1. **Encapsulamiento**: Ocultar los detalles internos y exponer solo lo necesario
2. **Herencia**: Crear nuevas clases basadas en clases existentes
3. **Polimorfismo**: Usar la misma interfaz para diferentes tipos de objetos
4. **Abstracción**: Simplificar la complejidad mediante modelos conceptuales

### Ventajas de la POO

- **Reutilización de código**: Las clases se pueden usar múltiples veces
- **Modularidad**: El código se organiza en unidades lógicas
- **Mantenibilidad**: Fácil modificar y extender el código
- **Modelado natural**: Representa mejor los problemas del mundo real

## CONCEPTOS BÁSICOS DE POO

### Clases y objetos: definición y características

#### ¿Qué es una clase?

Una **clase** es un molde o plantilla que define las características (atributos) y comportamientos (métodos) que tendrán los objetos creados a partir de ella.

```python
# Definición de una clase
class Animal:
    """Clase que representa un animal genérico"""
    pass  # Clase vacía por ahora
```

#### ¿Qué es un objeto?

Un **objeto** es una instancia específica de una clase. Es una entidad concreta que tiene valores específicos para los atributos definidos en la clase.

```python
# Crear objetos de la clase Animal
perro = Animal()  # perro es un objeto de la clase Animal
gato = Animal()   # gato es otro objeto de la clase Animal
```

#### Sintaxis para crear una clase

```python
class NombreDeLaClase:
    """Documentación opcional de la clase"""
    
    # Atributos de clase (compartidos por todas las instancias)
    atributo_de_clase = valor
    
    # Método constructor
    def __init__(self, parametros):
        # Atributos de instancia
        self.atributo = valor
    
    # Métodos de instancia
    def metodo(self):
        # Código del método
        pass
```

#### Creación de objetos (instanciación)

```python
# Crear un objeto (instanciar la clase)
nombre_objeto = NombreDeLaClase(argumentos)
```

#### Ejemplo básico

```python
class Estudiante:
    """Clase que representa a un estudiante"""
    
    def __init__(self, nombre, edad):
        self.nombre = nombre  # Atributo de instancia
        self.edad = edad      # Atributo de instancia
    
    def presentarse(self):
        return f"Hola, soy {self.nombre} y tengo {self.edad} años"

# Crear objetos
estudiante1 = Estudiante("Ana", 20)
estudiante2 = Estudiante("Carlos", 22)

# Usar los objetos
print(estudiante1.presentarse())  # Hola, soy Ana y tengo 20 años
print(estudiante2.presentarse())  # Hola, soy Carlos y tengo 22 años

# Acceder a los atributos
print(f"Nombre: {estudiante1.nombre}")  # Nombre: Ana
print(f"Edad: {estudiante1.edad}")      # Edad: 20
```

### Atributos y métodos

#### Atributos de instancia

Los **atributos de instancia** son variables que pertenecen a cada objeto específico. Cada objeto tiene sus propios valores para estos atributos.

```python
class Producto:
    def __init__(self, nombre, precio):
        self.nombre = nombre    # Atributo de instancia
        self.precio = precio    # Atributo de instancia
        self.stock = 0          # Atributo de instancia con valor por defecto

producto1 = Producto("Laptop", 800)
producto2 = Producto("Mouse", 25)

# Cada objeto tiene sus propios valores
print(producto1.nombre)  # Laptop
print(producto2.nombre)  # Mouse
```

#### Atributos de clase

Los **atributos de clase** son variables compartidas por todas las instancias de la clase.

```python
class Vehiculo:
    # Atributo de clase (estático)
    numero_de_vehiculos = 0
    tipo_transporte = "Terrestre"
    
    def __init__(self, marca, modelo):
        self.marca = marca      # Atributo de instancia
        self.modelo = modelo    # Atributo de instancia
        # Incrementar el contador de vehículos
        Vehiculo.numero_de_vehiculos += 1

# Crear objetos
coche1 = Vehiculo("Toyota", "Camry")
coche2 = Vehiculo("Honda", "Civic")

# Los atributos de clase se comparten
print(Vehiculo.numero_de_vehiculos)  # 2
print(coche1.tipo_transporte)       # Terrestre
print(coche2.tipo_transporte)       # Terrestre
```

#### Métodos

Los **métodos** son funciones definidas dentro de una clase que definen el comportamiento de los objetos.

```python
class Calculadora:
    def sumar(self, a, b):
        """Método para sumar dos números"""
        return a + b
    
    def restar(self, a, b):
        """Método para restar dos números"""
        return a - b
    
    def multiplicar(self, a, b):
        """Método para multiplicar dos números"""
        return a * b

# Usar los métodos
calc = Calculadora()
print(calc.sumar(5, 3))       # 8
print(calc.restar(10, 4))     # 6
print(calc.multiplicar(3, 7)) # 21
```

#### El método constructor `__init__()`

El método `__init__()` es el constructor de la clase. Se ejecuta automáticamente cuando se crea un nuevo objeto.

```python
class Libro:
    def __init__(self, titulo, autor, paginas=0):
        """Constructor de la clase Libro"""
        self.titulo = titulo
        self.autor = autor
        self.paginas = paginas
        self.abierto = False
        print(f"Se ha creado el libro: {titulo}")
    
    def abrir(self):
        self.abierto = True
        print(f"Se ha abierto el libro {self.titulo}")
    
    def cerrar(self):
        self.abierto = False
        print(f"Se ha cerrado el libro {self.titulo}")

# El constructor se ejecuta automáticamente
libro1 = Libro("El Quijote", "Cervantes", 1200)
# Salida: Se ha creado el libro: El Quijote

libro1.abrir()   # Se ha abierto el libro El Quijote
libro1.cerrar()  # Se ha cerrado el libro El Quijote
```
#### Métodos de clase
En Python, cuando defines un método de clase usando `@classmethod`, el primer parámetro del método es convencionalmente llamado `cls`. Esto es similar a cómo self se usa en los métodos de instancia, pero `cls` hace referencia a la propia clase, no a una instancia específica.

```java
class Animal:
    @classmethod
    def obtener_nombre_clase(cls):
        return f"El nombre de la clase es: {cls.__name__}"
print(Animal.obtener_nombre_clase())
```

Este método devuelve el nombre de la clase (en esta caso `Animal`). **name** es un atributo especial que todas las clases en Python tienen automáticamente, y que contiene el nombre de la clase como cadena.

#### Métodos estáticos
Un método estático es una función definida dentro de una clase que no accede ni a la instancia (self) ni a la clase (cls). Se declara con el decorador `@staticmethod` y se puede llamar desde la clase o desde una instancia.

```java
class Calculadora:
    @staticmethod
    def sumar(a, b):
        return a + b

# Uso del método estático
print(Calculadora.sumar(3, 5))  # 8
calc = Calculadora()
print(calc.sumar(10, 7))        # 17
```
Los métodos estáticos son útiles para funciones relacionadas con la clase pero que no necesitan acceder ni a los datos de instancia ni de clase.

#### Ejemplo completo: Clase Persona

```python
class Persona:
    """Clase que representa a una persona"""
    
    # Atributo de clase
    especie = "Homo sapiens"
    poblacion_total = 0
    
    def __init__(self, nombre, apellido, edad, email=""):
        """Constructor de la clase Persona"""
        # Atributos de instancia
        self.nombre = nombre
        self.apellido = apellido
        self.edad = edad
        self.email = email
        
        # Incrementar población total
        Persona.poblacion_total += 1
        
        print(f"Se ha registrado a {self.nombre_completo()}")
    
    def nombre_completo(self):
        """Método que devuelve el nombre completo"""
        return f"{self.nombre} {self.apellido}"
    
    def cumplir_anios(self):
        """Método para incrementar la edad"""
        self.edad += 1
        print(f"¡Feliz cumpleaños {self.nombre}! Ahora tienes {self.edad} años")
    
    def cambiar_email(self, nuevo_email):
        """Método para cambiar el email"""
        email_anterior = self.email
        self.email = nuevo_email
        print(f"Email cambiado de {email_anterior} a {nuevo_email}")
    
    def es_mayor_de_edad(self):
        """Método que verifica si es mayor de edad"""
        return self.edad >= 18
    
    def presentarse(self):
        """Método para presentarse"""
        estado = "mayor" if self.es_mayor_de_edad() else "menor"
        return f"Hola, soy {self.nombre_completo()}, tengo {self.edad} años y soy {estado} de edad"
    
    @classmethod
    def mostrar_especie_y_poblacion(cls):
        return f"Especie: {cls.especie}, Población total: {cls.poblacion_total}"

# Crear objetos
persona1 = Persona("Juan", "Pérez", 25, "juan@email.com")
persona2 = Persona("María", "García", 17)

# Usar métodos
print(persona1.presentarse())
# Hola, soy Juan Pérez, tengo 25 años y soy mayor de edad

print(persona2.presentarse())
# Hola, soy María García, tengo 17 años y soy menor de edad

# Modificar objetos
persona2.cumplir_anios()  # ¡Feliz cumpleaños María! Ahora tienes 18 años
persona1.cambiar_email("juan.perez@email.com")

# Acceder a atributos de clase
print(f"Especie: {Persona.especie}")           # Especie: Homo sapiens
print(f"Población total: {Persona.poblacion_total}")  # Población total: 2
print(Persona.mostrar_especie_y_poblacion())
# Especie: Homo sapiens, Población total: 2
```

## ENCAPSULAMIENTO

### Concepto de encapsulamiento

El **encapsulamiento** es uno de los principios fundamentales de la POO. Consiste en:

1. **Ocultar** los detalles internos de implementación
2. **Controlar** el acceso a los datos y métodos
3. **Proteger** la integridad de los datos

```python
# Sin encapsulamiento (problemático)
class CuentaBancaria:
    def __init__(self, saldo):
        self.saldo = saldo  # Acceso directo al saldo

cuenta = CuentaBancaria(1000)
cuenta.saldo = -500  # ¡Problema! Saldo negativo directo
```

### Uso de modificadores de acceso (público, privado)

En Python, los modificadores de acceso se implementan mediante convenciones de nomenclatura:

#### Atributos y métodos públicos

Los atributos y métodos **públicos** son accesibles desde cualquier lugar. No tienen prefijo especial.

```python
class Rectangulo:
    def __init__(self, ancho, alto):
        self.ancho = ancho  # Público
        self.alto = alto    # Público
    
    def calcular_area(self):  # Método público
        return self.ancho * self.alto

rect = Rectangulo(5, 3)
print(rect.ancho)           # 5 (acceso directo)
print(rect.calcular_area()) # 15
```

#### Atributos y métodos protegidos

Los atributos y métodos **protegidos** se marcan con un guion bajo (`_`). Son accesibles pero indican que son para uso interno.

```python
class Vehiculo:
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo
        self._numero_chasis = "ABC123"  # Protegido
        
    def _verificar_mantenimiento(self):  # Método protegido
        print("Verificando mantenimiento...")
        
    def obtener_info(self):
        self._verificar_mantenimiento()  # Uso interno
        return f"{self.marca} - Chasis: {self._numero_chasis}"

vehiculo = Vehiculo("Toyota", "Camry")
print(vehiculo.obtener_info())
# Acceso directo (no recomendado pero posible)
print(vehiculo._numero_chasis)  # ABC123
```

#### Atributos y métodos privados

Los atributos y métodos **privados** se marcan con doble guion bajo (`__`). Python aplica *name mangling* para hacerlos más difíciles de acceder.

```python
class CuentaBancaria:
    def __init__(self, titular, saldo_inicial):
        self.titular = titular
        self.__saldo = saldo_inicial  # Privado
        self.__numero_cuenta = "001234567"  # Privado
    
    def __validar_operacion(self, cantidad):  # Método privado
        return cantidad > 0 and cantidad <= self.__saldo
    
    def depositar(self, cantidad):
        if cantidad > 0:
            self.__saldo += cantidad
            print(f"Depositados {cantidad}€. Saldo actual: {self.__saldo}€")
        else:
            print("La cantidad debe ser positiva")
    
    def retirar(self, cantidad):
        if self.__validar_operacion(cantidad):
            self.__saldo -= cantidad
            print(f"Retirados {cantidad}€. Saldo actual: {self.__saldo}€")
        else:
            print("Operación no válida")
    
    def consultar_saldo(self):
        return self.__saldo

# Uso correcto
cuenta = CuentaBancaria("Juan Pérez", 1000)
cuenta.depositar(200)    # Depositados 200€. Saldo actual: 1200€
cuenta.retirar(300)      # Retirados 300€. Saldo actual: 900€
print(cuenta.consultar_saldo())  # 900

# Intentos de acceso directo (no funcionan)
# print(cuenta.__saldo)  # Error: AttributeError
# cuenta.__saldo = 5000  # No modifica el saldo real

# El name mangling permite acceso (no recomendado)
print(cuenta._CuentaBancaria__saldo)  # 900 (acceso técnicamente posible)
```
**Name mangling** significa que Python cambia el nombre de los atributos y métodos privados agregando el nombre de la clase como prefijo. Por ejemplo, `self.__saldo` en la clase `CuentaBancaria` realmente se almacena como `self._CuentaBancaria__saldo`.

Esto tiene implicaciones importantes: si intentas acceder a un atributo privado usando `self.__atributo` **fuera de la clase (o desde una subclase)**, Python no lo encontrará directamente, porque el nombre ha sido modificado internamente. Sin embargo, dentro de la propia clase, incluyendo métodos especiales como `__str__`, sí puedes usar `self.__atributo` normalmente.

Recuerda: solo fuera de la clase (o desde una subclase) necesitas usar el nombre modificado (`_Clase__atributo`).

**No se recomienda acceder a atributos privados fuera de la clase, pero es posible usando el nombre mangled.**

>**Recomendación:**
- Usa `__atributo` (privado) solo para datos muy sensibles o críticos.
- Usa `_atributo` (protegido) para atributos internos que pueden ser usados por subclases.
- Usa `atributo` (público) si no hay problema en que se acceda desde fuera.

### Métodos getters y setters

Los **getters** y **setters** son métodos que permiten acceder y modificar atributos privados de forma controlada.

#### Getters y setters tradicionales

```python
class Temperatura:
    def __init__(self, celsius=0):
        self.__celsius = celsius
    
    # Getter
    def get_celsius(self):
        return self.__celsius
    
    # Setter
    def set_celsius(self, valor):
        if valor >= -273.15:  # Cero absoluto
            self.__celsius = valor
        else:
            raise ValueError("La temperatura no puede ser menor a -273.15°C")
    
    # Getter para Fahrenheit
    def get_fahrenheit(self):
        return (self.__celsius * 9/5) + 32
    
    # Setter para Fahrenheit
    def set_fahrenheit(self, valor):
        celsius = (valor - 32) * 5/9
        self.set_celsius(celsius)

# Uso
temp = Temperatura(25)
print(f"Celsius: {temp.get_celsius()}°C")     # 25°C
print(f"Fahrenheit: {temp.get_fahrenheit()}°F") # 77.0°F

temp.set_celsius(30)
print(f"Nueva temperatura: {temp.get_celsius()}°C")  # 30°C

# Validación
try:
    temp.set_celsius(-300)  # Error controlado
except ValueError as e:
    print(f"Error: {e}")
```

#### Propiedades con `@property`

Python ofrece un decorador `@property` que permite crear getters y setters más elegantes:

```python
class Persona:
    def __init__(self, nombre, edad):
        self.__nombre = nombre # se asignan los valores de los parámetros sin validación
        self.__edad = edad
    # si queremos que se validen los valores pasados por parámetros entonces ponemos
        self.nombre=nombre # utiliza el setter de nombre
        self.edad = edad ## utiliza el setter de edad


    # Getter para nombre
    @property
    def nombre(self):
        return self.__nombre
    
    # Setter para nombre
    @nombre.setter
    def nombre(self, valor):
        if isinstance(valor, str) and len(valor) > 0:
            self.__nombre = valor.title()  # Capitalizar
        else:
            raise ValueError("El nombre debe ser una cadena no vacía")
    
    # Getter para edad
    @property
    def edad(self):
        return self.__edad
    
    # Setter para edad
    @edad.setter
    def edad(self, valor):
        if isinstance(valor, int) and 0 <= valor <= 150:
            self.__edad = valor
        else:
            raise ValueError("La edad debe ser un número entre 0 y 150")
    
    # Propiedad de solo lectura
    @property
    def es_adulto(self):
        return self.__edad >= 18

# Uso como si fueran atributos normales
persona = Persona("juan pérez", 25)

# Getters (acceso como atributo)
print(persona.nombre)     # Juan Pérez (saldrá capitalizado si utiliza la segunda opción)
print(persona.edad)       # 25
print(persona.es_adulto)  # True

# Setters (asignación como atributo)
persona.nombre = "maría garcía"
persona.edad = 30

print(persona.nombre)  # María García
print(persona.edad)    # 30

# Validaciones
try:
    persona.edad = -5  # Error
except ValueError as e:
    print(f"Error: {e}")

try:
    persona.nombre = ""  # Error
except ValueError as e:
    print(f"Error: {e}")
```

#### Ejemplo completo con encapsulamiento

```python
class ProductoInventario:
    """Clase que representa un producto en el inventario con encapsulamiento completo"""
    
    # Atributo de clase
    _productos_creados = 0
    
    def __init__(self, codigo, nombre, precio, stock_inicial=0):
        # Validaciones iniciales
        if not isinstance(codigo, str) or len(codigo) < 3:
            raise ValueError("El código debe tener al menos 3 caracteres")
        
        self.__codigo = codigo
        self.__nombre = None
        self.__precio = None
        self.__stock = None
        self.__activo = True
        
        # Usar setters para validaciones
        self.nombre = nombre
        self.precio = precio
        self.stock = stock_inicial
        
        ProductoInventario._productos_creados += 1
    
    # Propiedades de solo lectura - no tienen setter asociado
    @property
    def codigo(self):
        """Código del producto (solo lectura)"""
        return self.__codigo
    
    @property
    def activo(self):
        """Estado activo del producto"""
        return self.__activo
    
    # Propiedad nombre con validación
    @property
    def nombre(self):
        return self.__nombre
    
    @nombre.setter
    def nombre(self, valor):
        if not isinstance(valor, str) or len(valor.strip()) < 2:
            raise ValueError("El nombre debe tener al menos 2 caracteres")
        self.__nombre = valor.strip().title()
    
    # Propiedad precio con validación
    @property
    def precio(self):
        return self.__precio
    
    @precio.setter
    def precio(self, valor):
        if not isinstance(valor, (int, float)) or valor <= 0:
            raise ValueError("El precio debe ser un número positivo")
        self.__precio = round(float(valor), 2)
    
    # Propiedad stock con validación
    @property
    def stock(self):
        return self.__stock
    
    @stock.setter
    def stock(self, valor):
        if not isinstance(valor, int) or valor < 0:
            raise ValueError("El stock debe ser un número entero no negativo")
        self.__stock = valor
    
    # Propiedades calculadas
    @property
    def valor_inventario(self):
        """Valor total del inventario para este producto"""
        return self.__precio * self.__stock if self.__activo else 0
    
    @property
    def disponible(self):
        """Indica si el producto está disponible"""
        return self.__activo and self.__stock > 0
    
    # Métodos públicos
    def agregar_stock(self, cantidad):
        """Agregar stock al producto"""
        if not isinstance(cantidad, int) or cantidad <= 0:
            raise ValueError("La cantidad debe ser un número entero positivo")
        
        if not self.__activo:
            raise RuntimeError("No se puede agregar stock a un producto inactivo")
        
        self.__stock += cantidad
        return f"Stock actualizado. Nuevo stock: {self.__stock}"
    
    def retirar_stock(self, cantidad):
        """Retirar stock del producto"""
        if not isinstance(cantidad, int) or cantidad <= 0:
            raise ValueError("La cantidad debe ser un número entero positivo")
        
        if not self.__activo:
            raise RuntimeError("No se puede retirar stock de un producto inactivo")
        
        if cantidad > self.__stock:
            raise ValueError(f"Stock insuficiente. Stock actual: {self.__stock}")
        
        self.__stock -= cantidad
        return f"Stock retirado. Stock restante: {self.__stock}"
    
    def desactivar(self):
        """Desactivar el producto"""
        self.__activo = False
        return f"Producto {self.__nombre} desactivado"
    
    def activar(self):
        """Activar el producto"""
        self.__activo = True
        return f"Producto {self.__nombre} activado"
    
    def aplicar_descuento(self, porcentaje):
        """Aplicar descuento al precio"""
        if not isinstance(porcentaje, (int, float)) or not (0 <= porcentaje <= 100):
            raise ValueError("El porcentaje debe estar entre 0 y 100")
        
        descuento = self.__precio * (porcentaje / 100)
        self.__precio = round(self.__precio - descuento, 2)
        return f"Descuento del {porcentaje}% aplicado. Nuevo precio: {self.__precio}€"
    
    # Método privado
    def __str__(self):
        estado = "Activo" if self.__activo else "Inactivo"
        return f"[{self.__codigo}] {self.__nombre} - {self.__precio}€ (Stock: {self.__stock}) - {estado}"
    
    def __repr__(self):
        return f"ProductoInventario('{self.__codigo}', '{self.__nombre}', {self.__precio}, {self.__stock})"
    
    # Método de clase
    @classmethod
    def productos_creados(cls):
        return cls._productos_creados

class Usuario:
    """Clase que representa a un usuario del sistema"""
    
    # Atributo de clase
    tipo_usuario = "Usuario Generico"
    
    def __init__(self, nombre, email, dni):
        """Constructor de la clase Usuario"""
        self.nombre = nombre
        self.email = email
        self.dni = dni
    
    def __str__(self):
        return f"{self.nombre} ({self.tipo_usuario})"
    
    def __repr__(self):
        return f"Usuario('{self.nombre}', '{self.email}', '{self.dni}')"

class Estudiante(Usuario):
    """Clase que representa a un estudiante"""
    
    tipo_usuario = "Estudiante"
    
    def __init__(self, nombre, email, dni, carrera):
        super().__init__(nombre, email, dni)
        self.carrera = carrera
    
    def __str__(self):
        return f"{self.nombre} - {self.carrera} ({self.tipo_usuario})"

class Profesor(Usuario):
    """Clase que representa a un profesor"""
    
    tipo_usuario = "Profesor"
    
    def __init__(self, nombre, email, dni, departamento):
        super().__init__(nombre, email, dni)
        self.departamento = departamento
    
    def __str__(self):
        return f"{self.nombre} - {self.departamento} ({self.tipo_usuario})"

# Ejemplo de uso
if __name__ == "__main__":
    # Crear productos
    producto1 = ProductoInventario("LAP001", "laptop gaming", 1200.50, 10)
    producto2 = ProductoInventario("MOU001", "mouse inalámbrico", 25.99, 50)
    
    print("=== INFORMACIÓN INICIAL ===")
    print(producto1)  # [LAP001] Laptop Gaming - 1200.5€ (Stock: 10) - Activo
    print(producto2)  # [MOU001] Mouse Inalámbrico - 25.99€ (Stock: 50) - Activo
    
    print(f"\nProductos creados: {ProductoInventario.productos_creados()}")
    
    print("\n=== ACCESO A PROPIEDADES ===")
    print(f"Código: {producto1.codigo}")
    print(f"Nombre: {producto1.nombre}")
    print(f"Precio: {producto1.precio}€")
    print(f"Stock: {producto1.stock}")
    print(f"Disponible: {producto1.disponible}")
    print(f"Valor inventario: {producto1.valor_inventario}€")
    
    print("\n=== MODIFICACIONES ===")
    producto1.nombre = "laptop gaming pro"
    producto1.precio = 1100.00
    print(producto1)
    
    print("\n=== GESTIÓN DE STOCK ===")
    print(producto1.agregar_stock(5))   # Stock actualizado. Nuevo stock: 15
    print(producto1.retirar_stock(3))   # Stock retirado. Stock restante: 12
    
    print("\n=== DESCUENTOS ===")
    print(producto2.aplicar_descuento(10))  # Descuento del 10% aplicado. Nuevo precio: 23.39€
    
    print("\n=== DESACTIVACIÓN ===")
    print(producto2.desactivar())  # Producto Mouse Inalámbrico desactivado
    print(f"Disponible después de desactivar: {producto2.disponible}")  # False
    print(f"Valor inventario después de desactivar: {producto2.valor_inventario}€")  # 0
    
    # Crear usuarios
    usuario1 = Usuario("Juan Pérez", "juan@email.com", "12345678A")
    estudiante1 = Estudiante("Ana García", "ana@email.com", "87654321B", "Ingeniería")
    profesor1 = Profesor("Luis López", "luis@email.com", "11223344C", "Matemáticas")
    
    print("\n=== USUARIOS CREADOS ===")
    print(usuario1)
    print(estudiante1)
    print(profesor1)
```

:computer: Actividad 1

## HERENCIA

### Concepto de herencia y creación de clases derivadas

#### ¿Qué es la herencia?

La **herencia** es un principio fundamental de la POO que permite crear nuevas clases basándose en clases existentes. La clase nueva (llamada **clase hija** o **derivada**) hereda atributos y métodos de la clase existente (llamada **clase padre** o **base**).

**Ventajas de la herencia:**
- **Reutilización de código**: No necesitas reescribir código existente
- **Extensibilidad**: Puedes añadir funcionalidades específicas
- **Mantenimiento**: Cambios en la clase base se reflejan en las derivadas
- **Jerarquía lógica**: Modela relaciones del mundo real

#### Sintaxis de herencia

```python
class ClaseBase:
    # Definición de la clase base
    pass

class ClaseDerivada(ClaseBase):
    # La clase derivada hereda de ClaseBase
    pass
```

#### Ejemplo básico de herencia

```python
# Clase base
class Animal:
    def __init__(self, nombre, edad):
        self.__nombre = nombre  # Atributo privado
        self.__edad = edad      # Atributo privado
    
    def hacer_sonido(self):
        return "El animal hace un sonido"
    
    def dormir(self):
        return f"{self.__nombre} está durmiendo"
    
    def comer(self):
        return f"{self.__nombre} está comiendo"
    
    def __str__(self):
        return f"Animal: {self.__nombre}, Edad: {self.__edad}"

# Clase derivada
class Perro(Animal):
    def __init__(self, nombre, edad, raza):
        super().__init__(nombre, edad)
        self.__raza = raza  # Atributo privado
    
    def hacer_sonido(self):
        return f"{self._Animal__nombre} dice: ¡Guau! ¡Guau!"
    
    def mover_cola(self):
        return f"{self._Animal__nombre} está moviendo la cola alegremente"
    
    def __str__(self):
        return f"Perro: {super().__str__()}, Raza: {self.__raza}"

# Clase derivada
class Gato(Animal):
    def __init__(self, nombre, edad, color):
        super().__init__(nombre, edad)
        self.__color = color  # Atributo privado
    
    def hacer_sonido(self):
        return f"{self._Animal__nombre} dice: ¡Miau!"
    
    def ronronear(self):
        return f"{self._Animal__nombre} está ronroneando"
    
    def __str__(self):
        #Name mangling
        return f"Gato: {self._Animal__nombre}, Edad: {self._Animal__edad}, Color: {self.__color}"
        # crear y utilizar los métodos públicos get

# Uso de herencia
perro = Perro("Buddy", 3, "Golden Retriever")
gato = Gato("Whiskers", 2, "Negro")

# Métodos heredados
print(perro.dormir())    # Buddy está durmiendo
print(gato.comer())      # Whiskers está comiendo

# Métodos sobrescritos
print(perro.hacer_sonido())  # Buddy dice: ¡Guau! ¡Guau!
print(gato.hacer_sonido())   # Whiskers dice: ¡Miau!

# Métodos específicos
print(perro.mover_cola())    # Buddy está moviendo la cola alegremente
print(gato.ronronear())      # Whiskers está ronroneando

# Métodos mágicos __str__
print(perro)  # Perro: Buddy, Edad: 3, Raza: Golden Retriever
print(gato)   # Gato: Whiskers, Edad: 2, Color: Negro

# Verificar herencia
print(isinstance(perro, Animal))  # True
print(isinstance(gato, Animal))   # True
print(isinstance(perro, Perro))   # True
print(isinstance(gato, Gato))     # True
```

### Uso de `super()` para llamar métodos de la clase base

#### ¿Qué es `super()`?

`super()` es una función incorporada que proporciona acceso a métodos de la clase padre desde una clase hija. Permite:
- Llamar al constructor de la clase base
- Acceder a métodos de la clase base que han sido sobrescritos
- Mantener la cadena de herencia en herencia múltiple

#### Usar `super()` en el constructor

```python
class Vehiculo:
    def __init__(self, marca, modelo, anio):
        self.__marca = marca
        self.__modelo = modelo
        self.__anio = anio
        self.__kilometraje = 0
        print(f"Vehículo creado: {marca} {modelo} ({anio})")
    
    def acelerar(self):
        return "El vehículo está acelerando"

class Coche(Vehiculo):
    def __init__(self, marca, modelo, anio, num_puertas):
        # Llamar al constructor de la clase base
        super().__init__(marca, modelo, anio)
        self.__num_puertas = num_puertas
        print(f"Coche con {num_puertas} puertas creado")
    
    def abrir_puertas(self):
        return f"Abriendo las {self.__num_puertas} puertas del coche"

class Motocicleta(Vehiculo):
    def __init__(self, marca, modelo, anio, cilindrada):
        super().__init__(marca, modelo, anio)
        self.__cilindrada = cilindrada
        print(f"Motocicleta de {cilindrada}cc creada")
    
    def hacer_caballito(self):
        return "¡Haciendo un caballito!"

# Crear objetos
coche = Coche("Toyota", "Camry", 2023, 4)
# Salida: 
# Vehículo creado: Toyota Camry (2023)
# Coche con 4 puertas creado

moto = Motocicleta("Yamaha", "R1", 2023, 1000)
# Salida:
# Vehículo creado: Yamaha R1 (2023)
# Motocicleta de 1000cc creada
```

#### Usar `super()` en métodos

```python
class Empleado:
    def __init__(self, nombre, salario):
        self._nombre = nombre
        self._salario = salario
    
    def trabajar(self):
        return f"{self._nombre} está trabajando"
    
    def calcular_bonus(self):
        return self._salario * 0.1  # 10% de bonus base
    
    def __str__(self):
            return f"Empleado: {self._nombre}, Salario: {self._salario}€"

class Desarrollador(Empleado):
        
    def __init__(self, nombre, salario, lenguaje):
        super().__init__(nombre, salario)
        self._lenguaje = lenguaje
    
    def trabajar(self):
        # Llamar al método de la clase base y extenderlo
        trabajo_base = super().trabajar()
        return f"{trabajo_base} programando en {self._lenguaje}"
    
    def calcular_bonus(self):
        # Llamar al método base y modificarlo
        bonus_base = super().calcular_bonus()
        return bonus_base * 1.5  # 50% más de bonus para desarrolladores
    
    def __str__(self):
            return f"Desarrollador: {self._nombre}, Salario: {self._salario}€, Lenguaje: {self._lenguaje}"

class Gerente(Empleado):
        
    def __init__(self, nombre, salario, equipo_size):
        super().__init__(nombre, salario)
        self._equipo_size = equipo_size
    
    def trabajar(self):
        trabajo_base = super().trabajar()
        return f"{trabajo_base} gestionando un equipo de {self._equipo_size} personas"
    
    def calcular_bonus(self):
        bonus_base = super().calcular_bonus()
        return bonus_base * (1 + self._equipo_size * 0.1)  # Bonus según tamaño del equipo
    
    def __str__(self):
            return f"Gerente: {self._nombre}, Salario: {self._salario}€, Equipo: {self._equipo_size} personas"

# Uso
dev = Desarrollador("Ana", 50000, "Python")
manager = Gerente("Carlos", 70000, 5)

print(dev.trabajar())        # Ana está trabajando programando en Python
print(manager.trabajar())    # Carlos está trabajando gestionando un equipo de 5 personas

print(f"Bonus desarrollador: {dev.calcular_bonus()}")      # 7500.0
print(f"Bonus gerente: {manager.calcular_bonus()}")        # 10500.0
```

#### Ejemplo completo con `super()`

```python
class Forma:
    """Clase base para formas geométricas"""
    
    def __init__(self, color="blanco"):
        self.color = color
        print(f"Forma creada con color {color}")
    #Indicas explícitamente que todas las subclases deben implementar ese método.
    #Es útil para crear una “interfaz” o clase abstracta.
    def area(self):
        raise NotImplementedError("Este método debe ser implementado por las clases hijas")
    
    def perimetro(self):
        raise NotImplementedError("Este método debe ser implementado por las clases hijas")

class Rectangulo(Forma):
    def __init__(self, ancho, alto, color="blanco"):
        super().__init__(color)  # Llamar al constructor de la clase base
        self.ancho = ancho
        self.alto = alto
    
    def area(self):
        return self.ancho * self.alto
    
    def perimetro(self):
        return 2 * (self.ancho + self.alto)
    
    def info(self):
        return f"Rectángulo de color {self.color}"

class Cuadrado(Rectangulo):
    def __init__(self, lado, color="blanco"):
        # Un cuadrado es un rectángulo con lados iguales
        super().__init__(lado, lado, color)
    
    def info(self):
        info_base = super().info()
        return info_base.replace("Rectángulo", "Cuadrado")

# Crear objetos
print("=== Creando formas ===")
rectangulo = Rectangulo(5, 3, "azul")
cuadrado = Cuadrado(4, "rojo")

print("\n=== Información ===")
print(rectangulo.info())  # Forma de color azul - Rectángulo 5x3
print(cuadrado.info())    # Forma de color rojo - Cuadrado 4x4

print("\n=== Cálculos ===")
print(f"Área rectángulo: {rectangulo.area()}")      # 15
print(f"Perímetro rectángulo: {rectangulo.perimetro()}")  # 16
print(f"Área cuadrado: {cuadrado.area()}")          # 16
print(f"Perímetro cuadrado: {cuadrado.perimetro()}")     # 16
```

## CLASES ABSTRACTAS E INTERFACES

### Concepto de clases abstractas

Las **clases abstractas** son clases que no pueden ser instanciadas directamente y están diseñadas para ser heredadas. Definen una interfaz común que las clases derivadas deben implementar.

**Características principales:**
- No se pueden crear objetos directamente de una clase abstracta
- Pueden contener métodos abstractos (sin implementación) y métodos concretos (con implementación)
- Obligan a las clases hijas a implementar ciertos métodos
- Se implementan usando el módulo `abc` (Abstract Base Classes)

#### Crear clases abstractas con `abc`

```python
from abc import ABC, abstractmethod

class Figura(ABC):
    """Clase abstracta para figuras geométricas"""
    
    def __init__(self, color="blanco"):
        self.color = color
    
    @abstractmethod
    def area(self):
        """Método abstracto: debe ser implementado por las clases hijas"""
        pass
    
    @abstractmethod
    def perimetro(self):
        """Método abstracto: debe ser implementado por las clases hijas"""
        pass
    
    # Método concreto (con implementación)
    def describir(self):
        """Método concreto que pueden usar todas las clases hijas"""
        return f"Figura de color {self.color}"

# Intentar instanciar la clase abstracta genera error
# figura = Figura()  # TypeError: Can't instantiate abstract class

class Rectangulo(Figura):
    """Clase concreta que hereda de Figura"""
    
    def __init__(self, ancho, alto, color="blanco"):
        super().__init__(color)  # Llamar al constructor de la clase base
        self.ancho = ancho
        self.alto = alto
    
    # Implementar métodos abstractos (obligatorio)
    def area(self):
        return self.ancho * self.alto
    
    def perimetro(self):
        return 2 * (self.ancho + self.alto)

class Circulo(Figura):
    """Otra clase concreta"""
    
    def __init__(self, radio, color="blanco"):
        super().__init__(color)  # Llamar al constructor de la clase base
        self.radio = radio
    
    def area(self):
        return 3.14159 * self.radio ** 2
    
    def perimetro(self):
        return 2 * 3.14159 * self.radio

# Ahora sí podemos instanciar las clases concretas
rect = Rectangulo(5, 3, "azul")
circ = Circulo(4, "rojo")

print(rect.area())         # 15
print(rect.describir())    # Figura de color azul - Rectángulo 5x3
print(circ.perimetro())    # 25.13272
```

#### Métodos abstractos con implementación parcial

```python
from abc import ABC, abstractmethod

class Vehiculo(ABC):
    """Clase abstracta con métodos abstractos y concretos"""
    
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo
        self.velocidad = 0
    
    @abstractmethod
    def arrancar(self):
        """Método abstracto con implementación base"""
        print(f"Arrancando {self.marca} {self.modelo}")
        # Las clases hijas pueden llamar a super().arrancar()
    
    @abstractmethod
    def detener(self):
        """Método abstracto puro"""
    
    def acelerar(self, incremento=10):
        """Método concreto"""
        self.velocidad += incremento
        return f"Velocidad: {self.velocidad} km/h"

class Coche(Vehiculo):
    def arrancar(self):
        super().arrancar()  # Llamar a la implementación base
        print("Encendiendo motor de gasolina")
    
    def detener(self):
        self.velocidad = 0
        print("Coche detenido con frenos de disco")

class Motocicleta(Vehiculo):
    def arrancar(self):
        super().arrancar()
        print("Activando motor eléctrico")
    
    def detener(self):
        self.velocidad = 0
        print("Vehículo eléctrico detenido con frenos regenerativos")

# Ahora sí podemos instanciar las clases concretas
coche = Coche("Toyota", "Camry", 2023, 4)
coche.arrancar()
# Salida:
# Arrancando Toyota Camry
# Encendiendo motor de gasolina
    
electrico = Motocicleta("Yamaha", "R1", 2023, 1000)
electrico.arrancar()
# Salida:
# Arrancando Yamaha R1
# Activando motor eléctrico
```

### Interfaces en Python

Python no tiene una palabra clave específica para interfaces como otros lenguajes (Java, C#), pero se pueden simular usando:

1. **Clases abstractas con solo métodos abstractos**
2. **Protocolos (desde Python 3.8)**

#### Interfaces mediante clases abstractas

```python
from abc import ABC, abstractmethod

class Reproducible(ABC):
    """Interfaz para objetos reproducibles"""
    
    @abstractmethod
    def reproducir(self):
        """Inicia la reproducción"""
    
    @abstractmethod
    def pausar(self):
        """Pausa la reproducción"""
    
    @abstractmethod
    def detener(self):
        """Detiene la reproducción"""

class Descargable(ABC):
    """Interfaz para objetos descargables"""
    
    @abstractmethod
    def descargar(self, destino):
        """Descarga el contenido"""
    
    @abstractmethod
    def obtener_tamaño(self):
        """Retorna el tamaño del archivo"""

# Implementar múltiples interfaces (herencia múltiple)
class Video(Reproducible, Descargable):
    """Clase que implementa dos interfaces"""
    
    def __init__(self, titulo, url, tamaño_mb):
        self.titulo = titulo
        self.url = url
        self.tamaño_mb = tamaño_mb
        self.reproduciendo = False
    
    # Implementar métodos de Reproducible
    def reproducir(self):
        self.reproduciendo = True
        return f"Reproduciendo video: {self.titulo}"
    
    def pausar(self):
        return f"Video pausado: {self.titulo}"
    
    def detener(self):
        self.reproduciendo = False
        return f"Video detenido: {self.titulo}"
    
    # Implementar métodos de Descargable
    def descargar(self, destino):
        return f"Descargando {self.titulo} a {destino}"
    
    def obtener_tamaño(self):
        return self.tamaño_mb

class Audio(Reproducible, Descargable):
    """Otra clase que implementa las mismas interfaces"""
    
    def __init__(self, titulo, artista, url, tamaño_mb):
        self.titulo = titulo
        self.artista = artista
        self.url = url
        self.tamaño_mb = tamaño_mb
    
    def reproducir(self):
        return f"♪ Reproduciendo: {self.titulo} - {self.artista}"
    
    def pausar(self):
        return f"♪ Pausado: {self.titulo}"
    
    def detener(self):
        return f"♪ Detenido: {self.titulo}"
    
    def descargar(self, destino):
        return f"Descargando {self.titulo} de {self.artista}"
    
    def obtener_tamaño(self):
        return self.tamaño_mb

# Función polimórfica que trabaja con cualquier Reproducible
def reproducir_multimedia(items):
    """Reproduce cualquier objeto que implemente Reproducible"""
    for item in items:
        if isinstance(item, Reproducible):
            print(item.reproducir())

# Uso
video = Video("Tutorial Python", "https://...", 150)
audio = Audio("Canción", "Artista", "https://...", 5)

reproducir_multimedia([video, audio])
# Salida:
# Reproduciendo video: Tutorial Python
# ♪ Reproduciendo: Canción - Artista
```

#### Protocolos (Python 3.8+)

Los **protocolos** son una forma más "pythónica" de definir interfaces usando `typing.Protocol`:

```python
from typing import Protocol

class Volador(Protocol):
    """Protocolo para objetos que pueden volar"""
    
    def despegar(self) -> str:
        ...
    
    def aterrizar(self) -> str:
        ...
    
    def volar_a(self, destino: str) -> str:
        ...

class Ave:
    def despegar(self) -> str:
        return "El ave despega batiendo sus alas"
    
    def aterrizar(self) -> str:
        return "El ave aterriza suavemente"
    
    def volar_a(self, destino: str) -> str:
        return f"El ave vuela hacia {destino}"

class Avion:
    def despegar(self) -> str:
        return "El avión despega de la pista"
    
    def aterrizar(self) -> str:
        return "El avión aterriza en el aeropuerto"
    
    def volar_a(self, destino: str) -> str:
        return f"El avión vuela hacia {destino}"

def realizar_vuelo(volador: Volador, destino: str):
    """Función que trabaja con cualquier objeto que cumpla el protocolo"""
    print(volador.despegar())
    print(volador.volar_a(destino))
    print(volador.aterrizar())

# Uso - duck typing: si camina como pato y grazna como pato...
ave = Ave()
avion = Avion()

realizar_vuelo(ave, "sur")
realizar_vuelo(avion, "Madrid")
```

#### Ejemplo completo: Sistema de pagos

```python
from abc import ABC, abstractmethod

# Interfaz para métodos de pago
class MetodoPago(ABC):
    """Interfaz abstracta para métodos de pago"""
    
    @abstractmethod
    def procesar_pago(self, cantidad):
        """Procesa un pago"""
    
    @abstractmethod
    def validar(self):
        """Valida el método de pago"""
    
    @abstractmethod
    def obtener_descripcion(self):
        """Obtiene descripción del método"""

class TarjetaCredito(MetodoPago):
    def __init__(self, numero, titular, cvv):
        self.numero = numero
        self.titular = titular
        self.cvv = cvv
    
    def validar(self):
        # Validación simple
        return len(self.numero) == 16 and len(self.cvv) == 3
    
    def procesar_pago(self, cantidad):
        if not self.validar():
            raise ValueError("Tarjeta inválida")
        return f"Pago de {cantidad}€ procesado con tarjeta ****{self.numero[-4:]}"
    
    def obtener_descripcion(self):
        return f"Tarjeta de crédito ****{self.numero[-4:]}"

class PayPal(MetodoPago):
    def __init__(self, email):
        self.email = email
    
    def validar(self):
        return "@" in self.email and len(self.email) > 5
    
    def procesar_pago(self, cantidad):
        if not self.validar():
            raise ValueError("Email inválido")
        return f"Pago de {cantidad}€ procesado vía PayPal ({self.email})"
    
    def obtener_descripcion(self):
        return f"PayPal: {self.email}"

class Transferencia(MetodoPago):
    def __init__(self, iban, banco):
        self.iban = iban
        self.banco = banco
    
    def validar(self):
        return len(self.iban) >= 20
    
    def procesar_pago(self, cantidad):
        if not self.validar():
            raise ValueError("IBAN inválido")
        return f"Transferencia de {cantidad}€ procesada desde {self.banco}"
    
    def obtener_descripcion(self):
        return f"Transferencia bancaria: {self.iban[:4]}...{self.iban[-4:]}"

# Sistema de procesamiento de pagos
class SistemaPagos:
    def __init__(self):
        self.pagos_procesados = []
    
    def realizar_pago(self, metodo_pago: MetodoPago, cantidad: float):
        """Procesa un pago usando cualquier método que implemente MetodoPago"""
        try:
            print(f"\n--- Procesando con {metodo_pago.obtener_descripcion()} ---")
            resultado = metodo_pago.procesar_pago(cantidad)
            self.pagos_procesados.append({
                'metodo': metodo_pago.obtener_descripcion(),
                'cantidad': cantidad,
                'resultado': resultado
            })
            print(resultado)
            return True
        except ValueError as e:
            print(f"Error: {e}")
            return False
    
    def mostrar_historial(self):
        """Muestra el historial de pagos"""
        print("\n=== HISTORIAL DE PAGOS ===")
        for pago in self.pagos_procesados:
            print(f"- {pago['metodo']}: {pago['cantidad']}€")

# Uso del sistema
sistema = SistemaPagos()

# Diferentes métodos de pago
tarjeta = TarjetaCredito("1234567890123456", "Juan Pérez", "123")
paypal = PayPal("usuario@email.com")
transferencia = Transferencia("ES1234567890123456789012", "BBVA")

# Procesar pagos con diferentes métodos
sistema.realizar_pago(tarjeta, 150.00)
sistema.realizar_pago(paypal, 75.50)
sistema.realizar_pago(transferencia, 500.00)

# Mostrar historial
sistema.mostrar_historial()
```

## POLIMORFISMO

### Concepto de polimorfismo

El **polimorfismo** es otro de los principios fundamentales de la POO. Permite que objetos de diferentes clases sean tratados como objetos de una clase común a través de una interfaz compartida.

**Tipos de polimorfismo:**
- **Polimorfismo de inclusión**: Clases diferentes que son tratadas como instancias de una misma clase base (herencia).
- **Polimorfismo de sobrecarga**: Múltiples métodos con el mismo nombre pero comportamientos diferentes (no soportado nativamente en Python, se logra con argumentos por defecto o `*args`/`**kwargs`).
- **Polimorfismo de tiempo de ejecución**: Decisión sobre qué método ejecutar en tiempo de ejecución (logrado mediante métodos sobrescritos).

### Uso de métodos sobrescritos en clases derivadas

La **sobrescritura de métodos** (overriding) es una forma de polimorfismo donde una clase derivada proporciona una implementación específica de un método que ya está definido en su clase base.

#### Sobrescritura de métodos

```python
class Animal:
    def hacer_sonido(self):
        return "El animal hace un sonido"

class Perro(Animal):
    def hacer_sonido(self):
        return "Guau!"

class Gato(Animal):
    def hacer_sonido(self):
        return "Miau"

# Función que recibe un animal y hace que emita su sonido
def reproducir_sonido(animal: Animal):
    print(animal.hacer_sonido())

# Uso
mi_perro = Perro()
mi_gato = Gato()

reproducir_sonido(mi_perro)  # Guau!
reproducir_sonido(mi_gato)   # Miau
```

#### Utilización del Polimorfismo

El polimorfismo permite escribir código más genérico y reutilizable. Por ejemplo, una función puede aceptar cualquier objeto que tenga un método específico, sin importar su clase concreta.

```python
class Ave:
    def volar(self):
        return "El ave vuela en el cielo"

class Pinguino(Ave):
    def volar(self):
        return "Los pingüinos no vuelan, nadan en el agua"

# Función que hace que cualquier ave vuele
def hacer_volar(ave: Ave):
    print(ave.volar())

# Uso
mi_ave = Ave()
mi_pinguino = Pinguino()

hacer_volar(mi_ave)       # El ave vuela en el cielo
hacer_volar(mi_pinguino)  # Los pingüinos no vuelan, nadan en el agua
```

#### Ejemplo completo de polimorfismo

```python
class Forma:
    def area(self):
        raise NotImplementedError("Subclases deben implementar este método")
    
    def perimetro(self):
        raise NotImplementedError("Subclases deben implementar este método")

class Cuadrado(Forma):
    def __init__(self, lado):
        self.lado = lado
    
    def area(self):
        return self.lado ** 2
    
    def perimetro(self):
        return 4 * self.lado

class Triangulo(Forma):
    def __init__(self, base, altura):
        self.base = base
        self.altura = altura
    
    def area(self):
        return (self.base * self.altura) / 2
    
    def perimetro(self):
        # Suponiendo triángulo equilátero para simplificar
        return 3 * self.base

# Lista de formas
formas = [Cuadrado(4), Triangulo(3, 6)]

# Calcular áreas y perímetros
for forma in formas:
    print(f"Área: {forma.area()}, Perímetro: {forma.perimetro()}")
```

## MÉTODOS ESPECIALES

### ¿Qué son los métodos mágicos?

Los **métodos mágicos** (o métodos especiales) son funciones predefinidas en Python que permiten a las clases personalizar su comportamiento en ciertas situaciones. Se les conoce como "mágicos" porque empiezan y terminan con dobles guiones bajos (`__`), como `__init__`, `__str__`, `__add__`, entre otros.

### Uso de métodos mágicos como `__init__()`, `__str__()`, y `__repr__()`

#### El método `__init__()`

El método `__init__()` es el constructor de la clase. Se llama automáticamente al crear una nueva instancia de la clase.

```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad

# Crear objeto
persona1 = Persona("Juan", 30)

# Acceder a atributos
print(persona1.nombre)  # Juan
print(persona1.edad)    # 30
```

#### El método `__str__()`

El método `__str__()` define la representación en forma de cadena de un objeto, es decir, cómo se muestra el objeto como texto. Se llama automáticamente cuando se usa `print()` con un objeto de esa clase.

```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
    
    def __str__(self):
        return f"{self.nombre} tiene {self.edad} años"

# Crear objeto
persona1 = Persona("Ana", 25)

# Imprimir objeto
print(persona1)  # Ana tiene 25 años
```

#### El método `__repr__()`

El método `__repr__()` define una representación más detallada y técnica del objeto, útil para depuración. Se llama automáticamente cuando se usa `repr()` con un objeto de esa clase o en ciertas situaciones de depuración.

```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
    
    def __repr__(self):
        return f"Persona(nombre={self.nombre}, edad={self.edad})"

# Crear objeto
persona1 = Persona("Luis", 28)

# Representación para depuración
print(repr(persona1))  # Persona(nombre=Luis, edad=28)
```

#### Otros métodos especiales importantes

- `__add__(self, other)`: Sobrecarga del operador `+`
- `__sub__(self, other)`: Sobrecarga del operador `-`
- `__mul__(self, other)`: Sobrecarga del operador `*`
- `__truediv__(self, other)`: Sobrecarga del operador `/`
- `__len__(self)`: Define el comportamiento de la función `len()` para la clase
- `__getitem__(self, key)`: Sobrecarga del acceso a elementos, como `objeto[key]`
- `__setitem__(self, key, value)`: Sobrecarga de la asignación de elementos, como `objeto[key] = value`
- `__delitem__(self, key)`: Sobrecarga de la eliminación de elementos, como `del objeto[key]`
- `__iter__(self)`: Devuelve un iterador para la clase
- `__next__(self)`: Devuelve el siguiente elemento del iterador
- `__contains__(self, item)`: Sobrecarga del operador `in` para verificar pertenencia

### Ejemplo completo con métodos especiales

```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __add__(self, otro):
        return Vector(self.x + otro.x, self.y + otro.y)
    
    def __sub__(self, otro):
        return Vector(self.x - otro.x, self.y - otro.y)
    
    def __mul__(self, escalar):
        return Vector(self.x * escalar, self.y * escalar)
    
    def __truediv__(self, escalar):
        return Vector(self.x / escalar, self.y / escalar)
    
    def __repr__(self):
        return f"Vector({self.x}, {self.y})"

# Crear vectores
v1 = Vector(2, 3)
v2 = Vector(4, 5)

# Operaciones con vectores
print(v1 + v2)  # Vector(6, 8)
print(v1 - v2)  # Vector(-2, -2)
print(v1 * 3)   # Vector(6, 9)
print(v2 / 2)   # Vector(2.0, 2.5)
```

## MÓDULOS Y PAQUETES EN POO

### Organización de clases en módulos

#### ¿Por qué usar módulos?

Los **módulos** son archivos que contienen definiciones y declaraciones de Python. Permiten organizar el código en partes más manejables y reutilizables. Usar módulos tiene varias ventajas:

- **Organización**: Mantiene el código organizado y separado por funcionalidades.
- **Reutilización**: Permite reutilizar código en diferentes partes de un programa o en diferentes programas.
- **Mantenibilidad**: Facilita la actualización y mantenimiento del código.
- **Namespace**: Proporciona un espacio de nombres separado para evitar colisiones de nombres.

#### Crear un módulo con clases

Para crear un módulo, simplemente se define un archivo Python con las clases y funciones deseadas. Por ejemplo, un archivo `matematicas.py` con:

```python
# matematicas.py

class Calculadora:
    def sumar(self, a, b):
        return a + b
    
    def restar(self, a, b):
        return a - b
```

#### Importar clases desde módulos

Para usar las clases de un módulo, se debe importar el módulo en el script principal. Por ejemplo:

```python
# main.py
from matematicas import Calculadora

calc = Calculadora()
print(calc.sumar(5, 3))
```

### Creación y estructura de paquetes

#### ¿Qué es un paquete?

Un **paquete** es una forma de organizar módulos relacionados en un solo directorio. Un paquete es simplemente un directorio que contiene un archivo especial llamado `__init__.py` (puede estar vacío) y uno o más módulos.

#### El archivo `__init__.py`

El archivo `__init__.py` indica a Python que el directorio debe ser tratado como un paquete. Puede estar vacío o contener código de inicialización para el paquete.

#### Estructura de directorios

```
mi_proyecto/
│
├── matematicas/
│   ├── __init__.py
│   ├── basicas.py
│   └── avanzadas.py
│
└── main.py
```

### Importación avanzada de clases

#### Diferentes formas de importar

Existen varias formas de importar clases y módulos en Python:

- Importar todo el módulo:
```python
import matematicas
```

- Importar una clase específica de un módulo:
```python
from matematicas.basicas import Calculadora
```

- Importar múltiples clases o funciones:
```python
from matematicas.basicas import Calculadora, sumar
```

- Importar con alias:
```python
from matematicas.basicas import Calculadora as Calc
```

#### Alias y nombres personalizados

Se pueden usar alias para acortar nombres de módulos o clases al importarlos. Por ejemplo:

```python
from matematicas.basicas import Calculadora as Calc

calc = Calc()
```

#### Importación condicional

También es posible importar módulos de forma condicional, dentro de funciones o métodos, según sea necesario.

```python
def usar_calculadora():
    from matematicas.basicas import Calculadora
    calc = Calculadora()
    return calc.sumar(5, 3)
```

### Buenas prácticas y organización

#### Convenciones de nomenclatura

- Usar nombres en minúsculas para módulos y paquetes.
- Usar guiones bajos para separar palabras en nombres de módulos.
- Usar nombres descriptivos y significativos.

```python
# ✅ Buenos nombres
modulos/
├── vehiculos.py          # minúsculas, descriptivo
├── sistemas_navegacion.py # guiones bajos para múltiples palabras
└── config.py             # corto y claro

# ❌ Malos nombres
modulos/
├── Vehiculos.py          # No usar mayúsculas
├── v.py                  # Muy corto, no descriptivo
└── sistemasDeNavegacion.py # camelCase no es pythónico

```
#### Organización por funcionalidad

Organizar módulos y paquetes por funcionalidad relacionada. Por ejemplo, todos los módulos relacionados con matemáticas en un paquete `matematicas`, módulos de manejo de archivos en un paquete `archivos`, etc.

```python
# Estructura recomendada para proyecto POO
mi_app/
├── main.py                    # Punto de entrada
├── config.py                  # Configuración global
├── models/                    # Modelos de datos (clases principales)
│   ├── __init__.py
│   ├── usuario.py
│   ├── producto.py
│   └── pedido.py
├── services/                  # Lógica de negocio
│   ├── __init__.py
│   ├── autenticacion.py
│   ├── gestion_productos.py
│   └── procesamiento_pedidos.py
├── utils/                     # Utilidades y herramientas
│   ├── __init__.py
│   ├── validaciones.py
│   ├── formateo.py
│   └── constantes.py
├── interfaces/               # Interfaces de usuario
│   ├── __init__.py
│   ├── cli.py
│   └── web.py
└── tests/                   # Pruebas unitarias
    ├── __init__.py
    ├── test_models.py
    ├── test_services.py
    └── test_utils.py

```
#### Evitar importaciones circulares

Las **importaciones circulares** ocurren cuando dos o más módulos se importan entre sí. Esto puede causar problemas de dependencia y errores de importación. Para evitarlo:

- Reorganizar el código para eliminar dependencias circulares.
- Usar importaciones locales (dentro de funciones) en lugar de importaciones globales.
**❌ Importación circular (problema):**

```python
# archivo_a.py
from archivo_b import ClaseB

class ClaseA:
    def usar_b(self):
        return ClaseB()

# archivo_b.py  
from archivo_a import ClaseA  # ¡Importación circular!

class ClaseB:
    def usar_a(self):
        return ClaseA()
```

**✅ Soluciones:**

```python
# Solución 1: Importación local
# archivo_a.py
class ClaseA:
    def usar_b(self):
        from archivo_b import ClaseB  # Importación dentro de la función
        return ClaseB()

# Solución 2: Usar un módulo intermedio
# base.py
class ClaseBase:
    pass

# archivo_a.py
from base import ClaseBase

class ClaseA(ClaseBase):
    pass

# archivo_b.py
from base import ClaseBase

class ClaseB(ClaseBase):
    pass

# Solución 3: Reestructurar el código
# Mover ambas clases al mismo módulo si están muy relacionadas
```

#### Ejemplo de proyecto estructurado

**Proyecto: Sistema de Biblioteca** 
```
biblioteca/
├── main.py
├── config.py
├── modelos/
│   ├── __init__.py
│   └── libro.py
├── servicios/
│   ├── __init__.py
│   └── gestion_libros.py
├── utilidades/
│   ├── __init__.py
│   ├── validaciones.py
│   └── formateo.py
├── interfaces/
│   ├── __init__.py
│   └── cli.py
```
**main.py**
Script principal que inicia el sistema y muestra un menú básico usando la interfaz CLI.

```python
# filepath: biblioteca/main.py
from config import CONFIGURACION
from modelos import Libro
from servicios.gestion_libros import Biblioteca
from interfaces.cli import menu_principal

def main():
    biblioteca = Biblioteca()
    menu_principal(biblioteca)

if __name__ == "__main__":
    main()
```
**config.py**
Configuración global del sistema.

```python
# filepath: biblioteca/config.py
CONFIGURACION = {
    'dias_prestamo_default': 14,
    'max_renovaciones': 2,
    'multa_por_dia': 0.50
}
```
**modelos/`__init__.py`**
Expone las clases principales del paquete modelos.

```python
# filepath: biblioteca/modelos/__init__.py
from .libro import Libro, LibroFisico, LibroDigital, LibroAudio

__all__ = [
    'Libro', 'LibroFisico', 'LibroDigital', 'LibroAudio'
]
```
**modelos/libro.py**
Clases relacionadas con libros. La validación de ISBN se importa de utilidades.
```python
# filepath: biblioteca/modelos/libro.py
"""
Recomendación sobre organización de clases en ficheros:
- Si el número de clases relacionadas con libros es pequeño y sus definiciones son cortas, puedes mantenerlas todas en este fichero para facilitar la gestión y la lectura.
- Si el fichero empieza a crecer demasiado, las clases tienen muchas líneas de código, o cada tipo de libro tiene lógica específica compleja, es recomendable separar cada clase principal en su propio fichero (por ejemplo: libro_fisico.py, libro_digital.py, libro_audio.py).
- También puedes agrupar clases muy relacionadas en un mismo fichero y dejar utilidades o funciones auxiliares en otros módulos.
- El objetivo es mantener el código organizado, fácil de mantener y evitar ficheros excesivamente largos.
"""

from datetime import datetime
from utilidades.validaciones import validar_isbn

# ...existing code...
from datetime import datetime
from utilidades.validaciones import validar_isbn

class Libro:
    def __init__(self, titulo, autor, isbn, año_publicacion):
        self.titulo = titulo
        self.autor = autor
        self.isbn = validar_isbn(isbn)
        self.año_publicacion = año_publicacion
        self.disponible = True
        self.fecha_creacion = datetime.now()

    def marcar_no_disponible(self):
        self.disponible = False

    def marcar_disponible(self):
        self.disponible = True

    def __str__(self):
        estado = "Disponible" if self.disponible else "No disponible"
        return f"{self.titulo} por {self.autor} ({self.año_publicacion}) - {estado}"

class LibroFisico(Libro):
    def __init__(self, titulo, autor, isbn, año_publicacion, seccion, estante, posicion):
        super().__init__(titulo, autor, isbn, año_publicacion)
        self.seccion = seccion
        self.estante = estante
        self.posicion = posicion
        self.estado_fisico = "bueno"
        self.prestado_a = None

    @property
    def ubicacion(self):
        return f"{self.seccion}-{self.estante}-{self.posicion}"

class LibroDigital(Libro):
    FORMATOS_PERMITIDOS = ['pdf', 'epub', 'mobi', 'azw3']

    def __init__(self, titulo, autor, isbn, año_publicacion, formato, tamaño_mb, url_descarga):
        super().__init__(titulo, autor, isbn, año_publicacion)
        if formato.lower() not in self.FORMATOS_PERMITIDOS:
            raise ValueError(f"Formato no permitido. Use: {', '.join(self.FORMATOS_PERMITIDOS)}")
        self.formato = formato.lower()
        self.tamaño_mb = tamaño_mb
        self.url_descarga = url_descarga

class LibroAudio(Libro):
    def __init__(self, titulo, autor, isbn, año_publicacion, duracion_minutos, narrador, formato_audio='mp3'):
        super().__init__(titulo, autor, isbn, año_publicacion)
        self.duracion_minutos = duracion_minutos
        self.narrador = narrador
        self.formato_audio = formato_audio
```
**servicios/`__init__.py`**
Inicializa el paquete servicios.

```python
# filepath: biblioteca/servicios/__init__.py
# ...existing code...
```
**servicios/gestion_libros.py**
```python
# filepath: biblioteca/servicios/gestion_libros.py
from modelos import Libro, LibroFisico, LibroDigital, LibroAudio

class Biblioteca:
    def __init__(self):
        self.libros = []

    def agregar_libro(self, libro):
        self.libros.append(libro)

    def buscar_libro(self, titulo):
        return [libro for libro in self.libros if titulo.lower() in libro.titulo.lower()]

    def listar_libros(self):
        return self.libros
```
**utilidades/`__init__.py`**
Inicializa el paquete utilidades.

```python
# filepath: biblioteca/utilidades/__init__.py
# ...existing code...
```
**utilidades/validaciones.py**
Validación de ISBN para libros.

```python
# filepath: biblioteca/utilidades/validaciones.py
def validar_isbn(isbn):
    isbn_limpio = isbn.replace("-", "").replace(" ", "")
    if len(isbn_limpio) not in [10, 13]:
        raise ValueError(f"ISBN inválido: {isbn}")
    return isbn
```
**utilidades/formateo.py**
Funciones de formateo para libros.

```python
# filepath: biblioteca/utilidades/formateo.py
def formatear_libro(libro):
    return str(libro)
```
**interfaces/`__init__.py`**
Inicializa el paquete interfaces.

```python
# filepath: biblioteca/interfaces/__init__.py
# ...existing code...
```
**interfaces/cli.py**
Interfaz de línea de comandos para interactuar con la biblioteca.
```python
# filepath: biblioteca/interfaces/cli.py
def menu_principal(biblioteca):
    salir = False
    while not salir:
        print("\n--- Menú Biblioteca ---")
        print("1. Listar libros")
        print("2. Buscar libro")
        print("3. Salir")
        try:
            opcion = input("Seleccione opción: ")
            if opcion == "1":
                for libro in biblioteca.listar_libros():
                    print(libro)
            elif opcion == "2":
                titulo = input("Título a buscar: ")
                resultados = biblioteca.buscar_libro(titulo)
                for libro in resultados:
                    print(libro)
            elif opcion == "3":
                print("¡Hasta luego!")
                salir = True
            else:
                print("Opción no válida.")
        except Exception as e:
            print(f"Error: {e}")
```

:computer: Actividad 2

## PRUEBAS UNITARIAS PARA CLASES

### Importancia de probar clases

Las **pruebas unitarias** son fundamentales para asegurar que las clases y módulos funcionan correctamente. Permiten detectar errores y problemas de lógica en etapas tempranas del desarrollo.

**Beneficios de las pruebas unitarias:**
- Detectar errores rápidamente
- Asegurar el correcto funcionamiento del código
- Facilitar el mantenimiento y refactorización
- Proporcionar documentación adicional sobre el comportamiento del código

### Configuración de pruebas con `unittest`

El módulo `unittest` proporciona un marco de trabajo para crear y ejecutar pruebas unitarias en Python.

#### Estructura básica de pruebas para clases

```python
import unittest
from mi_modulo import MiClase

class TestMiClase(unittest.TestCase):
    def setUp(self):
        """Método que se ejecuta antes de cada prueba"""
        self.objeto = MiClase()
    
    def tearDown(self)
        """Método que se ejecuta después de cada prueba"""
        del self.objeto
    
    def test_metodo1(self):
        """Prueba para el método 1"""
        resultado = self.objeto.metodo1()
        self.assertEqual(resultado, "valor esperado")
    
    def test_metodo2(self):
        """Prueba para el método 2"""
        with self.assertRaises(ValueError):
            self.objeto.metodo2("entrada no válida")

if __name__ == "__main__":
    unittest.main()
```

#### Métodos `setUp()` y `tearDown()`

- `setUp()`: Se ejecuta antes de cada método de prueba. Se usa para preparar el entorno de la prueba, como crear objetos o establecer conexiones.
- `tearDown()`: Se ejecuta después de cada método de prueba. Se usa para limpiar el entorno de la prueba, como cerrar archivos o eliminar objetos.

### Pruebas de atributos y métodos

#### Probar inicialización de objetos

```python
def test_inicializacion(self):
    objeto = MiClase("valor1", "valor2")
    self.assertEqual(objeto.atributo1, "valor1")
    self.assertEqual(objeto.atributo2, "valor2")
```

#### Probar métodos públicos

```python
def test_metodo_publico(self):
    resultado = self.objeto.metodo_publico()
    self.assertTrue(resultado)
```

#### Pruebas de herencia y polimorfismo

```python
class TestClaseDerivada(unittest.TestCase):
    def setUp(self):
        self.objeto = ClaseDerivada()
    
    def test_metodo_sobrescrito(self):
        resultado = self.objeto.metodo()
        self.assertEqual(resultado, "comportamiento esperado")
```

### Pruebas de métodos especiales

#### Probar métodos mágicos

```python
def test_str(self):
    resultado = str(self.objeto)
    self.assertEqual(resultado, "representación en cadena esperada")
```

#### Probar operadores sobrecargados

```python
def test_suma(self):
    resultado = self.objeto1 + self.objeto2
    self.assertEqual(resultado, valor_esperado)
```

### Ejemplo completo de pruebas para el sistema de biblioteca

```python
# tests/test_libro.py
import unittest
from datetime import datetime
from modelos.libro import Libro, LibroFisico, LibroDigital, LibroAudio


class TestLibro(unittest.TestCase):
    """Pruebas para la clase Libro"""
    
    def setUp(self):
        """Preparar objetos de prueba"""
        self.libro = Libro("El Quijote", "Cervantes", "978-84-376-0494-7", 1605)
    
    def test_inicializacion(self):
        """Probar inicialización correcta"""
        self.assertEqual(self.libro.titulo, "El Quijote")
        self.assertEqual(self.libro.autor, "Cervantes")
        self.assertEqual(self.libro.año_publicacion, 1605)
        self.assertTrue(self.libro.disponible)
    
    def test_validacion_isbn(self):
        """Probar validación de ISBN"""
        with self.assertRaises(ValueError):
            Libro("Título", "Autor", "123", 2020)
    
    def test_marcar_disponible(self):
        """Probar cambio de disponibilidad"""
        self.libro.marcar_no_disponible()
        self.assertFalse(self.libro.disponible)
        
        self.libro.marcar_disponible()
        self.assertTrue(self.libro.disponible)
    
    def test_str(self):
        """Probar representación en cadena"""
        resultado = str(self.libro)
        self.assertIn("El Quijote", resultado)
        self.assertIn("Cervantes", resultado)
        self.assertIn("Disponible", resultado)


class TestLibroFisico(unittest.TestCase):
    """Pruebas para la clase LibroFisico"""
    
    def setUp(self):
        """Preparar objetos de prueba"""
        self.libro = LibroFisico(
            "El Quijote", "Cervantes",
            "978-84-376-0494-7", 1605,
            "Literatura", "A", 15
        )
    
    def test_ubicacion(self):
        """Probar propiedad de ubicación"""
        self.assertEqual(self.libro.ubicacion, "Literatura-A-15")
    
    def test_prestamo_exitoso(self):
        """Probar préstamo de libro"""
        self.libro.prestar("Juan Pérez")
        
        self.assertEqual(self.libro.prestado_a, "Juan Pérez")
        self.assertFalse(self.libro.disponible)
        self.assertEqual(len(self.libro.historial_prestamos), 1)
    
    def test_prestamo_libro_no_disponible(self):
        """Probar préstamo de libro no disponible"""
        self.libro.marcar_no_disponible()
        
        with self.assertRaises(RuntimeError):
            self.libro.prestar("Juan Pérez")
    
    def test_devolucion_exitosa(self):
        """Probar devolución de libro"""
        self.libro.prestar("Juan Pérez")
        self.libro.devolver()
        
        self.assertIsNone(self.libro.prestado_a)
        self.assertTrue(self.libro.disponible)
        self.assertIsNotNone(self.libro.historial_prestamos[0]['fecha_devolucion'])
    
    def test_marcar_daño(self):
        """Probar marcado de daño"""
        self.libro.marcar_daño("Páginas rotas", "grave")
        
        self.assertEqual(self.libro.estado_fisico, "grave")
        self.assertFalse(self.libro.disponible)


class TestLibroDigital(unittest.TestCase):
    """Pruebas para la clase LibroDigital"""
    
    def setUp(self):
        """Preparar objetos de prueba"""
        self.libro = LibroDigital(
            "Python para todos", "Guido van Rossum",
            "978-0-13-216993-6", 2020,
            "pdf", 5.2, "https://ejemplo.com/python.pdf"
        )
    
    def test_formato_invalido(self):
        """Probar formato no permitido"""
        with self.assertRaises(ValueError):
            LibroDigital("Título", "Autor", "978-0-13-216993-6", 2020,
                        "txt", 1.0, "https://ejemplo.com")
    
    def test_puede_descargar(self):
        """Probar límite de descargas"""
        self.assertTrue(self.libro.puede_descargar())
        
        # Simular 5 descargas simultáneas
        for _ in range(5):
            self.libro.iniciar_descarga()
        
        self.assertFalse(self.libro.puede_descargar())
    
    def test_iniciar_descarga(self):
        """Probar inicio de descarga"""
        url = self.libro.iniciar_descarga()
        
        self.assertEqual(url, "https://ejemplo.com/python.pdf")
        self.assertEqual(self.libro.descargas_simultaneas, 1)
        self.assertEqual(self.libro.total_descargas, 1)
    
    def test_finalizar_descarga(self):
        """Probar finalización de descarga"""
        self.libro.iniciar_descarga()
        self.libro.finalizar_descarga()
        
        self.assertEqual(self.libro.descargas_simultaneas, 0)
    
    def test_tamaño_formato(self):
        """Probar formato de tamaño"""
        # KB
        libro_pequeño = LibroDigital("T", "A", "978-0-13-216993-6", 2020,
                                     "pdf", 0.5, "url")
        self.assertIn("KB", libro_pequeño.obtener_tamaño_formato())
        
        # MB
        self.assertIn("MB", self.libro.obtener_tamaño_formato())
        
        # GB
        libro_grande = LibroDigital("T", "A", "978-0-13-216993-6", 2020,
                                    "pdf", 1500, "url")
        self.assertIn("GB", libro_grande.obtener_tamaño_formato())


class TestLibroAudio(unittest.TestCase):
    """Pruebas para la clase LibroAudio"""
    
    def setUp(self):
        """Preparar objetos de prueba"""
        self.libro = LibroAudio(
            "Cien años de soledad", "Gabriel García Márquez",
            "978-84-376-0494-8", 1967,
            850, "José Sacristán"
        )
    
    def test_duracion_formato(self):
        """Probar formato de duración"""
        self.assertEqual(self.libro.duracion_formato, "14:10")
    
    def test_reproducir(self):
        """Probar reproducción"""
        resultado = self.libro.reproducir()
        
        self.assertIn("Cien años de soledad", resultado)
        self.assertIn("José Sacristán", resultado)
        self.assertEqual(self.libro.reproducciones, 1)


class TestContadorLibros(unittest.TestCase):
    """Pruebas para el contador de libros"""
    
    def test_contador_incrementa(self):
        """Probar que el contador se incrementa"""
        total_inicial = Libro.total_libros()
        
        Libro("Título 1", "Autor 1", "978-0-13-216993-6", 2020)
        Libro("Título 2", "Autor 2", "978-0-13-216993-7", 2021)
        
        self.assertEqual(Libro.total_libros(), total_inicial + 2)


# Ejecutar pruebas
if __name__ == '__main__':
    unittest.main(verbosity=2)
    
```

`verbosity` controla cuánto detalle muestra en pantalla al ejecutar los tests:

1. verbosity=0: salida mínima (casi silenciosa).
2. verbosity=1: salida normal (aparecen puntos . por test, y F/E si fallan).
3. verbosity=2: salida detallada (muestra el nombre de cada test y si pasa o falla).

### Ejecutar las pruebas

Para ejecutar las pruebas, desde la terminal:

```bash
# Ejecutar todas las pruebas
python -m unittest tests/test_libro.py

# Ejecutar con más detalle
python -m unittest tests/test_libro.py -v

# Ejecutar una clase de prueba específica
python -m unittest tests.test_libro.TestLibroFisico

# Ejecutar un método de prueba específico
python -m unittest tests.test_libro.TestLibroFisico.test_prestamo_exitoso
```

### Cobertura de código

Para medir la cobertura de las pruebas, puedes usar la librería `coverage`:

```bash
# Instalar coverage
pip install coverage

# Ejecutar pruebas con coverage
coverage run -m unittest tests/test_libro.py

# Generar reporte
coverage report

# Generar reporte HTML
coverage html
```

:computer: Actividad 3 y Actividad 4
