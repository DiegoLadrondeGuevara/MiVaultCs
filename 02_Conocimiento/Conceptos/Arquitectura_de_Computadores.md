---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
tags:
  - computer-architecture
  - fundamentals
aliases:
  - Computer Architecture
  - Arquitectura de Computadores
---

# Arquitectura de Computadores

## Idea central

La [[Arquitectura_de_Computadores]] estudia cómo se organizan y diseñan los sistemas computacionales para ejecutar software.

No se trata solamente de estudiar hardware.

El objetivo es comprender la relación entre:

```text
Software
    ↓
Instrucciones
    ↓
Arquitectura
    ↓
Microarquitectura
    ↓
Circuitos
    ↓
Hardware
```

La arquitectura funciona como un puente entre el software y la implementación física.

---

## ¿Por qué estudiar arquitectura?

Un programa puede ser correcto y aun así ser ineficiente.

Por ejemplo, dos programas pueden producir el mismo resultado pero:

- utilizar diferente cantidad de memoria;
- ejecutar diferente cantidad de instrucciones;
- aprovechar de manera diferente el procesador;
- realizar diferentes accesos a memoria;
- utilizar diferentes tipos de operaciones.

Comprender arquitectura permite razonar sobre estas diferencias.

---

## La idea de abstracción

Una computadora es demasiado compleja para analizarla toda simultáneamente.

Por eso utilizamos niveles de abstracción.

Cada nivel oculta detalles innecesarios del nivel superior.

Por ejemplo:

```text
Aplicación
   ↓
Lenguaje de programación
   ↓
Compilador
   ↓
ISA
   ↓
Microarquitectura
   ↓
Circuitos digitales
   ↓
Transistores
```

Cada capa tiene una función diferente.

---

## Conexión con esta sesión

La representación de datos es uno de los primeros puntos donde debemos cambiar nuestra forma de pensar.

En programación pensamos:

```text
int x = 42;
```

En arquitectura debemos preguntar:

> ¿Qué bits existen realmente en memoria o en un registro y cómo interpreta el hardware esos bits?

Esta transición entre significado abstracto y representación física es fundamental para el curso.

---

## Pregunta mental

Cuando vea cualquier dato, debo preguntarme:

> **¿Cómo se representa este valor físicamente?**

Ese razonamiento conduce directamente a:

- [[Representacion_Binaria]]
- [[Complemento_a_Dos]]
- [[Punto_Flotante]]
- [[IEEE_754]]