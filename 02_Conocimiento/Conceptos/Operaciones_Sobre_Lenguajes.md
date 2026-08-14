---
tipo: concepto
area: Teoria_Computacion
tema: Lenguajes_Formales
version: 1.0
estado: activo
fuente: 1automatas-2026-2.html
---

# Operaciones Sobre Lenguajes

Sean $A$ y $B$ dos lenguajes.

## Unión

La unión contiene las cadenas que pertenecen a cualquiera de los dos lenguajes:

$$
A\cup B
=
\{w\mid w\in A\lor w\in B\}
$$

---

## Concatenación

La concatenación de lenguajes se define como:

$$
AB
=
\{xy\mid x\in A\land y\in B\}
$$

Es decir, se toma una cadena de $A$ y una cadena de $B$ y se concatenan.

---

## Estrella de Kleene

La estrella de Kleene de $A$ es:

$$
A^*
=
\{x_1x_2\ldots x_k
\mid
x_i\in A,\ k\geq0\}
$$

Como $k$ puede ser $0$:

$$
\epsilon\in A^*
$$

---

## Ejemplo

Sean:

$$
A=\{good,bad\}
$$

y:

$$
B=\{boy,girl\}
$$

Entonces:

$$
A\cup B
=
\{good,bad,boy,girl\}
$$

y:

$$
AB=
\{goodboy,goodgirl,badboy,badgirl\}
$$

Mientras:

$$
A^*
=
\{\epsilon,good,bad,goodgood,goodbad,badgood,badbad,\ldots\}
$$

---

## Relación con lenguajes regulares

Estas operaciones permiten construir nuevos lenguajes a partir de lenguajes existentes.

La pregunta importante es:

> Si $A$ y $B$ son regulares, ¿el resultado de aplicar estas operaciones sigue siendo regular?

Esto conduce al concepto de:

[[Clausura_De_Lenguajes_Regulares]]