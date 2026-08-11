---
tipo: semana-clase
curso: Análisis y Desarrollo de Algoritmos
semana: 1
fecha: 2026-08-11
profesor: Wilder Nina
tags: [universidad, aed, complejidad, notacion-asintotica]
---

# Semana 1 - AED: Introducción al Análisis de Complejidad y Notación Asintótica

## 📌 Datos Administrativos del Curso
* **Docente:** Wilder Nina
* **Horario de atención:** A partir de las 14:00 hrs.
* **Plataforma de trabajo y práctica:** Codeforces (los ejercicios de evaluaciones y clases se basarán en los problemas de esta plataforma).
* **Condición de aprobación:** Es un **curso candado**. Se requiere aprobar de manera obligatoria e independiente tanto la teoría como el laboratorio.
* **Entregables:** Cada alumno debe mantener un repositorio de algoritmos propio en GitHub, el cual servirá como biblioteca de consulta personal durante las implementaciones en evaluaciones.
* **Bibliografía oficial:** *Introduction to Algorithms* (Cormen et al., 4ta Edición, 2022).

---

## 📚 Introducción a la Notación Asintótica

En el análisis de algoritmos, nos interesa evaluar el comportamiento del tiempo de ejecución o el consumo de memoria cuando el tamaño de la entrada $n$ crece de forma indefinida ($n \to \infty$). 

### Definiciones Matemáticas Formales

1. **Cota Superior: Big O — $\mathcal{O}(g(n))$**
   * **Lectura:** $f(n)$ crece a lo mucho tan rápido como $c \cdot g(n)$ a partir de un punto $n_0$.
   * **Definición por conjuntos:** 
     $$\mathcal{O}(g(n)) = \{ f(n) : \exists \, c > 0 \text{ y } n_0 > 0 \text{ tales que } 0 \le f(n) \le c \cdot g(n), \, \forall n \ge n_0 \}$$

2. **Cota Inferior: Big Omega — $\Omega(g(n))$**
   * **Lectura:** $f(n)$ crece a lo peor (como mínimo) tan rápido como $c \cdot g(n)$ a partir de un punto $n_0$.
   * **Definición por conjuntos:** 
     $$\Omega(g(n)) = \{ f(n) : \exists \, c > 0 \text{ y } n_0 > 0 \text{ tales que } 0 \le c \cdot g(n) \le f(n), \, \forall n \ge n_0 \}$$

3. **Cota Estrecha: Big Theta — $\Theta(g(n))$**
   * **Lectura:** $f(n)$ está acotada tanto superior como inferiormente por la misma función $g(n)$.
   * **Definición por conjuntos:** 
     $$\Theta(g(n)) = \{ f(n) : \exists \, c_1 > 0, c_2 > 0 \text{ y } n_0 > 0 \text{ tales que } 0 \le c_1 g(n) \le f(n) \le c_2 g(n), \, \forall n \ge n_0 \}$$

4. **Cota Superior Estricta: Little o — $o(g(n))$**
   * **Definición:** Para **cualquier** constante positiva $c > 0$, existe un $n_0 > 0$ tal que $0 \le f(n) < c \cdot g(n)$ para todo $n \ge n_0$.

5. **Cota Inferior Estricta: Little omega — $\omega(g(n))$**
   * **Definición:** Para **cualquier** constante positiva $c > 0$, existe un $n_0 > 0$ tal que $0 \le c \cdot g(n) < f(n)$ para todo $n \ge n_0$.

---

## ✏️ Demostraciones Algebraicas Paso a Paso

### Ejemplo 1: Demostrar que $n^2 + 10n + 2 = \mathcal{O}(n^2)$

**Paso 0: Identificación**
Identificamos $f(n) = n^2 + 10n + 2$ y $g(n) = n^2$. Por la definición de $\mathcal{O}$, debemos encontrar un par de constantes $c > 0$ y $n_0 > 0$ tales que se cumpla la desigualdad:
$$0 \le n^2 + 10n + 2 \le c \cdot n^2, \quad \forall n \ge n_0$$

**Paso 1: Demostración de la parte izquierda ($0 \le f(n)$) para hallar $n_0$**
$$0 \le n^2 + 10n + 2$$
Factorizamos $n$ en los primeros términos:
$$0 \le n(n + 10) + 2 \implies -2 \le n(n + 10) \implies -\frac{2}{n} \le n + 10$$
Evaluamos para el valor entero positivo más pequeño, $n = 1$:
$$-\frac{2}{1} \le 1 + 10 \implies -2 \le 11 \quad \text{(Se cumple estrictamente)}$$
Por lo tanto, podemos fijar **$n_0 = 1$**.

**Paso 2: Demostración de la parte derecha ($f(n) \le c \cdot g(n)$) para hallar $c$**
Partimos de la desigualdad:
$$n^2 + 10n + 2 \le c \cdot n^2$$
Factorizamos $n$ en la expresión izquierda:
$$n(n + 10) + 2 \le c \cdot n^2$$
Para simplificar la búsqueda de $c$, podemos acotar superiormente la expresión $n + 10 + \frac{2}{n} \le c$. Reemplazamos nuestro $n_0 = 1$ directamente en la desigualdad original:
$$1^2 + 10(1) + 2 \le c \cdot (1)^2 \implies 1 + 10 + 2 \le c \implies 13 \le c$$

**Conclusión:**
La afirmación $n^2 + 10n + 2 = \mathcal{O}(n^2)$ es verdadera para **$n_0 = 1$** y para cualquier constante **$c \ge 13$**. *(Nota: Si tomamos $c = 12$, la desigualdad fallará para valores grandes de $n$)*.

---

### Ejemplo 2: Demostrar que $n^2 - 10n - 2 = \Omega(n^2)$

**Paso 0: Identificación**
Identificamos $f(n) = n^2 - 10n - 2$ y $g(n) = n^2$. Por definición de $\Omega$, debemos hallar $c > 0$ y $n_0 > 0$ tales que:
$$0 \le c \cdot n^2 \le n^2 - 10n - 2, \quad \forall n \ge n_0$$

**Paso 1: Hallar $n_0$ a partir de la restricción $0 \le f(n)$**
Para que la función sea no negativa:
$$0 \le n^2 - 10n - 2 \implies 2 \le n^2 - 10n \implies 2 \le n(n - 10) \implies \frac{2}{n} \le n - 10$$
Probamos valores enteros para $n$:
* Si $n = 10 \implies \frac{2}{10} \le 0 \implies 0.2 \le 0 \quad \text{(Falso)}$
* Si $n = 11 \implies \frac{2}{11} \le 11 - 10 \implies \frac{2}{11} \le 1 \implies 0.1818 \le 1 \quad \text{(Verdadero)}$

Por lo tanto, la función comienza a ser positiva estrictamente a partir de **$n_0 = 11$**.

**Paso 2: Hallar la constante $c$**
Reemplazamos $n = n_0 = 11$ en la desigualdad $c \cdot n^2 \le n^2 - 10n - 2$:
$$c(11)^2 \le (11)^2 - 10(11) - 2$$
$$121 \cdot c \le 121 - 110 - 2 \implies 121 \cdot c \le 9 \implies c \le \frac{9}{121}$$

**Conclusión:**
Se demuestra que $n^2 - 10n - 2 = \Omega(n^2)$ es válido para **$n_0 = 11$** y cualquier constante positiva **$c \le \frac{9}{121}$**.

---

## 📌 Ejercicios Propuestos para Práctica
- [x] Demostrar algebraicamente: $3n + 5 = \mathcal{O}(n)$
- [x] Demostrar algebraicamente: $3n^2 - 5n + 1000 = \mathcal{O}(n^2)$
- [ ] Demostrar algebraicamente: $n^2 - 3n = \mathcal{O}(n^2)$
- [ ] Demostrar formalmente por qué $\frac{n}{100} \neq \mathcal{O}(1)$
- [ ] Demostrar generalización: $an + b = \mathcal{O}(n)$ para todo $a > 0$
- [ ] **Desafío:** Resolver todas las demostraciones anteriores aplicando el método del límite:
  $$\lim_{n \to \infty} \frac{f(n)}{g(n)} = L$$


1) 3n + 5 = O (n)
g(n) = n | f(n) = 3n+5
0 <= 3n + 5 <= n* c
0= 3n+5
n0 = -5/3

3n+5 = n, remplazo n = -5/3
3(-5/3) +5 = -5/3 * c
0 = c

2) 3n^2 -5n + 1000 = O(n^2)
0 <= n(3n-5) + 1000 <= n^2 * c

-1000 <= n(3n-5)
-1000/n <= 3n-5
valor que cumple: n0 =2

remplazo
(2)(3(2)-5) <= (2)^2 * c 
2<= 4c
1/2 <= c

3) $n^2 - 3n = \mathcal{O}(n^2)$
 $0<=n^2 - 3n <= n^2$
 $0<=n( n- 3)$
  $0<=n( n- 3)$
caso 1) n = 0 (no puede ser porque n0 tiene que ser positivo)
caso 2) n = 3 (este es el correcto)
n0 = 3

remplazo n = 3
 $n^2 - 3n <= n^2$
 $(3)^2 - 3(3) <= (3)^2c$
 $0 <= 9c$
==Preguntar al profesor que pasa porque no me da el resultado==

4)$\frac{n}{100} \neq \mathcal{O}(1)$

$0<=\frac{n}{100} <= 1*c$
$0<=\frac{n}{100}$
$0*100<=n$
$0<=n$
n0= 1

$\frac{1}{100} <= 1*c$
$\frac{1}{100} <= c$

---

## 🔗 Referencias y Notas Relacionadas
* Explicación conceptual detallada: [[Notacion Asintotica]]
* Propiedades del orden asintótico: [[Propiedades de Notacion Asintotica]]