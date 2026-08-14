---
tipo: concepto
area: Teoria_Computacion
tema: Lenguajes_Regulares
version: 1.0
estado: activo
fuente: 1automatas-2026-2.html
---

# Lenguaje Regular

## Definición

Un lenguaje es **regular** si existe algún autómata finito que lo reconoce.

Formalmente:

$$
L\text{ es regular}
\iff
\exists M\text{ tal que }L=L(M)
$$

donde $M$ es un [[Automata_Finito_Determinista|autómata finito]].

---

## Idea fundamental

La definición establece una equivalencia conceptual:

$$
\boxed{
\text{Lenguaje Regular}
\leftrightarrow
\text{Lenguaje Reconocible por un AFD}
}
$$

Por tanto, para demostrar que un lenguaje es regular, una estrategia posible es construir un autómata finito que lo reconozca.

---

## Ejemplo

Si:

$$
A=
\{w\mid w\text{ contiene la subcadena }11\}
$$

y construimos un AFD $M_1$ que acepta exactamente esas cadenas, entonces:

$$
L(M_1)=A
$$

y por lo tanto:

$$
A
$$

es un lenguaje regular.

---

## Importancia

Este concepto permite pasar de una descripción abstracta de un lenguaje a una máquina concreta capaz de decidir pertenencia:

$$
w
\rightarrow
M
\rightarrow
\begin{cases}
\text{aceptar}\\
\text{rechazar}
\end{cases}
$$

---

## Relaciones

- [[Lenguaje]]
- [[Automata_Finito_Determinista]]
- [[Computacion_En_Un_Automata_Finito]]
- [[Operaciones_Sobre_Lenguajes]]
- [[Clausura_De_Lenguajes_Regulares]]