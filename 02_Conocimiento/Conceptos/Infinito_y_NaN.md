---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - IEEE-754
  - floating-point
---

# Infinito y NaN

## Infinito

Se obtiene cuando:

```text
Exponent = 111...111
Fraction = 000...000
```

Representa:

```text
+∞
-∞
```

El signo determina cuál.

---

## NaN

NaN significa:

```text
Not a Number
```

Se obtiene cuando:

```text
Exponent = 111...111
Fraction ≠ 0
```

---

## Ejemplo

La PPT utiliza:

```text
0.0 / 0.0
```

como ejemplo de resultado indefinido.

---

## Idea conceptual

NaN no significa simplemente:

```text
"un número muy grande"
```

Significa que el resultado no representa un valor numérico válido dentro de la operación realizada.

---

## Relación

[[IEEE_754]]

[[Valores_Especiales_IEEE_754]]