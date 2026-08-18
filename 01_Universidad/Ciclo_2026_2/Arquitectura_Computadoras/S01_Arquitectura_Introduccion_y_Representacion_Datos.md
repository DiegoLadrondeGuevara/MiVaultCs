---
version: 1.0
status: draft
created: 2026-08-11
updated: 2026-08-11
course: "Arquitectura de Computadoras"
week: 1
source: "Sem1_1.1ArchL-Introduction and data representation.pdf"
tags:
  - universidad
  - arquitectura-computadores
  - CS3051
  - S01
---

# S01 — Introducción y representación de datos

## Contexto

Esta sesión introduce los fundamentos de [[Arquitectura_de_Computadores]]de Computadores y comienza estudiando uno de los problemas fundamentales de cualquier computador:

> **¿Cómo representamos información utilizando una cantidad finita de bits?**

La sesión conecta tres ideas:

1. La arquitectura de computadores estudia cómo construir y analizar sistemas computacionales.
2. Los datos dentro del computador tienen representaciones binarias de tamaño finito.
3. Dependiendo del tipo de dato, los mismos bits pueden interpretarse de diferentes maneras.

Los temas principales fueron:

- [[Arquitectura_de_Computadores]]
- [[Representacion_Binaria]]
- [[Sistema_Unsigned]]
- [[Representacion_Signo_Magnitud]]
- [[Complemento_a_Dos]]
- [[Overflow]]
- [[Tipos_de_Datos_y_Tamanos]]
- [[Punto_Flotante]]
- [[IEEE_754]]
- [[Exponente_Bias]]
- [[Normalizacion_Punto_Flotante]]
- [[Precision_Punto_Flotante]]
- [[Numeros_Denormalizados]]
- [[Infinito_y_NaN]]
- [[Valores_Especiales_IEEE_754]]

---

# 1. Introducción a Computer Architecture

La arquitectura de computadores estudia y propone arquitecturas de sistemas utilizando análisis de diferentes niveles.

La motivación principal es que la tecnología de los sistemas computacionales cambia constantemente y, al mismo tiempo, también cambian las necesidades del software.

Esto significa que no basta con saber programar.

Un científico de la computación debe entender qué ocurre debajo del software:

```text
Software
   ↓
Representación de datos
   ↓
Instrucciones
   ↓
Procesador
   ↓
Memoria
   ↓
Hardware digital
```

Comprender arquitectura permite:

- entender mejor cómo se ejecutan los programas;
- comprender las limitaciones del hardware;
- diseñar software más eficiente;
- analizar el comportamiento de procesadores;
- participar en el diseño de nuevas arquitecturas.

---

# 2. Idea central de la sesión

El computador no almacena directamente conceptos como:

- "42"
- "-17"
- "3.14159"
- "A"
- "true"

El hardware trabaja con patrones de bits.

Por ejemplo:

```text
01010110
```

Ese patrón podría representar diferentes cosas dependiendo del contexto:

- un entero unsigned;
- un entero con signo;
- parte de un número de punto flotante;
- un carácter;
- una instrucción;
- una dirección;
- etc.

Por eso:

> **Los bits no tienen significado por sí mismos. La interpretación depende del formato utilizado.**

Esta idea será fundamental durante todo el curso.

---

# 3. Representación de números

Un número almacenado en `N` bits solamente puede representar una cantidad finita de valores.

Por ejemplo:

```text
N = 4
```

produce:

```text
2^4 = 16
```

combinaciones posibles.

Por tanto, cualquier sistema de representación debe decidir:

- qué valores representan esos 16 patrones;
- cuál es el rango;
- cómo se representan los negativos;
- qué ocurre cuando el resultado no cabe.

---

# 4. Representaciones enteras

La PPT repasa tres representaciones:

- [[Sistema_Unsigned]]
- [[Representacion_Signo_Magnitud]]
- [[Complemento_a_Dos]]

## Rangos

### Unsigned: $[0, 2^N - 1]$
### Signo-magnitud: $[-(2^(N-1)-1), 2^(N-1)-1]$
### Complemento a dos: 
$[-2^(N-1), 2^(N-1)-1]$


La diferencia más importante es que complemento a dos utiliza una combinación de bits que permite representar un valor negativo adicional respecto a signo-magnitud.

---

# 5. Ejemplo con 4 bits

Con 4 bits existen:

```text
2^4 = 16
```

combinaciones.

Unsigned:

```text
0000 → 0
0001 → 1
0010 → 2
...
1111 → 15
```

Por tanto:

```text
Unsigned:
0 ... 15
```

Complemento a dos:

```text
1000 → -8
1001 → -7
...
1111 → -1
0000 → 0
0001 → 1
...
0111 → 7
```

Por tanto:

```text
Two's Complement:
-8 ... 7
```

Signo-magnitud:

```text
0000 → +0
0001 → +1
...
0111 → +7

1000 → -0
1001 → -1
...
1111 → -7
```

Una diferencia importante es que signo-magnitud posee dos representaciones de cero:

```text
0000 → +0
1000 → -0
```

mientras que complemento a dos posee una sola representación de cero.

---

# 6. Problemas típicos

Cuando aparezca un ejercicio de representación binaria, primero debemos preguntar:

1. ¿Cuántos bits tengo?
2. ¿La representación es unsigned?
3. ¿Es signo-magnitud?
4. ¿Es complemento a dos?
5. ¿Cuál es el rango permitido?
6. ¿El resultado cabe?

No debemos empezar haciendo conversiones automáticamente.

Primero hay que identificar **el sistema de representación**.

---

# 7. Overflow

El overflow aparece cuando el resultado matemático no puede representarse utilizando la cantidad de bits disponible.

Ejemplo:

Con 4 bits unsigned:

```text
máximo = 15
```

Entonces:

```text
1001₂ + 0100₂
```

equivale a:

```text
9 + 4 = 13
```

No hay overflow.

Pero:

```text
1101₂ + 1011₂
```

es:

```text
13 + 11 = 24
```

y:

```text
24 > 15
```

Por lo tanto, un resultado de 4 bits no puede representar 24.

Hay overflow.

---

# 8. Complemento a dos y overflow

Para complemento a dos de `N` bits:

```text
mínimo = -2^(N-1)

máximo = 2^(N-1)-1
```

Para 6 bits:

```text
-32 ... 31
```

Por ejemplo:

```text
27 + 31 = 58
```

Pero:

```text
58 > 31
```

por lo que existe overflow.

Una regla muy útil:

> En complemento a dos, al sumar dos números del mismo signo, puede producirse overflow si el resultado aparente cambia de signo.

Por ejemplo:

```text
positivo + positivo → negativo
```

indica overflow.

También:

```text
negativo + negativo → positivo
```

indica overflow.

---

# 9. Representación de datos

La arquitectura también debe representar diferentes tipos de datos.

La PPT muestra tamaños típicos en C para arquitecturas de 32 y 64 bits:

| Tipo | 32-bit | 64-bit |
|---|---:|---:|
| char | 1 byte | 1 byte |
| short | 2 bytes | 2 bytes |
| int | 4 bytes | 4 bytes |
| long | 4 bytes | 8 bytes |
| float | 4 bytes | 4 bytes |
| double | 8 bytes | 8 bytes |
| pointer | 4 bytes | 8 bytes |

Estos tamaños deben interpretarse como los valores típicos mostrados por la PPT, no como una regla universal para todas las implementaciones de C.

---

# 10. Punto flotante

Los números enteros no son suficientes para representar valores como:

```text
0.75
-0.000001
3.141592
6.02 × 10^23
```

Para ello se utiliza [[Punto Flotante]].

La idea es similar a la notación científica:

```text
6.02 × 10^23
```

En binario se utiliza una forma equivalente:

```text
±1.xxxxx × 2^exponente
```

Esto permite representar números extremadamente grandes o pequeños utilizando una cantidad limitada de bits.

---

# 11. IEEE 754

La PPT introduce el estándar [[IEEE_754]].

Existen dos formatos principales:

```text
Single Precision → 32 bits
Double Precision → 64 bits
```

Single:

```text
1 bit  → signo
8 bits → exponente
23 bits → fracción
```

Double:

```text
1 bit  → signo
11 bits → exponente
52 bits → fracción
```

La representación tiene la forma:

```text
+-------------------------------+
| S | Exponent | Fraction       |
+-------------------------------+
```

---

# 12. Signo

El primer bit indica el signo:

```text
S = 0 → positivo
S = 1 → negativo
```

La contribución del signo puede escribirse:

```text
(-1)^S
```

Por ejemplo:

```text
S = 0

(-1)^0 = +1
```

Mientras:

```text
S = 1

(-1)^1 = -1
```

---

# 13. Significand y normalización

Un número normalizado se representa como:

```text
1.xxxxx₂ × 2^E
```

El `1` inicial no necesita almacenarse explícitamente.

Se conoce como:

> **hidden bit**

Por eso la fracción almacenada contiene únicamente la parte después del punto.

Por ejemplo:

```text
1.101₂
```

se almacena conceptualmente como:

```text
Fraction = 101...
```

y el hardware recupera el `1` inicial.

---

# 14. Exponente con Bias

El exponente no se almacena directamente.

Se utiliza [[Exponente_Bias]].

La fórmula es:

```text
Exponent_stored = Exponent_real + Bias
```

y para recuperar:

```text
Exponent_real = Exponent_stored - Bias
```

Para single precision:

```text
Bias = 127
```

Para double precision:

```text
Bias = 1023
```

> Nota: en una diapositiva aparece `1203`, pero las diapositivas posteriores utilizan `1023` y la representación estándar de double precision utiliza bias 1023. Por tanto, `1203` debe tratarse como un error tipográfico de la PPT.

---

# 15. Ejemplo: representar -0.75

Primero convertimos:

```text
0.75 = 0.11₂
```

Normalizamos:

```text
0.11₂ = 1.1₂ × 2^-1
```

Entonces:

```text
-0.75 = -1.1₂ × 2^-1
```

Ahora obtenemos:

```text
Sign = 1

Fraction = 1000...

Exponent real = -1
```

Para single:

```text
Exponent almacenado
= -1 + 127
= 126
```

En binario:

```text
126 = 01111110₂
```

Por tanto:

```text
S          = 1
Exponent   = 01111110
Fraction   = 1000...
```

Resultado:

```text
1011111101000...
```

---

# 16. Decodificar un float

El proceso inverso es igual de importante.

Dado:

```text
11000000101000...
```

separamos:

```text
S = 1
Exponent = 10000001
Fraction = 01000...
```

Convertimos:

```text
10000001₂ = 129
```

Deshacemos el bias:

```text
129 - 127 = 2
```

La significand es:

```text
1.010₂
```

Entonces:

```text
x = (-1)^1 × 1.010₂ × 2^2
```

Como:

```text
1.010₂ = 1.25
```

obtenemos:

```text
x = -1.25 × 4

x = -5
```

---

# 17. Rango

Single precision utiliza 8 bits para el exponente.

Los valores:

```text
00000000
11111111
```

están reservados para casos especiales.

Los exponentes normales son:

```text
00000001 ... 11111110
```

El rango aproximado mostrado por la PPT es:

```text
±1.2 × 10^-38
```

hasta:

```text
±3.4 × 10^38
```

Double precision alcanza aproximadamente:

```text
±2.2 × 10^-308
```

hasta:

```text
±1.8 × 10^308
```

---

# 18. Precisión

Hay que distinguir:

```text
Rango
```

de:

```text
Precisión
```

El rango responde:

> ¿Qué tan grande o pequeño puede ser el número?

La precisión responde:

> ¿Cuántos dígitos significativos puedo representar aproximadamente?

La PPT indica aproximadamente:

```text
float  → 6 dígitos decimales
double → 16 dígitos decimales
```

Por eso utilizar `double` no significa simplemente "permitir números más grandes"; también aumenta la cantidad de información significativa disponible.

---

# 19. Números denormalizados

Cuando el exponente es:

```text
000...000
```

el número deja de utilizar el `1` implícito.

Se utiliza:

```text
0.Fraction
```

en lugar de:

```text
1.Fraction
```

Esto permite representar valores extremadamente pequeños.

La ventaja es el:

> **gradual underflow**

En lugar de pasar abruptamente de un número muy pequeño a cero, podemos representar valores cada vez más pequeños sacrificando precisión.

---

# 20. Infinito y NaN

Cuando:

```text
Exponent = 111...111
```

estamos ante valores especiales.

Si:

```text
Fraction = 000...000
```

tenemos:

```text
±Infinity
```

Si:

```text
Fraction != 0
```

tenemos:

```text
NaN
```

NaN significa:

```text
Not a Number
```

y representa resultados indefinidos o no válidos.

Ejemplo mostrado:

```text
0.0 / 0.0
```

produce un NaN.

---

# 21. Tabla completa de valores especiales

| Exponente | Fracción | Significado |
|---|---|---|
| 0 | 0 | ±0 |
| 0 | ≠ 0 | número denormalizado |
| 1 ... máximo-1 | cualquiera | número normal |
| máximo | 0 | ±∞ |
| máximo | ≠ 0 | NaN |

---

# 22. Suma en punto flotante

La suma de números en punto flotante NO consiste simplemente en sumar los bits.

Debemos seguir una secuencia.

## Procedimiento

```text
1. Alinear exponentes
2. Desplazar la significand del número con menor exponente
3. Sumar las significands
4. Normalizar
5. Comprobar overflow/underflow
6. Redondear
7. Renormalizar si es necesario
```

---

# 23. Ejemplo conceptual

Supongamos:

```text
1.000₂ × 2^-1
+
1.110₂ × 2^-2
```

Los exponentes son diferentes.

Primero igualamos:

```text
1.000₂ × 2^-1
+
0.111₂ × 2^-1
```

Ahora podemos sumar:

```text
1.000₂
+
0.111₂
=
1.111₂
```

El resultado ya está normalizado:

```text
1.111₂ × 2^-1
```

---

# 24. ¿Por qué debemos alinear exponentes?

Porque las significands solamente pueden sumarse directamente cuando representan la misma potencia de dos.

Es exactamente la misma lógica que en notación científica decimal:

```text
9.999 × 10^1
+
1.610 × 10^-1
```

Primero convertimos:

```text
9.999 × 10^1
+
0.016 × 10^1
```

y recién después sumamos.

La PPT muestra precisamente este procedimiento. 

---

# 25. Multiplicación en punto flotante

La multiplicación es más sencilla conceptualmente.

Debemos:

```text
1. Sumar exponentes
2. Multiplicar significands
3. Normalizar
4. Comprobar overflow/underflow
5. Redondear
6. Determinar el signo
```

El signo se obtiene de:

```text
positivo × positivo = positivo
positivo × negativo = negativo
negativo × positivo = negativo
negativo × negativo = positivo
```

---

# 26. Ejemplo

Consideremos:

```text
1.000₂ × 2^-1
×
1.110₂ × 2^-2
```

Sumamos exponentes:

```text
-1 + (-2) = -3
```

Multiplicamos significands:

```text
1.000₂ × 1.110₂
=
1.110₂
```

Resultado:

```text
1.110₂ × 2^-3
```

Si los signos son:

```text
+ × - 
```

el resultado es:

```text
-1.110₂ × 2^-3
```

que corresponde a:

```text
-0.21875
```

---

# 27. Pregunta conceptual de la PPT

La PPT termina planteando:

> ¿Cuál requiere más hardware: Integer o Floating Point?

La respuesta que debemos discutir durante el curso es que una unidad de punto flotante requiere lógica adicional para manejar:

- exponentes;
- significands;
- alineamiento;
- normalización;
- redondeo;
- overflow;
- underflow;
- valores especiales.

Por tanto, la aritmética de punto flotante es considerablemente más compleja que una suma entera básica.

---

# 28. Ideas que debo poder explicar después de esta clase

Al terminar esta sesión debería poder responder:

### Representación

- ¿Por qué un computador necesita representar datos?
- ¿Por qué `N` bits producen solamente `2^N` combinaciones?
- ¿Cuál es la diferencia entre unsigned, signo-magnitud y complemento a dos?

### Enteros

- ¿Cuál es el rango de cada representación?
- ¿Cómo represento un número negativo?
- ¿Qué es overflow?
- ¿Cómo detecto overflow en complemento a dos?

### Punto flotante

- ¿Por qué necesitamos punto flotante?
- ¿Qué significa normalizar?
- ¿Qué son signo, exponente y fracción?
- ¿Qué es el Bias?
- ¿Cómo codifico un número en IEEE 754?
- ¿Cómo decodifico un IEEE 754?
- ¿Qué diferencia existe entre float y double?
- ¿Qué son los números denormalizados?
- ¿Qué significan Infinity y NaN?
- ¿Cómo se suma en punto flotante?
- ¿Cómo se multiplica en punto flotante?

---

# 29. Ejercicios incluidos en la PPT

La sesión incluye ejercicios sobre:

- conversión entre bits, bytes y nibbles;
- líneas numéricas de representaciones de 2 y 3 bits;
- suma unsigned;
- detección de overflow;
- complemento a dos;
- operaciones con números positivos y negativos.

Estos ejercicios deben utilizarse para validar el dominio de:

```text
[[Representacion Binaria]]
[[Complemento a Dos]]
[[Overflow]]
```

y posteriormente:

```text
[[IEEE 754]]
[[Suma en Punto Flotante]]
[[Multiplicacion en Punto Flotante]]
```

---

# 30. Preguntas para repaso

1. ¿Cuántos valores diferentes puedo representar con 8 bits?
2. ¿Cuál es el rango unsigned de 8 bits?
3. ¿Cuál es el rango en complemento a dos de 8 bits?
4. ¿Por qué signo-magnitud tiene dos ceros?
5. ¿Qué problema resuelve complemento a dos?
6. ¿Qué significa overflow?
7. ¿Cómo detecto overflow en complemento a dos?
8. ¿Qué tres campos tiene IEEE 754?
9. ¿Qué hace el Bias?
10. ¿Por qué existe un hidden bit?
11. ¿Qué diferencia existe entre un número normalizado y uno denormalizado?
12. ¿Qué representa exponent = todos unos?
13. ¿Qué representa fraction = 0 en ese caso?
14. ¿Qué representa fraction ≠ 0?
15. ¿Cómo se realiza una suma de punto flotante?
16. ¿Cómo se realiza una multiplicación de punto flotante?
17. ¿Por qué una FPU necesita más lógica que una operación entera sencilla?

---

# 31. Relación con otras notas

```text
[[Arquitectura de Computadores]]
        │
        └── [[Representacion Binaria]]
                │
                ├── [[Sistema Unsigned]]
                │
                ├── [[Representacion Signo Magnitud]]
                │
                ├── [[Complemento a Dos]]
                │       │
                │       └── [[Overflow]]
                │
                └── [[Punto Flotante]]
                        │
                        └── [[IEEE 754]]
                                │
                                ├── [[Exponente Bias]]
                                ├── [[Normalizacion Punto Flotante]]
                                ├── [[Precision Punto Flotante]]
                                ├── [[Numeros Denormalizados]]
                                ├── [[Infinito y NaN]]
                                ├── [[Valores Especiales IEEE 754]]
                                │
                                ├── [[Suma en Punto Flotante]]
                                └── [[Multiplicacion en Punto Flotante]]
```