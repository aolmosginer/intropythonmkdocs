---
layout: doc
title: Funciones
sidebar: true
outline: [2, 3]
aside: true
---

# 5: Introducció a les Funcions personalitzades

## 5.1. Paràmetres i Valor de Retorn

Les **funcions** personalitzades són blocs de codi reutilitzables dissenyats per a realitzar una tasca específica. Ens permeten organitzar el nostre codi, evitar la repetició i fer-lo més llegible. Dos conceptes clau en les funcions són els paràmetres (o arguments) i el valor de retorn.

Els **paràmetres** són les variables que una funció rep per a poder treballar. Actuen com les "dades d'entrada" de la funció. Es defineixen entre els parèntesis en la declaració de la funció:

```python
def mi_funcion(<parametro1>, <parametro2>, <parametro3> …):
    # Cos de la funció
```

Quan cridem a la funció (l'usem), hem de proporcionar els valors que prendran aquests paràmetres:

```python
mi_funcion(valor1, valor2)
```

El **valor de retorn** és el "resultat" que una funció lliura en finalitzar la seua execució. Per a tornar un valor, s'utilitza la paraula clau `return`, seguida del valor que es vol lliurar.

És important destacar que l'execució de la funció acaba immediatament així que es troba una instrucció `return`. Qualsevol codi dins de la funció que es trobe després d'un `return` no serà executat.

Vegem un exemple que combina ambdós conceptes. La següent funció rep un nombre com a paràmetre, realitza un càlcul i torna el resultat:

```python
def calculo(numero):
    resultado = (numero - 3) ** 3
    return resultado
# Per a usar el valor de retorn, el capturem en una variable o l'usem directament
valor_calculado = calculo(8)
print(valor_calculado) # Eixida: 125
```

Normalment, les funcions tindran diversos paràmetres i un valor de retorn, però no és obligatori. L'exemple següent mostra una funció sense paràmetres ni valor de retorn.

```python
def saluda():
    print("Hola mundo")
    print("Soy Python !!")
saluda()      # Aquesta funció no retorna cap valor, només imprimeix per pantalla
# Hola mundo
# Soy Python !!
```

## 5.2. Paràmetres opcionals

Una altra característica de les funcions és que poden tindre paràmetres opcionals que, si no es declaren en cridar a la funció, prenen el valor per defecte definit.

```python
def multiplicar(a=0, b=1):
    return a * b
print(multiplicar(4, 3)) # Eixida: 12
print(multiplicar(4))  # Eixida: 4 
print(multiplicar())  # Eixida:  0
```

Si no es passa cap valor a la funció, utilitzarà els valors per defecte `a=0` i `b=1`. Si es passa un sol valor, serà assignat a la primera variable `a` i per tant `b` prendrà el valor per defecte `0`.

## 5.3. Diversos valors de retorn

També podem dissenyar funcions que tornen més d'un valor, assignant els diferents valors separats per comes `,` després del `return`.

```python
def operaciones(a, b):
    suma = a + b
    resta = a - b
    multi = a * b
    return suma, resta, multi
s,r,m = operaciones(10,5)
print("suma =", s, "resta =", r, "multiplicación =", m)
# Eixida: suma = 15 resta = 5 multiplicación = 50
```

En utilitzar aquest tipus de funcions, hem de preveure els valors que ens tornarà i emmagatzemar-los en tantes variables com siga necessari `s,r,m = operaciones(10,5)`.

Si no ho fem així, perquè per exemple no sabem quants valors ens tornarà la funció, **es tornaran tots els valors dins d'una `tupla`** que haurem de tractar com corresponga.

```python
def operaciones(a, b):
    suma = a + b
    resta = a - b
    multi = a * b
    return suma, resta, multi
resultados = operaciones(10,5)
print("suma =", resultados[0]) # Eixida: suma = 15
print("resta =", resultados[1]) # Eixida: resta = 5
print("multiplicación =", resultados[2]) # Eixida: multiplicación = 50
```

De moment assumirem que una `tupla` és com una `lista[]`, però que guarda valors immutables (que no podem modificar).

## 5.4. Exemple Pràctic: Funcions Booleanes

Una funció booleana és un tipus específic de funció el propòsit de la qual és respondre a una pregunta amb un "sí" o un "no", és a dir, que sempre torna un valor booleà (`True` o `False`). Són extremadament útils per a encapsular la lògica de les condicions.

Un exemple clar és una funció que determina si un nombre és parell. Rep un nombre com a paràmetre i torna `True` si el nombre és divisible per 2, i `False` en cas contrari.

```python
def es_par(numero):
    if numero % 2 == 0:
        return True
    else:
        return False
print(es_par(8)) # Eixida: True
print(es_par(7)) # Eixida: False
```

**Refinant el Codi Booleà**

La funció `es_par` anterior és perfectament correcta i funcional. No obstant això, un programador amb experiència buscaria una manera més directa i concisa d'escriure-la. L'expressió `numero % 2 == 0` ja és en si mateixa una expressió booleana: s'avalua com a `True` si el nombre és parell i `False` si no ho és.

Per tant, podem reescriure la funció a una sola línia que torna directament el resultat d'aquesta expressió.

```python
def es_par(numero):
    return numero % 2 == 0
```

Aquest estil és considerat més "Pythonic" — elegant, llegible i eficient.

Ambdues versions de la funció produeixen exactament el mateix resultat, però la segona demostra una comprensió més profunda del llenguatge.

L'ús de funcions per a encapsular la lògica, com en `es_par`, fa que el codi principal siga molt més net i fàcil d'entendre, promovent una bona organització i reutilització.


