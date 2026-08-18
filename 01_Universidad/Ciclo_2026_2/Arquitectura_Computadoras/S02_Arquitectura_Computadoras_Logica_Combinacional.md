---
tipo: clase
materia: Arquitectura_Computadoras
ciclo: 2026_2
semana: S02
tema: Logica_Combinacional
fuente: "Sem2_02-ArchT-Combinational Logic.pdf"
---

# S02 – Logica Combinacional

## Objetivo de la sesión

La sesión introduce la **[[Logica_Combinacional]]** como nivel de abstracción para describir circuitos digitales mediante **[[Algebra_Booleana]]**, ecuaciones booleanas y su posterior realización con compuertas. La PPT parte del problema de que la operación de un procesador es compleja y necesita una forma matemática de especificar su funcionalidad. fileciteturn0file0L9-L20

## 1. Circuitos lógicos

Un circuito lógico tiene:

- **Entradas**: valores que recibe el circuito.
- **Salidas**: valores producidos por el circuito.
- **Especificación funcional**: relación entre entradas y salidas.
- **Especificación temporal**: retardo entre un cambio en las entradas y la respuesta en las salidas.

En un circuito compuesto aparecen nodos de entrada, salida e internos, además de subcircuitos que también pueden considerarse circuitos. fileciteturn0file0L33-L50

## 2. Tipos de circuitos lógicos

### [[Logica_Combinacional]]

Es **sin memoria**: las salidas dependen de la combinación de los valores actuales de las entradas. En un circuito combinacional compuesto, cada elemento es combinacional, cada nodo es una entrada o conecta exactamente con una salida y no existen caminos cíclicos. fileciteturn0file0L63-L73

### [[Logica_Secuencial]]

Tiene memoria o historial. Sus salidas dependen de los valores actuales y de valores anteriores de las entradas. La PPT indica que este tema se desarrolla en la sesión siguiente. fileciteturn0file0L74-L78

## 3. Ecuaciones booleanas

Las ecuaciones booleanas trabajan con los valores `0` y `1` y utilizan como operaciones base **OR, AND y NOT**. Una especificación funcional puede expresar las salidas como funciones de las entradas. fileciteturn0file0L80-L99

Ejemplo presentado: un sumador completo de 1 bit.

$$
S = A \oplus B \oplus C_{in}
$$

$$
C_{out} = AB + AC_{in} + BC_{in}
$$

## 4. Conceptos fundamentales

La PPT distingue:

- **Complemento**: variable complementada.
- **Literal**: una variable o su complemento.
- **Implicante**: producto de literales.
- **Mintermo**: producto que contiene todas las variables de entrada.
- **Maxtermino**: suma que contiene todas las variables de entrada.
- **Axioma**: postulado tomado como verdadero.
- **Teorema**: proposición demostrada como verdadera a partir de axiomas u otras proposiciones. fileciteturn0file0L110-L132

## 5. Dualidad booleana

La [[Dualidad_Booleana]] transforma una expresión reemplazando:

- AND por OR.
- OR por AND.
- `1` por `0`.
- `0` por `1`.

No se modifican los literales ni sus complementos. La PPT señala que los axiomas y teoremas aparecen en formas duales. fileciteturn0file0L133-L149

## 6. Axiomas y teoremas

Los primeros resultados usados para simplificar expresiones incluyen:

- Identidad.
- Elemento nulo.
- Idempotencia.
- Involución.
- Complemento.
- Conmutatividad.
- Asociatividad.
- Distributividad.
- Absorción o covering.
- Combining.
- Consensus.

Estos resultados se emplean para demostrar y simplificar expresiones booleanas. fileciteturn0file0L152-L169 fileciteturn0file0L227-L239

## 7. Leyes de DeMorgan

Las [[Leyes_DeMorgan]] permiten transformar tipos de expresiones y relacionar NAND/NOR con otras funciones lógicas. La PPT presenta:

$$
\overline{X \cdot Y \cdot Z} = \bar X + \bar Y + \bar Z
$$

$$
\overline{X + Y + Z} = \bar X \cdot \bar Y \cdot \bar Z
$$

Además, indica que NOR equivale a AND con entradas complementadas y NAND equivale a OR con entradas complementadas. fileciteturn0file0L339-L359

## 8. Formas canónicas

La tabla de verdad es una firma única de una función booleana, pero puede tener muchas expresiones equivalentes. Las formas canónicas proporcionan una representación algebraica estándar. fileciteturn0file0L394-L403

### [[Forma_SOP]]

La **Sum of Products** es una suma OR de términos producto AND. Se construye a partir de las filas donde la función vale `1`. Cada fila aporta un [[Mintermo]]. fileciteturn0file0L427-L438

### [[Forma_POS]]

La **Product of Sums** es un producto AND de términos suma OR. Se construye a partir de las filas donde la función vale `0`. Cada fila aporta un [[Maxtermino]]. fileciteturn0file0L441-L451

## 9. Notación de minterminos y maxterminos

Los índices se obtienen interpretando la combinación binaria de entradas como un número decimal. Por ejemplo, `111₂ = 7`, por lo que corresponde a `m7`; `100₂ = 4`, por lo que corresponde a `m4`. fileciteturn0file0L519-L542

Ejemplo de forma canónica SOP presentado:

$$
F(A,B,C) = \Sigma m(3,4,5,6,7)
$$

La PPT enfatiza que la **forma canónica no es necesariamente la forma mínima**. fileciteturn0file0L568-L579

Ejemplo equivalente en POS:

$$
F(A,B,C) = \Pi M(0,1,2)
$$

La conversión entre expansiones usa los índices complementarios de la tabla de verdad. fileciteturn0file0L687-L730 fileciteturn0file0L732-L750

## 10. De lógica a compuertas

La forma SOP conduce naturalmente a una realización de dos niveles con AND y OR. Cada término producto puede verse como una combinación de compuertas AND y luego las salidas de esos productos se combinan con OR. fileciteturn0file0L604-L615

## 11. Simplificación con mapas de Karnaugh

Los [[Mapas_De_Karnaugh]] permiten minimizar gráficamente expresiones booleanas combinando términos. La PPT presenta reglas de agrupación para mapas de 3 y 4 variables. fileciteturn0file0L754-L766

### Reglas principales

1. Cada `1` debe quedar cubierto al menos una vez.
2. Cada grupo debe abarcar una potencia de 2 de celdas: `1`, `2`, `4`, etc.
3. El grupo debe ser tan grande como sea posible.
4. Se permite envolver los bordes del mapa.
5. Un `don't care` (`X`) se agrupa solo si ayuda a minimizar la ecuación. fileciteturn0file0L887-L896

Un [[Implicante_Primo]] corresponde al grupo más grande de un mapa de Karnaugh. fileciteturn0file0L875-L886

## 12. Idea central de la sesión

La cadena conceptual de la sesión es:

```mermaid
flowchart LR
    A[Especificacion funcional] --> B[Tabla de verdad]
    B --> C[Forma canónica]
    C --> D[SOP / POS]
    D --> E[Expresion booleana]
    E --> F[Simplificacion]
    F --> G[Mapa de Karnaugh]
    G --> H[Circuito con compuertas]
```

La conclusión de la PPT es que los conceptos matemáticos permiten simplificar ecuaciones booleanas y que cada expresión representa un circuito equivalente; de esta manera, los circuitos combinacionales complejos pueden definirse mediante ecuaciones booleanas y reducirse mediante análisis. fileciteturn0file0L1159-L1171

## Red de conocimiento

[[Logica_Combinacional]]
[[Algebra_Booleana]]
[[Dualidad_Booleana]]
[[Teoremas_Algebra_Booleana]]
[[Leyes_DeMorgan]]
[[Mintermo]]
[[Maxtermino]]
[[Forma_SOP]]
[[Forma_POS]]
[[Forma_Canonica]]
[[Mapas_De_Karnaugh]]
[[Implicante]]
[[Implicante_Primo]]
[[Logica_Secuencial]]
