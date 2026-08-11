---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - algorithm
  - binary
  - two-complement
---

# Conversión a Complemento a Dos

## Objetivo

Representar un número negativo utilizando `N` bits.

---

## Procedimiento

Para representar:

```text
-x
```

1. Convertir `x` a binario usando exactamente `N` bits.
2. Invertir todos los bits.
3. Sumar `1`.

---

## Ejemplo

Representar `-5` en 8 bits.

### Paso 1

```text
5 = 00000101
```

### Paso 2

Invertir:

```text
11111010
```

### Paso 3

Sumar 1:

```text
11111010
+       1
---------
11111011
```

Resultado:

```text
-5 = 11111011
```

---

## Verificación

Podemos recuperar el valor:

```text
11111011
```

Invertimos:

```text
00000100
```

Sumamos:

```text
00000101 = 5
```

Por tanto:

```text
11111011 = -5
```

---

## Checklist

```text
[ ] ¿Tengo exactamente N bits?
[ ] ¿Convertí primero el valor absoluto?
[ ] ¿Invertí todos los bits?
[ ] ¿Sumé 1?
[ ] ¿El resultado está dentro del rango?
```

[[Complemento_a_Dos]]