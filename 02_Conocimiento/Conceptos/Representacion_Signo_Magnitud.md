---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - binary
  - signed
---

# Representación Signo-Magnitud

## Idea central

El bit más significativo representa el signo.

```text
0 → positivo
1 → negativo
```

Los bits restantes representan la magnitud.

---

## Estructura

Para `N` bits:

```text
S | Magnitud
```

Por ejemplo, con 4 bits:

```text
0 | 111 → +7
1 | 111 → -7
```

---

## Rango

$$
-(2^{N-1}-1)
\leq x \leq
2^{N-1}-1
$$

Para 4 bits:

```text
-7 ... +7
```

---

## Problema: dos ceros

Tenemos:

```text
0000 → +0
1000 → -0
```

Por tanto existen dos representaciones del cero.

Esta es una de las razones por las que complemento a dos resulta más conveniente para aritmética entera.

---

## Regla mental

No confundir:

```text
signo-magnitud
```

con:

```text
complemento a dos
```

En signo-magnitud:

> El bit de signo simplemente indica si la magnitud es positiva o negativa.

---

## Relación

[[Complemento_a_Dos]]

[[Representacion_Binaria]]