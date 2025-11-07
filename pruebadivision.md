# GUÍA COMPLETA: PRUEBAS UNITARIAS PARA DIVISIÓN

## Introducción

La división es una operación que requiere **especial atención** en las pruebas porque tiene varios casos límite y situaciones especiales que pueden causar errores si no se manejan correctamente.

Esta guía cubre todos los casos que deberías probar cuando implementas una función de división.

---

## Tabla de Contenidos

- [GUÍA COMPLETA: PRUEBAS UNITARIAS PARA DIVISIÓN](#guía-completa-pruebas-unitarias-para-división)
  - [Introducción](#introducción)
  - [Tabla de Contenidos](#tabla-de-contenidos)
  - [Función básica de división](#función-básica-de-división)
  - [1. División por cero (⚠️ CRÍTICO)](#1-división-por-cero-️-crítico)
  - [2. Cero como dividendo](#2-cero-como-dividendo)
  - [3. División que da exactamente 1](#3-división-que-da-exactamente-1)
  - [4. División por 1 (identidad)](#4-división-por-1-identidad)
  - [5. Números negativos (cambios de signo)](#5-números-negativos-cambios-de-signo)
  - [6. Números decimales y fracciones](#6-números-decimales-y-fracciones)
  - [7. Números muy grandes y muy pequeños](#7-números-muy-grandes-y-muy-pequeños)
  - [8. Precisión de punto flotante](#8-precisión-de-punto-flotante)
  - [9. División entera vs división flotante](#9-división-entera-vs-división-flotante)
  - [Suite completa de pruebas](#suite-completa-de-pruebas)
  - [Checklist para probar divisiones](#checklist-para-probar-divisiones)
    - [✅ Casos de error](#-casos-de-error)
    - [✅ Casos especiales](#-casos-especiales)
    - [✅ Signos](#-signos)
    - [✅ Tipos de números](#-tipos-de-números)
    - [✅ Precisión](#-precisión)
  - [Plantilla reutilizable](#plantilla-reutilizable)
  - [Consejo profesional](#consejo-profesional)

---

## Función básica de división

Primero, definamos la función que vamos a probar:

```python
def dividir(a, b):
    """
    Divide dos números.
    
    Args:
        a (float): Dividendo
        b (float): Divisor
    
    Returns:
        float: Resultado de la división
    
    Raises:
        ValueError: Si el divisor es cero
    """
    if b == 0:
        raise ValueError("No se puede dividir por cero")
    return a / b
```

---

## 1. División por cero (⚠️ CRÍTICO)

**El caso más importante:** La división por cero es indefinida matemáticamente y debe manejarse con un error.

```python
def probar_division_por_cero():
    """El caso más importante: división por cero."""
    print("Probando división por cero...")
    
    # Dividir cualquier número por cero debe dar error
    try:
        dividir(5, 0)
        assert False, "Debería lanzar ValueError"
    except ValueError as e:
        assert "No se puede dividir por cero" in str(e)
    
    try:
        dividir(0, 0)  # Incluso 0/0 es indefinido
        assert False, "Debería lanzar ValueError"
    except ValueError:
        pass
    
    try:
        dividir(-10, 0)
        assert False, "Debería lanzar ValueError"
    except ValueError:
        pass
    
    print("  ✅ División por cero manejada correctamente")
```

**¿Por qué es crítico?**
- Es el error más común en divisiones
- Puede hacer que el programa se detenga inesperadamente
- Debe manejarse explícitamente en el código

---

## 2. Cero como dividendo

**Caso especial:** Cero dividido por cualquier número (excepto cero) siempre es cero.

```python
def probar_cero_dividendo():
    """Probar cuando el numerador es cero."""
    print("Probando cero como dividendo...")
    
    # 0 dividido por cualquier número (excepto 0) es 0
    assert dividir(0, 1) == 0.0
    assert dividir(0, 5) == 0.0
    assert dividir(0, -3) == 0.0
    assert dividir(0, 100) == 0.0
    assert dividir(0, 0.5) == 0.0
    
    print("  ✅ Cero como dividendo funciona correctamente")
```

**Regla matemática:** `0 / n = 0` (donde n ≠ 0)

---

## 3. División que da exactamente 1

**Identidad:** Cualquier número dividido por sí mismo da 1.

```python
def probar_division_unitaria():
    """Probar divisiones que resultan en 1."""
    print("Probando divisiones unitarias...")
    
    # Número dividido por sí mismo
    assert dividir(1, 1) == 1.0
    assert dividir(5, 5) == 1.0
    assert dividir(-3, -3) == 1.0
    assert dividir(0.5, 0.5) == 1.0
    assert dividir(1000, 1000) == 1.0
    
    print("  ✅ Divisiones unitarias correctas")
```

**Regla matemática:** `n / n = 1` (donde n ≠ 0)

---

## 4. División por 1 (identidad)

**Elemento identidad:** Cualquier número dividido por 1 se mantiene igual.

```python
def probar_division_por_uno():
    """Probar divisiones por 1 (identidad)."""
    print("Probando división por 1...")
    
    # Cualquier número dividido por 1 da el mismo número
    assert dividir(5, 1) == 5.0
    assert dividir(-10, 1) == -10.0
    assert dividir(0, 1) == 0.0
    assert dividir(3.14, 1) == 3.14
    assert dividir(1000, 1) == 1000.0
    
    print("  ✅ División por 1 funciona correctamente")
```

**Regla matemática:** `n / 1 = n`

---

## 5. Números negativos (cambios de signo)

**Reglas de signos:** La combinación de números positivos y negativos afecta al resultado.

```python
def probar_numeros_negativos():
    """Probar divisiones con números negativos."""
    print("Probando números negativos...")
    
    # Positivo / Negativo = Negativo
    assert dividir(10, -2) == -5.0
    assert dividir(6, -3) == -2.0
    
    # Negativo / Positivo = Negativo
    assert dividir(-10, 2) == -5.0
    assert dividir(-15, 3) == -5.0
    
    # Negativo / Negativo = Positivo
    assert dividir(-10, -2) == 5.0
    assert dividir(-12, -3) == 4.0
    
    print("  ✅ Números negativos manejados correctamente")
```

**Tabla de signos:**

| Dividendo | Divisor | Resultado |
|-----------|---------|-----------|
| +         | +       | +         |
| +         | -       | -         |
| -         | +       | -         |
| -         | -       | +         |

---

## 6. Números decimales y fracciones

**Precisión decimal:** Las divisiones pueden producir números decimales o fracciones.

```python
def probar_numeros_decimales():
    """Probar divisiones con decimales."""
    print("Probando números decimales...")
    
    # Divisiones que dan resultado decimal
    assert dividir(7, 2) == 3.5
    assert dividir(1, 3) == 0.3333333333333333  # Periódico
    assert dividir(5, 4) == 1.25
    
    # Dividir por decimal
    assert dividir(10, 0.5) == 20.0
    assert dividir(1, 0.1) == 10.0
    
    # Decimal dividido por decimal
    assert dividir(2.5, 0.5) == 5.0
    assert dividir(7.5, 2.5) == 3.0
    
    print("  ✅ Números decimales funcionan correctamente")
```

**Nota:** Los números decimales periódicos (como 1/3 = 0.333...) tienen representación aproximada en punto flotante.

---

## 7. Números muy grandes y muy pequeños

**Casos extremos:** Probar con valores en los límites del sistema.

```python
def probar_numeros_extremos():
    """Probar con números muy grandes o muy pequeños."""
    print("Probando números extremos...")
    
    # Números muy grandes
    assert dividir(1e100, 1e50) == 1e50
    assert dividir(1000000, 1) == 1000000.0
    
    # Números muy pequeños
    assert dividir(1, 1000000) == 0.000001
    assert dividir(0.0001, 0.01) == 0.01
    
    # Muy grande dividido por muy pequeño
    resultado = dividir(1000000, 0.0001)
    assert resultado == 10000000000.0
    
    print("  ✅ Números extremos manejados correctamente")
```

**Atención:** Con números muy grandes o muy pequeños, pueden aparecer problemas de overflow o underflow.

---

## 8. Precisión de punto flotante

**Limitaciones de float:** Los números de punto flotante tienen precisión limitada.

```python
def probar_precision_flotante():
    """Probar casos donde la precisión flotante puede causar problemas."""
    print("Probando precisión de punto flotante...")
    
    # Algunas divisiones pueden tener pequeños errores de redondeo
    resultado = dividir(1, 3)
    # No comparar con == exacto, usar aproximación
    assert abs(resultado - 0.333333) < 0.000001
    
    # División que debería dar exactamente 0.1
    resultado = dividir(1, 10)
    assert abs(resultado - 0.1) < 0.0000001
    
    print("  ✅ Precisión flotante considerada")
```

**Buena práctica:** Usa `abs(resultado - esperado) < tolerancia` en lugar de `==` para comparar floats.

---

## 9. División entera vs división flotante

**Tipos de división en Python:**
- `/` → División flotante (siempre devuelve float)
- `//` → División entera (devuelve int o floor division)

```python
def comparar_division_entera_y_flotante():
    """Comparar división entera (//) vs división flotante (/)."""
    print("Comparando tipos de división...")
    
    # División flotante (/) - siempre devuelve float
    assert dividir(10, 3) == 3.3333333333333335
    assert type(dividir(10, 3)) == float
    
    # Si quisiéramos división entera, usaríamos //
    assert 10 // 3 == 3  # Devuelve int
    assert type(10 // 3) == int
    
    # División exacta también devuelve float con /
    assert dividir(10, 2) == 5.0
    assert type(dividir(10, 2)) == float
    
    print("  ✅ Tipos de división comprendidos")
```

**Diferencias:**
- `10 / 3` → `3.3333333333333335` (float)
- `10 // 3` → `3` (int, redondea hacia abajo)

---

## Suite completa de pruebas

Ejecuta todas las pruebas de una vez:

```python
def suite_completa_division():
    """
    Suite completa de pruebas para la función dividir.
    Cubre todos los casos límite importantes.
    """
    print("🧪 SUITE COMPLETA DE PRUEBAS - DIVISIÓN")
    print("=" * 60)
    
    # Ejecutar todas las pruebas de casos límite
    probar_division_por_cero()           # ⚠️ CRÍTICO
    probar_cero_dividendo()              # Caso especial
    probar_division_unitaria()           # Identidad
    probar_division_por_uno()            # Identidad
    probar_numeros_negativos()           # Signos
    probar_numeros_decimales()           # Fracciones
    probar_numeros_extremos()            # Límites numéricos
    probar_precision_flotante()          # Errores de redondeo
    comparar_division_entera_y_flotante() # Tipos de división
    
    print("=" * 60)
    print("🎉 ¡TODAS LAS PRUEBAS DE DIVISIÓN PASARON!")
    print("   La función dividir está completamente probada.")

# Ejecutar la suite
if __name__ == "__main__":
    suite_completa_division()
```

---

## Checklist para probar divisiones

Al probar una función de división, **siempre** verifica:

### ✅ Casos de error
- [ ] División por cero (a/0) → debe lanzar error

### ✅ Casos especiales
- [ ] Cero como dividendo (0/b) → resultado = 0
- [ ] División por sí mismo (a/a) → resultado = 1
- [ ] División por 1 (a/1) → resultado = a

### ✅ Signos
- [ ] Positivo / Positivo → Positivo
- [ ] Positivo / Negativo → Negativo
- [ ] Negativo / Positivo → Negativo
- [ ] Negativo / Negativo → Positivo

### ✅ Tipos de números
- [ ] Enteros que dividen exacto (10/2 = 5)
- [ ] Enteros que dan decimal (7/2 = 3.5)
- [ ] Decimales (2.5/0.5 = 5.0)
- [ ] Números muy grandes
- [ ] Números muy pequeños

### ✅ Precisión
- [ ] Divisiones con resultados periódicos (1/3)
- [ ] Comparaciones con tolerancia para flotantes

---

## Plantilla reutilizable

Usa esta plantilla para probar cualquier función de división:

```python
def plantilla_pruebas_division(funcion_dividir):
    """
    Plantilla reutilizable para probar funciones de división.
    
    Args:
        funcion_dividir: La función a probar (debe recibir 2 parámetros)
    """
    print(f"Probando {funcion_dividir.__name__}...")
    
    # 1. ERROR: División por cero
    try:
        funcion_dividir(5, 0)
        assert False, "Debería dar error al dividir por cero"
    except (ValueError, ZeroDivisionError):
        pass  # Correcto
    
    # 2. ESPECIAL: Cero dividendo
    assert funcion_dividir(0, 5) == 0
    
    # 3. IDENTIDAD: División por sí mismo
    assert funcion_dividir(7, 7) == 1
    
    # 4. IDENTIDAD: División por 1
    assert funcion_dividir(42, 1) == 42
    
    # 5. SIGNOS: Combinaciones
    assert funcion_dividir(10, -2) == -5   # +/-
    assert funcion_dividir(-10, 2) == -5   # -/+
    assert funcion_dividir(-10, -2) == 5   # -/-
    
    # 6. DECIMALES: Resultado no entero
    assert funcion_dividir(7, 2) == 3.5
    
    # 7. DECIMALES: Operandos decimales
    assert funcion_dividir(2.5, 0.5) == 5.0
    
    print(f"  ✅ {funcion_dividir.__name__} pasó todas las pruebas")

# Ejemplo de uso
plantilla_pruebas_division(dividir)
```

---

## Consejo profesional

**Siempre empieza verificando el caso de división por cero**, ya que es el error más común y puede hacer que tu programa se detenga inesperadamente.

El orden recomendado de pruebas es:
1. **División por cero** (prevenir crashes)
2. **Casos especiales** (0, 1, números iguales)
3. **Signos** (positivos/negativos)
4. **Tipos de números** (enteros, decimales, extremos)
5. **Precisión** (comparaciones con tolerancia)

---

**Documento creado para:** Curso 2025-26 - Python 2º DAM  
**Última actualización:** 2025
