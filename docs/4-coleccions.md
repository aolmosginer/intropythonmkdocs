---
layout: doc
title: Coleccions-Llistes
sidebar: true
outline: [2, 3]
aside: true
---

# 4: Treballant amb Col·leccions: Llistes

## 4.1. Creació i Definició de Llistes

Fins ara, hem treballat amb dades individuals en variables. Les llistes representen un salt fonamental, permetent-nos gestionar col·leccions senceres de dades, sobre les quals podem iterar amb els bucles for que ja coneixem. Una **llista** és una seqüència ordenada d'elements que ens permet agrupar múltiples valors, de qualsevol tipus, en una sola variable.

La sintaxi per a crear una llista és senzilla: es tanquen entre claudàtors `[]` els elements separats per comes.

```python
[elemento0, elemento1, ...]
```

Les llistes són molt flexibles i poden contindre elements de diferents tipus de dades, fins i tot barrejats en la mateixa llista.

```python
no_olvidar = ["huevos", "platanos", "lechuga", "naranjas", 7000]
```

També és possible crear llistes buides, que poden ser omplides més tard, de dues maneres:

```python
vacia1 = []
vacia2 = list()
```

A més, un element d'una llista pot ser, al seu torn, una altra llista. Això es coneix com a **llistes aniuades** i permet crear estructures de dades més complexes.

Una vegada que hem creat una llista, el següent pas és aprendre a accedir i manipular els elements que conté.

## 4.2. Accés i Modificació d'Elements d'una Llista

Una característica clau de les llistes en *Python* és que són **mutables**, la qual cosa significa que el seu contingut pot ser modificat després de la seua creació. Podem canviar, afegir o eliminar elements.

Per a accedir a un element individual dins d'una llista, utilitzem el seu **índex**, que és la seua posició numèrica. És molt important recordar que en *Python* (i en la gran majoria dels llenguatges de programació), **la numeració dels índexs comença en 0**. El primer element està en l'índex 0, el segon en l'índex 1, i així successivament. La sintaxi per a accedir és `nombre_lista[indice]`.

```python
no_olvidar = ["huevos", "platanos", "lechuga", "naranjas", 7000]
print(no_olvidar[2]) 
# Eixida: lechuga
```

Per a modificar un element existent, simplement assignem un nou valor a la seua posició d'índex:

```python
no_olvidar[1] = "queso"
print(no_olvidar) 
# Eixida: ['huevos', 'queso', 'lechuga', 'naranjas', 7000]
```

A més d'accedir a elements individuals, podem accedir a subseccions d'una llista usant la tècnica de ***slicing***. La sintaxi és `lista[inicio:fin:step]`, i extrau una nova llista que conté els elements des de l'índex inici fins a fi - 1.

```python
print(no_olvidar[1:4]) 
# Eixida: ['queso', 'lechuga', 'naranjas']
```

Per a recórrer tots els elements d'una llista de manera senzilla, podem usar un bucle `for`:

```python
for elemento in no_olvidar:
    print("No olvides", elemento)
```

En aquest exemple, en cada iteració del bucle `for`, la variable element prendrà un valor diferent de la llista `no_olvidar`, començant pel primer `queso` i arribant fins a l'últim `7000`.

```python
No olvides huevos
No olvides platanos
No olvides lechuga
No olvides naranjas
No olvides 7000
```

Sabent com accedir i modificar elements existents, el següent problema és: com podem canviar el nombre total d'elements en una llista?

## 4.3. Afegir i Eliminar Elements

Les llistes són dinàmiques, la qual cosa significa que la seua grandària pot canviar durant l'execució d'un programa. *Python* ofereix diversos mètodes per a afegir i llevar elements d'una llista de manera controlada.

Per a afegir elements, podem utilitzar els següents mètodes:

- **`lista.append(elemento)`**: Afig un únic `elemento` al **final** de la llista

```python
frutas = ["manzana", "pera"]
frutas.append("naranja")
print(frutas)
# Resultat: ['manzana', 'pera', 'naranja']
```

- **`lista.extend(lista2)`**: Afig tots els elements de `lista2` al final de la llista original, estenent-la.

```python
numeros = [1, 2, 3]
mas_numeros = [4, 5, 6]
numeros.extend(mas_numeros)
print(numeros)
# Resultat: [1, 2, 3, 4, 5, 6]
```

- **`lista.insert(index, elemento)`**: Insereix un `elemento` en la posició específica indicada per `index`, desplaçant els elements existents cap a la dreta.

```python
colores = ["rojo", "verde", "azul"]
colores.insert(1, "amarillo")  # Insereix en la posició 1
print(colores)
# Resultat: ['rojo', 'amarillo', 'verde', 'azul']
```

Per a eliminar elements podem usar els següents mètodes:

- **`variable = lista.pop()`**: Elimina i retorna l'**últim** element de la llista.

```python
animales = ["gato", "perro", "conejo"]
ultimo = animales.pop()
print("Elemento eliminado:", ultimo)
print(animales)
# Resultat:
# Elemento eliminado: conejo
# ['gato', 'perro']
```

- **`variable = lista.pop(indice)`**: Si vols eliminar un element per `indice`.

```python
primer_animal = animales.pop(0)
print("Primer animal eliminado:", primer_animal)
# Resultat: Primer animal eliminado: gato
```

- **`variable = lista.remove(valor)`**: Elimina la primera aparició del `valor` indicat.

```python
numeros = [10, 20, 30, 20, 40]
numeros.remove(20)  # Elimina el primer 20 trobat
print(numeros)
# Resultat: [10, 30, 20, 40]
```

Ara que sabem com manipular l'estructura de les llistes, explorem altres funcions i mètodes útils que ens proporcionen informació sobre elles.

## 4.4. Funcions incorporades 

*Python* proporciona un conjunt de funcions i mètodes incorporats ([*Built-In Functions*](https://docs.python.org/es/3.13/library/functions.html)) que ens permeten realitzar operacions comunes sobre les llistes de manera molt eficient, sense haver d'escriure la lògica nosaltres mateixos.

- **`len(lista)`**: Torna un nombre enter que representa la quantitat d'elements que hi ha en la `lista`.

```python
edades = [18, 25, 30, 22]
cantidad = len(edades)
print("Número de elementos:", cantidad)
# Resultat: Número de elementos: 4
```

- **`elemento in lista`**: És un operador que verifica si un `elemento` existeix dins d'una `lista`. Torna `True` si el troba, i `False` en cas contrari.

```python
frutas = ["manzana", "naranja", "pera"]
print("manzana" in frutas)  # True
print("sandía" in frutas)   # False
```

- **`lista.index(elemento)`**: Torna la posició (índex) de la primera aparició d'un `elemento` en la llista. Si l'element no es troba en la llista, genera un error de tipus `ValueError`.

```python
colores = ["rojo", "verde", "azul", "verde"]
posicion = colores.index("verde")
print("Primer 'verde' encontrado en el índice:", posicion)
# Resultat: Primer 'verde' encontrado en el índice: 1
# COMPTE: Si l'element no existeix, ocorre un error:
# colores.index("amarillo")  # ValueError
```

- **`string.split(separador)`**: Encara que és un mètode de les cadenes de text `str`, és extremadament útil per a crear llistes. Converteix una cadena de text en una llista de subcadenes, dividint-la en cada aparició del `separador` especificat.

```python
texto = "Python,Java,C++,JavaScript"
lenguajes = texto.split(",")
print(lenguajes)
# Resultat: ['Python', 'Java', 'C++', 'JavaScript']
frase = "Hola mundo desde Python"
palabras = frase.split(" ")
print(palabras)
# Resultat: ['Hola', 'mundo', 'desde', 'Python']
```

- **`lista.sort()`**: Ordena els elements de la llista de manera ascendent. **Aquest mètode modifica la llista original**. Si s'aplica a una llista de llistes, ordena les sublistes basant-se en el primer element de cadascuna.

```python
numeros = [5, 2, 9, 1]
numeros.sort()
print(numeros)
# Resultat: [1, 2, 5, 9]
```

Amb un bon maneig de les llistes, podem començar a organitzar el nostre codi de manera més eficient utilitzant funcions.


---
## EXERCICIS
Implementa els següents passos:

1. Crea una llista buida anomenada "motxilla"
2. Afegix "Llaterna" i "Botella"
3. Inserix "Mapa" al principi de la llista
4. Mostra la llista de la següent forma

```text
1 - Mapa
2 - Llanterna
3 - Botella
```

[**--> Més activitats de bucles, llistes i funcions ací <--**](arxius/AltresActivitats.pdf)