## PRUEBAS UNITARIAS

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