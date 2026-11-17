---
layout: doc
title: Funciones
sidebar: true
outline: [2, 3]
aside: true
---

# 7. Mòduls

Un mòdul és simplement un fitxer de *Python* amb extensió `.py` que conté definicions de funcions, classes i variables. Pots reutilitzar el codi d'un mòdul important-lo en altres arxius o programes. Vegem un exemple:

El següent codi pertany al mòdul `mi_modulo.py`.

```python
# mi_modulo.py
def saludar(nombre):
    return f"Hola, {nombre}!"
PI = 3.14159
```

Una vegada creat el mòdul, podem importar-lo a un altre programa i utilitzar les seues funcions i variables.

```python
# programa.py
import mi_modulo
print(mi_modulo.saludar("Juan"))  # Eixida: Hola, Juan!
print(mi_modulo.PI)               # Eixida: 3.14159
```

Quan hem importat un mòdul i volem utilitzar algun element d'aquest, hem d'usar el seu espai de noms seguit d'un punt i el nom de l'element que volem utilitzar. L'espai de noms no és més que el nom que hem indicat després de l'`import`.

## 7.1 Formes d'importar mòduls

### Importar tot el mòdul

```python
import mi_modulo                # L'espai de noms és => mi_modulo
print(mi_modulo.saludar("Ana"))  # S'ha d'usar l'espai de noms
```

### Importar elements específics

```python
from mi_modulo import saludar
print(saludar("Carlos"))       # No és necessari usar l'espai de noms
```

### Importar tots els elements

```python
from mi_modulo import *
print(saludar("Carlos"))       # No és necessari usar l'espai de noms
```

### Canviar el nom del mòdul

```python
import mi_modulo as mm
print(mm.PI)                # És necessari usar el nou espai de noms
```

## 7.2 Mòduls estàndard

*Python* inclou molts mòduls estàndard llestos per a utilitzar. Alguns exemples comuns són:

### Funcions matemàtiques `math`

```python
import math
print(math.sqrt(16))  # Eixida: 4.0
```

### Operacions del Sistema Operatiu `os`

```python
import os
print(os.getcwd())  # Obté el directori actual
```

### Generació de nombres aleatoris `random`

```python
import random
print(random.randint(1, 10))  # Nombre aleatori entre 1 i 10
```

### Tractament de dates i hores `datetime`

```python
from datetime import datetime, date
hoy = date.today()
ahora = datetime.now()
print(hoy)   # Eixida: 2026-01-25
print(hoy.year) # Eixida: 2026
print(hoy.month) # Eixida: 1
print(ahora)   # Eixida: 2026-01-25 18:35:47.188487
```

## 7.3 Ús de `__main__`

La construcció `if __name__ == "__main__":` és una forma estàndard d'assegurar-se que un bloc de codi només s'execute quan el fitxer s'executa directament, i no quan s'importa com a mòdul en un altre fitxer.

**Desglossament de la seua funció:**

- `__name__`: És una variable especial que es defineix automàticament.

Si el fitxer s'executa directament, `__name__` pren el valor de `__main__`.

Si el fitxer s'importa com a mòdul, `__name__` pren el nom del fitxer (sense l'extensió `.py`).

- `if __name__ == "__main__":`

Aquest condicional avalua si el fitxer està sent executat directament (i per tant no importat). Si la condició és `True`, el codi dins del bloc s'executarà.

**Per què és útil?:**

Això és especialment útil per:

- Separar el codi que ha d'executar-se només quan el fitxer és el "principal" del programa (com proves, lògica principal o execució directa).

- Permetre que el fitxer siga importat com a mòdul sense executar automàticament el seu codi principal.

### Exemple

A partir del següent codi:

```python
# Arxiu: mi_script.py
def funcion_util():
    print("Esta función se puede usar en otros módulos.")
if __name__ == "__main__":
    print("Este script se está ejecutando directamente")
    funcion_util()
```

Si executem `mi_script.py` directament per consola.

```python
$ python mi_script.py
# Eixida:
Este script se está ejecutando directamente.
Esta función se puede usar en otros módulos.
```

Si importem `mi_script.py` des d'un altre fitxer.

```python
import mi_script
mi_script.funcion_util()
# Eixida:
Esta función se puede usar en otros módulos.
```

El bloc dins de `if __name__ == "__main__":` no s'executarà perquè el fitxer no s'està executant directament.

## 7.4 Estructura d'un programa

Una vegada vistes les diferents variables, blocs, funcions i importacions, podem resumir tot l'exposat mitjançant un exemple de programa que mostra l'estructura típica d'un script en *Python*.

```python
# 1. Imports (mòduls externs o propis)
import math
import sys
# 2. Constants globals
PI = 3.14159
MAX_RETRIES = 5
# 3. Definició de funcions
def calcular_area_circulo(radio):
    return PI * radio ** 2
def saludar(nombre):
    print(f"Hola, {nombre}!")
# 4. Bloc principal (punt d'entrada del programa)
def main():
    saludar("Ana")
    area = calcular_area_circulo(5)
    print(f"El área del círculo es: {area:.2f}")
# 5. Comprovació si s'executa com a programa principal
if __name__ == "__main__":
    main()
```

Típicament, el codi principal d'un programa *Python* es defineix dins de la funció `main()`, que serà cridada directament després d'avaluar l'`if __name__ == "__main__"`.

---
## EXERCICIS
### Exercici 1 - Importar
Modifica [l'exercici de funcions](5-funcions.md) creant un mòdul. ​

Després importa la funció `salutacio()` i usa-la en un nou programa.​
```text
Bona vesprada Aitana
Bon dia Marc
```
El resultat és el mateix, però el programa en aquest cas utilitza un mòdul importat.

### Exercici 2 - Aleatori
Crea un programa en el qual:​

- es demanen a l'usuari 2 enters (`a` i `b`)​
- es crea un número `c` aleatori entre estos enters​
- es mostra per pantalla el missatge **“El número `c` és un enter aleatori entre `a` i `b`”​**

S'han d'incloure en un mòdul:​

- la funció que retorna el número aleatori​
- la funció que mostra el missatge per pantalla (no retorna res, només fa el `print`)​

El programa principal importarà les funcions del mòdul i les usarà com corresponga​.

```text
Primer enter: 5
Segon enter: 46
El número 29 és un enter aleatori entre 5 i 46
```

### Exercici 3 - \_\_name\_\_
Modifica l'exercici anterior incloent l'ús de `__name__` i creant la funció `principal()` com a punt d'entrada del programa principal​.
```text
Primer enter: 234
Segon enter: 7655
El número 3953 és un enter aleatori entre 234 i 7655
```
El resultat per pantalla no ha de canviar.