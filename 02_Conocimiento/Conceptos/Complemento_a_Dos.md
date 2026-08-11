---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - binary
  - signed
  - arithmetic
---

# Complemento a Dos

## Idea central

Complemento a dos es una representación binaria utilizada para representar números enteros con signo.

Para `N` bits:

$$
-2^{N-1}
\leq x \leq
2^{N-1}-1
$$

---

## Ejemplo de 4 bits

```text
1000 → -8
1001 → -7
1010 → -6
1011 → -5
1100 → -4
1101 → -3
1110 → -2
1111 → -1

0000 → 0
0001 → 1
0010 → 2
0011 → 3
0100 → 4
0101 → 5
0110 → 6
0111 → 7
```

---

## ¿Por qué existe un valor negativo adicional?

El rango es:

```text
-8 ... +7
```

Hay ocho valores negativos y ocho valores no negativos.

En cambio signo-magnitud tendría:

```text
-7 ... +7
```

porque necesita representar dos ceros.

---

## Conversión de positivo a negativo

Para representar `-x`:

1. Escribir `x` en binario.
2. Invertir todos los bits.
3. Sumar 1.

Ejemplo:

```text
+5 = 0101
```

Invertimos:

```text
1010
```

Sumamos:

```text
1010
+   1
----
1011
```

Por tanto:

```text
-5 = 1011
```

---

## Conversión de negativo a decimal

Si el bit más significativo es `1`, sabemos que es negativo.

Podemos:

1. Invertir bits.
2. Sumar 1.
3. Convertir a decimal.
4. Agregar signo negativo.

Ejemplo:

```text
1011
```

Invertimos:

```text
0100
```

Sumamos:

```text
0101
```

Entonces:

```text
1011 = -5
```

---

## Propiedad importante

La aritmética binaria puede realizarse prácticamente con el mismo circuito de suma.

Esto hace que complemento a dos sea especialmente conveniente para hardware.

---

## Relación

[[Overflow]]

[[Representacion_Signo_Magnitud]]

[[Representacion_Binaria]]