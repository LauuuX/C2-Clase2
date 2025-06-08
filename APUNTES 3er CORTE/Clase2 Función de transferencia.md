#  Función de Transferencia
>🔑Una función de transferencia es una representación matemática que relaciona la salida de un sistema con su entrada en el dominio de Laplace, suponiendo condiciones iniciales iguales a cero. Se utiliza para analizar el comportamiento dinámico de sistemas lineales e invariantes en el tiempo.

💡 Ejemplo 1:
- Hallar y(t) para la siguiente ecuación diferencial:<br>
$$\ddot{y}(t)+3 \dot{y}(t)+2 y(t)=3 \dot{u}(t)+3 u(t)$$<br>
- Aplicando transformada de LaPlace:<br>
$$s^2 Y(s)-y(0)-y^{\prime}(0)+3(s Y(s)-y(0))+2 Y(s)=3(s U(s)-u(0))+3 U(s)$$<br>
- Se despeja la variable que se quiere hallar:<br>
$$Y(s)=\frac{U(s)(3 s+3)-3 u(0)+y(0)+y^{\prime}(0)+3 y(0)}{s^2+3 s+2}$$<br>
- Al final se aplica transformada inversa de LaPlace para volver al dominio del tiempo<br>

# Función de Transferencia

## 1.  Función de transferencia

En el área de control, una **función de transferencia** es una representación matemática de un sistema dinámico. Se obtiene aplicando la **transformada de Laplace** a una ecuación diferencial, suponiendo que todas las condiciones iniciales son cero.

La función de transferencia se define como:

$$
G(s) = \frac{Y(s)}{U(s)}
$$

> ⚠ **Nota:** Esta definición aplica únicamente cuando se desea obtener la función de transferencia.  
> Si se quiere resolver la ecuación diferencial directamente, sí se deben tener en cuenta las condiciones iniciales, y no necesariamente son cero.

---

## 2.  Clasificación de funciones de transferencia

Una función de transferencia se expresa como:

$$
G(s) = \frac{N(s)}{D(s)}
$$

Donde:

- \( N(s) \): polinomio del numerador  
- \( D(s) \): polinomio del denominador

Clasificación según los grados de los polinomios:

$$
\text{Si } n > m,\ \text{la función es impropia}
$$

$$
\text{Si } n < m,\ \text{la función es estrictamente propia}
$$

$$
\text{Si } n = m,\ \text{la función es bipropia}
$$


## 3.  Ejemplos de clasificación

A continuación se muestran ejemplos de funciones de transferencia con su respectiva clasificación:

**Ejemplo 1:**

$$
G(s) = s^2 + 1 \quad \Rightarrow \text{Impropia}
$$

**Ejemplo 2:**

$$
G(s) = 2 \quad \Rightarrow \text{Bipropia}
$$

**Ejemplo 3:**

$$
G(s) = \frac{1}{s + 1} \quad \Rightarrow \text{Estrictamente propia}
$$

**Ejemplo 4:**

$$
G(s) = \frac{s^2 - 1}{s + 1} \quad \Rightarrow \text{Impropia}
$$

**Ejemplo 5:**

$$
G(s) = \frac{s - 1}{s + 1} \quad \Rightarrow \text{Bipropia}
$$


## 4.  Zeros de una función de transferencia

Los **ceros** de una función de transferencia son los valores de \( s \) que hacen que el numerador se anule:

- Se obtienen resolviendo \( N(s) = 0 \)
- Cuando el numerador se hace cero, la función de transferencia también vale cero
- Los ceros pueden ser **reales o complejos**, y se pueden ubicar en el **plano cartesiano**



## 5.  Ejemplo: Cálculo de ceros

Dada la función:

$$
G(s) = \frac{3s - 1}{s^2 + 3s + 2}
$$

Para hallar los ceros:

1. Igualamos el numerador a cero:

$$
3s - 1 = 0
$$

2. Despejamos \( s \):

$$
s = \frac{1}{3}
$$

Por lo tanto, el sistema tiene un **cero real en** 
$$\( s = \frac{1}{3} \)$$


## 🎯 Zeros de una función de transferencia

- Se iguala \( N(s) = 0 \)
- Si el numerador es cero, la función se vuelve cero.
- Los valores de \( s \) pueden ser reales o complejos.

### Hallar los zeros de una función de transferencia:

$$G(s) = \frac{s^2 + 4s + 1}{s^4 + 3s^3 + 3s^2 + s + 2}$$

### Paso 1: igualamos el numerador a cero

$$s^2 + 4s + 1 = 0$$

### Paso 2: aplicamos fórmula general:

$$\[ s = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} \]$$

Con:
- $$\( a = 1 \)$$ 
- $$\( b = 4 \)$$ 
- $$\( c = 1 \)$$

Reemplazamos:

$$s = \frac{-4 \pm \sqrt{4^2 - 4(1)(1)}}{2(1)}$$

$$s = \frac{-4 \pm \sqrt{16 - 4}}{2} = \frac{-4 \pm \sqrt{12}}{2}$$

$$s = \frac{-4 \pm 2\sqrt{3}}{2} = -2 \pm \sqrt{3}$$

✅ **Los ceros de esta función están en:**

$$s = -2 + \sqrt{3}, \quad s = -2 - \sqrt{3}$$
> ![image](https://github.com/user-attachments/assets/f3d845a9-a2fb-4551-a136-bc2d6590edaa)


## 🎯 Polos de una función de transferencia

- Si se iguala $$\( D(s) \)$$ a 0 se obtienen los valores de “s” que cumplen con la condición.
- Si el denominador se hace 0, toda la función de transferencia se vuelve infinita; de ahí el nombre para estos valores de “s”.
- Estos valores pueden ser reales o complejos, por lo tanto se pueden ubicar en un plano cartesiano.

---
### Hallar los polos de una función de transferencia 

$$G(s) = \frac{Y(s)}{U(s)} = \frac{3s - 1}{s^2 + 3s + 2} = \frac{N(s)}{D(s)}$$

Se identifica:

- $$( D(s) = s^2 + 3s + 2 \)$$ como el **polinomio característico**.
- Al igualarlo a cero:  
  $$D(s) = 0 \Rightarrow (s + 1)(s + 2) = 0$$

Polos del sistema:
$$s = -1, \quad s = -2$$


## 📍 Ubicación de polos y zeros

> ![Plano de polos y ceros](ruta/a/imagen5.png)


## 📍 Ubicación de polos y zeros en el plano complejo

> ![image](https://github.com/user-attachments/assets/beb5db50-0dd8-4677-a00a-7a61f11025ae)

- Polos complejos conjugados
- Polos reales diferentes
- Polos iguales repetidos

---

## 🧩 Grado de una función de transferencia

Se define por el polinomio característico en el denominador.

### Ejemplo:

$$D(s) = s^2 + 3s + 2 = 0 \Rightarrow$$
$$s = -1, -2$$

---

## 📍 Ubicación de polos y zeros en el plano complejo

**→ Segundo orden**

---

## 🔁 Teorema del valor final

El error en estado estacionario corresponde al error cuando \( t \to \infty \)

$$ \lim_{t \to \infty} f(t) = \lim_{s \to 0} sF(s) $$

### Ejemplo:

$$ G(s) = \frac{4}{5s + 1} $$

Si \( U(s) = \frac{4}{s} \), entonces:

$$ Y(s) = \frac{4}{s(5s + 1)} $$

Aplicando el teorema:

$$ \lim_{s \to 0} sY(s) = \lim_{s \to 0} \frac{4}{5s + 1} = 4 $$

---

## 📝 Actividad #1

### Calcular el valor final para:

1. $$ G(s) = \frac{8}{s^3 + 6s^2 + 11s + 6} $$

   Entrada escalón: \( U(s) = \frac{1}{s} \)

   $$ Y(s) = \frac{8}{s(s^3 + 6s^2 + 11s + 6)} $$

   Valor final:

   $$ \lim_{s \to 0} sY(s) = \lim_{s \to 0} \frac{8}{s^3 + 6s^2 + 11s + 6} = \frac{8}{6} = 1.33 $$

2. $$ G(s) = \frac{8}{s^3 + 8s^2 + 15s} $$

   Entrada escalón: \( U(s) = \frac{1}{s} \)

   $$ Y(s) = \frac{8}{s(s^3 + 8s^2 + 15s)} $$

   $$ = \frac{8}{s^4 + 8s^3 + 15s^2} $$

   Valor final:

   $$ \lim_{s \to 0} \frac{8s}{s^4 + 8s^3 + 15s^2} = \lim_{s \to 0} \frac{8}{s^3 + 8s^2 + 15s} = \infty $$

   👉 *No existe valor final finito; sistema inestable ante escalón.*

---

## 🧠 Actividad #2 (Completa)

Para la ecuación diferencial:

$$ \ddddot{y} + 5\ddot{y} + 13.5\dot{y} + 3.75y = 7.5\dot{u} + 3.75u $$

Transformada de Laplace (con condiciones iniciales cero):

\( s^3Y(s) + 5s^2Y(s) + 13.5sY(s) + 3.75Y(s) = 7.5sU(s) + 3.75U(s) \)

Factorizando:

$$ Y(s)(s^3 + 5s^2 + 13.5s + 3.75) = U(s)(7.5s + 3.75) $$

### Función de transferencia:

$$ G(s) = \frac{Y(s)}{U(s)} = \frac{7.5s + 3.75}{s^3 + 5s^2 + 13.5s + 3.75} $$

### Zeros:

Numerador: \( 7.5s + 3.75 = 0 \Rightarrow s = -0.5 \)

### Polos:

Denominador: \( s^3 + 5s^2 + 13.5s + 3.75 = 0 \) → usar método numérico o software (raíces complejas reales)

### Valor final frente a:

- Escalón unitario: \( U(s) = \frac{1}{s} \)

  $$ Y(s) = \frac{7.5s + 3.75}{s(s^3 + 5s^2 + 13.5s + 3.75)} $$

  $$ \lim_{s \to 0} sY(s) = \frac{3.75}{3.75} = 1 $$

- Rampa de pendiente 5: \( U(s) = \frac{5}{s^2} \)

  $$ Y(s) = \frac{(7.5s + 3.75)(5)}{s^2(s^3 + 5s^2 + 13.5s + 3.75)} $$

  $$ \lim_{s \to 0} sY(s) = \lim_{s \to 0} \frac{5(7.5s + 3.75)}{s(s^3 + 5s^2 + 13.5s + 3.75)} = \infty $$

  👉 *No hay valor final finito para entrada tipo rampa.*

---

## 📚 Entradas de prueba comunes en sistemas

### 1. Entrada escalón:

$$ u(t) = \begin{cases} A, & t > t_0 \\ 0, & t < t_0 \end{cases} $$

Transformada de Laplace:

$$ \mathcal{L}\{u(t)\} = \frac{A}{s} $$

### 2. Entrada rampa:

$$ x(t) = \begin{cases} At, & t > t_0 \\ 0, & t < t_0 \end{cases} $$

Transformada:

$$ \mathcal{L}\{x(t)\} = \frac{A}{s^2} $$

### 3. Entrada parábola:

$$ r(t) = \begin{cases} At^2, & t > t_0 \\ 0, & t < t_0 \end{cases} $$

Transformada:

$$ \mathcal{L}\{r(t)\} = \frac{A}{s^3} $$

---

## ✅ Resumen

- La **función de transferencia** representa el sistema dinámico.
- Contiene **respuesta transitoria** y **respuesta estacionaria**.
- Se asumen condiciones iniciales igual a cero.
- Polos y ceros se obtienen igualando los polinomios a cero.

---

## ❓ Preguntas...

> ¡Gracias por tu atención! Si tienes dudas, escríbeme o comenta el `README.md` 😄



