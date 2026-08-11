---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - algorithm
  - floating-point
---

# Multiplicación en Punto Flotante

## Algoritmo

Dados:

```text
A = Sa × Ma × 2^Ea
B = Sb × Mb × 2^Eb
```

---

## Paso 1 — Sumar exponentes

```text
E = Ea + Eb
```

Si trabajamos con exponentes almacenados con Bias:

```text
E_resultado =
E_A_stored + E_B_stored - Bias
```

---

## Paso 2 — Multiplicar significands

```text
M = Ma × Mb
```

---

## Paso 3 — Normalizar

Si la significand queda fuera de:

```text
1 ≤ M < 2
```

ajustamos la significand y el exponente.

---

## Paso 4 — Comprobar overflow / underflow

Verificar que el exponente resultante pueda representarse.

---

## Paso 5 — Redondear

Si es necesario reducir la precisión.

---

## Paso 6 — Determinar signo

```text
S_resultado = S_A XOR S_B
```

Es decir:

```text
+ × + → +
+ × - → -
- × + → -
- × - → +
```

---

## Regla mental

La multiplicación es:

```text
SUMAR EXPONENTES
→ MULTIPLICAR SIGNIFICANDS
→ NORMALIZAR
→ COMPROBAR
→ REDONDEAR
→ DETERMINAR SIGNO
```

[[Punto_Flotante]]