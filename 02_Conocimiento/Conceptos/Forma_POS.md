---
tipo: concepto
area: Arquitectura_Computadoras
tema: Forma_POS
---

# Forma_POS

**POS (Product of Sums)** es una expresión formada por un producto AND de términos suma OR. Se construye identificando las filas de la tabla de verdad donde la función vale `0` y formando sus [[Maxtermino]]s. fileciteturn0file0L441-L451

## Regla de construcción

1. Buscar las filas con `F = 0`.
2. Convertir cada fila en su maxtermino.
3. Conectar todos los maxterminos con AND.

Ejemplo de la PPT:

$$
F(A,B,C)=\Pi M(0,1,2)
$$

El material también relaciona POS con la aplicación de [[Leyes_DeMorgan]] a la forma SOP de la función complementada. fileciteturn0file0L667-L686

[[Forma_SOP]]
[[Maxtermino]]
[[Forma_Canonica]]
[[Leyes_DeMorgan]]
