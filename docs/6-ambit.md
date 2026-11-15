---
layout: doc
title: Funciones
sidebar: true
outline: [2, 3]
aside: true
---

# 6: Àmbit o *Scope*

En *Python*, l'àmbit d'una variable es refereix a la regió del codi on una variable és accessible. *Python* té regles específiques per a determinar on una variable es pot utilitzar o modificar.

Una variable definida dins d'una funció té un àmbit local. **Només pot ser accedida dins d'aquesta funció**. Si intentes accedir a una variable local fora de la seua funció, obtindràs un error.

```python
def funcion():
    y = 5   # Variable local
    print(y)

funcion()   # Eixida: 5
print(y)  # Error: NameError, 'y' no està definida en àmbit global  
```

En canvi, **els blocs `if`, `for` i `while` no creen un nou àmbit** (*scope*). Només les funcions, classes i mòduls creen àmbits nous.

```python
for i in range(3):
    print(i)  # Eixida: 0, 1, 2
    x=10
print(i)  # Eixida: 2 (la variable 'i' continua accessible fora del bucle)
print(x)  # Eixida: 10
```

A diferència d'altres llenguatges, en *Python* les variables definides en un bucle o bloc no estan limitades a aquell bloc i poden ser accedides fora d'ell.

