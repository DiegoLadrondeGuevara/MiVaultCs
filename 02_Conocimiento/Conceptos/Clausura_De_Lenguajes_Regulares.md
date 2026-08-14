---
tipo: concepto
area: Teoria_Computacion
tema: Lenguajes_Regulares
version: 1.0
estado: activo
fuente: 1automatas-2026-2.html
---

# Clausura De Lenguajes Regulares

## ¿Qué significa clausura?

Decir que una clase de lenguajes es **cerrada** bajo una operación significa que aplicar dicha operación a elementos de la clase produce otro elemento de la misma clase.

Para lenguajes regulares:

$$
L_1,L_2\text{ regulares}
\Rightarrow
L_1\cup L_2\text{ regular}
$$

y también:

$$
L_1,L_2\text{ regulares}
\Rightarrow
L_1L_2\text{ regular}
$$

---

# Clausura bajo unión

Sean:

$$
A_1=(Q_1,\Sigma,\delta_1,q_1,F_1)
$$

y:

$$
A_2=(Q_2,\Sigma,\delta_2,q_2,F_2)
$$

autómatas que reconocen $L_1$ y $L_2$ respectivamente.

Construimos un nuevo autómata:

$$
A=(Q,\Sigma,\delta,q_0,F)
$$

---

## Estados

El nuevo autómata mantiene simultáneamente la posición de ambos autómatas.

Por ello sus estados son pares:

$$
Q=
\{(r_1,r_2)
\mid
r_1\in Q_1,\ r_2\in Q_2
\}
$$

---

## Transición

Al leer un símbolo $a$, ambos autómatas avanzan:

$$
\delta((r_1,r_2),a)
=
(\delta_1(r_1,a),\delta_2(r_2,a))
$$

---

## Estado inicial

El estado inicial representa que ambos autómatas están en sus respectivos estados iniciales:

$$
q_0=(q_1,q_2)
$$

---

## Estados de aceptación

Como queremos reconocer una unión, basta con que uno de los dos autómatas acepte.

Por ello:

$$
F=
\{(r_1,r_2)
\mid
r_1\in F_1
\lor
r_2\in F_2
\}
$$

---

## Idea clave

No podemos:

$$
A_1
\rightarrow
\text{si falla}
\rightarrow
A_2
$$

porque al terminar de simular $A_1$ ya habríamos consumido la entrada.

La construcción utiliza un único autómata cuyo estado contiene información sobre ambos:

$$
(r_1,r_2)
$$

Esto se conoce como una construcción mediante producto de estados.

---

# Clausura bajo concatenación

También se establece:

$$
L_1,L_2\text{ regulares}
\Rightarrow
L_1L_2\text{ regular}
$$

La idea sería aceptar una cadena que pueda dividirse:

$$
w=xy
$$

de modo que:

$$
x\in L_1
$$

y:

$$
y\in L_2
$$

Sin embargo, existe una dificultad:

> El autómata no sabe en qué posición debe dividir la entrada.

Esta dificultad conduce al:

[[No_Determinismo]]

---

## Relaciones

- [[Lenguaje_Regular]]
- [[Operaciones_Sobre_Lenguajes]]
- [[Automata_Finito_Determinista]]
- [[No_Determinismo]]