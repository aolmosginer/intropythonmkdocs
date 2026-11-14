---
layout: doc
title: Conceptos
sidebar: true
outline: [2, 3]
aside: true
---

# 1: Conceptos Fundamentales de Python

## 1.1. Tipos de Datos

Para que un programa pueda realizar cualquier tarea, primero debe ser capaz de representar la información con la que trabaja. En *Python*, los **tipos de datos** son la forma en que el lenguaje clasifica y entiende diferentes clases de valores, como números, texto o valores lógicos. Comprender estos tipos es el primer paso fundamental para escribir código coherente y funcional. A continuación, se presentan los cuatro tipos de datos básicos o primitivos.

### Números Enteros (`int`)

Representa números enteros, tanto positivos como negativos, sin componentes decimales. Son la base para contar y realizar cálculos aritméticos simples.

- **Ejemplos:** 42, -139, 2017

### Números de Punto Flotante (`float`)

Representa números que tienen un punto decimal. Se utilizan para mediciones precisas y cálculos que requieren fracciones.

- **Ejemplos:** 1.25, -42.3899, 5.0

### Cadenas de Texto (`str`)

Representa secuencias de caracteres, como palabras, frases o cualquier tipo de texto. Se definen encerrando los caracteres entre comillas.

Es crucial entender que **un número representado como texto no es lo mismo que un número**. Por ejemplo, 4 es un *int* con el que se puede operar matemáticamente, mientras que "4" es un *str* que representa el carácter "cuatro".

- **Ejemplos:** "Cristian", "Aprendo a programar", "98394255".

### Valores Lógicos (`bool`)

Representa uno de dos valores de verdad: `True` (Verdadero) o `False` (Falso). Estos son la base de la lógica y la toma de decisiones en la programación. Note que deben escribirse siempre con la primera letra en mayúscula.

- **Ejemplos:** `True`, `False`

Para verificar el tipo de dato de cualquier valor en Python, podemos usar la función `type()`. Por ejemplo, `type(42)` devolverá `<class 'int'>`, mientras que `type("Hola mundo")` devolverá `<class 'str'>`.

Una vez que entendemos cómo *Python* representa los datos, podemos empezar a realizar operaciones con ellos.

## 1.2. Operadores y Expresiones

Los **operadores** son los símbolos especiales que *Python* utiliza para realizar cálculos, comparaciones y otras manipulaciones de datos. Cuando combinamos valores y operadores, formamos una **expresión**, que es una instrucción que *Python* evalúa para producir un nuevo valor. Por ejemplo, `7 + 5` es una expresión que utiliza el operador + para producir el valor `12`.

### Operadores Aritméticos

Estos operadores realizan las operaciones matemáticas fundamentales.

| Operador | Descripción                                                             |
|----------|-------------------------------------------------------------------------|
| \+       | Suma dos valores numéricos                                              |
| \-       | Resta un valor numérico de otro                                         |
| \*       | Multiplica dos valores numéricos                                        |
| /        | Realiza una división estándar. El resultado es siempre un `float`       |
| //       | Realiza una división entera, descartando la parte decimal del resultado |
| %        | Operador de módulo. Devuelve el resto de una división entera            |
| \*\*     | Operador de exponenciación. Eleva un número a la potencia de otro       |

### Operadores Relacionales (de Comparación)

Estos operadores comparan dos valores y siempre devuelven un resultado *booleano* (`True` o `False`).

| Operador | Descripción       |
|----------|-------------------|
| <       | Menor que         |
| \>       | Mayor que         |
| ==       | Igual que         |
| !=       | Distinto de       |
| <=      | Menor o igual que |
| \>=      | Mayor o igual que |

### Operadores Lógicos

Estos operadores se aplican a valores *booleanos* para combinarlos y crear condiciones más complejas.

| Operador | Descripción                                                                |
|----------|----------------------------------------------------------------------------|
| not      | Negación. Invierte el valor *booleano* (`not True` es `False`)             |
| and      | Conjunción (Y). Devuelve `True` solo si ambos operandos son `True`         |
| or       | Disyunción (O). Devuelve `True` si al menos uno de los operandos es `True` |

### Operadores de Texto

Estos operadores están diseñados para trabajar con cadenas de texto (`str`).

| Operador | Descripción                                                           |
|----------|-----------------------------------------------------------------------|
| \+       | Concatenación. Une dos cadenas de texto                               |
| \*       | Repetición. Repite una cadena de texto un número determinado de veces |

Cuando las expresiones son complejas, como `(3+5//4-2)-2**4+3*(7-2)`, *Python* sigue un orden específico conocido como **precedencia de operadores** para evaluarlas. Para controlar este orden y asegurar que los cálculos se realicen como deseamos, podemos usar paréntesis (), ya que tienen la máxima prioridad. En ausencia de paréntesis, *Python* sigue un orden estricto: primero se evalúan las potencias (\*\*), luego la multiplicación y división (\*, /, //, %), y finalmente la suma y resta (+, -).

Pero, ¿de qué sirve calcular un valor si el programa lo olvida inmediatamente? Para construir programas útiles, necesitamos una forma de guardar estos resultados, y para ello, utilizaremos **variables**.

## 1.3. Variables y Asignación

El propósito fundamental de las **variables** es permitirnos guardar un valor y asignarle un nombre para poder recordarlo y utilizarlo en múltiples lugares de nuestro programa. Piensa en una variable como una etiqueta que le ponemos a un dato en la memoria del ordenador.

El proceso de crear una variable y darle un valor se llama **asignación**, y se realiza con el operador de asignación `=`. La sintaxis es simple:

```python
nombre = expresión
```

Por ejemplo, para almacenar el precio por hora en un programa de estacionamiento, escribiríamos: 

```python
pesos_por_hora = 200
```

Una vez que una variable ha sido creada, su valor puede ser actualizado en cualquier momento con una nueva asignación, un proceso conocido como **reasignación**.

Al nombrar variables, debemos seguir algunas reglas:

- Deben **empezar con una letra o un guion bajo** (\_)
- Pueden contener letras (mayúsculas y minúsculas), números y guiones bajos

- **Las mayúsculas y minúsculas importan**. Una variable llamada `Vivaldi` es diferente de una llamada `vivaldi`
- Utiliza sintaxis **snake_case** (ej: `mi_variable_nueva`) siempre que puedas

Es crucial evitar el uso de **"Palabras Reservadas"** como nombres de variables. Estas palabras, como `if`, `for`, `while`, `True`, y `False`, tienen un significado especial para *Python* y su uso como nombres de variables causará un error.

Si intentas usar una variable que no ha sido definida previamente (es decir, a la que no se le ha asignado un valor), *Python* generará un error de tipo `NameError`.

Con la capacidad de almacenar y recordar información, estamos listos para que nuestros programas empiecen a comunicarse con el mundo exterior.

## 1.4. Comentarios

En *Python*, los comentarios se utilizan para añadir notas dentro del código que ayuden a explicar su funcionamiento y aclarar partes complejas. Los comentarios no son ejecutados por el intérprete, por lo que **no afectan al comportamiento del programa**. Existen dos formas principales de escribir comentarios:

### Comentarios de una sola línea

Se crean utilizando el símbolo `#`. Todo lo que aparezca después de este símbolo en la misma línea será ignorado.

```python
# Este es un comentario de una sola línea
x = 10  # También se puede comentar al final de una línea de código
```

### Comentarios multilínea

Se pueden usar cadenas de texto multilínea con comillas triples (`"""` o `'''`). Estas cadenas no asignadas a una variable son ignoradas por el intérprete y se usan habitualmente para documentar bloques de código.

```python
"""
Este bloque sirve como comentario multilínea.
Se puede usar para explicar funciones extensas o fragmentos de código más complejos.
"""
print("Hola, Mundo")
```

