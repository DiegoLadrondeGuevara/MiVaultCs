---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - algorithm
  - floating-point
---

# Suma en Punto Flotante

## Algoritmo

Dados:

```text
A = Sa × Ma × 2^Ea
B = Sb × Mb × 2^Eb
```

---

## Paso 1 — Comparar exponentes

Determinar cuál es menor.

---

## Paso 2 — Alinear exponentes

Desplazar hacia la derecha la significand del número con menor exponente.

Ejemplo:

```text
1.000 × 2^-1
1.110 × 2^-2
```

Convertimos:

```text
1.000 × 2^-1
0.111 × 2^-1
```

---

## Paso 3 — Sumar significands

```text
1.000
+0.111
------
1.111
```

---

## Paso 4 — Normalizar

Si obtenemos algo como:

```text
0.001 × 2^-1
```

debemos mover el punto hasta obtener:

```text
1.000 × 2^-4
```

---

## Paso 5 — Comprobar overflow / underflow

Revisar si el exponente está dentro del rango permitido.

---

## Paso 6 — Redondear

Si la precisión disponible no alcanza, se redondea.

---

## Paso 7 — Renormalizar

Después del redondeo puede ser necesario normalizar nuevamente.

---

## Regla mental

La suma de punto flotante es:

```text
ALINEAR
→ SUMAR
→ NORMALIZAR
→ COMPROBAR
→ REDONDEAR
→ NORMALIZAR
```

[[Punto_Flotante]]