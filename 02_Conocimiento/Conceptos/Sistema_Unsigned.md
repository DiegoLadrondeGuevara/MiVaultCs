---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - binary
  - unsigned
---

# Sistema Unsigned

## Definición

En una representación unsigned todos los bits contribuyen a representar la magnitud positiva.

Para `N` bits:

$$
0 \leq x \leq 2^N-1
$$

---

## Ejemplo de 4 bits

```text
0000 = 0
0001 = 1
0010 = 2
0011 = 3
0100 = 4
0101 = 5
0110 = 6
0111 = 7
1000 = 8
1001 = 9
1010 = 10
1011 = 11
1100 = 12
1101 = 13
1110 = 14
1111 = 15
```

---

## ¿Por qué el máximo es 2^N - 1?

Los valores posibles son:

```text
0 ... 2^N - 1
```

y existen exactamente:

$$
2^N
$$

valores.

---

## Overflow

Si el resultado es mayor que:

$$
2^N-1
$$

no puede representarse con `N` bits.

Ejemplo:

```text
4 bits

15 + 1 = 16
```

Pero:

```text
16 = 10000₂
```

necesita 5 bits.

Por tanto existe overflow.

---

## Regla mental

Para unsigned:

> Si el resultado matemático necesita más de `N` bits, hay overflow.

---

## Relación

[[Representacion_Binaria]]

[[Overflow]]