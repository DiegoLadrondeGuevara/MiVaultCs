---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - binary
  - data-representation
  - computer-architecture
---

# Representación Binaria

## Idea central

Los computadores representan información mediante bits.

Un bit solamente puede tomar dos estados:

```text
0
1
```

Con `N` bits existen:

$$
2^N
$$

combinaciones posibles.

---

## Ejemplo

Con 4 bits:

$$
2^4 = 16
$$

Por tanto existen 16 patrones:

```text
0000
0001
0010
...
1111
```

El significado de cada patrón depende del sistema de representación.

---

## El punto fundamental

El patrón:

```text
1111
```

no significa automáticamente `15`.

Puede representar:

```text
unsigned → 15
two's complement → -1
sign-magnitude → -7
```

Por tanto:

> **Los bits representan datos solamente cuando existe una convención que define cómo interpretarlos.**

---

## Sistemas estudiados

[[Sistema_Unsigned]]

[[Representacion_Signo_Magnitud]]

[[Complemento_a_Dos]]

---

## Método mental

Ante una cadena binaria:

```text
10110110
```

no debo convertirla inmediatamente.

Primero debo preguntar:

1. ¿Cuántos bits hay?
2. ¿Qué representación se está utilizando?
3. ¿Es signed o unsigned?
4. ¿Cuál es el rango?
5. ¿Cómo debo interpretar el bit más significativo?

Solo después convierto.

---

## Relación

```text
Representación Binaria
├── Unsigned
├── Signo Magnitud
└── Complemento a Dos
```