## Modelamiento de sistemas con diagrama de bloques 
## Modelamiento de sistemas complejos 
> 🔑 En dinámica de sistemas, los modelos de sistemas complejos se utilizan para simular y analizar el comportamiento de sistemas que interactúan entre sí y que tienen un comportamiento complejo en el tiempo. Estos modelos se basan en la teoría de sistemas de retroalimentación y se pueden utilizar para estudiar problemas dinámicos en áreas como la gestión, la economía, la ecología y la sociedad.

- Se podrían modelar sistemas como un todo hallando las funciones de transferencia de cada componente.
- Otro enfoque es utilizar modelos ya desarrollados ampliamente para construir modelos más complejos.
- Aún usando este enfoque hay muchos tipos de procesos y dispositivos.

## Selenoide
  ### ¿Qué es un selenoide?
  > 🔑 Se trata de un componente constituido por una bobina de alambre, una carcasa y un émbolo móvil (armadura), que puede producir un movimiento de ida y vuelta o    lineal cuando una fuerza es aplicada.
    - Un **solenoide** está formado por:
    - Un circuito eléctrico
    - Un acoplamiento electromecánico (**transductor**)
    - Un sistema mecánico de traslación
    ### 📘 Modelo del circuito electromagnético

  ![image](https://github.com/user-attachments/assets/989f8cc1-6216-4d66-923b-ff8349437bb5)
  
  La ecuación que modela el comportamiento eléctrico del solenoide es:
  
  $$L \frac{di}{dt} + Ri = v(t)$$
  
  Y en el dominio de Laplace se convierte en:
  
  $$I(s) = V(s) \cdot \frac{1}{Ls + R}$$
  
  Donde:
  - $$L$$: inductancia
  - $$R$$: resistencia
  - $$V(s)$$: voltaje de entrada
  - $$I(s)$$: corriente resultante
    
  ## 🧲 Acoplamiento electromecánico del electroimán
  
  - El **electroimán** produce una fuerza mecánica proporcional a la corriente que circula por el embobinado.
  
  ### 🧮 Ecuaciones:
  
  En el dominio del tiempo:
  
  $$f_s = K_s \cdot i$$
  
  En el dominio de Laplace:
  
  $$F_s(s) = K_s \cdot I(s)$$
  
  🔗 **Este modelo representa el acople entre la parte electromagnética y la parte mecánica del sistema.**
  
  ## ⚙️ Sistema mecánico del solenoide
  
  - El electroimán atrae una **masa** acoplada por medio de un **resorte**.
  - Se considera también el **amortiguamiento** generado por la envolvente de la bobina.
  
  
  ### 🧮 Ecuación del sistema mecánico:
  
  En el dominio del tiempo:
  
  $$m \frac{d^2x}{dt^2} + b \frac{dx}{dt} + kx = f(t)$$
  
  En el dominio de Laplace:
  
  $$X(s) = F(s) \cdot \frac{1}{ms^2 + bs + k}$$
  
  Donde:
  - $$m$$: masa
  - $$b$$: coeficiente de amortiguamiento
  - $$k$$: constante del resorte
  - $$x(t)$$: posición
  - $$f(t)$$: fuerza de entrada
  
  ## Representación del sistema selenoide en bloques 
  ![image](https://github.com/user-attachments/assets/decece59-6338-4851-b1a9-faf1f5e34ce8)
  ![image](https://github.com/user-attachments/assets/ec9b3d87-5994-4ca3-9d8a-e0455804780f)

## Motor DC 
### ¿Qué es un motor DC?
> 🔑 Un motor de corriente continua (DC), también conocido como motor de corriente directa, es una máquina eléctrica que convierte la energía eléctrica en energía mecánica, generando un movimiento rotatorio. Funciona mediante la interacción entre un campo magnético y el flujo de corriente eléctrica, produciendo un movimiento de rotación.

### Modelamiento del sistema
![image](https://github.com/user-attachments/assets/3539ebd9-bb9e-4edd-8d15-4234a30b275a)

## ⚙️ Motor DC (Corriente de campo)

### 🔌 Circuito electromagnético:

$$L_c \frac{di_c}{dt} + R_c i_c = v_c(t)$$

En Laplace:

$$I_c(s) = V_c(s) \cdot \frac{1}{sL_c + R_c}$$

---

### ⚡ Comportamiento del campo:

- El flujo en el entre hierro es proporcional a la corriente de campo:  
  $$\Phi = K_c i_c$$
- Torque desarrollado es proporcional al flujo y la corriente de armadura:  
  $$T_m = K_a i_a(t) K_c i_c(t)$$  
  $$T_m(s) = K_m I_c(s)$$
  donde:  
  $$K_m = K_a K_c I_a$$
- Torque aplicado a la carga:  
  $$T_c(s) = T_m(s) - T_p(s)$$

---

### ⚙️ Sistema rotacional:
El torque aplicado (parte mecánica) a la carag se comporta como un sistema rotacional clásico que se considera la incercia y la fricción mécanica 

$$J \frac{d^2\theta}{dt^2} + b \frac{d\theta}{dt} + k\theta = \tau(t)$$

En Laplace:

$$\Theta(s) = T_c(s) \cdot \frac{1}{Js^2 + bs}$$

---
### 🔁 Conexión de bloques

La conexión entre subsistemas da como resultado:

$$\Theta(s) = V_c(s) \cdot \frac{K_m}{(sL_c + R_c)(Js^2 + bs)} - T_p(s) \cdot \frac{1}{Js^2 + bs}$$

O, sin perturbación:

$$\frac{\Theta(s)}{V_c(s)} = \frac{K_m}{(sL_c + R_c)(Js^2 + bs)}$$

![image](https://github.com/user-attachments/assets/be67e459-27cb-4908-ac86-03cee524708d)


- La corriente de campo se considera constante por lo tanto el torque es:

$$T_m(s) = (K_a K_c I_c) I_a(s) = K_m I_a(s)$$

- La corriente de armadura se relaciona con el voltaje aplicado a la armadura por:  Re

$$V_a(s) = (sL_a + R_a) I_a(s) + V_b(s)$$

- El voltaje inducido en la armadura es proporcional a la velocidad angular del eje:

$$V_b(s) = K_b \omega(s)$$

- Combinando:

$$I_a(s) = \frac{V_a(s) - K_b \omega(s)}{sL_a + R_a}$$


### 🛠️ Parte mecánica:

La parte mecánica es igual que en el caso anterior:

$$T_c(s) = T_m(s) - T_p(s)$$

$$\Theta(s) = T_c(s) \cdot \frac{1}{s^2 J + bs}$$

### Diagramas de bloques resueltante
![image](https://github.com/user-attachments/assets/106e8133-9fa2-4d8c-af0c-9884d3337104)

## Elementos transmisores de energía 

### Engranajes y poleas 
## ⚙️ Engranajes y Poleas

![image](https://github.com/user-attachments/assets/98d25d65-c872-4f04-97dc-e5b113d102c1)

> 🔑 Son dispositivos mecánicos que **transmiten energía** de una parte del sistema a otra.
> 🔑 Se utilizan para modificar la velocidad angular, el torque y la inercia equivalente en sistemas mecánicos acoplados.

---

### 🔗 Relaciones fundamentales

- Relación de torque:

$$\frac{\tau_2}{\tau_1} = \frac{N_2}{N_1}$$

- Relación de desplazamiento angular:

$$\frac{N_2}{N_1} = -\frac{\theta_1}{\theta_2}$$

### 🛠️ Ajustes por engranajes en el modelo del motor DC

Cuando se considera el efecto de engranajes o poleas, cambian los parámetros $$J$$ y $$K_m$$

La función de transferencia ajustada es:

$$\Theta(s) = V_c(s) \cdot \frac{K_m}{(sL_c + R_c)(Js^2 + bs)} - T_p(s) \cdot \frac{1}{Js^2 + bs}$$

$$\frac{\Theta(s)}{V_c(s)} = \frac{K_m}{(sL_c + R_c)(Js^2 + bs)}$$

---

### ⚙️ Cálculo de parámetros equivalentes:

- Fricción equivalente:

$$\beta_{\text{equiv}} = \left( \frac{N_1}{N_2} \right)^2 \cdot \beta$$

- Inercia equivalente:

$$J_{\text{equiv}} = \left[ J_{N_1} + \left( \frac{N_1}{N_2} \right)^2 (J + J_{N_2}) \right]$$

### Diagrama de bloques 
![image](https://github.com/user-attachments/assets/8e8262de-f561-40e5-ab98-8b83db9adfba)

### Transimición rotacional a lineal 
![image](https://github.com/user-attachments/assets/2c430373-f249-4ffb-9448-5b0e19f30899)

--- 
## ⚖️ Palancas

> ![image](https://github.com/user-attachments/assets/1bc3421b-a549-46df-ab7e-cb43db19c03c)


> 🔑Las **palancas** son dispositivos mecánicos simples que permiten **multiplicar fuerzas** o **distancias** para facilitar el equilibrio o el movimiento. Se componen principalmente de:

- Un **punto de apoyo** o fulcro.
- Dos **brazos** (distancias desde el fulcro a cada extremo): $$d_1$$ y $$d_2$$
- Fuerzas aplicadas en cada extremo: $$f_1$$ y $$f_2$$

---

### 🔁 Relación de fuerzas y desplazamientos

El sistema se mantiene en equilibrio cuando se cumple:

$$\frac{-f_2}{f_1} = \frac{d_1}{d_2}$$

También existe una relación entre desplazamientos:

$$\frac{d_1}{d_2} = -\frac{x_1}{x_2}$$

Donde:
- $$x_1$$: desplazamiento del punto de aplicación de \( f_1 \)
- $$x_2$$: desplazamiento del punto de aplicación de \( f_2 \)


- Representar transformaciones de señales mecánicas en sensores

## 🎛 Potenciómetro de rotación

> ![image](https://github.com/user-attachments/assets/c1c75faa-bf89-4276-a2af-68facf5444c6)

> 🔑 Un potenciómetro rotativo es un sensor **electromecánico** que convierte una posición angular en un valor de voltaje proporcional. El **cursor** se mueve sobre una banda resistiva metálica.

###  Relación matemática:

$$V_o = \frac{\theta}{\theta_\text{máx}} \cdot V_{cc}$$

- $$\theta$$: ángulo actual (en grados o radianes)
- $$\theta_{\text{máx}}$$: ángulo máximo permitido por el sensor (ej. 270°)
- $$V_{cc}$$: voltaje de alimentación
- $$V_o$$: voltaje de salida

### 📊 Comportamiento
 ![image](https://github.com/user-attachments/assets/0b3fd256-a779-492b-b8e7-ba392fabf5e0)

Puede presentar dos tipos de respuesta:
- **Lineal**: la salida aumenta proporcionalmente al giro.
- **Logarítmica**: útil para audio o percepción humana, donde la ganancia no es lineal.

---

##  Potenciómetro de traslación

> ![image](https://github.com/user-attachments/assets/f47b2036-1dab-420f-aa4e-b88144bb5d1e)

> 🔑  Es similar al rotativo, pero convierte un **desplazamiento lineal** en voltaje proporcional. Se utiliza en sistemas donde se mide movimiento rectilíneo (como pistones, carros, etc.).

### 📐 Relación matemática:

$$V_o = \frac{x}{x_\text{máx}} \cdot V_{cc}$$

- $$x$$: posición del cursor
- $$x_{\text{máx}}$$: recorrido máximo
- $$V_o$$: voltaje de salida

---

### 📝 Aplicaciones comunes

- Medición de posición en sistemas de control
- Interfaz de usuario (como perillas)
- Robótica, mecatrónica y sistemas de retroalimentación

## 🌀 Tacómetro

> ![image](https://github.com/user-attachments/assets/676d1f0a-36e8-4e6a-b733-968975443975)

> 🔑 Los **tacómetros** son sensores utilizados para **medir la velocidad angular** de un eje y convertirla en una señal de **voltaje proporcional**. Son muy utilizados en sistemas de control de motores para obtener retroalimentación de velocidad.

---

### 🔧 Relación:

En el dominio del tiempo:

$$v(t) = k \cdot \frac{d\theta(t)}{dt}$$

Donde:
- $$v(t)$$: voltaje de salida del tacómetro
- $$\theta(t)$$: posición angular
- $$k$$: constante del tacómetro

---

### ⚙️ Función de transferencia:

En el dominio de Laplace:

$$G(s) = \frac{V(s)}{\Theta(s)} = ks$$

---

### 📦 Diagrama de bloques típicp
![image](https://github.com/user-attachments/assets/f274cc42-b751-440a-9b08-952b0c62f877)

- El tacómetro actúa como un bloque con ganancia $$k$$
- Se ubica después del sistema mecánico (eje o motor)
- Su salida se usa como señal de realimentación en sistemas de control

---

## Sensores Transmisores

> 🔑 Los sensores transmisores son dispositivos que convierten una **variable del proceso** $$PV(s)$$ en una **salida transmisible** $$TO(s)$$, usualmente en forma de voltaje, corriente o señal digital.

---

### ✅ Si son lineales:

La relación entre la señal de salida y la de entrada es directamente proporcional:

$$H(s) = \frac{TO(s)}{PV(s)} = K$$

Donde:
- $$K$$: ganancia del sensor transmisor

---

### ❌ Si no son lineales:

En este caso el sistema tiene una dinámica propia (como un retardo o un filtro de primer orden):

$$H(s) = \frac{TO(s)}{PV(s)} = \frac{K_T}{\tau_T s + 1}$$

Donde:
- $$K_T$$: ganancia del transmisor
- $$\tau_T$$: constante de tiempo del sensor transmisor

---

### 📦 Diagrama 

> ![image](https://github.com/user-attachments/assets/19a584f7-29ef-4342-8537-326103c33c08)

La variable del proceso $$PV(s)$$ entra al transmisor $$H(s)$$, que la convierte en una salida $$TO(s)$$ utilizable por el sistema de control:

## Modelos de otros procesos 
### 🧪 Mezcla de Sustancias

> ![image](https://github.com/user-attachments/assets/0e9f2f07-b37d-4f48-9a0e-fb1682749755)

En un sistema de mezcla continua, donde entra una sustancia a cierta concentración y velocidad y sale a igual velocidad con agitación, la función de transferencia es:

$$G(s) = \frac{Q(s)}{Q_i(s)} = \frac{\rho_{inicial} \cdot s + \rho_{in} \cdot v_{in}}{s + v_{out}}$$
---

##  Ejemplo

- Se tiene un tanque con 8 litros de agua salada (2 kg de sal).
- Ingresa una salmuera (agua salada) con 3 kg de sal/litro a 4 l/min.
- La mezcla se agita y sale a 4 l/min.

La función de transferencia:

$$G(s) = \frac{Q(s)}{Q_i(s)} = \frac{2s + 3 \cdot 4}{s + 4}$$

Es decir:

$$G(s) = \frac{2s + 12}{s + 4}$$

##  Sistema Térmico

El sistema térmico modela el comportamiento de un horno eléctrico que recibe una entrada de calor $$q_{in}$$ a través de un elemento calefactor. La salida del sistema es la temperatura interna del horno $$T_h$$, afectada por la transferencia de calor al ambiente $$T_A$$.

![image](https://github.com/user-attachments/assets/f67ed461-236b-430a-ab5f-63aeeeba7c92)

La función de transferencia que modela este sistema es:

$$G(s) = \frac{T(s)}{Q_{in}(s)} = \frac{1/C}{s + 1/RC}$$

---

##  Ejemplo de aplicación

En este sistema se introduce una señal de error $$e$$ que es amplificada, convertida en corriente a través de un solenoide y utilizada para controlar una válvula de vapor que regula la entrada de calor al horno. El proceso incluye retroalimentación con un termopar que mide la temperatura final.

![image](https://github.com/user-attachments/assets/83e5e9b2-0ffd-47f5-b80b-64b3982ac251)

En el diagrama de bloques, cada etapa está representada por una función de transferencia: desde la amplificación, el sistema electromecánico (solenoide), la válvula, hasta el modelo térmico del horno. La salida es la temperatura $$y$$, y se retroalimenta al amplificador para control automático.

![image](https://github.com/user-attachments/assets/a2aa1f77-ffd8-4cbc-98a9-67a2e4bdc49e)

## 📚Ejercicio 1 (Propio):

Modelar la función de transferencia del sistema solenoide desde el voltaje de entrada $$V(s)$$ hasta la posición de salida $$X(s)$$.

**Datos:**

- $$R = 4\ \Omega$$, $$L = 0.5\ \text{H}$$  
- $$K_s = 10\ \text{N/A}$$  
- $$m = 2\ \text{kg}$$, $$b = 3\ \text{N·s/m}$$, $$k = 50\ \text{N/m}$$  

**Desarrollo:**

1. **Parte eléctrica**  
   $$I(s) = \frac{V(s)}{Ls + R} = \frac{V(s)}{0.5s + 4}$$

2. **Fuerza del solenoide**  
   $$F(s) = K_s \cdot I(s) = 10 \cdot \frac{V(s)}{0.5s + 4}$$

3. **Sistema mecánico**  
$$X(s) = \frac{F(s)}{ms^2 + bs + k} = \frac{10 \cdot \frac{V(s)}{0.5s + 4}}{2s^2 + 3s + 50}$$

4. **Función de transferencia total**

$$ \frac{X(s)}{V(s)} = \frac{10}{(0.5s + 4)(2s^2 + 3s + 50)} $$


## 📚Ejercicio 2 (Propio):

Modelar el sistema de control de temperatura de un horno eléctrico con retroalimentación.

**Datos:**
$$K_A = 5$$  
$$G_1(s) = \frac{10}{0.5s + 4}$$  
$$G_2(s) = \frac{1}{5s + 1}$$ (con $$C = 1$$, $$R = 5$$)  
Realimentación unitaria

**Desarrollo:**

1. **Sistema en lazo directo:**  
$$G(s) = 5 \cdot \frac{10}{0.5s + 4} \cdot \frac{1}{5s + 1} = \frac{50}{(0.5s + 4)(5s + 1)}$$

2. Expandiendo el denominador.

$$ (0.5s + 4)(5s + 1) = 2.5s^2 + 20.5s + 4 $$

4. **Función de transferencia en lazo cerrado** .

$$G_{cl}(s) = \frac{G(s)}{1 + G(s)} = \frac{50}{2.5s^2 + 20.5s + 54}$$




## 📚Ejercicio 3 (Propio):

Se tiene un tanque bien mezclado con volumen constante. Se analiza la cantidad de sal en función del tiempo.

**Datos:**
- Volumen inicial: $$V = 8\ \text{L}$$  
- Sal inicial: $$2\ \text{kg}$$  
- Flujo de entrada y salida: $$q = 4\ \text{L/min}$$  
- Concentración de entrada: $$c_{in} = 3\ \text{kg/L}$$

**Modelamiento:**

La concentración de salida es proporcional a la del tanque.

1. Ecuación diferencial:

$$
\frac{dQ}{dt} = q \cdot c_{in} - q \cdot \frac{Q(t)}{V}
$$

2. Transformada de Laplace:

$$
sQ(s) - Q(0) = q \cdot C_{in}(s) - \frac{q}{V} Q(s)
$$

Con $$Q(0) = 2$$ y $$C_{in}(s) = \frac{3}{s}$$:

$$
sQ(s) - 2 = \frac{12}{s} - \frac{4}{8} Q(s)
$$

$$
sQ(s) + 0.5Q(s) = \frac{12}{s} + 2
$$

$$
Q(s)(s + 0.5) = \frac{12}{s} + 2
$$

$$
Q(s) = \frac{\frac{12}{s} + 2}{s + 0.5}
$$

3. Función de transferencia:

Si $$Q_i(s) = C_{in}(s) = \frac{3}{s}$$, entonces:

$$
G(s) = \frac{Q(s)}{Q_i(s)} = \frac{2s + 12}{s + 0.5}
$$

---

## 📚Ejercicio 4 (Propio):

Un motor de corriente directa mueve una carga mecánica a través de una reductora. Se modela desde el voltaje de entrada hasta la posición angular.

**Datos:**
- Parte eléctrica:  
  $$L = 0.2\ \text{H},\ R = 2\ \Omega$$  
  $$K_b = 0.5\ \text{V·s/rad}$$  
- Parte mecánica:  
  $$J = 0.02\ \text{kg·m}^2,\ B = 0.04\ \text{N·m·s/rad}$$  
  $$K_t = 0.5\ \text{N·m/A}$$  

**Ecuaciones:**

1. Parte eléctrica:

$$
V(s) = (Ls + R)I(s) + K_b s \theta(s)
$$

2. Parte mecánica:

$$
J s^2 \theta(s) + B s \theta(s) = K_t I(s)
$$

3. Despeje de $$I(s)$$:

$$
I(s) = \frac{J s^2 \theta(s) + B s \theta(s)}{K_t}
$$

4. Sustitución en la ecuación eléctrica:

$$
V(s) = (Ls + R) \cdot \frac{J s^2 \theta(s) + B s \theta(s)}{K_t} + K_b s \theta(s)
$$

Agrupando:

$$
V(s) = \left[ \frac{(Ls + R)(J s^2 + B s)}{K_t} + K_b s \right] \theta(s)
$$

5. Función de transferencia total:

$$
\frac{\theta(s)}{V(s)} = \frac{K_t}{(Ls + R)(Js^2 + Bs) + K_b K_t s}
$$

Sustituyendo valores:

$$
\frac{\theta(s)}{V(s)} = \frac{0.5}{(0.2s + 2)(0.02s^2 + 0.04s) + 0.25s}
$$

Desarrollando:

$$
= (0.2s + 2)(0.02s^2 + 0.04s) + 0.25s
$$

$$
= 0.004s^3 + 0.008s^2 + 0.04s^2 + 0.08s + 0.25s
$$

$$
= 0.004s^3 + 0.048s^2 + 0.33s
$$

6. Resultado final:

$$
\frac{\theta(s)}{V(s)} = \frac{0.5}{0.004s^3 + 0.048s^2 + 0.33s}
$$

