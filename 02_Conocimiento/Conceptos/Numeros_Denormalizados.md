---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - IEEE-754
  - floating-point
  - denormal
---

# Números Denormalizados

## Idea central

Los números denormalizados permiten representar valores más pequeños que el rango normal.

Ocurren cuando:

```text
Exponent = 000...000
Fraction ≠ 0
```

---

## Diferencia

Número normal:

```text
1.Fraction
```

Número denormalizado:

```text
0.Fraction
```

El hidden bit cambia de:

```text
1
```

a:

```text
0
```

---

## ¿Por qué existen?

Permiten:

> gradual underflow

Es decir, permiten aproximarse gradualmente a cero en lugar de pasar abruptamente de números normales pequeños a cero.

---

## Trade-off

La ventaja es mayor rango hacia cero.

La desventaja es:

```text
menor precisión
```

---

## Caso especial

Si:

```text
Exponent = 0
Fraction = 0
```

obtenemos cero.

Además existen dos ceros:

```text
+0
-0
```

dependiendo del bit de signo.
