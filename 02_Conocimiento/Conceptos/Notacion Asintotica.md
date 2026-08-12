---
tipo: concepto
area: [ciencias-de-la-computacion, algoritmos, matematicas]
materia_origen: Análisis y Desarrollo de Algoritmos
tags: [complejidad, asintotica, leetcode, cormen, teoria]
---

# Notación Asintótica

La **notación asintótica** es la herramienta matemática fundamental utilizada en la ciencia de la computación para analizar y clasificar la eficiencia de los algoritmos. Permite describir el comportamiento del tiempo de ejecución o del uso de memoria de un algoritmo a medida que el tamaño del conjunto de datos de entrada ($n$) se vuelve arbitrariamente grande ($n \to \infty$).

Al centrarnos en la tasa de crecimiento asintótico, ignoramos las constantes multiplicativas y los términos de menor orden, lo que nos permite comparar algoritmos de forma abstracta e independiente del hardware o del lenguaje de programación.

---

## 📐 Las 5 Notaciones Fundamentales

### 1. Big O ($\mathcal{O}$) — Cota Superior Asintótica
La notación $\mathcal{O}$ proporciona un límite superior para una función dentro de una constante multiplicativa. Se utiliza comúnmente para caracterizar el **peor caso** del tiempo de ejecución de un algoritmo.

* **Interpretación:** La función $f(n)$ crece *a lo mucho* tan rápido como $g(n)$.
* **Fórmula:** 
  $$\mathcal{O}(g(n)) = \{ f(n) : \exists \, c > 0, n_0 > 0 \text{ tal que } 0 \le f(n) \le c \cdot g(n), \, \forall n \ge n_0 \}$$

---

### 2. Big Omega ($\Omega$) — Cota Inferior Asintótica
La notación $\Omega$ proporciona un límite inferior para una función. Representa el ritmo de crecimiento mínimo que tendrá un algoritmo, utilizándose para acotar el **mejor caso** o establecer la complejidad mínima inherente a un problema.

* **Interpretación:** La función $f(n)$ crece *al menos* tan rápido como $g(n)$.
* **Fórmula:** 
  $$\Omega(g(n)) = \{ f(n) : \exists \, c > 0, n_0 > 0 \text{ tal que } 0 \le c \cdot g(n) \le f(n), \, \forall n \ge n_0 \}$$

---

### 3. Big Theta ($\Theta$) — Cota Estrecha o Ajustada
La notación $\Theta$ acota una función tanto por arriba como por abajo con la misma función de referencia $g(n)$. Decimos que $f(n) = \Theta(g(n))$ si y solo si $f(n) = \mathcal{O}(g(n))$ y $f(n) = \Omega(g(n))$.

* **Interpretación:** La función $f(n)$ crece *exactamente al mismo ritmo* que $g(n)$.
* **Fórmula:** 
  $$\Theta(g(n)) = \{ f(n) : \exists \, c_1 > 0, c_2 > 0, n_0 > 0 \text{ tal que } 0 \le c_1 g(n) \le f(n) \le c_2 g(n), \, \forall n \ge n_0 \}$$

---
.
### 4. Little o ($o$) — Cota Superior No Estrecha
A diferencia de Big O, que permite que la cota sea ajustada ($n^2 = \mathcal{O}(n^2)$), Little o denota un límite superior estrictamente mayor que no puede ser alcanzado.

* **Interpretación:** $f(n)$ se vuelve insignificante en comparación con $g(n)$ a medida que $n$ crece.
* **Fórmula:** 
  $$o(g(n)) = \{ f(n) : \forall \, c > 0, \exists \, n_0 > 0 \text{ tal que } 0 \le f(n) < c \cdot g(n), \, \forall n \ge n_0 \}$$
* **Criterio del Límite:** $\lim_{n \to \infty} \frac{f(n)}{g(n)} = 0$

---

### 5. Little omega ($\omega$) — Cota Inferior No Estrecha
Es la contraparte de Little o. Denota un límite inferior estrictamente menor.

* **Interpretación:** $f(n)$ crece estrictamente más rápido que $g(n)$.
* **Fórmula:** 
  $$\omega(g(n)) = \{ f(n) : \forall \, c > 0, \exists \, n_0 > 0 \text{ tal que } 0 \le c \cdot g(n) < f(n), \, \forall n \ge n_0 \}$$
* **Criterio del Límite:** $\lim_{n \to \infty} \frac{f(n)}{g(n)} = \infty$

---

## 📊 Resumen Comparativo

| Notación | Nombre | Relación Intuitiva | Análogo Matemático ($\mathbb{R}$) |
| :---: | :--- | :--- | :---: |
| $\mathcal{O}(g(n))$ | Big O | Cota Superior | $\le$ |
| $\Omega(g(n))$ | Big Omega | Cota Inferior | $\ge$ |
| $\Theta(g(n))$ | Big Theta | Cota Exacta / Estrecha | $=$ |
| $o(g(n))$ | Little o | Cota Superior Estricta | $<$ |
| $\omega(g(n))$| Little omega | Cota Inferior Estricta | $>$ |

---

## 🔗 Enlaces y Relaciones
* Ver las reglas algebraicas relacionales: [[Propiedades de Notacion Asintotica]]
* Registro de ejemplos desarrollados en clase: [[S01_AED_Analisis_de_Complejidad]]