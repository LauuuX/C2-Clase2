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



##  Ejemplo: Cálculo de ceros

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

![image](https://github.com/user-attachments/assets/f99208e2-b112-434b-89cc-845ce46ff220)

### Hallar los zeros de una función de transferencia:

$$G(s) = \frac{s^2 + 4s + 1}{s^4 + 3s^3 + 3s^2 + s + 2}$$

### Paso 1: igualamos el numerador a cero

$$s^2 + 4s + 1 = 0$$

### Paso 2: aplicamos fórmula general:

$$\[ s = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} \]$$

Con:
- $$a = 1$$ 
- $$b = 4$$ 
- $$c = 1$$

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


### Ubicación de polos y zeros

![image](https://github.com/user-attachments/assets/1fd2c862-564c-42e9-b47c-c648e28954d6)

## Ejemplo
  * Hallar los polos de la siguiente función de transferencia
    
Dada la función de transferencia:

$$G(s) = \frac{s + 2}{(s + 3)(s^2 + 0.5s + 1)}$$

### Paso 1: Identificar el denominador $$D(s)$$

$$D(s) = (s + 3)(s^2 + 0.5s + 1)$$

### Paso 2: Igualar a cero

$$(s + 3)(s^2 + 0.5s + 1) = 0$$

### Paso 3: Resolver cada factor

- Primer factor:

$$s + 3 = 0 \Rightarrow s = -3$$

- Segundo factor:
$$s^2 + 0.5s + 1 = 0$$

Usamos la fórmula general:

$$s = \frac{-0.5 \pm \sqrt{(0.5)^2 - 4(1)(1)}}{2(1)} = \frac{-0.5 \pm \sqrt{0.25 - 4}}{2}$$

$$s = \frac{-0.5 \pm \sqrt{-3.75}}{2} = \frac{-0.5 \pm j\sqrt{3.75}}{2}$$

$$s = -0.25 \pm j\cdot 0.968$$

### ✅ Resultado final:

Los polos son:

- $$s = -3$$ 
- $$s = -0.25 + j\cdot 0.968$$  
- $$s = -0.25 - j\cdot 0.968$$

Dos polos complejos conjugados y uno real negativo.

 > ![image](https://github.com/user-attachments/assets/ea9b8561-b854-4c58-a388-4b6feab26f0e)

---

## 🧩 Grado de una función de transferencia

- Otra forma de clasificar las funciones de transferencia es por su **orden** o **grado**.
- Este grado está determinado por el **polinomio característico**, es decir, el polinomio del denominador de \( G(s) \).
- El **grado** corresponde al mayor exponente de \( s \) en el denominador.

### 📘 Ejemplo:

$$G(s) = \frac{3s - 1}{s^2 + 3s + 2}$$

- El polinomio característico es: $$s^2 + 3s + 2$$
- El mayor exponente de $$s$$es 2

✅ **Por lo tanto, la función de transferencia es de segundo orden.**

## 🔁 Teorema del valor final

El error en estado estacionario corresponde al error cuando \( t \to \infty \)

$$ \lim_{t \to \infty} f(t) = \lim_{s \to 0} sF(s) $$

### Ejemplo:

$$G(s) = \frac{4}{5s + 1}$$

Si  $$U(s) = \frac{4}{s}$$, entonces:

$$Y(s) = \frac{4}{s(5s + 1)}$$

Aplicando el teorema:

$$\lim_{s \to 0} sY(s) = \lim_{s \to 0} \frac{4}{5s + 1} = 4$$

![image](https://github.com/user-attachments/assets/c69ac77e-5a28-4cb3-a123-a0c54ce98dc4)

---

## 📝 Actividad 

### Calcular el valor final para:

1. $$G(s) = \frac{8}{s^3 + 6s^2 + 11s + 6}$$

   Entrada escalón: $$U(s) = \frac{1}{s}$$
   $$Y(s) = \frac{8}{s(s^3 + 6s^2 + 11s + 6)}$$

   Valor final:

   $$\lim_{s \to 0} sY(s) = \lim_{s \to 0} \frac{8}{s^3 + 6s^2 + 11s + 6} = \frac{8}{6} = 1.33$$

2. $$G(s) = \frac{8}{s^3 + 8s^2 + 15s}$$

   Entrada escalón: $$U(s) = \frac{1}{s}$$

   $$Y(s) = \frac{8}{s(s^3 + 8s^2 + 15s)}$$

   $$= \frac{8}{s^4 + 8s^3 + 15s^2}$$

   Valor final:

   $$\lim_{s \to 0} \frac{8s}{s^4 + 8s^3 + 15s^2} = \lim_{s \to 0} \frac{8}{s^3 + 8s^2 + 15s} = \infty$$

   👉 *No existe valor final finito; sistema inestable ante escalón.*

---

# 📚 Entradas de prueba comunes en sistemas

## Respuesta de un sistema 
- Sería necesario modelar cada sistema desde cero si se tuvieran en cuenta las **señales reales**.
- Estas señales reales pueden verse afectadas por:
  - Ruido
  - Diferentes rangos
  - Diferentes tipos de señales
- En la práctica, esto haría muy complejo el análisis, por eso se utilizan modelos idealizados que permiten simular la respuesta del sistema con mayor facilidad.

![image](https://github.com/user-attachments/assets/f37ea0c9-3ef9-4cfd-8d1f-11b316989c53)

## Posibles entradas de un sistema 

- Si la solución de una ecuación diferencial depende de la entrada, la respuesta de un Sistema También
- Es muy difícil conocer la señales que están ocurriendo en un Sistema ya que depende de muchos factores como ruido, tipo de señales, ambiente , entre otras
- Además el Sistema de control debe diseñarse para que funcione ante cualquier señal
- En control se utilizan diferentes tipos de señales de prueba para evaluar el desempeño de un sistema

### 1. Entrada escalón:
- Es una entrada que considera un cambio de nivel repentino 
$$u(t) = \begin{cases} A, & t > t_0 \\ 0, & t < t_0 \end{cases}$$
 ![image](https://github.com/user-attachments/assets/afcd8459-5632-4601-8fd2-55ecdca0b5bd)

Transformada:

$$\mathcal{L}\{u(t)\} = \frac{A}{s}$$

### 2. Entrada rampa:

- Es una entrada que vería en el tiempo de forma lineal 

$$x(t) = \begin{cases} At, & t > t_0 \\ 0, & t < t_0 \end{cases}$$

![image](https://github.com/user-attachments/assets/463b5f83-1f98-41b7-b440-1f606f3cdd1a)

Transformada:

$$\mathcal{L}\{x(t)\} = \frac{A}{s^2}$$

### 3. Entrada parábola:
> Es una entrada que considera una variación no lineal en el tiempo lo cual permite evaluar diferentes condiciones de inicio y final.

$$r(t) = \begin{cases} At^2, & t > t_0 \\ 0, & t < t_0 \end{cases}$$

![image](https://github.com/user-attachments/assets/f7a69b5d-00d8-410f-aae7-99f5ab18af0b)


Transformada:

$$\mathcal{L}\{r(t)\} = \frac{A}{s^3}$$

---

## 🧠 Actividad

Dada la ecuación diferencial:

$$\dddot{y} + 5\ddot{y} + 13.5\dot{y} + 3.75y = 7.5\dot{u} + 3.75u$$

---

### 🎯 1. Función de transferencia

$$G(s) = \frac{7.5s + 3.75}{s^3 + 5s^2 + 13.5s + 3.75}$$

---

### 🔘 2. Ceros

$$7.5s + 3.75 = 0 \Rightarrow s = -0.5$$

✅ Cero: \( s = -0.5 \)

---

### ✳️ 3. Polos

$$s^3 + 5s^2 + 13.5s + 3.75 = 0$$

Solución (manualmente y por fórmula cúbica):

- $$s_1 = -0.304 + 1.807j$$  
- $$s_2 = -0.304 - 1.807j$$  
- $$s_3 = -4.391$$

✅ Polos: 2 complejos conjugados y 1 real

---

### 📉 4. Valor final

#### A. Escalón unitario \( U(s) = \frac{1}{s} \)

$$Y(s) = \frac{7.5s + 3.75}{s(s^3 + 5s^2 + 13.5s + 3.75)}$$

$$\lim_{s \to 0} sY(s) = \frac{3.75}{3.75} = 1$$

✅ Valor final escalón: **1**

---

#### B. Rampa pendiente 5 $$U(s) = \frac{5}{s^2}$$

$$Y(s) = \frac{5(7.5s + 3.75)}{s^2(s^3 + 5s^2 + 13.5s + 3.75)}$$


$$\lim_{s \to 0} sY(s) = \infty$$

⚠️ Valor final rampa: **Infinito**

---

### 📊 Gráfica de polos y ceros

>![image](https://github.com/user-attachments/assets/d08927bb-60d3-44cd-842c-beadb1a7b986)

---

### ✅ Resumen

| Concepto | Resultado |
|----------|-----------|
| Función de transferencia | $$\frac{7.5s + 3.75}{s^3 + 5s^2 + 13.5s + 3.75}$$ |
| Cero     | $$s = -0.5$$ |
| Polos    | $$-0.304 \pm 1.807j, -4.391$$ |
| Valor final (escalón) | 1 |
| Valor final (rampa)   | $$\infty$$|

## ✅ Resumen

- La **función de transferencia** representa el sistema dinámico.
- Contiene **respuesta transitoria** y **respuesta estacionaria**.
- Se asumen condiciones iniciales igual a cero.
- Polos y ceros se obtienen igualando los polinomios a cero.

# Ejercicios adicionales 
## Ejercicio 1 


