# Jerarquía de Excepciones en Python

## Estructura General

Las excepciones en Python tienen una **estructura jerárquica**. Todas heredan de `BaseException`, y la mayoría de excepciones que puedes capturar heredan de `Exception`.

```
BaseException
 ├── SystemExit
 ├── KeyboardInterrupt
 ├── GeneratorExit
 └── Exception
      ├── StopIteration
      ├── ArithmeticError
      │   ├── ZeroDivisionError
      │   └── ...
      ├── LookupError
      │   ├── IndexError
      │   ├── KeyError
      │   └── ...
      ├── ValueError
      ├── TypeError
      ├── RuntimeError
      └── ... (muchas más)
```

## Ventaja de la Jerarquía

Esto es útil porque **puedes capturar excepciones en diferentes niveles de la jerarquía**:

```python
try:
    # código
except Exception:      # Captura todas las excepciones normales
    pass

try:
    # código
except LookupError:    # Captura IndexError y KeyError
    pass

try:
    # código
except (ValueError, TypeError):  # Captura excepciones específicas
    pass
```

## Jerarquía de excepciones relaciondas ficheros

```
BaseException
 └── Exception
      ├── TypeError ⬅️ ERROR DE TIPO
      ├── OSError ⬅️ ERRORES DE SISTEMA/ARCHIVO
      │   ├── PermissionError ⬅️ FALTA DE PERMISOS (hereda de OSError)
      │   ├── FileNotFoundError
      │   ├── IsADirectoryError
      │   └── ... (otras derivadas de OSError)
      ├── LookupError
      │   ├── IndexError
      │   ├── KeyError
      │   └── ...
      ├── ValueError
      │   ├── UnicodeError
      │   │   └── UnicodeDecodeError
      │   └── UnidecodeError
      └── ... (más excepciones)
```

## Información Importante sobre IOError

**`IOError` es un alias de `OSError`** en Python 3. Es decir, son lo mismo.

Esto significa que capturar `OSError` automáticamente captura `IOError`, por lo que incluir ambas es redundante.

## Simplificación del Código (Sin Mensajes Distintos)

### Opción 1: Usar solo las excepciones necesarias

```python
except (TypeError, OSError) as e:
    print(f'[ERROR]:{e}')
    return None
```

Esto captura:
- **TypeError** → cualquier error de tipo
- **OSError** → errores de archivo, permisos, etc. (incluyendo `PermissionError`, `FileNotFoundError`, e `IOError`)

### Opción 2: Ser más general

Si quieres capturar casi cualquier excepción esperada, puedes usar solo `Exception`:

```python
except Exception as e:
    print(f'[ERROR]:{e}')
    return None
```

## 🎯 MENSAJES INFORMATIVOS DISTINTOS CON JERARQUÍA

**PUNTO IMPORTANTE:** Cuando quieres dar mensajes informativos diferentes según el tipo de error, necesitas capturar cada excepción por separado usando **múltiples bloques `except`** en orden jerárquico (de más específico a menos específico).

### Por qué el orden importa

El orden debe ser **siempre de más específico a menos específico**, porque Python usa el **primer `except` que coincida**. Si pusieras `except OSError` primero, nunca llegaría a `except PermissionError` (que hereda de `OSError`).

**❌ INCORRECTO (general primero):**
```python
try:
    # código
except OSError:           # Captura TODAS las derivadas
    print("Error de sistema")
except PermissionError:   # NUNCA SE EJECUTA, ya fue capturado arriba
    print("Falta de permisos")
```

**✅ CORRECTO (específico a general):**
```python
try:
    # código
except PermissionError:   # Específico primero
    print("Falta de permisos")
except FileNotFoundError: # Específico
    print("Archivo no encontrado")
except OSError:           # General al final
    print("Error de sistema general")
```


## Beneficios de usar la Jerarquía para Mensajes Distintos

| Beneficio | Explicación |
|-----------|-------------|
| **Mensajes claros** | Cada tipo de error recibe un mensaje específico y útil |
| **Debugging facilitado** | Sabes exactamente qué tipo de error ocurrió |
| **Logging estructurado** | Puedes registrar diferentes tipos de errores de forma diferente |
| **Manejo diferenciado** | Puedes tomar acciones distintas según el tipo de error |
| **Experiencia del usuario** | El usuario entiende qué salió mal y cómo corregirlo |
| **Respeto a la jerarquía** | Usas la estructura inherente de Python de forma efectiva |

## Orden De Especificidad en Operaciones de Archivo

Para operaciones de archivo, el orden correcto de más específico a menos específico es:

```python
except TypeError:          # Error de tipo de argumento
    ...
except FileNotFoundError:  # Archivo no existe (derivado de OSError)
    ...
except PermissionError:    # Falta de permisos (derivado de OSError)
    ...
except IsADirectoryError:  # Es un directorio, no archivo (derivado de OSError)
    ...
except OSError:            # Otros errores de sistema (padre de los anteriores)
    ...
```

## Tabla de Referencia Rápida

| Situación | Excepciones a capturar |
|-----------|------------------------|
| Quieres máxima precisión | `except ValueError:` o `except (TypeError, ValueError):` |
| Quieres un nivel intermedio | `except OSError:` (captura archivo, permisos, etc.) |
| Quieres ser general | `except Exception:` (casi cualquier error) |
| Quieres evitar que el programa muera | `except BaseException:` (¡casi nunca!) |
| Quieres mensajes distintos | Múltiples `except` en orden jerárquico (específico → general) |
