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
  - [POLIMORFISMO](#polimorfismo)
    - [Concepto de polimorfismo](#concepto-de-polimorfismo)
    - [Uso de métodos sobrescritos en clases derivadas](#uso-de-métodos-sobrescritos-en-clases-derivadas)
      - [Sobrescritura de métodos](#sobrescritura-de-métodos)
      - [Polimorfismo en acción](#polimorfismo-en-acción)
      - [Ejemplo completo de polimorfismo](#ejemplo-completo-de-polimorfismo)
  - [MÉTODOS ESPECIALES](#métodos-especiales)
    - [¿Qué son los métodos mágicos?](#qué-son-los-métodos-mágicos)
    - [Uso de métodos mágicos como `__init__()`, `__str__()`, y `__repr__()`](#uso-de-métodos-mágicos-como-__init__-__str__-y-__repr__)
      - [El método `__init__()`](#el-método-__init__)
      - [El método `__str__()`](#el-método-__str__)
      - [El método `__repr__()`](#el-método-__repr__)
      - [Otros métodos especiales importantes](#otros-métodos-especiales-importantes)
      - [Ejemplo completo con métodos especiales](#ejemplo-completo-con-métodos-especiales)
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
      - [Ejemplo completo de proyecto estructurado](#ejemplo-completo-de-proyecto-estructurado)
  - [PRUEBAS UNITARIAS PARA CLASES](#pruebas-unitarias-para-clases)
    - [Importancia de probar clases](#importancia-de-probar-clases)
    - [Configuración de pruebas con `unittest`](#configuración-de-pruebas-con-unittest)
      - [Estructura básica de pruebas para clases](#estructura-básica-de-pruebas-para-clases)
      - [Métodos `setUp()` y `tearDown()`](#métodos-setup-y-teardown)
    - [Pruebas de atributos y métodos](#pruebas-de-atributos-y-métodos)
      - [Probar inicialización de objetos](#probar-inicialización-de-objetos)
      - [Probar métodos públicos](#probar-métodos-públicos)
      - [Probar propiedades y validaciones](#probar-propiedades-y-validaciones)
    - [Pruebas de herencia y polimorfismo](#pruebas-de-herencia-y-polimorfismo)
      - [Probar clases derivadas](#probar-clases-derivadas)
      - [Probar comportamiento polimórfico](#probar-comportamiento-polimórfico)
    - [Pruebas de métodos especiales](#pruebas-de-métodos-especiales)
      - [Probar métodos mágicos](#probar-métodos-mágicos)
      - [Probar operadores sobrecargados](#probar-operadores-sobrecargados)
    - [Mocking y pruebas de integración](#mocking-y-pruebas-de-integración)
      - [Usando `unittest.mock`](#usando-unittestmock)
      - [Ejemplo completo de suite de pruebas](#ejemplo-completo-de-suite-de-pruebas)

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

---

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
    # Atributo de clase
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
    
    def cumplir_años(self):
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

# Crear objetos
persona1 = Persona("Juan", "Pérez", 25, "juan@email.com")
persona2 = Persona("María", "García", 17)

# Usar métodos
print(persona1.presentarse())
# Hola, soy Juan Pérez, tengo 25 años y soy mayor de edad

print(persona2.presentarse())
# Hola, soy María García, tengo 17 años y soy menor de edad

# Modificar objetos
persona2.cumplir_años()  # ¡Feliz cumpleaños María! Ahora tienes 18 años
persona1.cambiar_email("juan.perez@email.com")

# Acceder a atributos de clase
print(f"Especie: {Persona.especie}")           # Especie: Homo sapiens
print(f"Población total: {Persona.poblacion_total}")  # Población total: 2
```

---

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
        self.__nombre = nombre
        self.__edad = edad
    
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
print(persona.nombre)     # Juan Pérez (capitalizado automáticamente)
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
    
    # Propiedades de solo lectura
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

# Ejemplo de uso completo
try:
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
    
except ValueError as e:
    print(f"Error de validación: {e}")
except RuntimeError as e:
    print(f"Error de estado: {e}")
```

---

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
        self.nombre = nombre
        self.edad = edad
    
    def hacer_sonido(self):
        return "El animal hace un sonido"
    
    def dormir(self):
        return f"{self.nombre} está durmiendo"
    
    def comer(self):
        return f"{self.nombre} está comiendo"

# Clase derivada
class Perro(Animal):
    def __init__(self, nombre, edad, raza):
        # Llamar al constructor de la clase base
        super().__init__(nombre, edad)
        self.raza = raza
    
    # Sobrescribir método de la clase base
    def hacer_sonido(self):
        return f"{self.nombre} dice: ¡Guau! ¡Guau!"
    
    # Método específico de Perro
    def mover_cola(self):
        return f"{self.nombre} está moviendo la cola alegremente"

# Clase derivada
class Gato(Animal):
    def __init__(self, nombre, edad, color):
        super().__init__(nombre, edad)
        self.color = color
    
    # Sobrescribir método de la clase base
    def hacer_sonido(self):
        return f"{self.nombre} dice: ¡Miau!"
    
    # Método específico de Gato
    def ronronear(self):
        return f"{self.nombre} está ronroneando"

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
    def __init__(self, marca, modelo, año):
        self.marca = marca
        self.modelo = modelo
        self.año = año
        self.kilometraje = 0
        print(f"Vehículo creado: {marca} {modelo} ({año})")
    
    def acelerar(self):
        return "El vehículo está acelerando"

class Coche(Vehiculo):
    def __init__(self, marca, modelo, año, num_puertas):
        # Llamar al constructor de la clase base
        super().__init__(marca, modelo, año)
        self.num_puertas = num_puertas
        print(f"Coche con {num_puertas} puertas creado")
    
    def abrir_puertas(self):
        return f"Abriendo las {self.num_puertas} puertas del coche"

class Motocicleta(Vehiculo):
    def __init__(self, marca, modelo, año, cilindrada):
        super().__init__(marca, modelo, año)
        self.cilindrada = cilindrada
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
        self.nombre = nombre
        self.salario = salario
    
    def trabajar(self):
        return f"{self.nombre} está trabajando"
    
    def calcular_bonus(self):
        return self.salario * 0.1  # 10% de bonus base

class Desarrollador(Empleado):
    def __init__(self, nombre, salario, lenguaje):
        super().__init__(nombre, salario)
        self.lenguaje = lenguaje
    
    def trabajar(self):
        # Llamar al método de la clase base y extenderlo
        trabajo_base = super().trabajar()
        return f"{trabajo_base} programando en {self.lenguaje}"
    
    def calcular_bonus(self):
        # Llamar al método base y modificarlo
        bonus_base = super().calcular_bonus()
        return bonus_base * 1.5  # 50% más de bonus para desarrolladores

class Gerente(Empleado):
    def __init__(self, nombre, salario, equipo_size):
        super().__init__(nombre, salario)
        self.equipo_size = equipo_size
    
    def trabajar(self):
        trabajo_base = super().trabajar()
        return f"{trabajo_base} gestionando un equipo de {self.equipo_size} personas"
    
    def calcular_bonus(self):
        bonus_base = super().calcular_bonus()
        return bonus_base * (1 + self.equipo_size * 0.1)  # Bonus según tamaño del equipo

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
    
    def area(self):
        raise NotImplementedError("Este método debe ser implementado por las clases hijas")
    
    def perimetro(self):
        raise NotImplementedError("Este método debe ser implementado por las clases hijas")
    
    def info(self):
        return f"Forma de color {self.color}"

class Rectangulo(Forma):
    def __init__(self, ancho, alto, color="blanco"):
        super().__init__(color)  # Llamar constructor de la clase base
        self.ancho = ancho
        self.alto = alto
        print(f"Rectángulo de {ancho}x{alto} creado")
    
    def area(self):
        return self.ancho * self.alto
    
    def perimetro(self):
        return 2 * (self.ancho + self.alto)
    
    def info(self):
        info_base = super().info()  # Obtener info de la clase base
        return f"{info_base} - Rectángulo {self.ancho}x{self.alto}"

class Cuadrado(Rectangulo):
    def __init__(self, lado, color="blanco"):
        # Un cuadrado es un rectángulo con lados iguales
        super().__init__(lado, lado, color)
        print(f"Cuadrado de lado {lado} creado")
    
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

---

## POLIMORFISMO

### Concepto de polimorfismo

El **polimorfismo** es la capacidad de objetos de diferentes clases de responder al mismo mensaje (método) de manera específica para cada clase. Permite que el mismo código funcione con objetos de diferentes tipos.

**Tipos de polimorfismo:**
1. **Polimorfismo de herencia**: Diferentes clases hijas implementan el mismo método de manera diferente
2. **Polimorfismo de interfaz**: Diferentes clases implementan los mismos métodos sin necesariamente heredar

### Uso de métodos sobrescritos en clases derivadas

#### Sobrescritura de métodos

La **sobrescritura** (override) ocurre cuando una clase hija redefine un método que existe en la clase padre.

```python
class Instrumento:
    def __init__(self, nombre):
        self.nombre = nombre
    
    def tocar(self):
        return f"Tocando {self.nombre}"
    
    def afinar(self):
        return f"Afinando {self.nombre}"

class Piano(Instrumento):
    def __init__(self, nombre, num_teclas=88):
        super().__init__(nombre)
        self.num_teclas = num_teclas
    
    # Sobrescribir el método tocar
    def tocar(self):
        return f"Presionando las teclas del {self.nombre}"
    
    def pedales(self):
        return f"Usando los pedales del {self.nombre}"

class Guitarra(Instrumento):
    def __init__(self, nombre, num_cuerdas=6):
        super().__init__(nombre)
        self.num_cuerdas = num_cuerdas
    
    # Sobrescribir el método tocar
    def tocar(self):
        return f"Rasguеando las cuerdas de la {self.nombre}"
    
    def cambiar_cuerdas(self):
        return f"Cambiando las cuerdas de la {self.nombre}"

class Bateria(Instrumento):
    def __init__(self, nombre, num_tambores=5):
        super().__init__(nombre)
        self.num_tambores = num_tambores
    
    # Sobrescribir el método tocar
    def tocar(self):
        return f"Golpeando los tambores de la {self.nombre}"
    
    # Sobrescribir el método afinar
    def afinar(self):
        return f"Tensando los parches de la {self.nombre}"

# Crear instrumentos
piano = Piano("Piano de cola")
guitarra = Guitarra("Guitarra clásica")
bateria = Bateria("Batería acústica")

# Métodos sobrescritos - cada uno se comporta diferente
print(piano.tocar())     # Presionando las teclas del Piano de cola
print(guitarra.tocar())  # Rasguеando las cuerdas de la Guitarra clásica
print(bateria.tocar())   # Golpeando los tambores de la Batería acústica

# Método heredado (sin sobrescribir)
print(piano.afinar())    # Afinando Piano de cola
print(guitarra.afinar()) # Afinando Guitarra clásica
print(bateria.afinar())  # Tensando los parches de la Batería acústica
```

#### Polimorfismo en acción

```python
def concierto(instrumentos):
    """Función que demuestra polimorfismo"""
    print("🎵 ¡Comenzando el concierto! 🎵")
    
    for instrumento in instrumentos:
        print(f"- {instrumento.tocar()}")
        print(f"- {instrumento.afinar()}")
        print()

# Lista de diferentes instrumentos
banda = [
    Piano("Piano eléctrico"),
    Guitarra("Guitarra eléctrica", 7),
    Bateria("Batería electrónica"),
    Guitarra("Bajo eléctrico", 4)
]

# El mismo código funciona con diferentes tipos de objetos
concierto(banda)
```

#### Ejemplo completo de polimorfismo

```python
class Figura:
    """Clase base para figuras geométricas"""
    
    def __init__(self, nombre):
        self.nombre = nombre
    
    def area(self):
        raise NotImplementedError("Debe implementarse en la clase derivada")
    
    def perimetro(self):
        raise NotImplementedError("Debe implementarse en la clase derivada")
    
    def descripcion(self):
        return f"{self.nombre}: Área = {self.area():.2f}, Perímetro = {self.perimetro():.2f}"

class Circulo(Figura):
    def __init__(self, radio):
        super().__init__("Círculo")
        self.radio = radio
    
    def area(self):
        return 3.14159 * self.radio ** 2
    
    def perimetro(self):
        return 2 * 3.14159 * self.radio

class Rectangulo(Figura):
    def __init__(self, ancho, alto):
        super().__init__("Rectángulo")
        self.ancho = ancho
        self.alto = alto
    
    def area(self):
        return self.ancho * self.alto
    
    def perimetro(self):
        return 2 * (self.ancho + self.alto)

class Triangulo(Figura):
    def __init__(self, base, altura, lado1, lado2):
        super().__init__("Triángulo")
        self.base = base
        self.altura = altura
        self.lado1 = lado1
        self.lado2 = lado2
    
    def area(self):
        return (self.base * self.altura) / 2
    
    def perimetro(self):
        return self.base + self.lado1 + self.lado2

# Función polimórfica
def analizar_figuras(figuras):
    """Analiza una lista de figuras de diferentes tipos"""
    print("=== ANÁLISIS DE FIGURAS ===")
    
    area_total = 0
    perimetro_total = 0
    
    for figura in figuras:
        print(figura.descripcion())
        area_total += figura.area()
        perimetro_total += figura.perimetro()
    
    print(f"\nÁrea total: {area_total:.2f}")
    print(f"Perímetro total: {perimetro_total:.2f}")

def figura_mas_grande(figuras):
    """Encuentra la figura con mayor área"""
    if not figuras:
        return None
    
    mayor = figuras[0]
    for figura in figuras[1:]:
        if figura.area() > mayor.area():
            mayor = figura
    
    return mayor

# Crear diferentes figuras
figuras = [
    Circulo(5),
    Rectangulo(4, 6),
    Triangulo(8, 6, 7, 9),
    Circulo(3),
    Rectangulo(10, 2)
]

# Polimorfismo: el mismo código funciona con diferentes tipos
analizar_figuras(figuras)

print(f"\nFigura más grande: {figura_mas_grande(figuras).descripcion()}")
```

---

## MÉTODOS ESPECIALES

### ¿Qué son los métodos mágicos?

Los **métodos especiales** (también llamados **métodos mágicos** o **dunder methods**) son métodos predefinidos en Python que comienzan y terminan con doble guion bajo (`__`). Permiten que tus objetos se comporten como tipos incorporados de Python.

**Características:**
- Se llaman automáticamente en situaciones específicas
- Permiten personalizar el comportamiento de operadores
- Hacen que los objetos sean más "pythónicos"
- No se llaman directamente (Python los invoca automáticamente)

### Uso de métodos mágicos como `__init__()`, `__str__()`, y `__repr__()`

#### El método `__init__()`

Ya lo hemos usado extensivamente. Es el constructor que se llama al crear un objeto.

```python
class Punto:
    def __init__(self, x=0, y=0):
        self.x = x
        self.y = y
        print(f"Punto creado en ({x}, {y})")

# Se llama automáticamente al crear el objeto
p = Punto(3, 4)  # Punto creado en (3, 4)
```

#### El método `__str__()`

Define la representación "amigable" del objeto cuando se usa `str()` o `print()`.

```python
class Libro:
    def __init__(self, titulo, autor, paginas):
        self.titulo = titulo
        self.autor = autor
        self.paginas = paginas
    
    def __str__(self):
        return f"{self.titulo} por {self.autor} ({self.paginas} páginas)"

libro = Libro("El Quijote", "Cervantes", 1200)
print(libro)        # El Quijote por Cervantes (1200 páginas)
print(str(libro))   # El Quijote por Cervantes (1200 páginas)
```

#### El método `__repr__()`

Define la representación "técnica" del objeto, idealmente debe ser una expresión válida de Python.

```python
class Punto:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __str__(self):
        return f"Punto({self.x}, {self.y})"
    
    def __repr__(self):
        return f"Punto(x={self.x}, y={self.y})"

p = Punto(3, 4)
print(str(p))   # Punto(3, 4)
print(repr(p))  # Punto(x=3, y=4)
print(p)        # Punto(3, 4) (usa __str__ si existe, sino __repr__)

# En lista, usa __repr__
puntos = [Punto(1, 2), Punto(3, 4)]
print(puntos)   # [Punto(x=1, y=2), Punto(x=3, y=4)]
```

#### Otros métodos especiales importantes

```python
class Producto:
    def __init__(self, nombre, precio):
        self.nombre = nombre
        self.precio = precio
    
    # Representación en string
    def __str__(self):
        return f"{self.nombre} - {self.precio}€"
    
    def __repr__(self):
        return f"Producto('{self.nombre}', {self.precio})"
    
    # Comparaciones
    def __eq__(self, other):
        """Igualdad (==)"""
        if isinstance(other, Producto):
            return self.precio == other.precio
        return False
    
    def __lt__(self, other):
        """Menor que (<)"""
        if isinstance(other, Producto):
            return self.precio < other.precio
        return NotImplemented
    
    def __le__(self, other):
        """Menor o igual (<=)"""
        return self < other or self == other
    
    def __gt__(self, other):
        """Mayor que (>)"""
        if isinstance(other, Producto):
            return self.precio > other.precio
        return NotImplemented
    
    def __ge__(self, other):
        """Mayor o igual (>=)"""
        return self > other or self == other
    
    # Operaciones aritméticas
    def __add__(self, other):
        """Suma (+)"""
        if isinstance(other, Producto):
            return self.precio + other.precio
        elif isinstance(other, (int, float)):
            return Producto(self.nombre, self.precio + other)
        return NotImplemented
    
    def __mul__(self, other):
        """Multiplicación (*)"""
        if isinstance(other, (int, float)):
            return Producto(self.nombre, self.precio * other)
        return NotImplemented
    
    # Longitud y contenido
    def __len__(self):
        """Longitud del nombre del producto"""
        return len(self.nombre)
    
    def __contains__(self, item):
        """Operador 'in' """
        return item.lower() in self.nombre.lower()
    
    # Conversión a bool
    def __bool__(self):
        """Verdadero si tiene precio positivo"""
        return self.precio > 0
    
    # Hacer el objeto iterable
    def __iter__(self):
        """Hacer el producto iterable"""
        return iter([self.nombre, self.precio])

# Ejemplos de uso
producto1 = Producto("Laptop", 800)
producto2 = Producto("Mouse", 25)
producto3 = Producto("Laptop", 800)

print("=== REPRESENTACIONES ===")
print(str(producto1))    # Laptop - 800€
print(repr(producto1))   # Producto('Laptop', 800)

print("\n=== COMPARACIONES ===")
print(producto1 == producto3)  # True (mismo precio)
print(producto1 > producto2)   # True (800 > 25)
print(producto2 < producto1)   # True (25 < 800)

print("\n=== OPERACIONES ARITMÉTICAS ===")
suma = producto1 + producto2   # Suma de precios
print(suma)                    # 825

descuento = producto1 * 0.9    # 10% descuento
print(descuento)               # Laptop - 720.0€

print("\n=== OTROS MÉTODOS ===")
print(len(producto1))          # 6 (longitud de "Laptop")
print("lap" in producto1)      # True
print(bool(producto1))         # True (precio > 0)

# Iteración
for elemento in producto1:
    print(elemento)            # Laptop, luego 800
```

#### Ejemplo completo con métodos especiales

```python
class Vector:
    """Clase Vector con múltiples métodos especiales"""
    
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    # Representaciones
    def __str__(self):
        return f"({self.x}, {self.y})"
    
    def __repr__(self):
        return f"Vector({self.x}, {self.y})"
    
    # Operaciones aritméticas
    def __add__(self, other):
        """Suma de vectores"""
        if isinstance(other, Vector):
            return Vector(self.x + other.x, self.y + other.y)
        return NotImplemented
    
    def __sub__(self, other):
        """Resta de vectores"""
        if isinstance(other, Vector):
            return Vector(self.x - other.x, self.y - other.y)
        return NotImplemented
    
    def __mul__(self, scalar):
        """Multiplicación por escalar"""
        if isinstance(scalar, (int, float)):
            return Vector(self.x * scalar, self.y * scalar)
        return NotImplemented
    
    def __rmul__(self, scalar):
        """Multiplicación por escalar (orden inverso)"""
        return self * scalar
    
    def __truediv__(self, scalar):
        """División por escalar"""
        if isinstance(scalar, (int, float)) and scalar != 0:
            return Vector(self.x / scalar, self.y / scalar)
        return NotImplemented
    
    # Operaciones unarias
    def __neg__(self):
        """Vector negativo"""
        return Vector(-self.x, -self.y)
    
    def __abs__(self):
        """Magnitud del vector"""
        return (self.x ** 2 + self.y ** 2) ** 0.5
    
    # Comparaciones
    def __eq__(self, other):
        """Igualdad"""
        if isinstance(other, Vector):
            return self.x == other.x and self.y == other.y
        return False
    
    def __lt__(self, other):
        """Comparación por magnitud"""
        if isinstance(other, Vector):
            return abs(self) < abs(other)
        return NotImplemented
    
    # Acceso como secuencia
    def __getitem__(self, index):
        """Acceso por índice"""
        if index == 0:
            return self.x
        elif index == 1:
            return self.y
        else:
            raise IndexError("Vector solo tiene índices 0 y 1")
    
    def __setitem__(self, index, value):
        """Asignación por índice"""
        if index == 0:
            self.x = value
        elif index == 1:
            self.y = value
        else:
            raise IndexError("Vector solo tiene índices 0 y 1")
    
    def __len__(self):
        """Longitud del vector (siempre 2)"""
        return 2
    
    def __iter__(self):
        """Hacer iterable"""
        return iter([self.x, self.y])
    
    # Métodos de contexto
    def __enter__(self):
        """Entrada del contexto"""
        print(f"Trabajando con vector {self}")
        return self
    
    def __exit__(self, exc_type, exc_val, exc_tb):
        """Salida del contexto"""
        print(f"Finalizando trabajo con vector {self}")
        return False
    
    # Métodos adicionales
    def magnitud(self):
        return abs(self)
    
    def producto_punto(self, other):
        """Producto punto con otro vector"""
        if isinstance(other, Vector):
            return self.x * other.x + self.y * other.y
        return NotImplemented

# Ejemplo de uso completo
print("=== CREACIÓN Y REPRESENTACIÓN ===")
v1 = Vector(3, 4)
v2 = Vector(1, 2)
print(f"v1: {v1}")       # (3, 4)
print(f"v2: {repr(v2)}")  # Vector(1, 2)

print("\n=== OPERACIONES ARITMÉTICAS ===")
suma = v1 + v2
print(f"v1 + v2 = {suma}")      # (4, 6)

resta = v1 - v2
print(f"v1 - v2 = {resta}")     # (2, 2)

escalar = v1 * 2
print(f"v1 * 2 = {escalar}")    # (6, 8)

division = v1 / 2
print(f"v1 / 2 = {division}")   # (1.5, 2.0)

negativo = -v1
print(f"-v1 = {negativo}")      # (-3, -4)

print("\n=== MAGNITUDES Y COMPARACIONES ===")
print(f"|v1| = {abs(v1)}")      # 5.0
print(f"|v2| = {abs(v2)}")      # 2.23606797749979
print(f"v1 > v2: {v1 > v2}")    # True (mayor magnitud)

print("\n=== ACCESO COMO SECUENCIA ===")
print(f"v1[0] = {v1[0]}")       # 3
print(f"v1[1] = {v1[1]}")       # 4
print(f"len(v1) = {len(v1)}")   # 2

v1[0] = 5
print(f"Después de v1[0] = 5: {v1}")  # (5, 4)

print("\n=== ITERACIÓN ===")
for componente in v1:
    print(f"Componente: {componente}")  # 5, luego 4

print("\n=== CONTEXTO (with) ===")
with Vector(2, 3) as v:
    resultado = v * 4
    print(f"Resultado en contexto: {resultado}")

print("\n=== MÉTODOS ADICIONALES ===")
print(f"Magnitud de v1: {v1.magnitud()}")
print(f"Producto punto v1·v2: {v1.producto_punto(v2)}")

---

## MÓDULOS Y PAQUETES EN POO

A medida que nuestros programas orientados a objetos crecen, es fundamental saber cómo organizar las clases de manera eficiente. Los **módulos** y **paquetes** nos permiten estructurar el código de forma modular, reutilizable y mantenible.

### Organización de clases en módulos

#### ¿Por qué usar módulos?

Los módulos ofrecen varios beneficios importantes:

- **Reutilización**: Las clases pueden usarse en múltiples programas
- **Organización**: Código más limpio y estructurado
- **Mantenimiento**: Fácil localizar y modificar código específico
- **Colaboración**: Diferentes desarrolladores pueden trabajar en módulos separados
- **Namespace**: Evita conflictos de nombres entre clases

#### Crear un módulo con clases

Un **módulo** es simplemente un archivo `.py` que contiene definiciones de clases, funciones y variables.

**Ejemplo: Archivo `vehiculos.py`**

```python
# vehiculos.py
"""
Módulo que contiene clases relacionadas con vehículos
"""

class Vehiculo:
    """Clase base para todos los vehículos"""
    
    def __init__(self, marca, modelo, año):
        self.marca = marca
        self.modelo = modelo
        self.año = año
        self.velocidad = 0
    
    def acelerar(self, incremento=10):
        """Aumenta la velocidad del vehículo"""
        self.velocidad += incremento
        return f"{self.marca} {self.modelo} acelera a {self.velocidad} km/h"
    
    def frenar(self, decremento=10):
        """Reduce la velocidad del vehículo"""
        self.velocidad = max(0, self.velocidad - decremento)
        return f"{self.marca} {self.modelo} frena a {self.velocidad} km/h"
    
    def __str__(self):
        return f"{self.marca} {self.modelo} ({self.año})"


class Coche(Vehiculo):
    """Clase que representa un coche"""
    
    def __init__(self, marca, modelo, año, puertas=4):
        super().__init__(marca, modelo, año)
        self.puertas = puertas
        self.maletero_abierto = False
    
    def abrir_maletero(self):
        """Abre el maletero del coche"""
        self.maletero_abierto = True
        return f"Maletero de {self} abierto"
    
    def cerrar_maletero(self):
        """Cierra el maletero del coche"""
        self.maletero_abierto = False
        return f"Maletero de {self} cerrado"


class Motocicleta(Vehiculo):
    """Clase que representa una motocicleta"""
    
    def __init__(self, marca, modelo, año, cilindrada):
        super().__init__(marca, modelo, año)
        self.cilindrada = cilindrada
        self.caballito = False
    
    def hacer_caballito(self):
        """Hace un caballito con la motocicleta"""
        if self.velocidad > 0:
            self.caballito = True
            return f"¡{self} haciendo caballito!"
        return "Necesitas velocidad para hacer caballito"
    
    def parar_caballito(self):
        """Para el caballito"""
        self.caballito = False
        return f"{self} vuelve a las dos ruedas"


# Variables del módulo
VEHICULOS_CREADOS = 0

def crear_vehiculo(tipo, marca, modelo, año, **kwargs):
    """Función factory para crear vehículos"""
    global VEHICULOS_CREADOS
    VEHICULOS_CREADOS += 1
    
    if tipo.lower() == 'coche':
        return Coche(marca, modelo, año, kwargs.get('puertas', 4))
    elif tipo.lower() == 'motocicleta':
        return Motocicleta(marca, modelo, año, kwargs.get('cilindrada', 125))
    else:
        return Vehiculo(marca, modelo, año)
```

#### Importar clases desde módulos

**Archivo principal: `main.py`**

```python
# main.py

# 1. Importar todo el módulo
import vehiculos

# Usar clases con notación de punto
mi_coche = vehiculos.Coche("Toyota", "Corolla", 2023)
print(mi_coche.acelerar())

# 2. Importar clases específicas
from vehiculos import Coche, Motocicleta, crear_vehiculo

# Usar clases directamente
mi_moto = Motocicleta("Honda", "CBR", 2022, 600)
print(mi_moto.acelerar(20))
print(mi_moto.hacer_caballito())

# 3. Importar con alias
from vehiculos import Vehiculo as VehiculoBase

# Usar con alias
vehiculo_generico = VehiculoBase("Ford", "Transit", 2021)

# 4. Usar función factory
nuevo_coche = crear_vehiculo("coche", "BMW", "X3", 2023, puertas=5)
print(f"Vehículos creados hasta ahora: {vehiculos.VEHICULOS_CREADOS}")
```

### Creación y estructura de paquetes

#### ¿Qué es un paquete?

Un **paquete** es una colección de módulos organizados en directorios. Permite agrupar módulos relacionados bajo un nombre común.

#### El archivo `__init__.py`

Este archivo especial convierte un directorio en un paquete Python. Puede estar vacío o contener código de inicialización.

#### Estructura de directorios

```
mi_proyecto/
├── main.py
└── transporte/                 # Paquete principal
    ├── __init__.py
    ├── vehiculos/              # Subpaquete
    │   ├── __init__.py
    │   ├── terrestres.py
    │   ├── aereos.py
    │   └── acuaticos.py
    ├── personas/               # Subpaquete
    │   ├── __init__.py
    │   ├── conductores.py
    │   └── pasajeros.py
    └── utils/                  # Subpaquete de utilidades
        ├── __init__.py
        └── validaciones.py
```

**Archivo `transporte/__init__.py`**

```python
# transporte/__init__.py
"""
Paquete de transporte
Contiene clases y funciones para manejar diferentes tipos de transporte
"""

# Importar clases principales para acceso fácil
from .vehiculos.terrestres import Coche, Motocicleta, Bicicleta
from .vehiculos.aereos import Avion, Helicoptero
from .personas.conductores import Conductor, Piloto

# Metadata del paquete
__version__ = "1.0.0"
__author__ = "Tu Nombre"

# Lista de elementos públicos
__all__ = [
    'Coche', 'Motocicleta', 'Bicicleta',
    'Avion', 'Helicoptero',
    'Conductor', 'Piloto'
]

print(f"Paquete transporte v{__version__} cargado")
```

**Archivo `transporte/vehiculos/__init__.py`**

```python
# transporte/vehiculos/__init__.py
"""Subpaquete de vehículos"""

from .terrestres import Coche, Motocicleta
from .aereos import Avion
from .acuaticos import Barco

__all__ = ['Coche', 'Motocicleta', 'Avion', 'Barco']
```

**Archivo `transporte/vehiculos/terrestres.py`**

```python
# transporte/vehiculos/terrestres.py
"""Vehículos terrestres"""

from ..utils.validaciones import validar_año

class VehiculoTerrestre:
    """Clase base para vehículos terrestres"""
    
    def __init__(self, marca, modelo, año):
        self.marca = marca
        self.modelo = modelo
        self.año = validar_año(año)
        self.velocidad = 0
    
    def acelerar(self, incremento=10):
        self.velocidad += incremento
        return f"Acelerando a {self.velocidad} km/h"


class Coche(VehiculoTerrestre):
    """Clase que representa un coche"""
    
    def __init__(self, marca, modelo, año, puertas=4):
        super().__init__(marca, modelo, año)
        self.puertas = puertas
    
    def tocar_claxon(self):
        return f"¡BEEP BEEP! - {self.marca} {self.modelo}"


class Motocicleta(VehiculoTerrestre):
    """Clase que representa una motocicleta"""
    
    def __init__(self, marca, modelo, año, cilindrada):
        super().__init__(marca, modelo, año)
        self.cilindrada = cilindrada
    
    def rugir_motor(self):
        return f"¡BRUM BRUM! - {self.marca} {self.modelo} {self.cilindrada}cc"


class Bicicleta(VehiculoTerrestre):
    """Clase que representa una bicicleta"""
    
    def __init__(self, marca, modelo, tipo="urbana"):
        # Las bicicletas no tienen año de fabricación específico
        super().__init__(marca, modelo, 2023)
        self.tipo = tipo
        self.velocidad_maxima = 30  # km/h
    
    def acelerar(self, incremento=5):
        self.velocidad = min(self.velocidad + incremento, self.velocidad_maxima)
        return f"Pedaleando a {self.velocidad} km/h"
```

**Archivo `transporte/utils/validaciones.py`**

```python
# transporte/utils/validaciones.py
"""Utilidades de validación"""

from datetime import datetime

def validar_año(año):
    """Valida que el año sea razonable"""
    año_actual = datetime.now().year
    
    if not isinstance(año, int):
        raise ValueError("El año debe ser un número entero")
    
    if año < 1900 or año > año_actual + 1:
        raise ValueError(f"Año inválido: {año}. Debe estar entre 1900 y {año_actual + 1}")
    
    return año

def validar_velocidad(velocidad, velocidad_maxima=200):
    """Valida que la velocidad sea razonable"""
    if velocidad < 0:
        return 0
    elif velocidad > velocidad_maxima:
        return velocidad_maxima
    return velocidad
```

### Importación avanzada de clases

#### Diferentes formas de importar

**Archivo `main.py`**

```python
# main.py - Ejemplos de importación

# 1. Importar paquete completo
import transporte
mi_coche = transporte.Coche("Toyota", "Prius", 2023)

# 2. Importar subpaquete
import transporte.vehiculos
mi_moto = transporte.vehiculos.Motocicleta("Honda", "CBR", 2022, 600)

# 3. Importar módulo específico
import transporte.vehiculos.terrestres
bici = transporte.vehiculos.terrestres.Bicicleta("Trek", "FX", "híbrida")

# 4. Importar clases específicas del paquete
from transporte import Coche, Conductor

# 5. Importar desde subpaquete
from transporte.vehiculos.terrestres import Motocicleta, Bicicleta

# 6. Importar desde módulo específico
from transporte.vehiculos.aereos import Avion

# 7. Importar todo (no recomendado para paquetes grandes)
from transporte.vehiculos.terrestres import *
```

#### Alias y nombres personalizados

```python
# Usar alias para nombres largos o conflictos
from transporte.vehiculos.terrestres import Coche as CocheTerrestre
from transporte.vehiculos.acuaticos import Coche as CocheAnfibio  # Si existiera

# Alias para paquetes
import transporte.vehiculos.terrestres as terrestres
import transporte.vehiculos.aereos as aereos

# Crear instancias
mi_coche = terrestres.Coche("BMW", "X5", 2023)
mi_avion = aereos.Avion("Boeing", "747", 1995)
```

#### Importación condicional

```python
# Importación condicional según disponibilidad
try:
    from transporte.vehiculos.aereos import AvionElectrico
    AEREO_ELECTRICO_DISPONIBLE = True
except ImportError:
    AEREO_ELECTRICO_DISPONIBLE = False
    print("Avión eléctrico no disponible en esta versión")

# Importación según configuración
MODO_DESARROLLO = True

if MODO_DESARROLLO:
    from transporte.utils.debug import DebugVehiculo as Vehiculo
else:
    from transporte.vehiculos.terrestres import Coche as Vehiculo
```

### Buenas prácticas y organización

#### Convenciones de nomenclatura

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

#### Ejemplo completo de proyecto estructurado

**Proyecto: Sistema de Biblioteca**

```
biblioteca/
├── main.py
├── config.py
├── models/
│   ├── __init__.py
│   ├── libro.py
│   ├── usuario.py
│   └── prestamo.py
├── services/
│   ├── __init__.py
│   ├── gestion_libros.py
│   ├── gestion_usuarios.py
│   └── gestion_prestamos.py
├── utils/
│   ├── __init__.py
│   ├── validaciones.py
│   └── formateo.py
└── interfaces/
    ├── __init__.py
    └── cli.py
```

**Archivo `models/__init__.py`**

```python
# models/__init__.py
"""Modelos de datos del sistema de biblioteca"""

from .libro import Libro, LibroDigital, LibroFisico
from .usuario import Usuario, Estudiante, Profesor
from .prestamo import Prestamo, PrestamoDigital

__version__ = "1.0.0"

__all__ = [
    'Libro', 'LibroDigital', 'LibroFisico',
    'Usuario', 'Estudiante', 'Profesor', 
    'Prestamo', 'PrestamoDigital'
]

# Configuración global para todos los modelos
CONFIGURACION = {
    'dias_prestamo_default': 14,
    'max_renovaciones': 2,
    'multa_por_dia': 0.50
}
```

**Archivo `models/libro.py`**

```python
# models/libro.py
"""Modelos relacionados con libros"""

from datetime import datetime
from ..utils.validaciones import validar_isbn

class Libro:
    """Clase base para todos los tipos de libros"""
    
    def __init__(self, titulo, autor, isbn, año_publicacion):
        self.titulo = titulo
        self.autor = autor
        self.isbn = validar_isbn(isbn)
        self.año_publicacion = año_publicacion
        self.disponible = True
        self.fecha_creacion = datetime.now()
    
    def __str__(self):
        return f"{self.titulo} por {self.autor} ({self.año_publicacion})"
    
    def __repr__(self):
        return f"Libro('{self.titulo}', '{self.autor}', '{self.isbn}')"


class LibroFisico(Libro):
    """Libro físico con ubicación en biblioteca"""
    
    def __init__(self, titulo, autor, isbn, año_publicacion, 
                 seccion, estante, posicion):
        super().__init__(titulo, autor, isbn, año_publicacion)
        self.seccion = seccion
        self.estante = estante  
        self.posicion = posicion
        self.estado_fisico = "bueno"  # bueno, regular, malo
    
    @property
    def ubicacion(self):
        return f"{self.seccion}-{self.estante}-{self.posicion}"
    
    def marcar_daño(self, descripcion):
        """Marca el libro como dañado"""
        self.estado_fisico = "malo"
        self.descripcion_daño = descripcion
        self.disponible = False


class LibroDigital(Libro):
    """Libro en formato digital"""
    
    def __init__(self, titulo, autor, isbn, año_publicacion, 
                 formato, tamaño_mb, url_descarga):
        super().__init__(titulo, autor, isbn, año_publicacion)
        self.formato = formato  # pdf, epub, mobi
        self.tamaño_mb = tamaño_mb
        self.url_descarga = url_descarga
        self.descargas_simultaneas = 0
        self.max_descargas_simultaneas = 5
    
    def puede_descargar(self):
        """Verifica si se puede descargar el libro"""
        return self.descargas_simultaneas < self.max_descargas_simultaneas
```

**Archivo `main.py`**

```python
# main.py
"""Aplicación principal del sistema de biblioteca"""

# Importar desde nuestros paquetes
from models import Libro, LibroFisico, Usuario, Estudiante
from services import GestionLibros, GestionUsuarios, GestionPrestamos
from interfaces.cli import InterfazCLI
from config import CONFIGURACION_SISTEMA

def main():
    """Función principal de la aplicación"""
    
    print("=== Sistema de Gestión de Biblioteca ===")
    print(f"Versión: {CONFIGURACION_SISTEMA['version']}")
    
    # Inicializar servicios
    gestion_libros = GestionLibros()
    gestion_usuarios = GestionUsuarios()
    gestion_prestamos = GestionPrestamos()
    
    # Crear algunos datos de ejemplo
    libro1 = LibroFisico(
        "El Quijote", "Miguel de Cervantes", 
        "978-84-376-0494-7", 1605,
        "Literatura", "A", 15
    )
    
    estudiante1 = Estudiante(
        "Ana García", "ana@universidad.edu",
        "12345678A", "Ingeniería Informática"
    )
    
    # Registrar en el sistema
    gestion_libros.agregar_libro(libro1)
    gestion_usuarios.registrar_usuario(estudiante1)
    
    # Iniciar interfaz de usuario
    interfaz = InterfazCLI(gestion_libros, gestion_usuarios, gestion_prestamos)
    interfaz.ejecutar()

if __name__ == "__main__":
    main()
```

**Ventajas de esta organización:**

1. **Separación clara** de responsabilidades
2. **Fácil mantenimiento** y extensión
3. **Reutilización** de componentes
4. **Pruebas unitarias** más sencillas
5. **Colaboración** eficiente en equipo
6. **Escalabilidad** del proyecto

Los módulos y paquetes son fundamentales para crear aplicaciones POO robustas y mantenibles. Permiten organizar el código de manera lógica, facilitando tanto el desarrollo como el mantenimiento a largo plazo.

---

## PRUEBAS UNITARIAS PARA CLASES

### Importancia de probar clases

Las **pruebas unitarias** son esenciales al trabajar con clases porque:

- **Verifican el comportamiento**: Aseguran que los métodos funcionan correctamente
- **Validan la inicialización**: Comprueban que los objetos se crean correctamente
- **Detectan regresiones**: Evitan que cambios futuros rompan funcionalidad existente
- **Documentan el uso**: Muestran cómo usar la clase correctamente
- **Facilitan refactoring**: Permiten cambiar implementación con confianza

### Configuración de pruebas con `unittest`

#### Estructura básica de pruebas para clases

```python
import unittest

# Clase a probar
class Calculadora:
    def sumar(self, a, b):
        return a + b
    
    def dividir(self, a, b):
        if b == 0:
            raise ValueError("No se puede dividir por cero")
        return a / b

# Clase de pruebas
class TestCalculadora(unittest.TestCase):
    
    def test_sumar_numeros_positivos(self):
        """Probar suma de números positivos"""
        calc = Calculadora()
        resultado = calc.sumar(2, 3)
        self.assertEqual(resultado, 5)
    
    def test_dividir_numeros_validos(self):
        """Probar división de números válidos"""
        calc = Calculadora()
        resultado = calc.dividir(10, 2)
        self.assertEqual(resultado, 5.0)
    
    def test_dividir_por_cero_lanza_excepcion(self):
        """Probar que dividir por cero lanza excepción"""
        calc = Calculadora()
        with self.assertRaises(ValueError):
            calc.dividir(10, 0)

# Ejecutar pruebas
if __name__ == '__main__':
    unittest.main()
```

#### Métodos `setUp()` y `tearDown()`

```python
class TestCuentaBancaria(unittest.TestCase):
    
    def setUp(self):
        """Se ejecuta antes de cada prueba"""
        self.cuenta = CuentaBancaria("Juan Pérez", 1000)
        print("Configurando cuenta para prueba")
    
    def tearDown(self):
        """Se ejecuta después de cada prueba"""
        print("Limpiando después de la prueba")
        # Aquí podrías limpiar archivos, cerrar conexiones, etc.
    
    def test_saldo_inicial(self):
        """Probar saldo inicial"""
        self.assertEqual(self.cuenta.consultar_saldo(), 1000)
    
    def test_deposito_valido(self):
        """Probar depósito válido"""
        self.cuenta.depositar(200)
        self.assertEqual(self.cuenta.consultar_saldo(), 1200)
    
    def test_retiro_valido(self):
        """Probar retiro válido"""
        self.cuenta.retirar(300)
        self.assertEqual(self.cuenta.consultar_saldo(), 700)
```

### Pruebas de atributos y métodos

#### Probar inicialización de objetos

```python
class Persona:
    def __init__(self, nombre, edad, email=""):
        if not nombre or not isinstance(nombre, str):
            raise ValueError("Nombre debe ser una cadena no vacía")
        if not isinstance(edad, int) or edad < 0:
            raise ValueError("Edad debe ser un entero no negativo")
        
        self.nombre = nombre
        self.edad = edad
        self.email = email

class TestPersona(unittest.TestCase):
    
    def test_inicializacion_correcta(self):
        """Probar inicialización con datos válidos"""
        persona = Persona("Ana", 25, "ana@email.com")
        
        self.assertEqual(persona.nombre, "Ana")
        self.assertEqual(persona.edad, 25)
        self.assertEqual(persona.email, "ana@email.com")
    
    def test_inicializacion_sin_email(self):
        """Probar inicialización sin email (opcional)"""
        persona = Persona("Carlos", 30)
        
        self.assertEqual(persona.nombre, "Carlos")
        self.assertEqual(persona.edad, 30)
        self.assertEqual(persona.email, "")
    
    def test_nombre_invalido_lanza_excepcion(self):
        """Probar que nombre inválido lanza excepción"""
        with self.assertRaises(ValueError):
            Persona("", 25)
        
        with self.assertRaises(ValueError):
            Persona(123, 25)
    
    def test_edad_invalida_lanza_excepcion(self):
        """Probar que edad inválida lanza excepción"""
        with self.assertRaises(ValueError):
            Persona("Juan", -5)
        
        with self.assertRaises(ValueError):
            Persona("Juan", "veinticinco")
    
    def test_tipo_de_instancia(self):
        """Probar que el objeto es del tipo correcto"""
        persona = Persona("María", 28)
        self.assertIsInstance(persona, Persona)
```

#### Probar métodos públicos

```python
class Rectangulo:
    def __init__(self, ancho, alto):
        self.ancho = ancho
        self.alto = alto
    
    def area(self):
        return self.ancho * self.alto
    
    def perimetro(self):
        return 2 * (self.ancho + self.alto)
    
    def es_cuadrado(self):
        return self.ancho == self.alto
    
    def redimensionar(self, factor):
        self.ancho *= factor
        self.alto *= factor

class TestRectangulo(unittest.TestCase):
    
    def setUp(self):
        self.rect = Rectangulo(4, 6)
    
    def test_area_calculo_correcto(self):
        """Probar cálculo del área"""
        self.assertEqual(self.rect.area(), 24)
    
    def test_perimetro_calculo_correcto(self):
        """Probar cálculo del perímetro"""
        self.assertEqual(self.rect.perimetro(), 20)
    
    def test_es_cuadrado_false(self):
        """Probar detección de no-cuadrado"""
        self.assertFalse(self.rect.es_cuadrado())
    
    def test_es_cuadrado_true(self):
        """Probar detección de cuadrado"""
        cuadrado = Rectangulo(5, 5)
        self.assertTrue(cuadrado.es_cuadrado())
    
    def test_redimensionar(self):
        """Probar redimensionamiento"""
        self.rect.redimensionar(2)
        self.assertEqual(self.rect.ancho, 8)
        self.assertEqual(self.rect.alto, 12)
        self.assertEqual(self.rect.area(), 96)
    
    def test_redimensionar_con_decimal(self):
        """Probar redimensionamiento con factor decimal"""
        self.rect.redimensionar(0.5)
        self.assertEqual(self.rect.ancho, 2.0)
        self.assertEqual(self.rect.alto, 3.0)
```

#### Probar propiedades y validaciones

```python
class Temperatura:
    def __init__(self, celsius=0):
        self._celsius = None
        self.celsius = celsius  # Usar el setter
    
    @property
    def celsius(self):
        return self._celsius
    
    @celsius.setter
    def celsius(self, valor):
        if valor < -273.15:
            raise ValueError("Temperatura no puede ser menor que el cero absoluto")
        self._celsius = valor
    
    @property
    def fahrenheit(self):
        return (self._celsius * 9/5) + 32
    
    @property
    def kelvin(self):
        return self._celsius + 273.15

class TestTemperatura(unittest.TestCase):
    
    def test_celsius_valido(self):
        """Probar asignación de temperatura válida"""
        temp = Temperatura(25)
        self.assertEqual(temp.celsius, 25)
    
    def test_celsius_cero_absoluto_invalido(self):
        """Probar que temperatura menor a cero absoluto es inválida"""
        with self.assertRaises(ValueError):
            Temperatura(-300)
    
    def test_setter_celsius_invalido(self):
        """Probar setter con valor inválido"""
        temp = Temperatura(20)
        with self.assertRaises(ValueError):
            temp.celsius = -300
    
    def test_conversion_fahrenheit(self):
        """Probar conversión a Fahrenheit"""
        temp = Temperatura(0)
        self.assertEqual(temp.fahrenheit, 32)
        
        temp.celsius = 100
        self.assertEqual(temp.fahrenheit, 212)
    
    def test_conversion_kelvin(self):
        """Probar conversión a Kelvin"""
        temp = Temperatura(0)
        self.assertEqual(temp.kelvin, 273.15)
        
        temp.celsius = -273.15  # Cero absoluto
        self.assertEqual(temp.kelvin, 0)
    
    def test_propiedad_solo_lectura(self):
        """Probar que Fahrenheit y Kelvin son solo lectura"""
        temp = Temperatura(25)
        
        # Estas asignaciones no deberían funcionar
        with self.assertRaises(AttributeError):
            temp.fahrenheit = 100
        
        with self.assertRaises(AttributeError):
            temp.kelvin = 300
```

### Pruebas de herencia y polimorfismo

#### Probar clases derivadas

```python
class Animal:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
    
    def hacer_sonido(self):
        return "Sonido genérico"
    
    def dormir(self):
        return f"{self.nombre} está durmiendo"

class Perro(Animal):
    def __init__(self, nombre, edad, raza):
        super().__init__(nombre, edad)
        self.raza = raza
    
    def hacer_sonido(self):
        return "¡Guau!"
    
    def mover_cola(self):
        return f"{self.nombre} mueve la cola"

class TestHerencia(unittest.TestCase):
    
    def setUp(self):
        self.animal = Animal("Genérico", 5)
        self.perro = Perro("Buddy", 3, "Labrador")
    
    def test_herencia_correcta(self):
        """Probar que la herencia funciona correctamente"""
        # El perro es una instancia de Animal
        self.assertIsInstance(self.perro, Animal)
        self.assertIsInstance(self.perro, Perro)
        
        # El animal no es una instancia de Perro
        self.assertIsInstance(self.animal, Animal)
        self.assertNotIsInstance(self.animal, Perro)
    
    def test_atributos_heredados(self):
        """Probar que los atributos se heredan correctamente"""
        self.assertEqual(self.perro.nombre, "Buddy")
        self.assertEqual(self.perro.edad, 3)
        self.assertEqual(self.perro.raza, "Labrador")
    
    def test_metodos_heredados(self):
        """Probar que los métodos se heredan correctamente"""
        # Método heredado sin sobrescribir
        self.assertEqual(self.perro.dormir(), "Buddy está durmiendo")
    
    def test_sobrescritura_metodos(self):
        """Probar que la sobrescritura funciona"""
        # Método sobrescrito
        self.assertEqual(self.animal.hacer_sonido(), "Sonido genérico")
        self.assertEqual(self.perro.hacer_sonido(), "¡Guau!")
    
    def test_metodos_especificos_clase_derivada(self):
        """Probar métodos específicos de la clase derivada"""
        self.assertEqual(self.perro.mover_cola(), "Buddy mueve la cola")
        
        # El animal no tiene este método
        with self.assertRaises(AttributeError):
            self.animal.mover_cola()
```

#### Probar comportamiento polimórfico

```python
class Forma:
    def area(self):
        raise NotImplementedError
    
    def descripcion(self):
        return f"Área: {self.area()}"

class Circulo(Forma):
    def __init__(self, radio):
        self.radio = radio
    
    def area(self):
        return 3.14159 * self.radio ** 2

class Cuadrado(Forma):
    def __init__(self, lado):
        self.lado = lado
    
    def area(self):
        return self.lado ** 2

def calcular_area_total(formas):
    """Función polimórfica"""
    return sum(forma.area() for forma in formas)

class TestPolimorfismo(unittest.TestCase):
    
    def setUp(self):
        self.circulo = Circulo(5)
        self.cuadrado = Cuadrado(4)
        self.formas = [self.circulo, self.cuadrado]
    
    def test_polimorfismo_area(self):
        """Probar que diferentes formas calculan área correctamente"""
        self.assertAlmostEqual(self.circulo.area(), 78.54, places=2)
        self.assertEqual(self.cuadrado.area(), 16)
    
    def test_funcion_polimorfica(self):
        """Probar función que trabaja con diferentes tipos"""
        area_total = calcular_area_total(self.formas)
        area_esperada = self.circulo.area() + self.cuadrado.area()
        self.assertAlmostEqual(area_total, area_esperada, places=2)
    
    def test_comportamiento_uniforme(self):
        """Probar que todas las formas responden al mismo mensaje"""
        for forma in self.formas:
            # Todas las formas pueden calcular su área
            area = forma.area()
            self.assertIsInstance(area, (int, float))
            self.assertGreater(area, 0)
            
            # Todas las formas pueden dar su descripción
            desc = forma.descripcion()
            self.assertIsInstance(desc, str)
            self.assertIn("Área:", desc)
```

### Pruebas de métodos especiales

#### Probar métodos mágicos

```python
class Punto:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __str__(self):
        return f"({self.x}, {self.y})"
    
    def __repr__(self):
        return f"Punto({self.x}, {self.y})"
    
    def __eq__(self, other):
        if isinstance(other, Punto):
            return self.x == other.x and self.y == other.y
        return False
    
    def __add__(self, other):
        if isinstance(other, Punto):
            return Punto(self.x + other.x, self.y + other.y)
        return NotImplemented
    
    def __len__(self):
        return 2
    
    def __getitem__(self, index):
        if index == 0:
            return self.x
        elif index == 1:
            return self.y
        else:
            raise IndexError("Punto solo tiene índices 0 y 1")

class TestMetodosEspeciales(unittest.TestCase):
    
    def setUp(self):
        self.p1 = Punto(3, 4)
        self.p2 = Punto(1, 2)
        self.p3 = Punto(3, 4)  # Igual a p1
    
    def test_str_representation(self):
        """Probar representación con __str__"""
        self.assertEqual(str(self.p1), "(3, 4)")
    
    def test_repr_representation(self):
        """Probar representación con __repr__"""
        self.assertEqual(repr(self.p1), "Punto(3, 4)")
    
    def test_equality(self):
        """Probar igualdad con __eq__"""
        self.assertEqual(self.p1, self.p3)  # Puntos iguales
        self.assertNotEqual(self.p1, self.p2)  # Puntos diferentes
        
        # Comparar con tipo diferente
        self.assertNotEqual(self.p1, (3, 4))
        self.assertNotEqual(self.p1, "punto")
    
    def test_addition(self):
        """Probar suma con __add__"""
        resultado = self.p1 + self.p2
        self.assertEqual(resultado.x, 4)
        self.assertEqual(resultado.y, 6)
        self.assertIsInstance(resultado, Punto)
    
    def test_length(self):
        """Probar longitud con __len__"""
        self.assertEqual(len(self.p1), 2)
    
    def test_indexing(self):
        """Probar acceso por índice con __getitem__"""
        self.assertEqual(self.p1[0], 3)  # x
        self.assertEqual(self.p1[1], 4)  # y
        
        # Índice inválido
        with self.assertRaises(IndexError):
            _ = self.p1[2]
```

#### Probar operadores sobrecargados

```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)
    
    def __sub__(self, other):
        return Vector(self.x - other.x, self.y - other.y)
    
    def __mul__(self, scalar):
        return Vector(self.x * scalar, self.y * scalar)
    
    def __eq__(self, other):
        return self.x == other.x and self.y == other.y
    
    def __lt__(self, other):
        return self.magnitud() < other.magnitud()
    
    def magnitud(self):
        return (self.x ** 2 + self.y ** 2) ** 0.5

class TestOperadoresSobrecargados(unittest.TestCase):
    
    def setUp(self):
        self.v1 = Vector(3, 4)
        self.v2 = Vector(1, 2)
    
    def test_suma_vectores(self):
        """Probar suma de vectores"""
        resultado = self.v1 + self.v2
        self.assertEqual(resultado.x, 4)
        self.assertEqual(resultado.y, 6)
    
    def test_resta_vectores(self):
        """Probar resta de vectores"""
        resultado = self.v1 - self.v2
        self.assertEqual(resultado.x, 2)
        self.assertEqual(resultado.y, 2)
    
    def test_multiplicacion_escalar(self):
        """Probar multiplicación por escalar"""
        resultado = self.v1 * 2
        self.assertEqual(resultado.x, 6)
        self.assertEqual(resultado.y, 8)
    
    def test_comparacion_magnitud(self):
        """Probar comparación por magnitud"""
        v_pequeño = Vector(1, 1)
        v_grande = Vector(5, 5)
        
        self.assertTrue(v_pequeño < v_grande)
        self.assertFalse(v_grande < v_pequeño)
    
    def test_operadores_encadenados(self):
        """Probar operaciones encadenadas"""
        resultado = (self.v1 + self.v2) * 2
        self.assertEqual(resultado.x, 8)  # (3+1)*2
        self.assertEqual(resultado.y, 12)  # (4+2)*2
```

### Mocking y pruebas de integración

#### Usando `unittest.mock`

```python
from unittest.mock import Mock, patch, MagicMock
import requests  # Ejemplo con biblioteca externa

class ServicioWeb:
    def __init__(self, base_url):
        self.base_url = base_url
    
    def obtener_datos(self, endpoint):
        """Método que hace una llamada HTTP"""
        response = requests.get(f"{self.base_url}/{endpoint}")
        if response.status_code == 200:
            return response.json()
        else:
            raise Exception(f"Error HTTP: {response.status_code}")

class TestServicioWebConMock(unittest.TestCase):
    
    def setUp(self):
        self.servicio = ServicioWeb("https://api.ejemplo.com")
    
    @patch('requests.get')
    def test_obtener_datos_exitoso(self, mock_get):
        """Probar obtención exitosa de datos usando mock"""
        # Configurar el mock
        mock_response = Mock()
        mock_response.status_code = 200
        mock_response.json.return_value = {"data": "test"}
        mock_get.return_value = mock_response
        
        # Ejecutar el método
        resultado = self.servicio.obtener_datos("usuarios")
        
        # Verificaciones
        self.assertEqual(resultado, {"data": "test"})
        mock_get.assert_called_once_with("https://api.ejemplo.com/usuarios")
    
    @patch('requests.get')
    def test_obtener_datos_error_http(self, mock_get):
        """Probar manejo de errores HTTP"""
        # Configurar el mock para error
        mock_response = Mock()
        mock_response.status_code = 404
        mock_get.return_value = mock_response
        
        # Verificar que se lanza la excepción
        with self.assertRaises(Exception) as context:
            self.servicio.obtener_datos("no-existe")
        
        self.assertIn("Error HTTP: 404", str(context.exception))

class RepositorioUsuarios:
    def __init__(self, servicio_web):
        self.servicio = servicio_web
    
    def buscar_usuario(self, user_id):
        """Buscar usuario usando el servicio web"""
        datos = self.servicio.obtener_datos(f"usuarios/{user_id}")
        return {
            'id': datos['id'],
            'nombre': datos['nombre'],
            'email': datos['email']
        }

class TestRepositorioConMock(unittest.TestCase):
    
    def setUp(self):
        # Crear un mock del servicio
        self.mock_servicio = Mock(spec=ServicioWeb)
        self.repositorio = RepositorioUsuarios(self.mock_servicio)
    
    def test_buscar_usuario(self):
        """Probar búsqueda de usuario con servicio mockeado"""
        # Configurar el mock
        self.mock_servicio.obtener_datos.return_value = {
            'id': 123,
            'nombre': 'Juan Pérez',
            'email': 'juan@email.com',
            'otros_datos': 'no_necesarios'
        }
        
        # Ejecutar
        usuario = self.repositorio.buscar_usuario(123)
        
        # Verificar
        self.assertEqual(usuario['id'], 123)
        self.assertEqual(usuario['nombre'], 'Juan Pérez')
        self.assertEqual(usuario['email'], 'juan@email.com')
        self.assertNotIn('otros_datos', usuario)
        
        # Verificar que se llamó correctamente al servicio
        self.mock_servicio.obtener_datos.assert_called_once_with("usuarios/123")
```

#### Ejemplo completo de suite de pruebas

```python
import unittest
from unittest.mock import Mock, patch

# Sistema completo a probar
class BaseDatos:
    def conectar(self):
        pass
    
    def guardar(self, datos):
        pass
    
    def buscar(self, criterio):
        pass

class Usuario:
    def __init__(self, nombre, email, edad):
        self.nombre = nombre
        self.email = email
        self.edad = edad
    
    def es_mayor_edad(self):
        return self.edad >= 18
    
    def to_dict(self):
        return {
            'nombre': self.nombre,
            'email': self.email,
            'edad': self.edad
        }

class RepositorioUsuario:
    def __init__(self, base_datos):
        self.db = base_datos
    
    def guardar_usuario(self, usuario):
        if not usuario.es_mayor_edad():
            raise ValueError("Usuario debe ser mayor de edad")
        
        datos = usuario.to_dict()
        return self.db.guardar(datos)
    
    def buscar_por_email(self, email):
        resultado = self.db.buscar({'email': email})
        if resultado:
            return Usuario(**resultado)
        return None

class TestSuiteCompleta(unittest.TestCase):
    """Suite de pruebas completa que demuestra diferentes técnicas"""
    
    def setUp(self):
        """Configuración común para todas las pruebas"""
        self.mock_db = Mock(spec=BaseDatos)
        self.repositorio = RepositorioUsuario(self.mock_db)
        
        self.usuario_adulto = Usuario("Ana García", "ana@email.com", 25)
        self.usuario_menor = Usuario("Luis Pérez", "luis@email.com", 16)
    
    def tearDown(self):
        """Limpieza después de cada prueba"""
        self.mock_db.reset_mock()
    
    def test_usuario_mayor_edad(self):
        """Probar detección de mayoría de edad"""
        self.assertTrue(self.usuario_adulto.es_mayor_edad())
        self.assertFalse(self.usuario_menor.es_mayor_edad())
    
    def test_usuario_to_dict(self):
        """Probar conversión a diccionario"""
        datos = self.usuario_adulto.to_dict()
        self.assertEqual(datos['nombre'], "Ana García")
        self.assertEqual(datos['email'], "ana@email.com")
        self.assertEqual(datos['edad'], 25)
    
    def test_guardar_usuario_adulto_exitoso(self):
        """Probar guardado exitoso de usuario adulto"""
        self.mock_db.guardar.return_value = True
        
        resultado = self.repositorio.guardar_usuario(self.usuario_adulto)
        
        self.assertTrue(resultado)
        self.mock_db.guardar.assert_called_once_with({
            'nombre': "Ana García",
            'email': "ana@email.com",
            'edad': 25
        })
    
    def test_guardar_usuario_menor_falla(self):
        """Probar que no se puede guardar usuario menor"""
        with self.assertRaises(ValueError) as context:
            self.repositorio.guardar_usuario(self.usuario_menor)
        
        self.assertIn("mayor de edad", str(context.exception))
        self.mock_db.guardar.assert_not_called()
    
    def test_buscar_usuario_existente(self):
        """Probar búsqueda de usuario existente"""
        self.mock_db.buscar.return_value = {
            'nombre': "Carlos López",
            'email': "carlos@email.com",
            'edad': 30
        }
        
        usuario = self.repositorio.buscar_por_email("carlos@email.com")
        
        self.assertIsInstance(usuario, Usuario)
        self.assertEqual(usuario.nombre, "Carlos López")
        self.mock_db.buscar.assert_called_once_with({'email': "carlos@email.com"})
    
    def test_buscar_usuario_inexistente(self):
        """Probar búsqueda de usuario inexistente"""
        self.mock_db.buscar.return_value = None
        
        usuario = self.repositorio.buscar_por_email("noexiste@email.com")
        
        self.assertIsNone(usuario)
    
    @patch('BaseDatos')
    def test_integracion_con_base_datos(self, mock_db_class):
        """Probar integración completa con base de datos mockeada"""
        # Configurar el mock de la clase
        mock_db_instance = mock_db_class.return_value
        mock_db_instance.guardar.return_value = True
        
        # Crear repositorio con base de datos mockeada
        repo = RepositorioUsuario(mock_db_instance)
        
        # Ejecutar operación
        resultado = repo.guardar_usuario(self.usuario_adulto)
        
        # Verificar
        self.assertTrue(resultado)
        mock_db_instance.guardar.assert_called_once()

# Clase para ejecutar todas las pruebas
class TestRunner:
    """Utilidad para ejecutar suites de pruebas específicas"""
    
    @staticmethod
    def ejecutar_pruebas_clase(clase_prueba):
        """Ejecutar pruebas de una clase específica"""
        suite = unittest.TestLoader().loadTestsFromTestCase(clase_prueba)
        runner = unittest.TextTestRunner(verbosity=2)
        return runner.run(suite)
    
    @staticmethod
    def ejecutar_todas_las_pruebas():
        """Ejecutar todas las pruebas del módulo"""
        unittest.main(verbosity=2)

# Ejemplo de uso
if __name__ == '__main__':
    # Ejecutar pruebas específicas
    print("=== Ejecutando pruebas de Usuario ===")
    TestRunner.ejecutar_pruebas_clase(TestSuiteCompleta)
    
    # O ejecutar todas las pruebas
    # TestRunner.ejecutar_todas_las_pruebas()
```

Este tema 4 cubre comprehensivamente todos los aspectos de la Programación Orientada a Objetos en Python, incluyendo:

- **Conceptos básicos**: Clases, objetos, atributos y métodos
- **Encapsulamiento**: Modificadores de acceso y métodos getters/setters  
- **Herencia**: Creación de clases derivadas y uso de `super()`
- **Polimorfismo**: Métodos sobrescritos y comportamiento polimórfico
- **Métodos especiales**: Métodos mágicos para personalizar el comportamiento
- **Pruebas unitarias**: Testing completo de clases con `unittest` y mocking
- **Ejemplos prácticos** y **ejercicios completos**
- **Buenas prácticas** de programación orientada a objetos

El contenido está estructurado de manera progresiva, comenzando con conceptos simples y avanzando hacia implementaciones más complejas y realistas, incluyendo técnicas profesionales de testing y validación.