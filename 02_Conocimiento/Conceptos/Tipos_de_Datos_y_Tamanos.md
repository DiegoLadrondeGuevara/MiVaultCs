---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - data-types
  - memory
  - C
---

# Tipos de Datos y Tamaños

## Idea central

Los programas trabajan con tipos abstractos:

```text
int
float
double
pointer
char
```

Pero el hardware debe almacenar cada valor utilizando una cantidad concreta de bits.

La cantidad de bytes determina cuánta información puede almacenarse.

---

## Tamaños mostrados en la PPT

| Tipo | 32-bit | 64-bit |
|---|---:|---:|
| char | 1 byte | 1 byte |
| short | 2 bytes | 2 bytes |
| int | 4 bytes | 4 bytes |
| long | 4 bytes | 8 bytes |
| float | 4 bytes | 4 bytes |
| double | 8 bytes | 8 bytes |
| pointer | 4 bytes | 8 bytes |

---

## Punto importante

El tamaño de un tipo no es solamente una característica del lenguaje.

También depende de:

- arquitectura;
- ABI;
- compilador;
- plataforma.

Por eso los valores de la tabla deben entenderse como tamaños típicos.

---

## Conexión

El tamaño determina el espacio disponible para representar información.

Por ejemplo:

```text
32 bits = 4 bytes
64 bits = 8 bytes
```

Esto conecta directamente con:

[[Representacion_Binaria]]

[[Punto_Flotante]]

[[IEEE_754]]