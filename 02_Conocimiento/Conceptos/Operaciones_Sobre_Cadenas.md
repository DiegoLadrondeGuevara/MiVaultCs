---
tipo: concepto
area: Teoria_Computacion
tema: Lenguajes_Formales
version: 1.0
estado: activo
fuente: 1automatas-2026-2.html
---

# Operaciones Sobre Cadenas

## Concatenación

La operación fundamental presentada sobre cadenas es la **concatenación**.

Sean:

$$
x=x_1x_2\ldots x_m
$$

y:

$$
y=y_1y_2\ldots y_n
$$

Su concatenación es:

$$
xy=x_1x_2\ldots x_my_1y_2\ldots y_n
$$

La concatenación simplemente coloca una cadena después de la otra.

---

## Ejemplo

Si:

$$
x=abc
$$

y:

$$
y=101
$$

entonces:

$$
xy=abc101
$$

Mientras que:

$$
yx=101abc
$$

Por lo tanto, en general:

$$
xy\neq yx
$$

---

## Elemento neutro

La cadena vacía $\epsilon$ es el elemento neutro:

$$
\epsilon w=w\epsilon=w
$$

Esto significa que concatenar la cadena vacía no modifica una cadena.

---

## Potencias de un alfabeto

Para un [[Alfabeto]] $\Sigma$:

$$
\Sigma^k
$$

representa todas las cadenas de longitud $k$ sobre $\Sigma$.

Por ejemplo:

$$
\Sigma=\{0,1\}
$$

entonces:

$$
\Sigma^2=\{00,01,10,11\}
$$

---

## Estrella de Kleene

La estrella:

$$
\Sigma^*
$$

representa todas las cadenas posibles sobre $\Sigma$, incluida $\epsilon$:

$$
\Sigma^*
=
\Sigma^0\cup\Sigma^1\cup\Sigma^2\cup\cdots
$$

---

## Cierre positivo

El conjunto:

$$
\Sigma^+
$$

contiene todas las cadenas no vacías:

$$
\Sigma^+
=
\Sigma^1\cup\Sigma^2\cup\Sigma^3\cup\cdots
$$

Por tanto:

$$
\Sigma^*
=
\Sigma^+\cup\{\epsilon\}
$$

---

## Relación

- [[Alfabeto]]
- [[Cadena]]
- [[Lenguaje]]
- [[Operaciones_Sobre_Lenguajes]]