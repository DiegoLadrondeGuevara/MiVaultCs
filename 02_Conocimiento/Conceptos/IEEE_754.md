---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - IEEE-754
  - floating-point
---

# IEEE 754

## Idea central

IEEE 754 define una representación estandarizada para números de punto flotante.

La PPT presenta:

```text
Single Precision → 32 bits
Double Precision → 64 bits
```

---

## Single Precision

```text
1 bit  → Sign
8 bits → Exponent
23 bits → Fraction
```

Total:

```text
1 + 8 + 23 = 32 bits
```

---

## Double Precision

```text
1 bit  → Sign
11 bits → Exponent
52 bits → Fraction
```

Total:

```text
1 + 11 + 52 = 64 bits
```

---

## Fórmula de un número normalizado

Para un número normal:

$$
x = (-1)^S(1+Fraction)2^{Exponent-Bias}
$$

---

## Sign

```text
S = 0 → positivo
S = 1 → negativo
```

---

## Exponent

Se almacena con [[Exponente_Bias]].

```text
Exponent_real =
Exponent_stored - Bias
```

---

## Fraction

Representa la parte fraccionaria de la significand.

El `1` inicial de un número normalizado es implícito.

Por eso se conoce como:

```text
hidden bit
```

---

## Bias

```text
Single → 127
Double → 1023
```

---

## Valores especiales

IEEE 754 también permite representar:

- cero;
- números denormalizados;
- infinito;
- NaN.

[[Valores_Especiales_IEEE_754]]