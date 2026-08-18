---
tipo: concepto
area: Arquitectura_Computadoras
tema: Mapas_De_Karnaugh
---

# Mapas_De_Karnaugh

Los **mapas de Karnaugh (K-Maps)** son una técnica gráfica para minimizar expresiones booleanas mediante la combinación de términos. fileciteturn0file0L754-L766

## Reglas

- Cada `1` debe estar cubierto al menos una vez.
- Un grupo debe contener una cantidad de celdas que sea potencia de `2`: `1`, `2`, `4`, etc.
- Los grupos deben hacerse tan grandes como sea posible.
- Se pueden envolver los bordes del mapa.
- Las entradas `X` de tipo **don't care** se agrupan solamente si ayudan a reducir la expresión. fileciteturn0file0L887-L896

## Relación con implicantes

Un [[Implicante_Primo]] corresponde al grupo más grande posible en el mapa. En la expresión resultante solo se conservan los literales que no varían dentro del grupo. fileciteturn0file0L869-L886

## Propósito

La meta es partir de una representación lógica y obtener una expresión equivalente con menos términos/literales, facilitando una implementación más simple del circuito.

[[Implicante]]
[[Implicante_Primo]]
[[Forma_SOP]]
[[Logica_Combinacional]]
