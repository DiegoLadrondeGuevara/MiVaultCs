---
tipo: concepto
area: Teoria_Computacion
tema: Lenguajes_Formales
version: 1.0
estado: activo
fuente: 1automatas-2026-2.html
---

# Lenguaje

## Definición

Un **lenguaje** sobre un [[Alfabeto]] $\Sigma$ es un subconjunto de:

$$
\Sigma^*
$$

Formalmente:

$$
L\subseteq\Sigma^*
$$

Por tanto, un lenguaje es simplemente un conjunto de cadenas que cumplen alguna condición.

---

## Intuición

Si el alfabeto determina:

> ¿Qué símbolos puedo utilizar?

el lenguaje determina:

> ¿Qué cadenas de esas posibles me interesan?

Por ejemplo:

$$
\Sigma=\{0,1\}
$$

y:

$$
L=\{0,00,11,000,111,0000,\ldots\}
$$

Entonces $L$ contiene únicamente determinadas cadenas construidas utilizando $0$ y $1$.

---

## Lenguaje vacío

El conjunto:

$$
\emptyset
$$

es un lenguaje sobre $\Sigma$.

No contiene ninguna cadena.

---

## Lenguaje de la cadena vacía

También:

$$
\{\epsilon\}
$$

es un lenguaje.

Pero:

$$
\boxed{\emptyset\neq\{\epsilon\}}
$$

La diferencia es fundamental:

- $\emptyset$: no contiene ninguna cadena.
- $\{\epsilon\}$: contiene una cadena, específicamente $\epsilon$.

---

## Ejemplo

El lenguaje de cadenas que contienen $n$ ceros seguidos de $n$ unos, para algún:

$$
n\geq0
$$

es:

$$
L=
\{\epsilon,01,0011,000111,\ldots\}
$$

---

## Relación con autómatas

Un [[Automata_Finito_Determinista|autómata finito]] puede reconocer un lenguaje.

El lenguaje reconocido por un autómata $M$ se representa como:

$$
L(M)
$$

Los lenguajes que pueden ser reconocidos mediante autómatas finitos son los [[Lenguaje_Regular|lenguajes regulares]].

---

## Relaciones

- [[Alfabeto]]
- [[Cadena]]
- [[Operaciones_Sobre_Lenguajes]]
- [[Automata_Finito_Determinista]]
- [[Lenguaje_Regular]]