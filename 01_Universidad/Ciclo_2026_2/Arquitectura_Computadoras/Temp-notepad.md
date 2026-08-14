Hardware description Languages

Introduction
modules, puertas transistores como programar

comparativa entre la programacion de hardware y progrmaacion en c++ (definir algo)

Partes:
1) simulacion: Codeo un programa utilizando modules, puertas y transistores (en vivado verilog), lo que busoc es que de un resultado en la vida real (prender un led), para no pasar a la fisico se realiza una simulacion
	Ejmp, tengo un progrmaa que quieor encender un led de 0 a 10 se este encendido y de 10s a 20s este apagado. Como es una simulacion lo que hare es que obtendre una funcion 1 y 0 simulnado un led (waveforce (funciones de onda): representa lo que quiero que salga como funcion, como ==señales de corriente==, ) Supoganmos que la simulacion fue un exito, paso a una segunda parte:
2) Sintesis: Proceso similar  "compilar un programa" es un archivo de 0's y 1's que puedo meterlo en una placa, y en la placa puedo ya ver el resultado final del led

Tipos de dispositivos programables:
- Procesador: tODA LA Arquitectura ya esta fija, se utiliza ==para propositos generales==, programo un archivo ejecutable, puedo programar en escala de minutos y puedo programr en c/c++ y python (Logica (reglas) fija, solo aprendo a utilizar explotar al maximo sus caracteristicas)
- FPGA: Placas con harware re configurable (es una capa intermedia entre un procesaodr y un asic) ==utiliza bits files==, lo que le entregamos de la sistensis, dias de completado desde hacer el programa hasta los test pasando por la sistesis, utiliza verilog

- ASIC: Hechos especificamente para un programa en especifico, Puedo adecuarlo al programar que deseo ejecutar, Maxima performance, tiene mascara de diseño (el proceso es distinto al de un procesador general) busco hacer una arquitectura de chip lo que se traduce a una mascara, estan hechas para poder fabricar mas chips iguales, procesos largos que peude demorar meses, utiliza el lengauje de verilog 

Lenguajes de descripcon de arboles (HDLS)
nos va apermitir hacer:
1) la simulacion
2) la sistesis

icarus, online para desarrollar el codigo, necesitaremos vivao para generar el archivo 

task: instalar vivao 

utilizaremos verilog 

##general processor programming vs hardware description
tneemos que cambiar el tipo de raazonamiento

idea -> impleemnto y testeo -> progrma final

pero en arquitectura de comupu

idea -> implemento y simulo -> obtengo el final chip (con testeo final)
	- Concurrencia vs paralelismo
	- Ya no trabajamos con variables a, sino con ==una señal a==, la diferencia es que una señal va a tener un comportamiento físico, ejemplo: Yo envio pulsos y el pulso recorre todo el cirtuot y no se puede detener en el proceso. Para una señal puede ocurrir que obtenga dos resultados porque pase por dos circuitos, puede terminar en problemas asi como en beneficios

EDAplayground: Puedo hacer las simulacion y es online

Sintasis 

Verilog:
- seinsitivo a la masyusculas
- No puedes hacer variables que empiecen con numeros (2good esta mal)
- para hacer anotaciones //hola o /* hola* /
- poner foto de operadores
- ~ & | ^

Formato de numero
N'Bxx: 8'b0000_0001
N: numero de bits (define el rango de numero )
B es la base (binaria, decimar, hexadecimal, octal)
xx el numero en si
el _ es para poder ver mejor cada bits

Podemos tnere X (invalido) o Z (flotante) en los valores

Problemas a la hora de programar
Si sale todo verte, todo ok, tu resultado son 0 y 1 en una onda (puede que la logica algo este mal pero tienes el resutlado)
si sale rojo y con una X quiere decir que no esta bien definido el valor en X, mi progrmana no sabe si sabe si X es 0 o 1. Al final X sera algo con lo que vamos a jugar en el flujo del progrma, algo mas problematico es el Z
Z: no esta bien definido la variable, ya es un problema que hay que corregir algo, yan o es algo con lo que jugaqmos, es un resultado que nos alerta de que algo esta mal y debemos corregirlo, ya sea a nivel decodigo o a nivel de coneciones

Definir un modilo en verilog

a----|               |
b----|example|------y
c----|               |

verilog:
Crear modulo:
module example (a, b, c, y) ;
	input a;
	input b;
	input c;
	output y;
	//aca describimos el circuitos
	/...
endmodule //fin dle modulo, ya no va ;

Ahora puedo invocar el modulo creado

Invocación:
example ex1 (a, b, c, y);
example ex2 (....);


Definicion de input y output con bits

numero de bis : rango end - rango star +1

input [31:0] a; //a[31], a[32]

Como manipular bits

wire [15:0] longbus;
wire [7:0] shortbus;

assing shortbus = longbus [12:5];

concatenar:
asing y = {a[2], a[1], a[0], a[0]};

duplication
assign x = {a[0], a[0], a[0], a[0]};
asing y = {4{a[0]}} //creo que esta mal, corregir


Como describir lo que pasa en el circuito
Forma estructura y la forma behavior (comportamiento) [son complementarias]

1) Estructural
	- Describir lo que veo en el cirtuito, cada puerta, cada conexcion esta descrita aca
2) Al Behavior le importa la lógica del circuito

test bench
task practicar diagrams de circuotos con logica proporcional con and or xor not xor not 

