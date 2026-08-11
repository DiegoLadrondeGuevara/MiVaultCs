# Arquitectura lab martes 11/08/2026
Curso enfocado a programar en hardware
Preguntar cualquier cosa si me pierdo
Formas de representar un numero

Unsigned
Two's Complement
Sing/Magnitud

El mas significativo es el signo de la izquierda en cadenas de bits (Two's Complenet y Sing / Magnitud)

Unsigned problemas : no tiene representacion de los negativos, los numeros representados llegan estan en el rago de [0, (2^N) -1 ]

Two's Complement: ´es el que usaremos mas en el curso

Numeros importantes:
para una cadenade n bits
el mas negativo sera
10000...00
cantidad de 0 es n-1

y mayor negativo es 1111111111, con n cantidad de 1

positivos
el menor positivo es el 


Una forma de encontrar el numero es
si es negativo:
realizo la forma de bases elavadas a la posición y el ultimo digito a la izquieda (es 1) se pone en negativo y se suma todo
ejemp
+1x2^0
+0x2^1
+0x2^2
==-1x2^3

-7

y otra forma es unvetir el numero y sumarle 1
0111
lo invierto
1000+
  1
  --
  1001
overflow no es cunado hayu n bit de mas, sino cunado excedamos el rango del rango permitido