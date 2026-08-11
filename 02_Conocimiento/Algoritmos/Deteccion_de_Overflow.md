---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - algorithm
  - overflow
  - arithmetic
---

# Detección de Overflow

## Paso 1 — Determinar el formato

Primero identificar:

```text
unsigned
```

o:

```text
two's complement
```

Nunca debemos hablar de overflow sin especificar la representación.

---

## Unsigned

Con `N` bits:

$$
0 \leq x \leq 2^N-1
$$

Después de calcular la suma:

```text
si resultado > máximo
    overflow
```

---

## Complemento a dos

Con `N` bits:

$$
-2^{N-1}
\leq x \leq
2^{N-1}-1
$$

Para suma:

```text
positivo + positivo → negativo
```

o:

```text
negativo + negativo → positivo
```

indica overflow.

---

## Ejemplo

6 bits:

```text
rango = -32 ... 31
```

Problema:

```text
27 + 31
```

Resultado:

```text
58
```

Como:

```text
58 > 31
```

hay overflow.

---

## Estrategia para examen

Nunca confíes solamente en mirar el carry.

Primero piensa:

> ¿El resultado matemático cabe en el rango de la representación?

Después utiliza los bits para confirmar.