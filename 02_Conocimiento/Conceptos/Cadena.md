---
tipo: concepto
area: Teoria_Computacion
tema: Lenguajes_Formales
version: 1.0
estado: activo
fuente: 1automatas-2026-2.html
---

# Cadena

## Definición

Una **cadena** sobre un [[Alfabeto]] $\Sigma$ es una secuencia finita de símbolos pertenecientes a $\Sigma$.

Si:

$$
\Sigma=\{0,1\}
$$

entonces:

$$
w=01001
$$

es una cadena sobre $\Sigma$.

---

## Longitud

La longitud de una cadena $w$ se representa mediante:

$$
|w|
$$

y corresponde al número de símbolos que contiene.

Por ejemplo:

$$
w=01001
$$

tiene:

$$
|w|=5
$$

Si:

$$
w=w_1w_2\ldots w_n
$$

entonces:

$$
|w|=n
$$

---

## Cadena vacía

La cadena vacía se representa mediante:

$$
\epsilon
$$

No contiene ningún símbolo:

$$
|\epsilon|=0
$$

Es importante entender que $\epsilon$ **es una cadena**, aunque no contenga símbolos.

---

## Concatenación

Si:

$$
x=x_1x_2\ldots x_m
$$

y:

$$
y=y_1y_2\ldots y_n
$$

entonces:

$$
xy=x_1x_2\ldots x_my_1y_2\ldots y_n
$$

La cadena vacía es el elemento neutro:

$$
\epsilon w=w\epsilon=w
$$

---

## Relación

Una cadena utiliza símbolos de un [[Alfabeto]].

Un conjunto de cadenas puede formar un [[Lenguaje]].

Las operaciones sobre cadenas se estudian en:

[[Operaciones_Sobre_Cadenas]]