---
tipo: concepto
area: [ciencias-de-la-computacion, matematicas]
materia_origen: Análisis y Desarrollo de Algoritmos
tags: [complejidad, propiedades, demostracion, teoria]
---

# Propiedades Relacionales de la Notación Asintótica

Dado que las notaciones asintóticas acotan el ritmo de crecimiento de funciones, comparten propiedades algebraicas muy similares a las relaciones de orden de los números reales ($=, \le, \ge, <, >$).

---

## 1. Transitividad

La propiedad transitiva permite encadenar cotas asintóticas a través de funciones intermedias.

* **Para Big O:** 
  $$f(n) = \mathcal{O}(g(n)) \;\land\; g(n) = \mathcal{O}(h(n)) \implies f(n) = \mathcal{O}(h(n))$$
* **Para Big Omega:** 
  $$f(n) = \Omega(g(n)) \;\land\; g(n) = \Omega(h(n)) \implies f(n) = \Omega(h(n))$$
* **Para Big Theta:** 
  $$f(n) = \Theta(g(n)) \;\land\; g(n) = \Theta(h(n)) \implies f(n) = \Theta(h(n))$$
* **Para Little o y Little omega:** Se cumple exactamente bajo la misma regla de encadenamiento estricto.

---

## 2. Reflexividad

Toda función se acota a sí misma con el mismo orden de magnitud.

* $f(n) = \mathcal{O}(f(n))$
* $f(n) = \Omega(f(n))$
* $f(n) = \Theta(f(n))$

*(Nota importante: Las notaciones estrictas $o$ y $\omega$ **NO son reflexivas**, al igual que la relación $<$ no cumple que $a < a$).*

---

## 3. Simetría

La simetría aplica únicamente para la cota estrecha ($\Theta$), equivalente a la igualdad en números reales.

* $$f(n) = \Theta(g(n)) \iff g(n) = \Theta(f(n))$$

---

## 4. Simetría Transpuesta

La simetría transpuesta invierte la relación de acotamiento al cambiar el orden de las funciones.

* **Entre $\mathcal{O}$ y $\Omega$:**
  $$f(n) = \mathcal{O}(g(n)) \iff g(n) = \Omega(f(n))$$
  *(Análogo a $a \le b \iff b \ge a$)*

* **Entre $o$ y $\omega$:**
  $$f(n) = o(g(n)) \iff g(n) = \omega(f(n))$$
  *(Análogo a $a < b \iff b > a$)*

---

## 5. Incomparabilidad Asintótica

A diferencia de la **Tricotomía** en números reales (donde para cualquier par de números $a, b \in \mathbb{R}$ se cumple necesariamente que $a < b$, $a = b$ o $a > b$), dos funciones reales $f(n)$ y $g(n)$ **pueden no ser comparables asintóticamente**.

Es decir, existen casos donde no se cumple ni $f(n) = \mathcal{O}(g(n))$ ni $f(n) = \Omega(g(n))$.

### Ejemplo de Incomparabilidad:
Consideremos las siguientes funciones:
* $f(n) = n$
* $g(n) = n^{1 + \sin n}$

Debido a que la función seno ($\sin n$) oscila continuamente entre $-1$ y $1$ a medida que $n \to \infty$:
* Cuando $\sin n = 1$, $g(n) = n^2$, por lo que $g(n)$ crece mucho más rápido que $f(n)$.
* Cuando $\sin n = -1$, $g(n) = n^0 = 1$, por lo que $f(n)$ crece mucho más rápido que $g(n)$.

Al no existir un $n_0$ a partir del cual una función se mantenga consistentemente por encima o por debajo de la otra, las funciones **no son comparables asintóticamente**.

---

## 🔗 Conexiones
* Definiciones formales de las notaciones: [[Notacion Asintotica]]
* Aplicación de demostraciones prácticas: [[S01_AED_Analisis_de_Complejidad]]