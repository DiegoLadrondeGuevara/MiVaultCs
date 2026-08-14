---
tipo: concepto
area: Teoria_Computacion
tema: Automatas
version: 1.0
estado: activo
fuente: 1automatas-2026-2.html
---

# Autómata Finito Determinista

## Idea principal

Un **Autómata Finito Determinista (AFD)** es un modelo matemático que procesa una cadena símbolo por símbolo mediante una cantidad finita de estados.

Al terminar de procesar la cadena, el autómata:

- acepta la cadena, o
- rechaza la cadena.

La palabra **determinista** significa que para cada estado y símbolo de entrada existe una única transición.

---

## Definición formal

Un AFD se representa mediante una 5-tupla:

$$
M=(Q,\Sigma,\delta,q_0,F)
$$

donde:

### $Q$: estados

Es un conjunto finito de estados:

$$
Q=\{q_0,q_1,\ldots,q_n\}
$$

### $\Sigma$: alfabeto

Es el conjunto finito de símbolos que puede recibir el autómata.

### $\delta$: función de transición

Define el siguiente estado:

$$
\delta:Q\times\Sigma\rightarrow Q
$$

Por ejemplo:

$$
\delta(q_0,1)=q_1
$$

significa que desde $q_0$, al leer $1$, se pasa a $q_1$.

### $q_0$: estado inicial

Es el estado desde el cual comienza el procesamiento.

### $F$: estados de aceptación

Es el conjunto de estados en los cuales una cadena puede terminar para ser aceptada:

$$
F\subseteq Q
$$

---

## Cómo procesa una cadena

Supongamos:

$$
w=w_1w_2\ldots w_n
$$

El procesamiento consiste en:

$$
q_0
\xrightarrow{w_1}
r_1
\xrightarrow{w_2}
r_2
\rightarrow\cdots\rightarrow
r_n
$$

Si:

$$
r_n\in F
$$

entonces:

$$
\boxed{\text{ACEPTAR}}
$$

En caso contrario:

$$
\boxed{\text{RECHAZAR}}
$$

---

## Ejemplo

El material presenta:

$$
Q=\{q_0,q_1,q_2\}
$$

$$
\Sigma=\{0,1\}
$$

$$
F=\{q_2\}
$$

con $q_0$ como estado inicial.

Las transiciones son:

| Estado | $0$ | $1$ |
|---|---|---|
| $q_0$ | $q_0$ | $q_1$ |
| $q_1$ | $q_0$ | $q_2$ |
| $q_2$ | $q_2$ | $q_2$ |

Este autómata reconoce las cadenas que contienen:

$$
11
$$

como subcadena.

---

## Idea para diseñar AFD

El estado debe representar la información relevante que necesitamos recordar de la entrada.

Por ejemplo, para reconocer:

> cadenas con un número par de $1$

solo necesitamos recordar una de dos situaciones:

$$
\text{cantidad de 1 vista = par}
$$

o:

$$
\text{cantidad de 1 vista = impar}
$$

Esto permite construir dos estados.

La estrategia general de diseño será estudiada mediante ejercicios de construcción.

---

## Relación

- [[Alfabeto]]
- [[Cadena]]
- [[Lenguaje]]
- [[Computacion_En_Un_Automata_Finito]]
- [[Lenguaje_Regular]]
- [[No_Determinismo]]