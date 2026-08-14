---
tipo: bitacora
curso: Teoria_Computacion
ciclo: 2026_2
semana: 1
tema: Automatas
version: 1.0
estado: en_revision
fuente: 1automatas-2026-2.html
---

# S01 — Autómatas

## Objetivo de la clase

Introducir los conceptos fundamentales necesarios para estudiar autómatas y lenguajes formales.

La clase comienza estableciendo los objetos básicos con los que trabaja la teoría de la computación:

- [[Alfabeto]]
- [[Cadena]]
- [[Operaciones_Sobre_Cadenas]]
- [[Lenguaje]]

A partir de ellos se introduce el [[Automata_Finito_Determinista]], su forma de procesar una cadena y el concepto de [[Lenguaje_Regular]].

Finalmente se estudian operaciones sobre lenguajes y la idea de clausura de los lenguajes regulares, llegando a la motivación del [[No_Determinismo]].

---

## 1. Conceptos fundamentales

### Alfabeto

Un [[Alfabeto]] es un conjunto finito y no vacío de símbolos.

Ejemplos:

$$
\Sigma_1 = \{0,1\}
$$

$$
\Sigma_2 = \{a,b,\ldots,z\}
$$

El alfabeto determina qué símbolos pueden aparecer en las cadenas que vamos a estudiar.

---

### Cadena

Una [[Cadena]] sobre un alfabeto es una secuencia finita de símbolos pertenecientes a dicho alfabeto.

Ejemplos:

$$
w = 01001
$$

sobre

$$
\Sigma_1 = \{0,1\}
$$

y

$$
\alpha = abracadabra
$$

sobre un alfabeto que contiene las letras utilizadas.

La longitud de una cadena indica cuántos símbolos contiene:

$$
|w| = 5
$$

La cadena vacía se representa mediante:

$$
\epsilon
$$

y cumple:

$$
|\epsilon| = 0
$$

---

## 2. Operaciones sobre cadenas

Una cadena puede construirse mediante la [[Operaciones_Sobre_Cadenas|concatenación]] de otras cadenas.

Si:

$$
x = x_1x_2\ldots x_m
$$

y:

$$
y = y_1y_2\ldots y_n
$$

entonces:

$$
xy = x_1x_2\ldots x_my_1y_2\ldots y_n
$$

La cadena vacía funciona como elemento neutro de la concatenación:

$$
\epsilon w = w\epsilon = w
$$

---

## 3. Conjuntos de cadenas

Para un alfabeto $\Sigma$, se puede definir:

$$
\Sigma^k
$$

como el conjunto de todas las cadenas de longitud $k$ sobre $\Sigma$.

Por ejemplo, si:

$$
\Sigma = \{0,1\}
$$

entonces:

$$
\Sigma^0 = \{\epsilon\}
$$

$$
\Sigma^1 = \{0,1\}
$$

$$
\Sigma^2 = \{00,01,10,11\}
$$

La estrella de Kleene:

$$
\Sigma^*
$$

representa el conjunto de todas las cadenas posibles sobre $\Sigma$, incluyendo la cadena vacía:

$$
\Sigma^*
=
\Sigma^0 \cup \Sigma^1 \cup \Sigma^2 \cup \cdots
$$

Mientras que:

$$
\Sigma^+
$$

representa todas las cadenas no vacías:

$$
\Sigma^+
=
\Sigma^1 \cup \Sigma^2 \cup \Sigma^3 \cup \cdots
$$

Por tanto:

$$
\Sigma^*
=
\Sigma^+ \cup \{\epsilon\}
$$

---

## 4. Lenguajes

Un [[Lenguaje]] sobre un alfabeto $\Sigma$ es cualquier subconjunto de:

$$
\Sigma^*
$$

Es decir:

$$
L \subseteq \Sigma^*
$$

Esto significa que un lenguaje simplemente selecciona determinadas cadenas que cumplen alguna propiedad.

Por ejemplo:

$$
L = \{0,00,11,000,111,0000,\ldots\}
$$

es un lenguaje sobre:

$$
\Sigma = \{0,1\}
$$

Es importante diferenciar:

$$
\emptyset
$$

de:

$$
\{\epsilon\}
$$

porque:

$$
\emptyset \neq \{\epsilon\}
$$

El primero no contiene ninguna cadena, mientras que el segundo contiene exactamente una cadena: la cadena vacía.

---

## 5. Autómatas Finitos Deterministas

Un [[Automata_Finito_Determinista|Autómata Finito Determinista]] es un modelo matemático que procesa cadenas símbolo por símbolo y finalmente decide si una cadena pertenece o no a un lenguaje.

La idea fundamental es:

> Una cadena entra al autómata, el autómata la procesa mediante transiciones entre estados y finalmente responde **aceptar** o **rechazar**.

Por ejemplo, el material presenta un autómata $M_1$ con:

$$
Q = \{q_0,q_1,q_2\}
$$

$$
\Sigma = \{0,1\}
$$

$$
F = \{q_2\}
$$

El estado inicial es:

$$
q_0
$$

El autómata reconoce las cadenas que contienen la subcadena:

$$
11
$$

Por ejemplo:

$$
01101
$$

es aceptada, mientras que:

$$
00101
$$

es rechazada.

---

## 6. Modelo de computación

El procesamiento de una cadena puede verse como un algoritmo:

1. Comenzar en el estado inicial.
2. Leer el siguiente símbolo.
3. Seguir la transición correspondiente.
4. Repetir hasta consumir toda la cadena.
5. Si el estado final pertenece al conjunto de aceptación, aceptar.
6. En caso contrario, rechazar.

Por tanto:

$$
\text{Entrada} \rightarrow \text{Procesamiento} \rightarrow \text{Aceptar/Rechazar}
$$

---

## 7. Definición formal del AFD

Un [[Automata_Finito_Determinista|Autómata Finito Determinista]] se representa mediante una 5-tupla:

$$
M = (Q,\Sigma,\delta,q_0,F)
$$

donde:

- $Q$: conjunto finito de estados.
- $\Sigma$: alfabeto de entrada.
- $\delta$: función de transición.
- $q_0$: estado inicial.
- $F$: conjunto de estados de aceptación.

La función de transición tiene la forma:

$$
\delta : Q \times \Sigma \rightarrow Q
$$

Por ejemplo:

$$
\delta(q,a)=r
$$

significa que estando en el estado $q$, al leer el símbolo $a$, el autómata pasa al estado $r$.

---

## 8. Computación formal

Sea:

$$
w = w_1w_2\ldots w_n
$$

una cadena donde:

$$
w_i \in \Sigma
$$

El autómata acepta $w$ si existe una secuencia de estados:

$$
r_0,r_1,\ldots,r_n
$$

tal que:

$$
r_0=q_0
$$

y:

$$
r_i=\delta(r_{i-1},w_i)
\qquad
1\leq i\leq n
$$

y además:

$$
r_n \in F
$$

La idea importante es que el último estado alcanzado determina la respuesta.

---

## 9. Lenguaje reconocido por un autómata

El lenguaje reconocido por $M$ se define como:

$$
L(M)=\{w\mid M\text{ acepta }w\}
$$

Por lo tanto:

> Un autómata no solamente procesa cadenas; define un lenguaje mediante las cadenas que acepta.

En el ejemplo de $M_1$:

$$
L(M_1)=A
$$

donde:

$$
A=
\{w\mid w\text{ contiene la subcadena }11\}
$$

---

## 10. Lenguajes regulares

Un [[Lenguaje_Regular|lenguaje regular]] es un lenguaje para el cual existe algún autómata finito que lo reconoce.

Formalmente:

$$
L\text{ es regular}
\iff
\exists M\text{ AFD tal que }L=L(M)
$$

Esta definición conecta directamente:

$$
\boxed{\text{Lenguaje Regular} \leftrightarrow \text{Autómata Finito}}
$$

---

## 11. Diseño de autómatas

La clase plantea varios problemas de diseño de AFD sobre:

$$
\Sigma=\{0,1\}
$$

Entre ellos:

- Cadenas con un número impar de $1$.
- Cadenas con un número par de $1$.
- Cadenas donde el número de $1$ es múltiplo de $3$.
- Cadenas con un número par de ceros después del último $1$ y al menos un $1$.
- Cadenas que contienen $001$.
- Cadenas que contienen $011$.
- Cadenas con tres ceros consecutivos.
- Cadenas cuyo segundo símbolo desde la derecha es $1$.
- Cadenas que comienzan en $1$ y terminan en $0$.
- Cadenas que contienen $0101$.
- Todas las cadenas excepto $\epsilon$.
- Cadenas cuyo tercer símbolo desde la derecha es $1$.
- El lenguaje vacío.
- Cadenas de longitud máxima $5$.
- Cadenas con una cantidad impar de $1$ y una cantidad impar de $0$.

Estos ejercicios son importantes porque obligan a convertir una propiedad de las cadenas en una estructura de estados y transiciones.

---

## 12. Operaciones sobre lenguajes

Sean $A$ y $B$ lenguajes.

### Unión

$$
A\cup B
=
\{w\mid w\in A\lor w\in B\}
$$

Una cadena pertenece a la unión si pertenece a cualquiera de los dos lenguajes.

### Concatenación

$$
A\cdot B
=
\{xy\mid x\in A\land y\in B\}
$$

También puede escribirse:

$$
AB
$$

### Estrella de Kleene

$$
A^*
=
\{x_1x_2\ldots x_k
\mid
x_i\in A,\ k\geq0\}
$$

Una consecuencia importante es:

$$
\epsilon\in A^*
$$

---

## 13. Ejemplo de operaciones

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

La concatenación es:

$$
AB=
\{goodboy,goodgirl,badboy,badgirl\}
$$

Y:

$$
A^*
=
\{\epsilon,good,bad,goodgood,goodbad,badgood,badbad,\ldots\}
$$

---

## 14. Clausura de los lenguajes regulares

La clase de [[Lenguaje_Regular|lenguajes regulares]] es cerrada bajo determinadas operaciones.

Esto significa que si comenzamos con lenguajes regulares y aplicamos una de estas operaciones, el resultado sigue siendo regular.

La clase presenta primero la unión:

$$
L_1,L_2\text{ regulares}
\Rightarrow
L_1\cup L_2\text{ regular}
$$

La demostración se realiza mediante construcción de un nuevo autómata.

---

## 15. Construcción para la unión

Sean:

$$
A_1=(Q_1,\Sigma,\delta_1,q_1,F_1)
$$

y:

$$
A_2=(Q_2,\Sigma,\delta_2,q_2,F_2)
$$

Construimos:

$$
A=(Q,\Sigma,\delta,q,F)
$$

donde los estados son pares:

$$
Q=
\{(r_1,r_2)\mid r_1\in Q_1,\ r_2\in Q_2\}
$$

La transición es:

$$
\delta((r_1,r_2),a)
=
(\delta_1(r_1,a),\delta_2(r_2,a))
$$

El estado inicial es:

$$
q_0=(q_1,q_2)
$$

Y se acepta si al menos uno de los dos autómatas estaría en un estado de aceptación:

$$
F=
\{(r_1,r_2)
\mid
r_1\in F_1
\lor
r_2\in F_2
\}
$$

La idea fundamental es que el nuevo autómata **simula ambos autómatas simultáneamente**.

---

## 16. Clausura bajo concatenación

También se establece que los lenguajes regulares son cerrados bajo concatenación:

$$
L_1,L_2\text{ regulares}
\Rightarrow
L_1L_2\text{ regular}
$$

La intención de la construcción es crear un autómata que acepte una cadena cuando esta pueda dividirse en dos partes:

$$
w=xy
$$

donde:

$$
x\in L_1
$$

y:

$$
y\in L_2
$$

El problema es que un autómata determinista no sabe necesariamente en qué posición debe realizar la división.

Esto conduce naturalmente al siguiente concepto:

[[No_Determinismo]]

---

# Ideas que debo entender

- [[Alfabeto]] define los símbolos disponibles.
- [[Cadena]] es una secuencia finita de símbolos.
- $\Sigma^*$ contiene todas las cadenas posibles sobre $\Sigma$.
- Un [[Lenguaje]] es un subconjunto de $\Sigma^*$.
- Un [[Automata_Finito_Determinista]] procesa una cadena mediante estados y transiciones.
- $L(M)$ es el conjunto de cadenas aceptadas por $M$.
- Un [[Lenguaje_Regular]] es un lenguaje reconocido por algún autómata finito.
- Las operaciones sobre lenguajes permiten construir nuevos lenguajes.
- Los lenguajes regulares son cerrados bajo determinadas operaciones.
- La construcción producto permite simular dos AFD simultáneamente.
- La dificultad de decidir dónde dividir una cadena para concatenación motiva el [[No_Determinismo]].

---

# Preguntas para repasar

1. ¿Qué diferencia existe entre un alfabeto y una cadena?
2. ¿Qué representa $\Sigma^*$?
3. ¿Cuál es la diferencia entre $\emptyset$ y $\{\epsilon\}$?
4. ¿Qué significa que $L\subseteq\Sigma^*$?
5. ¿Qué componentes tiene un AFD?
6. ¿Qué representa la función $\delta$?
7. ¿Cuándo acepta un AFD una cadena?
8. ¿Qué significa $L(M)$?
9. ¿Cuándo un lenguaje es regular?
10. ¿Cómo construirías un AFD que reconozca cadenas con un número par de $1$?
11. ¿Cómo construirías un AFD para cadenas que contienen $001$?
12. ¿Qué significa que una clase de lenguajes sea cerrada bajo una operación?
13. ¿Cómo se construye un autómata para reconocer $L_1\cup L_2$?
14. ¿Por qué necesitamos simular ambos autómatas simultáneamente para la unión?
15. ¿Por qué la concatenación presenta el problema de no saber dónde dividir la entrada?
16. ¿Por qué este problema motiva el no determinismo?

---

# Estado

- [ ] Revisar [[Alfabeto]]
- [ ] Revisar [[Cadena]]
- [ ] Revisar [[Operaciones_Sobre_Cadenas]]
- [ ] Revisar [[Lenguaje]]
- [ ] Revisar [[Automata_Finito_Determinista]]
- [ ] Revisar [[Computacion_En_Un_Automata_Finito]]
- [ ] Revisar [[Lenguaje_Regular]]
- [ ] Revisar [[Operaciones_Sobre_Lenguajes]]
- [ ] Revisar [[Clausura_De_Lenguajes_Regulares]]
- [ ] Revisar [[No_Determinismo]]
- [ ] Resolver ejercicios de diseño de AFD