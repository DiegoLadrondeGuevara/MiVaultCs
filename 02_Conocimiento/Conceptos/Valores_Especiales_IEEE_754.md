---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - IEEE-754
  - special-values
---

# Valores Especiales IEEE 754

| Exponente | Fracción | Significado |
|---|---|---|
| `0` | `0` | `±0` |
| `0` | ≠ `0` | Denormal |
| `1 ... 254` | cualquiera | Número normal |
| `255` | `0` | `±∞` |
| `255` | ≠ `0` | `NaN` |

Para double:

```text
0
1 ... 2046
2047
```

---

## Regla mental

Cuando el exponente es normal:

```text
1 ... máximo-1
```

utilizamos:

```text
1.Fraction × 2^E
```

Cuando el exponente es cero:

```text
0.Fraction
```

Cuando el exponente es máximo:

```text
Fraction = 0 → Infinity
Fraction ≠ 0 → NaN
```

Esta tabla es una de las más importantes para resolver ejercicios de IEEE 754.