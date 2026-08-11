---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - IEEE-754
  - exponent
---

# Exponente Bias

## Problema

Necesitamos representar exponentes positivos y negativos.

En lugar de almacenar directamente:

```text
-3
-2
-1
0
1
2
3
```

IEEE 754 utiliza una representación sesgada.

---

## Fórmula

Para almacenar:

$$
E_{stored} = E_{real} + Bias
$$

Para recuperar:

$$
E_{real} = E_{stored} - Bias
$$

---

## Single

```text
Bias = 127
```

Ejemplo:

```text
E_real = -1

E_stored = -1 + 127
          = 126
```

Entonces:

```text
126 = 01111110₂
```

---

## Double

```text
Bias = 1023
```

Ejemplo:

```text
E_real = -1

E_stored = -1 + 1023
          = 1022
```

---

## ¿Por qué utilizar Bias?

Permite almacenar el exponente como un entero unsigned mientras el valor matemático puede ser negativo.

---

## Regla mental

Si recibo un exponente IEEE:

```text
no lo interpreto directamente como el exponente real.
```

Primero:

```text
exponente real =
exponente almacenado - bias
```