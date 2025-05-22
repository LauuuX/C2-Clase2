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

