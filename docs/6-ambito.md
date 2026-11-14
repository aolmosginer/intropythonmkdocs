---
layout: doc
title: Funciones
sidebar: true
outline: [2, 3]
aside: true
---

# 6: Ámbito o *Scope*

En *Python*, el ámbito de una variable se refiere en la región del código donde una variable es accesible. *Python* tiene reglas específicas para determinar donde una variable se puede utilizar o modificar.

Una variable definida dentro de una función tiene un ámbito local. **Solo puede ser accedida dentro de esta función**. Si intentas acceder a una variable local fuera de su función, obtendrás un error.

```python
def funcion():
    y = 5   # Variable local
    print(y)

funcion()   # Salida: 5
print(y)  # Error: NameError, 'y' no está definida en ámbito global  
```

En cambio, **los bloques `if`, `for` y `while` no crean un nuevo ámbito** (*scope*). Solo las funciones, clases y módulos crean ámbitos nuevos.

```python
for i in range(3):
    print(i)  # Salida: 0, 1, 2
    x=10
print(i)  # Salida: 2 (la variable 'i' sigue accesible fuera del bucle)
print(x)  # Salida: 10
```

A diferencia otros lenguajes, en *Python* las variables definidas en un bucle o bloque no están limitadas a aquel bloque y pueden ser accedidas fuera de él.

