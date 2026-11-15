---
layout: doc
title: Conceptos
sidebar: true
outline: [2, 3]
aside: true
---

# 1: Conceptes Fonamentals de Python

## 1.1. Tipus de Dades

Perquè un programa puga realitzar qualsevol tasca, primer ha de ser capaç de representar la informació amb la qual treballa. En *Python*, els **tipus de dades** són la manera com el llenguatge classifica i entén diferents classes de valors, com ara números, text o valors lògics. Comprendre aquests tipus és el primer pas fonamental per a escriure codi coherent i funcional. A continuació, es presenten els quatre tipus de dades bàsics o primitius.

### Nombres Enters (`int`)

Representa nombres enters, tant positius com negatius, sense components decimals. Són la base per a comptar i realitzar càlculs aritmètics simples.

- **Exemples:** 42, -139, 2017

### Nombres de Punt Flotant (`float`)

Representa nombres que tenen un punt decimal. S'utilitzen per a mesuraments precisos i càlculs que requereixen fraccions.

- **Exemples:** 1.25, -42.3899, 5.0

### Cadenes de Text (`str`)

Representa seqüències de caràcters, com ara paraules, frases o qualsevol tipus de text. Es defineixen tancant els caràcters entre cometes.

És crucial entendre que **un nombre representat com a text no és el mateix que un nombre**. Per exemple, 4 és un *int* amb el qual es pot operar matemàticament, mentre que "4" és un *str* que representa el caràcter "quatre".

- **Exemples:** "Cristian", "Aprenc a programar", "98394255".

### Valors Lògics (`bool`)

Representa un de dos valors de veritat: `True` (Veritable) o `False` (Fals). Aquests són la base de la lògica i la presa de decisions en la programació. Tingueu en compte que s'han d'escriure sempre amb la primera lletra en majúscula.

- **Exemples:** `True`, `False`

Per a verificar el tipus de dada de qualsevol valor en Python, podem utilitzar la funció `type()`. Per exemple, `type(42)` tornarà `<class 'int'>`, mentre que `type("Hola mundo")` tornarà `<class 'str'>`.

Una vegada que entenem com *Python* representa les dades, podem començar a realitzar operacions amb elles.

## 1.2. Operadors i Expressions

Els **operadors** són els símbols especials que *Python* utilitza per a realitzar càlculs, comparacions i altres manipulacions de dades. Quan combinem valors i operadors, formem una **expressió**, que és una instrucció que *Python* avalua per a produir un nou valor. Per exemple, `7 + 5` és una expressió que utilitza l'operador + per a produir el valor `12`.

### Operadors Aritmètics

Aquests operadors realitzen les operacions matemàtiques fonamentals.

| Operador | Descripció                                                              |
|----------|-------------------------------------------------------------------------|
| \+       | Suma dos valors numèrics                                                |
| \-       | Resta un valor numèric d'un altre                                       |
| \*       | Multiplica dos valors numèrics                                          |
| /        | Realitza una divisió estàndard. El resultat és sempre un `float`        |
| //       | Realitza una divisió entera, descartant la part decimal del resultat    |
| %        | Operador de mòdul. Torna el residu d'una divisió entera                 |
| \*\*     | Operador d'exponenciació. Eleva un nombre a la potència d'un altre      |

### Operadors Relacionals (de Comparació)

Aquests operadors comparen dos valors i sempre tornen un resultat *booleà* (`True` o `False`).

| Operador | Descripció        |
|----------|-------------------|
| <       | Menor que         |
| \>       | Major que         |
| ==       | Igual que         |
| !=       | Diferent de       |
| <=      | Menor o igual que |
| \>=      | Major o igual que |

### Operadors Lògics

Aquests operadors s'apliquen a valors *booleans* per a combinar-los i crear condicions més complexes.

| Operador | Descripció                                                                 |
|----------|----------------------------------------------------------------------------|
| not      | Negació. Inverteix el valor *booleà* (`not True` és `False`)               |
| and      | Conjunció (I). Torna `True` només si els dos operands són `True`           |
| or       | Disjunció (O). Torna `True` si almenys un dels operands és `True`          |

### Operadors de Text

Aquests operadors estan dissenyats per a treballar amb cadenes de text (`str`).

| Operador | Descripció                                                            |
|----------|-----------------------------------------------------------------------|
| \+       | Concatenació. Uneix dues cadenes de text                              |
| \*       | Repetició. Repeteix una cadena de text un nombre determinat de vegades |

Quan les expressions són complexes, com `(3+5//4-2)-2**4+3*(7-2)`, *Python* segueix un ordre específic conegut com a **precedència d'operadors** per a avaluar-les. Per a controlar aquest ordre i assegurar que els càlculs es realitzen com desitgem, podem utilitzar parèntesis (), ja que tenen la màxima prioritat. En absència de parèntesis, *Python* segueix un ordre estricte: primer s'avaluen les potències (\*\*), després la multiplicació i divisió (\*, /, //, %), i finalment la suma i resta (+, -).

Però, de què serveix calcular un valor si el programa l'oblida immediatament? Per a construir programes útils, necessitem una manera de guardar aquests resultats, i per a això, utilitzarem **variables**.

## 1.3. Variables i Assignació

El propòsit fonamental de les **variables** és permetre'ns guardar un valor i assignar-li un nom per a poder recordar-lo i utilitzar-lo en múltiples llocs del nostre programa. Pensa en una variable com una etiqueta que posem a una dada en la memòria de l'ordinador.

El procés de crear una variable i donar-li un valor s'anomena **assignació**, i es realitza amb l'operador d'assignació `=`. La sintaxi és simple:

```python
nombre = expresión
```

Per exemple, per a emmagatzemar el preu per hora en un programa d'estacionament, escriuríem: 

```python
pesos_por_hora = 200
```

Una vegada que una variable ha sigut creada, el seu valor pot ser actualitzat en qualsevol moment amb una nova assignació, un procés conegut com a **reassignació**.

En anomenar variables, hem de seguir algunes regles:

- Han de **començar amb una lletra o un guió baix** (\_)
- Poden contindre lletres (majúscules i minúscules), nombres i guions baixos

- **Les majúscules i minúscules importen**. Una variable anomenada `Vivaldi` és diferent d'una anomenada `vivaldi`
- Utilitza sintaxi **snake_case** (ex: `mi_variable_nueva`) sempre que puguis

És crucial evitar l'ús de **"Paraules Reservades"** com a noms de variables. Aquestes paraules, com `if`, `for`, `while`, `True`, i `False`, tenen un significat especial per a *Python* i el seu ús com a noms de variables causarà un error.

Si intentes utilitzar una variable que no ha sigut definida prèviament (és a dir, a la qual no se li ha assignat un valor), *Python* generarà un error de tipus `NameError`.

Amb la capacitat d'emmagatzemar i recordar informació, estem preparats perquè els nostres programes comencen a comunicar-se amb el món exterior.

## 1.4. Comentaris

En *Python*, els comentaris s'utilitzen per a afegir notes dins del codi que ajuden a explicar-ne el funcionament i aclarir parts complexes. Els comentaris no són executats per l'intèrpret, per la qual cosa **no afecten el comportament del programa**. Hi ha dues formes principals d'escriure comentaris:

### Comentaris d'una sola línia

Es creen utilitzant el símbol `#`. Tot el que aparega després d'aquest símbol en la mateixa línia serà ignorat.

```python
# Este és un comentari d'una sola línia
x = 10  # També es pot comentar al final d'una línia de codi
```

### Comentaris multilínia

Es poden usar cadenes de text multilínia amb cometes triples (`"""` o `'''`). Aquestes cadenes no assignades a una variable són ignorades per l'intèrpret i s'usen habitualment per a documentar blocs de codi.

```python
"""
Aquest bloc serveix com a comentari multilínia.
Es pot usar per a explicar funcions extenses o fragments de codi més complexos.
"""
print("Hola, Mundo")
```

