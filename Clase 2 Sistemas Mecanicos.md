# Sistemas mecánicos 
> 🔑 Los sistemas mecánicos son un conjunto de componentes, elementos o dispositivos físicos cuya función específica es convertir o transmitir el movimiento y la fuerza de entrada generada por alguna fuente de energía, al movimiento y la fuerza de salida que se desea producir. Por tanto, son sistemas que tienen partes móviles.

![image](https://github.com/user-attachments/assets/b709b76f-9a0b-42e8-9ae2-c3b98cc9705c)

Figura 1. Representación de sistemas 

## Principio general de modelamiento 
Tasa de acumulación × (Masa o Energía) = Flujo de (Masa o Energía) de Entrada - Flujo de (Masa o Energía) de Salida

## Sitemas mecánicos: 
### Resorte:
> 🔑 Se asumen resortes lineales, la fuerza externa aplicada y el desplazamiento están relacionados por una constante de proporcionalidad.

$$F = kx = k(x_1 - x_2)$$

Donde:
- $$\( F \)$$ es la fuerza.
- $$\( k \)$$ es la constante de elasticidad.
- $$\( (x_1 - x_2) \)$$ es la distancia comprimida o estirada del resorte.
  
![image](https://github.com/user-attachments/assets/ea767fdc-764c-4ba3-914a-dc28875ed51f)

Figura 2. Resorte

![image](https://github.com/user-attachments/assets/a1d73215-4af7-485c-a273-aae052e3a521)

Figura 3. Gráfica de los tipos de resorte 

### Amortiguador 
> 🔑 Un amortiguador es un elemento que absorbe la energía del sistema. Se utiliza para reducir la transmisión de vibraciones y ruidos.

* Comportamiento lineal, proporcional a la velocidad del desplazamiento. 
![image](https://github.com/user-attachments/assets/9fc49ae7-abea-4c16-866f-afa109c507e5)

Figura 4. Amortiguador 

$$F = b\dot{x} = b(\dot{x}_1 - \dot{x}_2)$$

Donde:
- $$F$$ es la fuerza de fricción viscosa.
- $$b$$ es la constante de fricción viscosa.
- $$\dot{x}$$ es la velocidad.
- $$\dot{x}_1$$ y $$\dot{x}_2$$ son las velocidades relativas de los puntos en contacto.


## Tipos de Fricción
  > 🔑 Es aquella que se presenta cuando un cuerpo con una superficie no lubricada se desliza sobre otra superficie no lubricada.
  * Fricción estática
  * Fricción por deslizamiento
  * Fricción por rodamiento
    
    ![image](https://github.com/user-attachments/assets/a9b53518-b6bd-47c9-a552-530991cec203)

    Figura 5. Tipos de fricción  

### Fricción estática 
 > 🔑 Es aquella que se representa cuando un cuerpo con una superficie no lubricada se desliza sobre otra superficie no lubricada.

  ![image](https://github.com/user-attachments/assets/557ddb5c-b6f5-40dd-9e0b-c21ef582080d)

  Figura 6. Fricción estática  

### Fricción por deslizamiento
> 🔑 fricción por deslizamiento como la resistencia que crean dos objetos cualesquiera al deslizarse uno contra el otro . Esta fricción, también conocida como fricción cinética, se define como la fuerza necesaria para mantener una superficie deslizándose sobre otra.

  ![image](https://github.com/user-attachments/assets/46ca6eda-8a20-4fa1-84a3-32e61c581dd2)

  Figura 7. Fricción por deslizamiento   


### Fricción por Rodamiento
> 🔑El rozamiento por rodadura es la fricción que se produce cuando dos cuerpos ruedan o se deslizan entre sí. Se presenta cuando uno de los cuerpos se deforma, o ambos. 

  ![image](https://github.com/user-attachments/assets/70cd5274-ef6e-4f76-a7e3-3288b1a27b0d)

  Figura 8. Fricción por rodamiento 
## Sistema masa - resorte - amortiguador 
* $$F_R = k_2 \cdot x \quad \text{→ Ley de Hooke}$$

* $$F_F = k_1 \cdot v_m \quad \text{→ Fricción viscosa}$$

* $$F = m \cdot a \quad \text{→ Leyes de Newton}$$

  ![image](https://github.com/user-attachments/assets/6131fb3d-4e1b-4ea5-a614-1917c25dc112)

  Figura 9. Sistema masa - resorte
  
### Diagrama de cuerpo libre 
  ![image](https://github.com/user-attachments/assets/f985c2d4-3c10-4926-8d3c-d25fe07a2646)

  Figura 10. Diagrama de cuerpo libre 
### Solución 

$$u - F_R - F_F = m \cdot a$$

$$F_R = k_2 \cdot y(t)$$

$$u(t) - k_2 \cdot y(t) - F_F = m \cdot a$$

$$F_F = k_1 \cdot \frac{dy(t)}{dt}$$

$$u(t) - k_2 \cdot y(t) - k_1 \cdot \frac{dy(t)}{dt} = m \cdot a$$

$$a = \frac{d^2y(t)}{dt^2}$$

$$u(t) - k_2 \cdot y(t) - k_1 \cdot \frac{dy(t)}{dt} = m \cdot \frac{d^2y(t)}{dt^2}$$

💡**Ejemplo :**
* Encontrar el modelo matemático para el sistema que representa a la suspención de un automóvil.
  
    ![image](https://github.com/user-attachments/assets/7edc7562-81b3-4cbb-ab0f-297b90f3fd16)
  
     Figura 10. Sistema masa - resorte - amortiguador
  
### Solución 

![image](https://github.com/user-attachments/assets/5cf17dd6-0505-42b7-9931-b9973ba1be34)

Figura 11. Comportamiento de un resorte 

 No se tiene en cuenta el efecto de la fuerza de gravedad si se considera el desplazamiento desde la posición de equilibrio, puesto que en ese caso:
$$k \cdot \delta = m \cdot g$$

Y si se considera la sustitución:

$$y = x + \delta$$

El término correspondiente a la fuerza de gravedad desaparece.

#### Diagrama de cuerpo libre: 
  ![image](https://github.com/user-attachments/assets/5ee39e91-2ccc-42b8-8879-b838fd292e69)
  
  Figura 12. Diagrama de cuerpo libre masa - resorte - amortiguador
 
### Solución de la ecuación diferencial 

* $$sum F = m \cdot a$$
  
* Las fuerzas que actúan sobre la masa \( m \) son:

- $$F_R = k_2 \cdot y(t)$$: fuerza del resorte (hacia arriba)
- $$F_F = k_1 \cdot \frac{dy(t)}{dt}$$: fricción viscosa (hacia arriba)
- $$F_W = m \cdot g$$: peso (hacia abajo)
- $$u(t)$$: fuerza externa (hacia abajo)

$$u(t) - F_R - F_F = m \cdot \frac{d^2y(t)}{dt^2}$$

$$u(t) - k_2 \cdot y(t) - k_1 \cdot \frac{dy(t)}{dt} = m \cdot \frac{d^2y(t)}{dt^2}$$

$$m \cdot \frac{d^2y(t)}{dt^2} + k_1 \cdot \frac{dy(t)}{dt} + k_2 \cdot y(t) = u(t)$$

## Vibración libre

- Aún aplicando entrada durante un intervalo de tiempo definido es posible provocar un comportamiento oscilatorio en la variable de salida del sistema.
- Por ejemplo, en el caso de la suspensión, si se aplica una fuerza constante durante un intervalo corto de tiempo y luego se retira dicho estímulo, el sistema tiende a vibrar.
- Este movimiento periódico se conoce como **vibración libre**

💡 Ejemplo: 

 ### Respuesta del sistema bajo vibración libre

- $$k = 22500\ \frac{N}{m}$$
- $$b = 2000\ \frac{Ns}{m}$$
- $$m = 460\ kg$$ masa del vehículo + 2 personas de 80 kg

 ### Ecuación del sistema

$$m \cdot \frac{d^2y}{dt^2} + b \cdot \frac{dy}{dt} + k \cdot y = 0$$
$$460 \cdot \ddot{y}(t) + 2000 \cdot \dot{y}(t) + 22500 \cdot y(t) = 0$$

## Sistemas mecánicos más complejos
> 🔑 Son aquellos que tienen más de dos elementos de enlace. Se caracterizan por tener partes interconectadas que generan un comportamiento inesperado.

💡**Ejemplo 1:**\
![image](Imagenes/a.png)

Diagrama de cuerpo libre de cada masa:

| **D.C.L masa 1** | **D.C.L masa 2** |
|------------------|------------------|
|       ![image](Imagenes/b.png)       |                       ![image](Imagenes/c.png)            |

-Ecuacion para la masa 1:

$$ u - F_{R1} - F_{R2} - F_F = m_1 \cdot a_{m1} $$

La distancia de elongación del resorte 2 depende del movimiento de ambas masas

La velocidad del émbolo del amortiguador del resorte 2 depende del movimiento de ambas masas

Reemplazando valores queda:

$$ u(t) - k_1 x_1(t) - k_2 (x_1(t) - x_2(t)) - b \cdot \frac{d(x_1(t) - x_2(t))}{dt} = m_1 \cdot \frac{d^2 x_1(t)}{dt^2} $$

<br>
------------------------------------------------------------------------
<br>
-Ecuacion para la masa 2:

$$ F_{R2} + F_F - F_{R3}= m_2 \cdot a_{m2} $$

La distancia de elongación del resorte 2 depende del movimiento de ambas masas

La velocidad del émbolo del amortiguador del resorte 2 depende del movimiento de ambas masas

Reemplazando valores queda:

$$ k_2 \cdot (x_1(t) - x_2(t)) + b \cdot \frac{d(x_1(t) - x_2(t))}{dt} - k_3 \cdot x_2(t) = m_2 \cdot \frac{d^2 x_2(t)}{dt^2} $$


## Modelo resultante:

![image](Imagenes/a.png)

$$u(t) - k_1 x_1(t) - k_2 (x_1(t) - x_2(t)) - b \cdot \frac{d(x_1(t) - x_2(t))}{dt} = m_1 \cdot \frac{d^2 x_1(t)}{dt^2}$$

$$k_2 \cdot (x_1(t) - x_2(t)) + b \cdot \frac{d(x_1(t) - x_2(t))}{dt} - k_3 \cdot x_2(t) = m_2 \cdot \frac{d^2 x_2(t)}{dt^2}$$

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

💡**Ejemplo 1:**

![image](https://github.com/user-attachments/assets/da866a79-91ce-4fa7-ac0d-ce9416c9ba9a)

Una masa $$m$$ unida a:
  - Un resorte con constante $$k$$
  - Dos amortiguadores: $$b_1$$ (con el suelo) y $$b_2$$ (en serie con el resorte)
- Entrada: fuerza externa $$u(t)$$
- Variables de posición:  
  - $$x_1(t)$$: posición de la masa  
  - $$x_2(t)$$: posición del punto entre el resorte y el amortiguador $$b_2$$

---

### 📊 Elementos del sistema

- Fuerza del resorte:  

$$F_k = k (x_2 - x_1)$$

- Fuerza del amortiguador $$b_2$$:  

$$F_{b_2} = b_2 (\dot{x}_2 - \dot{x}_1)$$

- Fuerza del amortiguador $$b_1$$:  

$$F_{b_1} = b_1 \cdot \dot{x}_1$$

### Aplicando la Segunda Ley de Newton a la masa

$$u(t) - k(x_1 - x_2) - b_2(\dot{x}_1 - \dot{x}_2) - b_1 \cdot \dot{x}_1 = m \cdot \ddot{x}_1$$


### Ecuación diferencial final

$$m \cdot \ddot{x}_1 + (b_1 + b_2) \cdot \dot{x}_1 + k \cdot x_1 = b_2 \cdot \dot{x}_2 + k \cdot x_2 + u(t)$$


