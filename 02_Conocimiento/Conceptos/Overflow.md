---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - arithmetic
  - binary
  - overflow
---

# Overflow

## Definición

Existe overflow cuando el resultado matemático no puede representarse con la cantidad de bits disponible.

---

## Unsigned

Con `N` bits:

$$
0 \leq x \leq 2^N-1
$$

Si:

$$
x > 2^N-1
$$

existe overflow.

---

## Complemento a dos

Con `N` bits:

$$
-2^{N-1}
\leq x \leq
2^{N-1}-1
$$

---

## Regla de signos

Al sumar dos números de complemento a dos:

```text
positivo + positivo → negativo
```

indica overflow.

También:

```text
negativo + negativo → positivo
```

indica overflow.

En cambio:

```text
positivo + negativo
```

no produce overflow por esta condición.

---

## Ejemplo

Con 6 bits:

```text
rango = -32 ... 31
```

Consideremos:

```text
27 + 31
```

Matemáticamente:

```text
58
```

Pero:

```text
58 > 31
```

Por tanto existe overflow.

---

## Método de resolución

Antes de sumar:

1. Determinar el rango.
2. Convertir los operandos.
3. Realizar la suma.
4. Interpretar el resultado con `N` bits.
5. Comparar con el resultado matemático.
6. Determinar si ocurrió overflow.

---

## Importante

Overflow no significa que el circuito "no pueda sumar".

Significa:

> El resultado producido no representa correctamente el resultado matemático dentro del formato disponible.