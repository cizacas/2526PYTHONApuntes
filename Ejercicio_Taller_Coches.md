# EJERCICIO PRÁCTICO: SISTEMA DE GESTIÓN DE TALLER DE COCHES

## 📋 DESCRIPCIÓN DEL PROYECTO

Crear un sistema de gestión para un taller de coches utilizando **módulos y paquetes con funciones**. El sistema debe permitir registrar vehículos, gestionar reparaciones, calcular costos y generar reportes.

## 🎯 OBJETIVOS DE APRENDIZAJE

- Aplicar conceptos de módulos y paquetes
- Organizar funciones en diferentes módulos según su responsabilidad
- Practicar importaciones entre módulos
- Trabajar con estructuras de datos (listas y diccionarios)
- Implementar funciones con parámetros y valores de retorno

## 📁 ESTRUCTURA DEL PROYECTO

```
taller_coches/
├── __init__.py
├── vehiculos.py
├── reparaciones.py
├── facturacion.py
├── reportes.py
├── utils.py
└── main.py
```

## 📝 ESPECIFICACIONES TÉCNICAS

### Módulo `vehiculos.py`
Funciones para gestionar el registro de vehículos:
- `registrar_vehiculo(matricula, marca, modelo, año, propietario, telefono)`
- `buscar_vehiculo(matricula)`
- `listar_vehiculos()`
- `actualizar_kilometraje(matricula, kilometros)`
- `vehiculo_existe(matricula)`

### Módulo `reparaciones.py`
Funciones para gestionar las reparaciones:
- `crear_reparacion(id_reparacion, matricula, descripcion, tipo_reparacion, fecha_inicio)`
- `finalizar_reparacion(id_reparacion, fecha_fin, horas_trabajo)`
- `listar_reparaciones(estado=None)` # estado: 'en_proceso', 'finalizada'
- `buscar_reparaciones_vehiculo(matricula)`
- `calcular_tiempo_reparacion(id_reparacion)`

### Módulo `facturacion.py`
Funciones para calcular costos y generar facturas:
- `calcular_costo_mano_obra(horas, tarifa_por_hora=45.0)`
- `calcular_costo_repuestos(lista_repuestos)`
- `aplicar_descuento(total, porcentaje_descuento)`
- `generar_factura(id_reparacion)`
- `registrar_pago(id_reparacion, metodo_pago, fecha_pago)`

### Módulo `reportes.py`
Funciones para generar reportes e estadísticas:
- `reporte_vehiculos_por_marca()`
- `reporte_reparaciones_mes(mes, año)`
- `estadisticas_tipos_reparacion()`
- `vehiculos_mas_reparados(limite=5)`
- `ingresos_totales_periodo(fecha_inicio, fecha_fin)`

### Módulo `utils.py`
Funciones auxiliares y validaciones:
- `validar_matricula(matricula)`
- `validar_telefono(telefono)`
- `formatear_fecha(fecha)`
- `generar_id_unico()`
- `limpiar_texto(texto)`

## 💻 CÓDIGO DE IMPLEMENTACIÓN

### `taller_coches/__init__.py`
```python
"""
Sistema de gestión de taller de coches.

Un paquete completo para gestionar vehículos, reparaciones y facturación.
"""

__version__ = "1.0.0"
__author__ = "Estudiante Python"

# Importar funciones principales para acceso directo
from .vehiculos import registrar_vehiculo, buscar_vehiculo, listar_vehiculos
from .reparaciones import crear_reparacion, finalizar_reparacion, listar_reparaciones
from .facturacion import generar_factura, calcular_costo_mano_obra
from .reportes import reporte_vehiculos_por_marca, estadisticas_tipos_reparacion

# Lista de elementos públicos
__all__ = [
    'registrar_vehiculo', 'buscar_vehiculo', 'listar_vehiculos',
    'crear_reparacion', 'finalizar_reparacion', 'listar_reparaciones',
    'generar_factura', 'calcular_costo_mano_obra',
    'reporte_vehiculos_por_marca', 'estadisticas_tipos_reparacion'
]

print(f"🔧 Sistema Taller de Coches v{__version__} inicializado")
```

### `taller_coches/vehiculos.py`
```python
"""Módulo para gestión de vehículos del taller."""

from .utils import validar_matricula, validar_telefono, limpiar_texto

# Base de datos de vehículos (en memoria)
vehiculos_registrados = {}

def registrar_vehiculo(matricula, marca, modelo, año, propietario, telefono):
    """
    Registra un nuevo vehículo en el sistema del taller.
    
    Args:
        matricula (str): Matrícula del vehículo
        marca (str): Marca del vehículo
        modelo (str): Modelo del vehículo
        año (int): Año de fabricación
        propietario (str): Nombre del propietario
        telefono (str): Teléfono de contacto
    
    Returns:
        bool: True si se registró correctamente
    
    Raises:
        ValueError: Si los datos no son válidos o el vehículo ya existe
    """
    # Validaciones
    matricula = validar_matricula(matricula)
    telefono = validar_telefono(telefono)
    
    if vehiculo_existe(matricula):
        raise ValueError(f"El vehículo con matrícula {matricula} ya está registrado")
    
    if año < 1980 or año > 2025:
        raise ValueError("Año de fabricación no válido")
    
    # Crear registro del vehículo
    vehiculo = {
        'matricula': matricula,
        'marca': limpiar_texto(marca),
        'modelo': limpiar_texto(modelo),
        'año': año,
        'propietario': limpiar_texto(propietario),
        'telefono': telefono,
        'kilometraje': 0,
        'fecha_registro': None,  # Se podría usar datetime
        'reparaciones_realizadas': []
    }
    
    vehiculos_registrados[matricula] = vehiculo
    print(f"✅ Vehículo registrado: {marca} {modelo} ({matricula})")
    return True

def buscar_vehiculo(matricula):
    """
    Busca un vehículo por su matrícula.
    
    Args:
        matricula (str): Matrícula a buscar
    
    Returns:
        dict or None: Datos del vehículo o None si no existe
    """
    matricula = validar_matricula(matricula)
    return vehiculos_registrados.get(matricula)

def listar_vehiculos():
    """
    Lista todos los vehículos registrados.
    
    Returns:
        list: Lista de todos los vehículos
    """
    return list(vehiculos_registrados.values())

def actualizar_kilometraje(matricula, kilometros):
    """
    Actualiza el kilometraje de un vehículo.
    
    Args:
        matricula (str): Matrícula del vehículo
        kilometros (int): Nuevo kilometraje
    
    Returns:
        bool: True si se actualizó correctamente
    
    Raises:
        ValueError: Si el vehículo no existe o el kilometraje no es válido
    """
    vehiculo = buscar_vehiculo(matricula)
    if not vehiculo:
        raise ValueError(f"Vehículo {matricula} no encontrado")
    
    if kilometros < 0:
        raise ValueError("El kilometraje no puede ser negativo")
    
    if kilometros < vehiculo['kilometraje']:
        raise ValueError("El nuevo kilometraje no puede ser menor al actual")
    
    vehiculo['kilometraje'] = kilometros
    print(f"📊 Kilometraje actualizado para {matricula}: {kilometros} km")
    return True

def vehiculo_existe(matricula):
    """
    Verifica si un vehículo existe en el sistema.
    
    Args:
        matricula (str): Matrícula a verificar
    
    Returns:
        bool: True si existe, False si no
    """
    matricula = validar_matricula(matricula)
    return matricula in vehiculos_registrados

def obtener_vehiculos_por_marca(marca):
    """
    Obtiene todos los vehículos de una marca específica.
    
    Args:
        marca (str): Marca a filtrar
    
    Returns:
        list: Lista de vehículos de la marca especificada
    """
    marca = limpiar_texto(marca)
    return [v for v in vehiculos_registrados.values() 
            if v['marca'].lower() == marca.lower()]
```

### `taller_coches/reparaciones.py`
```python
"""Módulo para gestión de reparaciones."""

from .vehiculos import buscar_vehiculo, vehiculo_existe
from .utils import generar_id_unico

# Base de datos de reparaciones
reparaciones = {}

# Tipos de reparación válidos
TIPOS_REPARACION = [
    'motor', 'frenos', 'suspension', 'electricidad', 
    'carroceria', 'climatizacion', 'transmision', 'neumaticos'
]

def crear_reparacion(matricula, descripcion, tipo_reparacion, mecanico_asignado):
    """
    Crea una nueva reparación para un vehículo.
    
    Args:
        matricula (str): Matrícula del vehículo
        descripcion (str): Descripción del problema
        tipo_reparacion (str): Tipo de reparación
        mecanico_asignado (str): Nombre del mecánico
    
    Returns:
        str: ID de la reparación creada
    
    Raises:
        ValueError: Si los datos no son válidos
    """
    # Validaciones
    if not vehiculo_existe(matricula):
        raise ValueError(f"Vehículo {matricula} no encontrado")
    
    if tipo_reparacion.lower() not in TIPOS_REPARACION:
        raise ValueError(f"Tipo de reparación no válido. Opciones: {TIPOS_REPARACION}")
    
    if not descripcion.strip():
        raise ValueError("La descripción no puede estar vacía")
    
    # Generar ID único
    id_reparacion = generar_id_unico()
    
    # Crear reparación
    reparacion = {
        'id': id_reparacion,
        'matricula': matricula,
        'descripcion': descripcion.strip(),
        'tipo': tipo_reparacion.lower(),
        'mecanico': mecanico_asignado.strip(),
        'estado': 'en_proceso',
        'fecha_inicio': None,  # Se podría usar datetime
        'fecha_fin': None,
        'horas_trabajo': 0,
        'repuestos_utilizados': [],
        'costo_total': 0.0
    }
    
    reparaciones[id_reparacion] = reparacion
    
    # Actualizar historial del vehículo
    vehiculo = buscar_vehiculo(matricula)
    vehiculo['reparaciones_realizadas'].append(id_reparacion)
    
    print(f"🔧 Reparación creada: {id_reparacion} para vehículo {matricula}")
    return id_reparacion

def finalizar_reparacion(id_reparacion, horas_trabajo, repuestos_utilizados=None):
    """
    Finaliza una reparación marcándola como completada.
    
    Args:
        id_reparacion (str): ID de la reparación
        horas_trabajo (float): Horas de trabajo invertidas
        repuestos_utilizados (list): Lista de repuestos usados
    
    Returns:
        bool: True si se finalizó correctamente
    
    Raises:
        ValueError: Si la reparación no existe o ya está finalizada
    """
    if id_reparacion not in reparaciones:
        raise ValueError(f"Reparación {id_reparacion} no encontrada")
    
    reparacion = reparaciones[id_reparacion]
    
    if reparacion['estado'] == 'finalizada':
        raise ValueError("La reparación ya está finalizada")
    
    if horas_trabajo <= 0:
        raise ValueError("Las horas de trabajo deben ser positivas")
    
    # Actualizar reparación
    reparacion['estado'] = 'finalizada'
    reparacion['horas_trabajo'] = horas_trabajo
    reparacion['fecha_fin'] = None  # Se podría usar datetime
    
    if repuestos_utilizados:
        reparacion['repuestos_utilizados'] = repuestos_utilizados
    
    print(f"✅ Reparación {id_reparacion} finalizada - {horas_trabajo} horas")
    return True

def listar_reparaciones(estado=None):
    """
    Lista reparaciones filtradas por estado.
    
    Args:
        estado (str, optional): Estado a filtrar ('en_proceso', 'finalizada')
    
    Returns:
        list: Lista de reparaciones
    """
    if estado:
        return [r for r in reparaciones.values() if r['estado'] == estado]
    return list(reparaciones.values())

def buscar_reparaciones_vehiculo(matricula):
    """
    Busca todas las reparaciones de un vehículo específico.
    
    Args:
        matricula (str): Matrícula del vehículo
    
    Returns:
        list: Lista de reparaciones del vehículo
    """
    return [r for r in reparaciones.values() if r['matricula'] == matricula]

def obtener_reparacion(id_reparacion):
    """
    Obtiene una reparación por su ID.
    
    Args:
        id_reparacion (str): ID de la reparación
    
    Returns:
        dict or None: Datos de la reparación o None si no existe
    """
    return reparaciones.get(id_reparacion)

def agregar_repuesto_reparacion(id_reparacion, repuesto, cantidad, precio_unitario):
    """
    Agrega un repuesto a una reparación existente.
    
    Args:
        id_reparacion (str): ID de la reparación
        repuesto (str): Nombre del repuesto
        cantidad (int): Cantidad utilizada
        precio_unitario (float): Precio por unidad
    
    Returns:
        bool: True si se agregó correctamente
    """
    reparacion = obtener_reparacion(id_reparacion)
    if not reparacion:
        raise ValueError(f"Reparación {id_reparacion} no encontrada")
    
    repuesto_info = {
        'nombre': repuesto,
        'cantidad': cantidad,
        'precio_unitario': precio_unitario,
        'subtotal': cantidad * precio_unitario
    }
    
    reparacion['repuestos_utilizados'].append(repuesto_info)
    print(f"🔩 Repuesto agregado: {cantidad}x {repuesto}")
    return True
```

### `taller_coches/facturacion.py`
```python
"""Módulo para cálculos de facturación y costos."""

from .reparaciones import obtener_reparacion
from .vehiculos import buscar_vehiculo

# Configuración de precios
TARIFA_MANO_OBRA_DEFECTO = 45.0  # euros por hora
IVA_PORCENTAJE = 21.0

def calcular_costo_mano_obra(horas, tarifa_por_hora=None):
    """
    Calcula el costo de mano de obra.
    
    Args:
        horas (float): Número de horas trabajadas
        tarifa_por_hora (float, optional): Tarifa por hora
    
    Returns:
        float: Costo total de mano de obra
    """
    if tarifa_por_hora is None:
        tarifa_por_hora = TARIFA_MANO_OBRA_DEFECTO
    
    if horas < 0:
        raise ValueError("Las horas no pueden ser negativas")
    
    return horas * tarifa_por_hora

def calcular_costo_repuestos(repuestos):
    """
    Calcula el costo total de repuestos.
    
    Args:
        repuestos (list): Lista de diccionarios con repuestos
    
    Returns:
        float: Costo total de repuestos
    """
    total = 0.0
    for repuesto in repuestos:
        if 'subtotal' in repuesto:
            total += repuesto['subtotal']
        else:
            total += repuesto['cantidad'] * repuesto['precio_unitario']
    
    return total

def aplicar_descuento(total, porcentaje_descuento):
    """
    Aplica un descuento al total.
    
    Args:
        total (float): Total antes del descuento
        porcentaje_descuento (float): Porcentaje de descuento (0-100)
    
    Returns:
        tuple: (total_con_descuento, descuento_aplicado)
    """
    if porcentaje_descuento < 0 or porcentaje_descuento > 100:
        raise ValueError("El porcentaje de descuento debe estar entre 0 y 100")
    
    descuento = total * (porcentaje_descuento / 100)
    total_con_descuento = total - descuento
    
    return total_con_descuento, descuento

def calcular_iva(subtotal, porcentaje_iva=None):
    """
    Calcula el IVA sobre un subtotal.
    
    Args:
        subtotal (float): Subtotal sin IVA
        porcentaje_iva (float, optional): Porcentaje de IVA
    
    Returns:
        tuple: (total_con_iva, iva_aplicado)
    """
    if porcentaje_iva is None:
        porcentaje_iva = IVA_PORCENTAJE
    
    iva = subtotal * (porcentaje_iva / 100)
    total_con_iva = subtotal + iva
    
    return total_con_iva, iva

def generar_factura(id_reparacion, porcentaje_descuento=0):
    """
    Genera una factura completa para una reparación.
    
    Args:
        id_reparacion (str): ID de la reparación
        porcentaje_descuento (float): Descuento a aplicar
    
    Returns:
        dict: Factura completa con todos los detalles
    
    Raises:
        ValueError: Si la reparación no existe o no está finalizada
    """
    reparacion = obtener_reparacion(id_reparacion)
    if not reparacion:
        raise ValueError(f"Reparación {id_reparacion} no encontrada")
    
    if reparacion['estado'] != 'finalizada':
        raise ValueError("Solo se pueden facturar reparaciones finalizadas")
    
    vehiculo = buscar_vehiculo(reparacion['matricula'])
    
    # Calcular costos
    costo_mano_obra = calcular_costo_mano_obra(reparacion['horas_trabajo'])
    costo_repuestos = calcular_costo_repuestos(reparacion['repuestos_utilizados'])
    
    subtotal = costo_mano_obra + costo_repuestos
    
    # Aplicar descuento si corresponde
    if porcentaje_descuento > 0:
        subtotal_con_descuento, descuento = aplicar_descuento(subtotal, porcentaje_descuento)
    else:
        subtotal_con_descuento = subtotal
        descuento = 0.0
    
    # Calcular IVA
    total_con_iva, iva = calcular_iva(subtotal_con_descuento)
    
    # Generar factura
    factura = {
        'id_reparacion': id_reparacion,
        'vehiculo': {
            'matricula': vehiculo['matricula'],
            'marca': vehiculo['marca'],
            'modelo': vehiculo['modelo'],
            'propietario': vehiculo['propietario']
        },
        'reparacion': {
            'descripcion': reparacion['descripcion'],
            'tipo': reparacion['tipo'],
            'mecanico': reparacion['mecanico'],
            'horas_trabajo': reparacion['horas_trabajo']
        },
        'costos': {
            'mano_obra': costo_mano_obra,
            'repuestos': costo_repuestos,
            'subtotal': subtotal,
            'descuento_porcentaje': porcentaje_descuento,
            'descuento_importe': descuento,
            'subtotal_con_descuento': subtotal_con_descuento,
            'iva_porcentaje': IVA_PORCENTAJE,
            'iva_importe': iva,
            'total': total_con_iva
        },
        'repuestos_detalle': reparacion['repuestos_utilizados'],
        'fecha_factura': None  # Se podría usar datetime
    }
    
    # Actualizar el costo total en la reparación
    reparacion['costo_total'] = total_con_iva
    
    return factura

def imprimir_factura(factura):
    """
    Imprime una factura de manera formateada.
    
    Args:
        factura (dict): Diccionario con datos de la factura
    """
    print("\n" + "="*50)
    print("           TALLER DE COCHES PYTHON")
    print("="*50)
    print(f"Factura para reparación: {factura['id_reparacion']}")
    print(f"Vehículo: {factura['vehiculo']['marca']} {factura['vehiculo']['modelo']}")
    print(f"Matrícula: {factura['vehiculo']['matricula']}")
    print(f"Propietario: {factura['vehiculo']['propietario']}")
    print(f"Mecánico: {factura['reparacion']['mecanico']}")
    print("-"*50)
    print(f"Descripción: {factura['reparacion']['descripcion']}")
    print(f"Tipo: {factura['reparacion']['tipo']}")
    print(f"Horas trabajadas: {factura['reparacion']['horas_trabajo']}")
    print("-"*50)
    
    # Detalle de costos
    costos = factura['costos']
    print(f"Mano de obra: {costos['mano_obra']:.2f} €")
    print(f"Repuestos: {costos['repuestos']:.2f} €")
    print(f"Subtotal: {costos['subtotal']:.2f} €")
    
    if costos['descuento_importe'] > 0:
        print(f"Descuento ({costos['descuento_porcentaje']}%): -{costos['descuento_importe']:.2f} €")
        print(f"Subtotal con descuento: {costos['subtotal_con_descuento']:.2f} €")
    
    print(f"IVA ({costos['iva_porcentaje']}%): {costos['iva_importe']:.2f} €")
    print("="*50)
    print(f"TOTAL A PAGAR: {costos['total']:.2f} €")
    print("="*50)
    
    # Detalle de repuestos si hay
    if factura['repuestos_detalle']:
        print("\nDETALLE DE REPUESTOS:")
        for repuesto in factura['repuestos_detalle']:
            print(f"  {repuesto['cantidad']}x {repuesto['nombre']} - "
                  f"{repuesto['precio_unitario']:.2f}€ c/u = {repuesto['subtotal']:.2f}€")
```

### `taller_coches/reportes.py`
```python
"""Módulo para generar reportes y estadísticas."""

from .vehiculos import vehiculos_registrados
from .reparaciones import reparaciones, TIPOS_REPARACION

def reporte_vehiculos_por_marca():
    """
    Genera un reporte de vehículos agrupados por marca.
    
    Returns:
        dict: Diccionario con marcas y conteos
    """
    marcas = {}
    
    for vehiculo in vehiculos_registrados.values():
        marca = vehiculo['marca']
        if marca not in marcas:
            marcas[marca] = []
        marcas[marca].append(vehiculo)
    
    print("📊 REPORTE DE VEHÍCULOS POR MARCA")
    print("="*40)
    for marca, vehiculos in sorted(marcas.items()):
        print(f"{marca}: {len(vehiculos)} vehículos")
        for vehiculo in vehiculos:
            print(f"  • {vehiculo['modelo']} ({vehiculo['matricula']})")
    
    return marcas

def estadisticas_tipos_reparacion():
    """
    Genera estadísticas de los tipos de reparación más comunes.
    
    Returns:
        dict: Estadísticas por tipo de reparación
    """
    estadisticas = {}
    
    # Inicializar contadores
    for tipo in TIPOS_REPARACION:
        estadisticas[tipo] = {
            'cantidad': 0,
            'horas_total': 0,
            'costo_total': 0.0
        }
    
    # Contar reparaciones
    for reparacion in reparaciones.values():
        tipo = reparacion['tipo']
        if tipo in estadisticas:
            estadisticas[tipo]['cantidad'] += 1
            estadisticas[tipo]['horas_total'] += reparacion['horas_trabajo']
            estadisticas[tipo]['costo_total'] += reparacion['costo_total']
    
    print("📈 ESTADÍSTICAS POR TIPO DE REPARACIÓN")
    print("="*50)
    
    # Ordenar por cantidad de reparaciones
    tipos_ordenados = sorted(estadisticas.items(), 
                           key=lambda x: x[1]['cantidad'], reverse=True)
    
    for tipo, stats in tipos_ordenados:
        if stats['cantidad'] > 0:
            promedio_horas = stats['horas_total'] / stats['cantidad']
            promedio_costo = stats['costo_total'] / stats['cantidad']
            
            print(f"{tipo.upper()}:")
            print(f"  Reparaciones: {stats['cantidad']}")
            print(f"  Horas totales: {stats['horas_total']:.1f}")
            print(f"  Promedio horas: {promedio_horas:.1f}")
            print(f"  Costo total: {stats['costo_total']:.2f}€")
            print(f"  Promedio costo: {promedio_costo:.2f}€")
            print("-"*30)
    
    return estadisticas

def vehiculos_mas_reparados(limite=5):
    """
    Lista los vehículos con más reparaciones.
    
    Args:
        limite (int): Número máximo de vehículos a mostrar
    
    Returns:
        list: Lista de vehículos ordenados por número de reparaciones
    """
    vehiculos_con_reparaciones = []
    
    for vehiculo in vehiculos_registrados.values():
        num_reparaciones = len(vehiculo['reparaciones_realizadas'])
        if num_reparaciones > 0:
            vehiculos_con_reparaciones.append((vehiculo, num_reparaciones))
    
    # Ordenar por número de reparaciones
    vehiculos_ordenados = sorted(vehiculos_con_reparaciones, 
                               key=lambda x: x[1], reverse=True)
    
    print(f"🏆 TOP {limite} VEHÍCULOS MÁS REPARADOS")
    print("="*40)
    
    for i, (vehiculo, num_reparaciones) in enumerate(vehiculos_ordenados[:limite], 1):
        print(f"{i}. {vehiculo['marca']} {vehiculo['modelo']} ({vehiculo['matricula']})")
        print(f"   Reparaciones: {num_reparaciones}")
        print(f"   Propietario: {vehiculo['propietario']}")
        print("-"*30)
    
    return vehiculos_ordenados[:limite]

def ingresos_totales():
    """
    Calcula los ingresos totales del taller.
    
    Returns:
        dict: Información sobre ingresos
    """
    ingresos_info = {
        'total_facturado': 0.0,
        'reparaciones_facturadas': 0,
        'reparaciones_pendientes': 0,
        'promedio_por_reparacion': 0.0
    }
    
    for reparacion in reparaciones.values():
        if reparacion['estado'] == 'finalizada' and reparacion['costo_total'] > 0:
            ingresos_info['total_facturado'] += reparacion['costo_total']
            ingresos_info['reparaciones_facturadas'] += 1
        elif reparacion['estado'] == 'en_proceso':
            ingresos_info['reparaciones_pendientes'] += 1
    
    if ingresos_info['reparaciones_facturadas'] > 0:
        ingresos_info['promedio_por_reparacion'] = (
            ingresos_info['total_facturado'] / 
            ingresos_info['reparaciones_facturadas']
        )
    
    print("💰 RESUMEN DE INGRESOS")
    print("="*30)
    print(f"Total facturado: {ingresos_info['total_facturado']:.2f}€")
    print(f"Reparaciones facturadas: {ingresos_info['reparaciones_facturadas']}")
    print(f"Reparaciones pendientes: {ingresos_info['reparaciones_pendientes']}")
    print(f"Promedio por reparación: {ingresos_info['promedio_por_reparacion']:.2f}€")
    
    return ingresos_info

def reporte_completo():
    """Genera un reporte completo del taller."""
    print("\n🔧 REPORTE COMPLETO DEL TALLER")
    print("="*60)
    
    print(f"\nVehículos registrados: {len(vehiculos_registrados)}")
    print(f"Reparaciones totales: {len(reparaciones)}")
    
    # Estadísticas por estado
    en_proceso = len([r for r in reparaciones.values() if r['estado'] == 'en_proceso'])
    finalizadas = len([r for r in reparaciones.values() if r['estado'] == 'finalizada'])
    
    print(f"Reparaciones en proceso: {en_proceso}")
    print(f"Reparaciones finalizadas: {finalizadas}")
    
    print("\n")
    reporte_vehiculos_por_marca()
    print("\n")
    estadisticas_tipos_reparacion()
    print("\n")
    vehiculos_mas_reparados(3)
    print("\n")
    ingresos_totales()
```

### `taller_coches/utils.py`
```python
"""Módulo de utilidades y funciones auxiliares."""

import random
import string

def validar_matricula(matricula):
    """
    Valida y normaliza una matrícula española.
    
    Args:
        matricula (str): Matrícula a validar
    
    Returns:
        str: Matrícula normalizada
    
    Raises:
        ValueError: Si la matrícula no es válida
    """
    if not matricula or not isinstance(matricula, str):
        raise ValueError("La matrícula debe ser una cadena de texto")
    
    matricula = matricula.upper().replace(" ", "").replace("-", "")
    
    # Formato básico: 4 números + 3 letras (ej: 1234ABC)
    if len(matricula) != 7:
        raise ValueError("La matrícula debe tener 7 caracteres (ej: 1234ABC)")
    
    if not matricula[:4].isdigit():
        raise ValueError("Los primeros 4 caracteres deben ser números")
    
    if not matricula[4:].isalpha():
        raise ValueError("Los últimos 3 caracteres deben ser letras")
    
    return matricula

def validar_telefono(telefono):
    """
    Valida un número de teléfono.
    
    Args:
        telefono (str): Teléfono a validar
    
    Returns:
        str: Teléfono normalizado
    
    Raises:
        ValueError: Si el teléfono no es válido
    """
    if not telefono or not isinstance(telefono, str):
        raise ValueError("El teléfono debe ser una cadena de texto")
    
    # Limpiar espacios, guiones y paréntesis
    telefono_limpio = telefono.replace(" ", "").replace("-", "").replace("(", "").replace(")", "")
    
    # Verificar que solo contenga números y el símbolo +
    if not all(c.isdigit() or c == '+' for c in telefono_limpio):
        raise ValueError("El teléfono solo puede contener números y el símbolo +")
    
    # Longitud básica (9 dígitos españoles o más con prefijo internacional)
    if telefono_limpio.startswith('+'):
        if len(telefono_limpio) < 10:
            raise ValueError("Teléfono internacional muy corto")
    else:
        if len(telefono_limpio) != 9:
            raise ValueError("El teléfono español debe tener 9 dígitos")
    
    return telefono_limpio

def limpiar_texto(texto):
    """
    Limpia y normaliza un texto.
    
    Args:
        texto (str): Texto a limpiar
    
    Returns:
        str: Texto limpio y normalizado
    """
    if not texto:
        return ""
    
    # Eliminar espacios extra y capitalizar
    return " ".join(texto.strip().split()).title()

def generar_id_unico():
    """
    Genera un ID único para reparaciones.
    
    Returns:
        str: ID único
    """
    # Formato: REP + 4 números + 2 letras (ej: REP2024AB)
    numeros = ''.join(random.choices(string.digits, k=4))
    letras = ''.join(random.choices(string.ascii_uppercase, k=2))
    return f"REP{numeros}{letras}"

def formatear_moneda(cantidad):
    """
    Formatea una cantidad como moneda europea.
    
    Args:
        cantidad (float): Cantidad a formatear
    
    Returns:
        str: Cantidad formateada
    """
    return f"{cantidad:.2f}€"

def es_numero_positivo(valor):
    """
    Verifica si un valor es un número positivo.
    
    Args:
        valor: Valor a verificar
    
    Returns:
        bool: True si es positivo, False si no
    """
    try:
        numero = float(valor)
        return numero > 0
    except (ValueError, TypeError):
        return False

def validar_año(año):
    """
    Valida un año de fabricación de vehículo.
    
    Args:
        año (int): Año a validar
    
    Returns:
        bool: True si es válido, False si no
    """
    return isinstance(año, int) and 1980 <= año <= 2025
```

### `taller_coches/main.py`
```python
"""Programa principal del sistema de taller."""

# Importaciones desde nuestros módulos
from .vehiculos import (
    registrar_vehiculo, listar_vehiculos, buscar_vehiculo, 
    actualizar_kilometraje
)
from .reparaciones import (
    crear_reparacion, finalizar_reparacion, listar_reparaciones,
    agregar_repuesto_reparacion
)
from .facturacion import generar_factura, imprimir_factura
from .reportes import reporte_completo, estadisticas_tipos_reparacion
from .utils import formatear_moneda

def inicializar_datos_ejemplo():
    """Carga datos de ejemplo en el sistema."""
    print("📝 Cargando datos de ejemplo...")
    
    # Registrar vehículos de ejemplo
    vehiculos_ejemplo = [
        ("1234ABC", "Toyota", "Corolla", 2020, "Juan Pérez", "666123456"),
        ("5678DEF", "BMW", "Serie 3", 2019, "María García", "677987654"),
        ("9012GHI", "Volkswagen", "Golf", 2021, "Carlos López", "688456789"),
        ("3456JKL", "Ford", "Focus", 2018, "Ana Martín", "699321654"),
        ("7890MNO", "Seat", "León", 2022, "Luis González", "655789123")
    ]
    
    for matricula, marca, modelo, año, propietario, telefono in vehiculos_ejemplo:
        try:
            registrar_vehiculo(matricula, marca, modelo, año, propietario, telefono)
        except ValueError as e:
            print(f"Error registrando {matricula}: {e}")
    
    # Crear algunas reparaciones
    reparaciones_ejemplo = [
        ("1234ABC", "Cambio de aceite y filtros", "motor", "José Mecánico"),
        ("5678DEF", "Revisión sistema de frenos", "frenos", "Pedro Técnico"),
        ("1234ABC", "Reparación aire acondicionado", "climatizacion", "Ana Especialista"),
        ("9012GHI", "Cambio de neumáticos", "neumaticos", "José Mecánico")
    ]
    
    ids_reparaciones = []
    for matricula, descripcion, tipo_rep, mecanico in reparaciones_ejemplo:
        try:
            id_rep = crear_reparacion(matricula, descripcion, tipo_rep, mecanico)
            ids_reparaciones.append(id_rep)
        except ValueError as e:
            print(f"Error creando reparación: {e}")
    
    # Finalizar algunas reparaciones
    if len(ids_reparaciones) >= 2:
        try:
            # Finalizar primera reparación
            finalizar_reparacion(ids_reparaciones[0], 2.5)
            agregar_repuesto_reparacion(ids_reparaciones[0], "Aceite motor 5L", 1, 25.50)
            agregar_repuesto_reparacion(ids_reparaciones[0], "Filtro aceite", 1, 8.90)
            
            # Finalizar segunda reparación
            finalizar_reparacion(ids_reparaciones[1], 4.0)
            agregar_repuesto_reparacion(ids_reparaciones[1], "Pastillas freno delanteras", 1, 45.00)
            agregar_repuesto_reparacion(ids_reparaciones[1], "Discos freno delanteros", 2, 35.50)
            
        except ValueError as e:
            print(f"Error finalizando reparaciones: {e}")
    
    return ids_reparaciones

def demostrar_facturacion(ids_reparaciones):
    """Demuestra el sistema de facturación."""
    print("\n💰 DEMOSTRACIÓN DE FACTURACIÓN")
    print("="*50)
    
    # Generar factura para la primera reparación finalizada
    reparaciones_finalizadas = listar_reparaciones('finalizada')
    
    if reparaciones_finalizadas:
        primera_reparacion = reparaciones_finalizadas[0]
        id_reparacion = primera_reparacion['id']
        
        print(f"Generando factura para reparación: {id_reparacion}")
        
        try:
            # Factura sin descuento
            factura = generar_factura(id_reparacion)
            imprimir_factura(factura)
            
            # Factura con descuento
            print(f"\n{'-'*50}")
            print("FACTURA CON DESCUENTO DEL 10%:")
            factura_descuento = generar_factura(id_reparacion, 10)
            imprimir_factura(factura_descuento)
            
        except ValueError as e:
            print(f"Error generando factura: {e}")

def menu_interactivo():
    """Menú interactivo básico para probar funciones."""
    
    while True:
        print("\n🔧 SISTEMA DE TALLER - MENÚ PRINCIPAL")
        print("="*45)
        print("1. Ver todos los vehículos")
        print("2. Ver todas las reparaciones")
        print("3. Ver estadísticas de reparaciones")
        print("4. Ver reporte completo")
        print("5. Ver reparaciones en proceso")
        print("6. Ver reparaciones finalizadas")
        print("0. Salir")
        
        opcion = input("\nSeleccione una opción: ").strip()
        
        if opcion == "1":
            print("\n🚗 VEHÍCULOS REGISTRADOS:")
            vehiculos = listar_vehiculos()
            if vehiculos:
                for vehiculo in vehiculos:
                    print(f"  {vehiculo['matricula']} - {vehiculo['marca']} {vehiculo['modelo']} "
                          f"({vehiculo['año']}) - {vehiculo['propietario']}")
            else:
                print("  No hay vehículos registrados")
        
        elif opcion == "2":
            print("\n🔧 TODAS LAS REPARACIONES:")
            reparaciones = listar_reparaciones()
            if reparaciones:
                for rep in reparaciones:
                    estado_emoji = "🟢" if rep['estado'] == 'finalizada' else "🟡"
                    print(f"  {estado_emoji} {rep['id']} - {rep['matricula']} - "
                          f"{rep['descripcion']} ({rep['estado']})")
            else:
                print("  No hay reparaciones registradas")
        
        elif opcion == "3":
            estadisticas_tipos_reparacion()
        
        elif opcion == "4":
            reporte_completo()
        
        elif opcion == "5":
            print("\n🟡 REPARACIONES EN PROCESO:")
            reparaciones_proceso = listar_reparaciones('en_proceso')
            if reparaciones_proceso:
                for rep in reparaciones_proceso:
                    print(f"  {rep['id']} - {rep['matricula']} - "
                          f"{rep['descripcion']} - {rep['mecanico']}")
            else:
                print("  No hay reparaciones en proceso")
        
        elif opcion == "6":
            print("\n🟢 REPARACIONES FINALIZADAS:")
            reparaciones_finalizadas = listar_reparaciones('finalizada')
            if reparaciones_finalizadas:
                for rep in reparaciones_finalizadas:
                    costo = formatear_moneda(rep['costo_total']) if rep['costo_total'] > 0 else "Sin facturar"
                    print(f"  {rep['id']} - {rep['matricula']} - "
                          f"{rep['descripcion']} - {costo}")
            else:
                print("  No hay reparaciones finalizadas")
        
        elif opcion == "0":
            print("¡Gracias por usar el sistema de taller!")
            break
        
        else:
            print("❌ Opción no válida. Intente de nuevo.")

def main():
    """Función principal del programa."""
    print("🔧 SISTEMA DE GESTIÓN DE TALLER DE COCHES")
    print("="*50)
    
    # Inicializar con datos de ejemplo
    ids_reparaciones = inicializar_datos_ejemplo()
    
    # Demostrar facturación
    demostrar_facturacion(ids_reparaciones)
    
    # Mostrar estadísticas iniciales
    print(f"\n📊 ESTADO INICIAL DEL SISTEMA")
    print(f"Vehículos registrados: {len(listar_vehiculos())}")
    print(f"Reparaciones totales: {len(listar_reparaciones())}")
    print(f"Reparaciones finalizadas: {len(listar_reparaciones('finalizada'))}")
    
    # Menú interactivo
    menu_interactivo()

if __name__ == "__main__":
    main()
```

## 📚 TAREAS Y EJERCICIOS

### **Ejercicio 1: Completar Funcionalidades Básicas**
Implementa las siguientes funciones que faltan:

1. **En `vehiculos.py`:**
   - `eliminar_vehiculo(matricula)`: Elimina un vehículo del sistema
   - `buscar_vehiculos_por_propietario(nombre_propietario)`: Busca vehículos por propietario

2. **En `reparaciones.py`:**
   - `cancelar_reparacion(id_reparacion, motivo)`: Cancela una reparación
   - `reasignar_mecanico(id_reparacion, nuevo_mecanico)`: Cambia el mecánico asignado

### **Ejercicio 2: Mejoras en Facturación**
Extiende el módulo `facturacion.py`:

1. Crea una función `generar_presupuesto(matricula, descripcion, horas_estimadas, repuestos_estimados)`
2. Implementa `registrar_pago(id_reparacion, metodo_pago, fecha_pago)`
3. Añade función `facturas_pendientes_cobro()`

### **Ejercicio 3: Reportes Avanzados**
En el módulo `reportes.py`, implementa:

1. `reporte_mensual(mes, año)`: Reporte de actividad de un mes específico
2. `mecanicos_mas_productivos()`: Ranking de mecánicos por horas trabajadas
3. `analisis_rentabilidad_por_tipo()`: Análisis de rentabilidad por tipo de reparación

### **Ejercicio 4: Validaciones Avanzadas**
En `utils.py`, añade:

1. `validar_email(email)`: Validación de correos electrónicos
2. `calcular_antiguedad_vehiculo(año)`: Calcula años desde fabricación
3. `formatear_duracion(horas)`: Convierte horas a formato "X días, Y horas"

### **Ejercicio 5: Sistema de Citas**
Crea un nuevo módulo `citas.py` que incluya:

1. `programar_cita(matricula, fecha, hora, tipo_servicio)`
2. `listar_citas_dia(fecha)`
3. `confirmar_cita(id_cita)`
4. `reagendar_cita(id_cita, nueva_fecha, nueva_hora)`

## 🎯 CRITERIOS DE EVALUACIÓN

### **Funcionalidad (40%)**
- ✅ Todas las funciones implementadas funcionan correctamente
- ✅ Manejo adecuado de errores con `try/except`
- ✅ Validación correcta de datos de entrada
- ✅ Lógica de negocio implementada correctamente

### **Organización del Código (25%)**
- ✅ Uso correcto de módulos y paquetes
- ✅ Separación adecuada de responsabilidades
- ✅ Importaciones correctas entre módulos
- ✅ Estructura de archivos ordenada

### **Documentación (20%)**
- ✅ Docstrings completos en todas las funciones
- ✅ Comentarios explicativos cuando sea necesario
- ✅ Nombres de variables y funciones descriptivos
- ✅ Ejemplos de uso en la documentación

### **Buenas Prácticas (15%)**
- ✅ Seguimiento de convenciones de nomenclatura Python (PEP 8)
- ✅ Uso eficiente de estructuras de datos
- ✅ Código reutilizable y modular
- ✅ Manejo de casos especiales y errores

## 🚀 EXTENSIONES OPCIONALES (Para estudiantes avanzados)

1. **Persistencia de Datos**: Implementar guardado/carga desde archivos JSON
2. **Sistema de Notificaciones**: Crear módulo para enviar recordatorios
3. **Interfaz Gráfica**: Añadir interfaz simple con tkinter
4. **API REST**: Convertir el sistema en una API usando Flask
5. **Base de Datos**: Migrar desde listas/diccionarios a SQLite

## 📖 RECURSOS DE APOYO

- **Documentación oficial de Python**: https://docs.python.org/3/
- **PEP 8 - Guía de estilo**: https://pep8.org/
- **Módulos y paquetes**: https://docs.python.org/3/tutorial/modules.html

---

**¡Buena suerte con el desarrollo del sistema de taller!** 🔧🚗

Este ejercicio te permitirá aplicar todos los conceptos de módulos y paquetes mientras desarrollas un sistema práctico y útil.