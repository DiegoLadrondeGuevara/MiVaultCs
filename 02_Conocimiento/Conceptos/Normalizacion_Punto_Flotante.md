---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - floating-point
  - IEEE-754
---

# Normalización en Punto Flotante

## Objetivo

La normalización busca representar un número binario en la forma:

$$
1.xxxxx_2 \times 2^E
$$

---

## Ejemplo

Tenemos:

```text
0.1101₂
```

Movemos el punto:

```text
1.101₂ × 2^-1
```

Por tanto:

```text
0.1101₂
=
1.101₂ × 2^-1
```

---

## ¿Por qué normalizar?

Porque proporciona una representación única o canónica para los números normales.

Además permite aprovechar el bit inicial `1` como hidden bit.

---

## Hidden bit

En:

```text
1.101₂
```

no necesitamos almacenar el primer `1`.

Guardamos:

```text
101...
```

y sabemos que para un número normal debemos reconstruir:

```text
1.101...
```

---

## Conexión

[[IEEE_754]]

[[Exponente_Bias]]

[[Precision_Punto_Flotante]]