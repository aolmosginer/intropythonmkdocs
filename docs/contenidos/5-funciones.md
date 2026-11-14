---
layout: doc
title: Funciones
sidebar: true
outline: [2, 3]
aside: true
---

# 5: Introducción a las Funciones personalizadas

## 5.1. Parámetros y Valor de Retorno

Las **funciones** personalizadas son bloques de código reutilizables diseñados para realizar una tarea específica. Nos permiten organizar nuestro código, evitar la repetición y hacerlo más legible. Dos conceptos clave en las funciones son los parámetros (o argumentos) y el valor de retorno.

Los **parámetros** son las variables que una función recibe para poder trabajar. Actúan como los "datos de entrada" de la función. Se definen entre los paréntesis en la declaración de la función:

```python
def mi_funcion(<parametro1>, <parametro2>, <parametro3> …):
    # Cuerpo de la función
```

Cuando llamamos a la función (la usamos), debemos proporcionar los valores que tomarán estos parámetros:

```python
mi_funcion(valor1, valor2)
```

El **valor de retorno** es el "resultado" que una función entrega al finalizar su ejecución. Para devolver un valor, se utiliza la palabra clave return, seguida del valor que se desea entregar.

Es importante destacar que la ejecución de la función termina inmediatamente en cuanto se encuentra una instrucción return. Cualquier código dentro de la función que se encuentre después de un return no será ejecutado.

Veamos un ejemplo que combina ambos conceptos. La siguiente función recibe un número como parámetro, realiza un cálculo y devuelve el resultado:

```python
def calculo(numero):
    resultado = (numero - 3) ** 3
    return resultado
# Para usar el valor de retorno, lo capturamos en una variable o lo usamos directamente
valor_calculado = calculo(8)
print(valor_calculado) # Salida: 125
```

Normalmente, las funciones tendrán varios parámetros y un valor de retorno, pero no es obligatorio. El siguiente ejemplo muestra una función sin parámetros ni valor de retorno.

```python
def saluda():
    print("Hola mundo")
    print("Soy Python !!")
saluda()      # Esta función no retorna ningún valor, solo imprime por pantalla
# Hola mundo
# Soy Python !!
```

## 5.2. Parámetros opcionales

Otra característica de las funciones es que pueden tener parámetros opcionales que, si no se declaran al llamar a la función, toman el valor por defecto definido.

```python
def multiplicar(a=0, b=1):
    return a * b
print(multiplicar(4, 3)) # Salida: 12
print(multiplicar(4))  # Salida: 4 
print(multiplicar())  # Salida:  0
```

Si no se pasa ningún valor a la función, utilizará los valores por defecto a=0 y b=1. Si se pasa un solo valor, será asignado a la primera variable a y por lo tanto b tomará el valor por defecto (0).

## 5.3. Varios valores de retorno

También podemos diseñar funciones que devuelvan más de un valor, asignando los diferentes valores separados por comas “, “ después del return.

```python
def operaciones(a, b):
    suma = a + b
    resta = a - b
    multi = a * b
    return suma, resta, multi
s,r,m = operaciones(10,5)
print("suma =", s, "resta =", r, "multiplicación =", m)
# Salida: suma = 15 resta = 5 multiplicación = 50
```

Al utilizar este tipo de funciones, debemos prever los valores que nos devolverá y almacenarlos en tantas variables como sea necesario (s,r,m = operaciones(10,5)).

Si no lo hacemos así, porque por ejemplo no sabemos cuántos valores nos va a devolver la función, **se devolverán todos los valores dentro de una *tupla*** que deberemos tratar como corresponda.

```python
def operaciones(a, b):
    suma = a + b
    resta = a - b
    multi = a * b
    return suma, resta, multi
resultados = operaciones(10,5)
print("suma =", resultados[0]) # Salida: suma = 15
print("resta =", resultados[1]) # Salida: resta = 5
print("multiplicación =", resultados[2]) # Salida: multiplicación = 50
```

De momento asumiremos que una *tupla* es como una lista\[\], pero que guarda valores inmutables (que no podemos modificar).

## 5.4. Ejemplo Práctico: Funciones Booleanas

Una función booleana es un tipo específico de función cuyo propósito es responder a una pregunta con un "sí" o un "no", es decir, que siempre devuelve un valor booleano (True o False). Son extremadamente útiles para encapsular la lógica de las condiciones.

Un ejemplo claro es una función que determina si un número es par. Recibe un número como parámetro y devuelve True si el número es divisible por 2, y False en caso contrario.

```python
def es_par(numero):
    if numero % 2 == 0:
        return True
    else:
        return False
print(es_par(8)) # Salida: True
print(es_par(7)) # Salida: False
```

**Refinando el Código Booleano**

La función es_par anterior es perfectamente correcta y funcional. Sin embargo, un programador con experiencia buscaría una forma más directa y concisa de escribirla. La expresión numero % 2 == 0 ya es en sí misma una expresión booleana: se evalúa como True si el número es par y False si no lo es.

Por lo tanto, podemos reescribir la función a una sola línea que devuelve directamente el resultado de esta expresión.

```python
def es_par(numero):
    return numero % 2 == 0
```

Este estilo es considerado más "Pythonic" —elegante, legible y eficiente.

Ambas versiones de la función producen exactamente el mismo resultado, pero la segunda demuestra una comprensión más profunda del lenguaje.

El uso de funciones para encapsular la lógica, como en es_par, hace que el código principal sea mucho más limpio y fácil de entender, promoviendo una buena organización y reutilización.


