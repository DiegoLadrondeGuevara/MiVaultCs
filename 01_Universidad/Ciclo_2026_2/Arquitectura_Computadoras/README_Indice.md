# S02 – Red de conocimiento

## Bitácora

[[S02_Arquitectura_Computadoras_Logica_Combinacional]]

## Conceptos principales

[[Logica_Combinacional]]
[[Logica_Secuencial]]
[[Algebra_Booleana]]
[[Dualidad_Booleana]]
[[Teoremas_Algebra_Booleana]]
[[Leyes_DeMorgan]]
[[Forma_Canonica]]
[[Mintermo]]
[[Maxtermino]]
[[Forma_SOP]]
[[Forma_POS]]
[[Mapas_De_Karnaugh]]
[[Implicante]]
[[Implicante_Primo]]

## Grafo conceptual

```mermaid
flowchart TD
    LC[Logica_Combinacional] --> AB[Algebra_Booleana]
    AB --> DB[Dualidad_Booleana]
    AB --> TAB[Teoremas_Algebra_Booleana]
    AB --> LD[Leyes_DeMorgan]
    LC --> FC[Forma_Canonica]
    FC --> SOP[Forma_SOP]
    FC --> POS[Forma_POS]
    SOP --> MI[Mintermo]
    POS --> MA[Maxtermino]
    SOP --> K[Mapas_De_Karnaugh]
    K --> I[Implicante]
    K --> IP[Implicante_Primo]
```
