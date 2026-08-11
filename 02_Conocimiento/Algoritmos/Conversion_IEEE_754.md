---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - algorithm
  - IEEE-754
  - floating-point
---

# Conversión IEEE 754

## Problema A

Convertir un número decimal a IEEE 754.

---

## Procedimiento

### 1. Determinar el signo

```text
positivo → S = 0
negativo → S = 1
```

### 2. Convertir el valor absoluto a binario

Ejemplo:

```text
0.75 = 0.11₂
```

### 3. Normalizar

```text
0.11₂
=
1.1₂ × 2^-1
```

### 4. Obtener la fracción

Eliminar el `1.`:

```text
1.1
 ↓
1
```

Fraction:

```text
1000...
```

### 5. Calcular exponente almacenado

Single:

```text
E_stored = E_real + 127
```

Double:

```text
E_stored = E_real + 1023
```

### 6. Convertir el exponente a binario

### 7. Construir

```text
Sign | Exponent | Fraction
```

---

# Problema B

Dado IEEE 754, encontrar el número.

## Procedimiento

### 1. Separar campos

```text
S | Exponent | Fraction
```

### 2. Determinar signo

```text
(-1)^S
```

### 3. Convertir exponent

```text
E_real = E_stored - Bias
```

### 4. Reconstruir significand

Para números normales:

```text
1.Fraction
```

### 5. Aplicar

$$
x=(-1)^S(1+Fraction)2^{E_{real}}
$$

### 6. Convertir a decimal

---

## Checklist

```text
[ ] Sign
[ ] Exponent
[ ] Bias
[ ] Fraction
[ ] Normalización
[ ] Valor final
```

[[IEEE_754]]

[[Exponente_Bias]]

[[Normalizacion_Punto_Flotante]]