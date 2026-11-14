---
layout: doc
title: Colecciones-Listas
sidebar: true
outline: [2, 3]
aside: true
---

# 4: Trabajando con Colecciones: Listas

## 4.1. Creación y Definición de Listas

Hasta ahora, hemos trabajado con datos individuales en variables. Las listas representan un salto fundamental, permitiéndonos gestionar colecciones enteras de datos, sobre las cuales podemos iterar con los bucles for que ya conocemos. Una **lista** es una secuencia ordenada de elementos que nos permite agrupar múltiples valores, de cualquier tipo, en una sola variable.

La sintaxis para crear una lista es sencilla: se encierran entre corchetes `[]` los elementos separados por comas.

```python
[elemento0, elemento1, ...]
```

Las listas son muy flexibles y pueden contener elementos de diferentes tipos de datos, incluso mezclados en la misma lista.

```python
no_olvidar = ["huevos", "palta", "lechuga", "naranjas", 7000]
```

También es posible crear listas vacías, que pueden ser llenadas más tarde, de dos formas:

```python
vacia1 = []
vacia2 = list()
```

Además, un elemento de una lista puede ser, a su vez, otra lista. Esto se conoce como **listas anidadas** y permite crear estructuras de datos más complejas.

Una vez que hemos creado una lista, el siguiente paso es aprender a acceder y manipular los elementos que contiene.

## 4.2. Acceso y Modificación de Elementos de una Lista

Una característica clave de las listas en *Python* es que son **mutables**, lo que significa que su contenido puede ser modificado después de su creación. Podemos cambiar, agregar o eliminar elementos.

Para acceder a un elemento individual dentro de una lista, utilizamos su **índice**, que es su posición numérica. Es muy importante recordar que en *Python* (y en la gran mayoría de los lenguajes de programación), **la numeración de los índices comienza en 0**. El primer elemento está en el índice 0, el segundo en el índice 1, y así sucesivamente. La sintaxis para acceder es `nombre_lista[indice]`.

```python
no_olvidar = ["huevos", "platanos", "lechuga", "naranjas", 7000]
print(no_olvidar[2]) 
# Salida: lechuga
```

Para modificar un elemento existente, simplemente asignamos un nuevo valor a su posición de índice:

```python
no_olvidar[1] = "queso"
print(no_olvidar) 
# Salida: ['huevos', 'queso', 'lechuga', 'naranjas', 7000]
```

Además de acceder a elementos individuales, podemos acceder a sub-secciones de una lista usando la técnica de ***slicing***. La sintaxis es `lista[inicio:fin:step]`, y extrae una nueva lista que contiene los elementos desde el índice inicio hasta fin - 1.

```python
print(no_olvidar[1:4]) 
# Salida: ['queso', 'lechuga', 'naranjas']
```

Para recorrer todos los elementos de una lista de manera sencilla, podemos usar un bucle `for`:

```python
for elemento in no_olvidar:
    print("No olvides", elemento)
```

En este ejemplo, en cada iteración del bucle `for`, la variable elemento tomará un valor diferente de la lista `no_olvidar`, comenzando por el primero `queso` y llegando hasta el último `7000`.

```python
# Salida
No olvides huevos
No olvides palta
No olvides lechuga
No olvides naranjas
No olvides 7000
```

Sabiendo cómo acceder y modificar elementos existentes, el siguiente problema es: ¿cómo podemos cambiar el número total de elementos en una lista?

## 4.3. Agregar y Eliminar Elementos

Las listas son dinámicas, lo que significa que su tamaño puede cambiar durante la ejecución de un programa. *Python* ofrece varios métodos para agregar y quitar elementos de una lista de forma controlada.

Para agregar elementos, podemos utilizar los siguientes métodos:

- **`lista.append(elemento)`**: Agrega un único `elemento` al **final** de la lista

```python
frutas = ["manzana", "pera"]
frutas.append("naranja")
print(frutas)
# Resultado: ['manzana', 'pera', 'naranja']
```

- **`lista.extend(lista2)`**: Agrega todos los elementos de `lista2` al final de la lista original, extendiéndola.

```python
numeros = [1, 2, 3]
mas_numeros = [4, 5, 6]
numeros.extend(mas_numeros)
print(numeros)
# Resultado: [1, 2, 3, 4, 5, 6]
```

- **`lista.insert(index, elemento)`**: Inserta un `elemento` en la posición específica indicada por `index`, desplazando los elementos existentes hacia la derecha.

```python
colores = ["rojo", "verde", "azul"]
colores.insert(1, "amarillo")  # Inserta en la posición 1
print(colores)
# Resultado: ['rojo', 'amarillo', 'verde', 'azul']
```

Para eliminar elementos podemos usar los siguientes métodos:

- **`variable = lista.pop()`**: Elimina y retorna el **último** elemento de la lista.

```python
animales = ["gato", "perro", "conejo"]
ultimo = animales.pop()
print("Elemento eliminado:", ultimo)
print(animales)
# Resultado:
# Elemento eliminado: conejo
# ['gato', 'perro']
```

- **`variable = lista.pop(indice)`**: Si quieres eliminar un elemento por `indice`.

```python
primer_animal = animales.pop(0)
print("Primer animal eliminado:", primer_animal)
# Resultado: Primer animal eliminado: gato
```

- **`variable = lista.remove(valor)`**: Elimina la primera aparición del `valor` indicado.

```python
numeros = [10, 20, 30, 20, 40]
numeros.remove(20)  # Elimina el primer 20 encontrado
print(numeros)
# Resultado: [10, 30, 20, 40]
```

Ahora que sabemos cómo manipular la estructura de las listas, exploremos otras funciones y métodos útiles que nos proporcionan información sobre ellas.

## 4.4. Funciones incorporadas 

*Python* proporciona un conjunto de funciones y métodos incorporados ([*Built-In Functions*](https://docs.python.org/es/3.13/library/functions.html)) que nos permiten realizar operaciones comunes sobre las listas de manera muy eficiente, sin tener que escribir la lógica nosotros mismos.

- **`len(lista)`**: Devuelve un número entero que representa la cantidad de elementos que hay en la `lista`.

```python
edades = [18, 25, 30, 22]
cantidad = len(edades)
print("Número de elementos:", cantidad)
# Resultado: Número de elementos: 4
```

- **`elemento in lista`**: Es un operador que verifica si un `elemento` existe dentro de una `lista`. Devuelve `True` si lo encuentra, y `False` en caso contrario.

```python
frutas = ["manzana", "naranja", "pera"]
print("manzana" in frutas)  # True
print("sandía" in frutas)   # False
```

- **`lista.index(elemento)`**: Devuelve la posición (índice) de la primera aparición de un `elemento` en la lista. Si el elemento no se encuentra en la lista, genera un error de tipo `ValueError`.

```python
colores = ["rojo", "verde", "azul", "verde"]
posicion = colores.index("verde")
print("Primer 'verde' encontrado en el índice:", posicion)
# Resultado: Primer 'verde' encontrado en el índice: 1
# OJO: Si el elemento no existe, ocurre un error:
# colores.index("amarillo")  # ValueError
```

- **`string.split(separador)`**: Aunque es un método de las cadenas de texto `str`, es extremadamente útil para crear listas. Convierte una cadena de texto en una lista de subcadenas, dividiéndola en cada aparición del `separador` especificado.

```python
texto = "Python,Java,C++,JavaScript"
lenguajes = texto.split(",")
print(lenguajes)
# Resultado: ['Python', 'Java', 'C++', 'JavaScript']
frase = "Hola mundo desde Python"
palabras = frase.split(" ")
print(palabras)
# Resultado: ['Hola', 'mundo', 'desde', 'Python']
```

- **`lista.sort()`**: Ordena los elementos de la lista de forma ascendente. **Este método modifica la lista original**. Si se aplica a una lista de listas, ordena las sub-listas basándose en el primer elemento de cada una.

```python
numeros = [5, 2, 9, 1]
numeros.sort()
print(numeros)
# Resultado: [1, 2, 5, 9]
```

Con un buen manejo de las listas, podemos empezar a organizar nuestro código de manera más eficiente utilizando funciones.


