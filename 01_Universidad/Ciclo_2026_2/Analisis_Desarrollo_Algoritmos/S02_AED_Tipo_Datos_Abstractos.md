
#### Notas de la clase (Preview)
- Evaluaciones: Miércoles (Practicas de 2 de lab: semana 2, 4, 6 | 10, 12, 14)
	*Escrito (40 min)
	Computadora (60 min) - Codesforces*
- Semana 8 parcial
- Semana 16 final
- Proyecto 1: Semana 7
- Proyecto 2: Semana 16

___
# Tipos de datos Abstractos
Un TDA es una descripción de *qué* datos se almacenan y *qué* operaciones se pueden hacer con ellos *sin decir como están implementadas por dentro*
- TDA lista

### Interfaz vs implementación
- Interfaz: es el contrato, qué operaciones existen y qué hacen
- Implementación: es la estructura de datos concreta que hace ese contrato por dentro

Analogía: Un control remoto tiene botones (interfaz): “subir volumen”, “cambiar canal”. No necesitas saber qué circuito electrónico hay detrás de cada botón (implementación) para usarlo correctamente.

#### TDA's ejemplos
| **TDA**                  | **Operaciones típicas**                  |
| ------------------------ | ---------------------------------------- |
| **Lista**                | Insertar, eliminar, acceder por posición |
| **Pila**                 | Apilar, desapilar (LIFO)                 |
| **Cola**                 | Encolar, desencolar (FIFO)               |
| **Conjunto**             | Insertar, eliminar, ¿pertenece?          |
| **Mapa**                 | Asociar llave→valor, buscar por llave    |
| **Árbol / Grafo / Heap** | Estructuras con relaciones más ricas     |
|                          |                                          |
|                          |                                          |

#### ¿Por qué separar interfaz de implementación?
- Razón 1: *se puede cambiar la implementación sin romper nada.* Si tu código solo usa la interfaz (insertar, acceder, . . . ), puedes cambiar de arreglo a lista enlazada por dentro sin tocar una sola línea del código que la usa.
- Razón 2: *se pueden comparar implementaciones.* Distintas implementaciones del mismo TDA suelen tener complejidades distintas para las mismas operaciones. Elegir bien depende de qué operación usarás más.

### Qué es un arreglo
bloque de memoria contiguo, de tamaño fijo, donde todos los elementos son del mismo tipo

Una de las implementaciones más simples del TDA Lista Soporta acceso por posición de forma directísima — vamos a ver por qué en un momento

Acceso indexado en O(1) = dirección(a[i]) = base + i × tamaño del tipo.

```cpp
int a[6] = {5, 3, 8, 1, 9, 2};
int primero = a[0]; // O(1)
int ultimo = a[5]; // O(1)
a[2] = 100; // O(1), tambien escribir es O(1)
```

>En C++, int a[n] reserva exactamente n enteros — ni uno más. El tamaño se fija en tiempo de compilación (o al momento de pedir la memoria) y no puede cambiar después.


### Arreglos multidimensionales
Una matriz n × m es, por dentro, un arreglo de n · m elementos organizado por filas; a[i][j] es solo azúcar sintáctico sobre esa aritmética.
```cpp
int mat[3][4]; //reserva 12 enteros contiguos; 
/*acceder a mat[i][j] sigue siendo O(1): la dirección es base + (i · 4 + j) × tamaño del tipo.*/
```

## Operaciones y su complejidad

### Búsqueda Lineal
```cpp
int buscar(int a[], int n, int x) { 
	for (int i = 0; i < n; i++) 
		if (a[i] == x) return i; 
	return -1; }
```
- En el peor caso (no está, o está al final), recorremos los n elementos: O(n).

>¿Y si el arreglo ya está ordenado?
>Si el arreglo está ordenado, se puede buscar mucho más rápido descartando la mitad del arreglo en cada paso — búsqueda binaria, O(log n).

### Inserción al final (si hay espacio reservado)
Si el arreglo tiene espacio de sobra al final (por ejemplo, int a[10] pero solo usas los primeros 6), agregar un elemento nuevo es tan simple como escribir en la siguiente posición: O(1).
>Esto solo funciona si ya habías reservado espacio de más.

### Inserción en medio (o al inicio): hay que desplazar
Para insertar un valor en la posición i manteniendo el orden, todos los elementos desde la posición i en adelante deben correrse un lugar a la derecha para abrir espacio.

##### Análisis: ¿por qué inserción en medio es O(n)?
```cpp
for (int j = n; j > i; j--) a[j] = a[j - 1]; // desplazar 
a[i] = valor;
```
Insertar en la posición 0 (al inicio) obliga a desplazar los n elementos existentes: O(n).
*Mejor caso*: Insertar al final (posición n, con espacio reservado) no desplaza nada: O(1).

### Eliminación: el mismo problema al revés
Para eliminar el elemento en la posición i sin dejar un “hueco”, todos los elementos después de i deben correrse un lugar a la izquierda.

Ejemplo trabajado: eliminar la posición 1 (Hacer ejemplo)
##### Análisis: ¿por qué eliminación en medio es O(n)?
```cpp
for (int j = i; j < n - 1; j++) a[j] = a[j + 1]; // desplazar 
n--;
```
*Peor caso:* Eliminar la posición 0 desplaza los n − 1 elementos restantes: O(n).
*Mejor caso:* Eliminar el último elemento no desplaza nada: O(1).

| Operación                            | Complejidad |
| ------------------------------------ | ----------- |
| **Acceso por índice**                | $\Theta(1)$ |
| **Búsqueda (no ordenado)**           | $O(n)$      |
| **Inserción al final (con espacio)** | $O(1)$      |
| **Inserción en medio/al inicio**     | $O(n)$      |
| **Eliminación al final**             | $O(1)$      |
| **Eliminación en medio/al inicio**   | $O(n)$      |

Ejercicio:
Para cada operación, indica su complejidad y por qué

1. Leer el elemento del medio de un arreglo de n elementos.
2. Insertar un elemento nuevo al inicio de un arreglo de n elementos (con espacio de sobra al final). 
3. Buscar el valor máximo en un arreglo de n elementos sin ordenar. 

(1) O(1) *Porque sé la posición n/2 por lo tanto solo tengo que leer esa posición, no más, O(1)*
(2) O(n) *porque a pesar de tener espacio de sobra al final debo mover todos los elementos desde el inicio ha una posición a la derecha*
(3) O(n) *Porque con una variable int maximo = 0, recorro todo el arreglo y voy actualizando mi variable maximo, al final de recorrer todo el arreglo O(n) retorno la variable máxima*

### La grieta en el arreglo
Tienes int a[6], ya está lleno con 6 elementos, y necesitas agregar uno más. ¿Qué haces? No puedes simplemente “pedir un espacio más”: en C++, el tamaño de un arreglo declarado *así es fijo desde que se crea.*

>¿Cuánto cuesta esa copia?: Para n elementos, O(n): hay que tocar cada uno.

