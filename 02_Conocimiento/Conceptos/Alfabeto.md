---
tipo: concepto
area: Teoria_Computacion
tema: Lenguajes_Formales
version: 1.0
estado: activo
fuente: 1automatas-2026-2.html
---

# Alfabeto

## Definición

Un **alfabeto** es un conjunto finito y no vacío de elementos llamados **símbolos**.

Se representa normalmente mediante:

$$
\Sigma
$$

Por ejemplo:

$$
\Sigma=\{0,1\}
$$

es un alfabeto binario.

Otro ejemplo:

$$
\Sigma=\{a,b,\ldots,z\}
$$

representa un alfabeto formado por letras.

---

## Propiedades

Un alfabeto debe cumplir dos condiciones:

1. Es **finito**.
2. No es vacío.

Por tanto:

$$
|\Sigma|<\infty
$$

y:

$$
\Sigma\neq\emptyset
$$

---

## Intuición

El alfabeto responde a la pregunta:

> **¿Qué símbolos tengo permitido utilizar?**

A partir de los símbolos del alfabeto podemos construir [[Cadena|cadenas]].

Por ejemplo, dado:

$$
\Sigma=\{0,1\}
$$

podemos construir:

$$
0,\quad1,\quad00,\quad01,\quad10,\quad11,\quad10101,\ldots
$$

---

## Relación con otros conceptos

$$
\boxed{
\text{Alfabeto}
\rightarrow
\text{Cadenas}
\rightarrow
\text{Lenguajes}
\rightarrow
\text{Autómatas}
}
$$

- [[Cadena]]
- [[Operaciones_Sobre_Cadenas]]
- [[Lenguaje]]
- [[Automata_Finito_Determinista]]