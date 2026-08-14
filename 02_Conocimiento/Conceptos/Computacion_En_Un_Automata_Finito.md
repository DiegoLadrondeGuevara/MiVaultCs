---
tipo: concepto
area: Teoria_Computacion
tema: Automatas
version: 1.0
estado: activo
fuente: 1automatas-2026-2.html
---

# Computación En Un Autómata Finito

## Idea

Un autómata procesa una cadena recorriendo una secuencia de estados.

Sea:

$$
w=w_1w_2\ldots w_n
$$

donde:

$$
w_i\in\Sigma
$$

La computación comienza en:

$$
r_0=q_0
$$

y para cada símbolo:

$$
r_i=\delta(r_{i-1},w_i)
$$

para:

$$
1\leq i\leq n
$$

Al finalizar:

$$
r_n
$$

es el estado donde termina la computación.

---

## Criterio de aceptación

La cadena es aceptada si:

$$
r_n\in F
$$

Por tanto:

$$
w\text{ es aceptada}
\iff
\text{el procesamiento de }w\text{ termina en }F
$$

---

## Algoritmo mental

Cuando se recibe una cadena:

1. Colocarse en $q_0$.
2. Leer el primer símbolo.
3. Consultar $\delta$.
4. Moverse al nuevo estado.
5. Leer el siguiente símbolo.
6. Repetir.
7. Cuando no queden símbolos:
   - si el estado pertenece a $F$, aceptar;
   - si no pertenece a $F$, rechazar.

---

## Ejemplo

Para:

$$
w=01101
$$

se debe procesar:

$$
q_0
\xrightarrow{0}
\cdots
\xrightarrow{1}
\cdots
\xrightarrow{1}
\cdots
\xrightarrow{0}
\cdots
\xrightarrow{1}
r_n
$$

La respuesta depende de si:

$$
r_n\in F
$$

---

## Lenguaje reconocido

El conjunto de todas las cadenas aceptadas por $M$ es:

$$
L(M)=\{w\mid M\text{ acepta }w\}
$$

Esto conecta la computación del autómata con el concepto de [[Lenguaje]].

---

## Relaciones

- [[Automata_Finito_Determinista]]
- [[Cadena]]
- [[Lenguaje]]
- [[Lenguaje_Regular]]