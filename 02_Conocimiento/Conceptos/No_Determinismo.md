---
tipo: concepto
area: Teoria_Computacion
tema: Automatas
version: 1.0
estado: introduccion
fuente: 1automatas-2026-2.html
---

# No Determinismo

## Motivación

El [[Clausura_De_Lenguajes_Regulares|teorema de clausura bajo concatenación]] plantea el siguiente problema.

Dados dos autómatas:

$$
A_1
$$

y:

$$
A_2
$$

queremos construir un autómata que acepte una cadena cuando pueda dividirse como:

$$
w=xy
$$

donde:

$$
x\in L(A_1)
$$

y:

$$
y\in L(A_2)
$$

---

## El problema

El nuevo autómata necesita decidir en qué momento termina la parte correspondiente a $A_1$ y comienza la parte correspondiente a $A_2$.

Pero no necesariamente conoce de antemano la posición correcta.

El material expresa esta dificultad como:

> El autómata no sabe en qué momento dividir su entrada.

Por esta razón se introduce un modelo con mayores posibilidades:

$$
\boxed{\text{No Determinismo}}
$$

---

## Estado de la nota

Esta nota contiene únicamente la motivación introducida en la clase.

Los detalles formales del [[Automata_Finito_No_Determinista|Autómata Finito No Determinista]], sus transiciones y su relación con los AFD deben agregarse cuando aparezca ese contenido en clase.

---

## Relaciones

- [[Automata_Finito_Determinista]]
- [[Lenguaje_Regular]]
- [[Clausura_De_Lenguajes_Regulares]]