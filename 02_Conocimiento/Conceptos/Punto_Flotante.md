---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - floating-point
  - numbers
---

# Punto Flotante

## Idea central

El punto flotante permite representar números no enteros y números con magnitudes muy grandes o muy pequeñas.

La idea es similar a notación científica.

Decimal:

$$
6.02 \times 10^{23}
$$

Binario:

$$
1.xxxxx_2 \times 2^E
$$

---

## ¿Por qué no utilizar simplemente enteros?

Un entero puede representar:

```text
42
```

pero necesitamos otra representación para:

```text
0.000001
3.14159
6.02 × 10^23
```

El punto flotante permite distribuir los bits entre:

```text
signo
exponente
significand
```

---

## La idea fundamental

El punto decimal/binario parece "moverse" dependiendo del exponente.

Por ejemplo:

```text
1.101 × 2^3
```

representa un número diferente de:

```text
1.101 × 2^-3
```

aunque la significand sea la misma.

---

## IEEE 754

La representación estudiada en la PPT es:

[[IEEE_754]]

---

## Operaciones

Las operaciones de punto flotante requieren más pasos que las operaciones enteras.

[[Suma_en_Punto_Flotante]]

[[Multiplicacion_en_Punto_Flotante]]