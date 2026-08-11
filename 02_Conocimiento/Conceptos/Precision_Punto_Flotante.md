---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - floating-point
  - precision
---

# Precisión de Punto Flotante

## Rango vs precisión

Son conceptos diferentes.

### Rango

Indica qué tan grandes o pequeños pueden ser los números.

### Precisión

Indica cuánta información significativa podemos conservar.

---

## Single precision

Tiene:

```text
23 bits de fraction
```

La PPT aproxima la precisión decimal a:

```text
≈ 6 dígitos decimales
```

---

## Double precision

Tiene:

```text
52 bits de fraction
```

La PPT aproxima:

```text
≈ 16 dígitos decimales
```

---

## Idea importante

Un número puede estar dentro del rango de representación pero no ser representado exactamente.

Por eso:

> Punto flotante no significa "todos los números reales".

Significa:

> Un subconjunto finito de números reales representados mediante un formato binario.

---

## Consecuencia

Las operaciones pueden requerir:

```text
redondeo
```

Esto explica por qué las operaciones de punto flotante no siempre producen resultados matemáticamente exactos.