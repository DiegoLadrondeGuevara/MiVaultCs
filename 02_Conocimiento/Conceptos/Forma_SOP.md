---
tipo: concepto
area: Arquitectura_Computadoras
tema: Forma_SOP
---

# Forma_SOP

**SOP (Sum of Products)** es una expresión formada por una suma OR de términos producto AND. Se construye identificando las filas de la tabla de verdad donde la función vale `1` y sumando sus [[Mintermo]]s. fileciteturn0file0L427-L438

## Regla de construcción

1. Buscar las filas con `F = 1`.
2. Convertir cada fila en su mintermo.
3. Conectar todos los minterminos con OR.

Ejemplo de la PPT:

$$
F(A,B,C)=\Sigma m(3,4,5,6,7)
$$

La forma SOP se puede llevar directamente a una realización de dos niveles AND/OR. fileciteturn0file0L604-L615

[[Forma_POS]]
[[Mintermo]]
[[Forma_Canonica]]
[[Leyes_DeMorgan]]
