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

