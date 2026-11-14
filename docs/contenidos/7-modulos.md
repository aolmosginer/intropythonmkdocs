---
layout: doc
title: Funciones
sidebar: true
outline: [2, 3]
aside: true
---

# 7. Módulos

Un módulo es simplemente un fichero de *Python* con extensión .py que contiene definiciones de funciones, clases y variables. Puedes reutilizar el código de un módulo importándolo en otros archivos o programas. Veamos un ejemplo:

El siguiente código pertenece al módulo “mi_modulo.py”.

```python
# mi_modulo.py
def saludar(nombre):
    return f"Hola, {nombre}!"
PI = 3.14159
```

Una vez creado el módulo, podemos importarlo a otro programa y utilizar sus funciones y variables.

```python
# programa.py
import mi_modulo
print(mi_modulo.saludar("Juan"))  # Salida: Hola, Juan!
print(mi_modulo.PI)               # Salida: 3.14159
```

Cuando hemos importado un módulo y queremos utilizar algún elemento del mismo, tenemos que usar su espacio de nombres seguido de un punto y el nombre del elemento que queremos utilizar. El espacio de nombres no es más que el nombre que hemos indicado después del import.

## 7.1 Formas de importar módulos

### Importar todo el módulo

```python
import mi_modulo                # El espacio de nombres es => mi_modulo
print(mi_modulo.saludar("Ana"))  # Se debe usar el espacio de nombres
```

### Importar elementos específicos

```python
from mi_modulo import saludar
print(saludar("Carlos"))       # No es necesario usar el espacio de nombres
```

### Importar todos los elementos

```python
from mi_modulo import *
print(saludar("Carlos"))       # No es necesario usar el espacio de nombres
```

### Renombrar el módulo

```python
import mi_modulo as mm
print(mm.PI)                # Es necesario usar el nuevo espacio de nombres
```

## 7.2 Módulos estándar

*Python* incluye muchos módulos estándar listos para utilizar. Algunos ejemplos comunes son:

- Funciones matemáticas math:

```python
import math
print(math.sqrt(16))  # Salida: 4.0
```

- Operaciones del Sistema Operativo os:

```python
import os
print(os.getcwd())  # Obtiene el directorio actual
```

- Generación de números aleatorios random:

```python
import random
print(random.randint(1, 10))  # Número aleatorio entre 1 y 10
```

- Tratamiento de fechas y horas datetime:

```python
from datetime import datetime, date
hoy = date.today()
ahora = datetime.now()
print(hoy)   # Salida: 2026-01-25
print(hoy.year) # Salida: 2026
print(hoy.month) # Salida: 1
print(ahora)   # Salida: 2026-01-25 18:35:47.188487
```

## 7.3 Uso de \_\_main\_\_

La construcción if \_\_name\_\_ == "\_\_main\_\_": es una forma estándar de asegurarse que un bloque de código solo se ejecute cuando el fichero se ejecuta directamente, y no cuando se importa como un módulo en otro fichero.

**Desglose de su función:**

- \_\_name\_\_: Es una variable especial que se define automáticamente.

Si el fichero se ejecuta directamente, \_\_name\_\_ toma el valor de "\_\_main\_\_".

Si el fichero se importa como módulo, \_\_name\_\_ toma el nombre del fichero (sin la extensión .py).

- if \_\_name\_\_ == "\_\_main\_\_":

Este condicional evalúa si el fichero está siendo ejecutado directamente (y por lo tanto no importado). Si la condición es verdadera, el código dentro del bloque se ejecutará.

**¿Por qué es útil?:**

Esto es especialmente útil por:

- Separar el código que tiene que ejecutarse solo cuando el fichero es el "principal" del programa (como pruebas, lógica principal o ejecución directa).

- Permitir que el fichero sea importado como módulo sin ejecutar automáticamente su código principal.

### Ejemplo

A partir del siguiente código:

```python
# Archivo: mi_script.py
def funcion_util():
    print("Esta función se puede usar en otros módulos.")
if __name__ == "__main__":
    print("Este script se está ejecutando directamente")
    funcion_util()
```

Si ejecutamos *mi_script.py* directamente por consola.

```python
$ python mi_script.py
# Salida:
Este script se está ejecutando directamente.
Esta función se puede usar en otros módulos.
```

Si importamos *mi_script.py* desde otro fichero.

```python
import mi_script
mi_script.funcion_util()
# Salida:
Esta función se puede usar en otros módulos.
```

El bloque dentro de if \_\_name\_\_ == "\_\_main\_\_": no se ejecutará porque el fichero no se está ejecutando directamente.

## 7.4 Estructura de un programa

Una vez vistas las diferentes variables, bloques, funciones e importaciones, podemos resumir todo lo expuesto mediante un ejemplo de programa que muestra la estructura típica de un script en Python.

```python
# 1. Imports (módulos externos o propios)
import math
import sys
# 2. Constantes globales
PI = 3.14159
MAX_RETRIES = 5
# 3. Definición de funciones
def calcular_area_circulo(radio):
    return PI * radio ** 2
def saludar(nombre):
    print(f"Hola, {nombre}!")
# 4. Bloque principal (punto de entrada del programa)
def main():
    saludar("Ana")
    area = calcular_area_circulo(5)
    print(f"El área del círculo es: {area:.2f}")
# 5. Comprobación si se ejecuta como programa principal
if __name__ == "__main__":
    main()
```

Típicamente, el código principal de un programa Python se define dentro de la función main(), que será llamada directamente tras evaluar el if \_\_name\_\_ == "\_\_main\_\_".

