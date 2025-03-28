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
- \( F \) es la fuerza de fricción viscosa.
- \( b \) es la constante de fricción viscosa.
- \( \dot{x} \) es la velocidad.
- \( \dot{x}_1 \) y \( \dot{x}_2 \) son las velocidades relativas de los puntos en contacto.


## Tipos de Fricción

### Fricción en seco
 > 🔑 Es aquella que se representa cuando un cuerpo con una superficie no lubricada se desliza sobre otra superficie no lubricada.

### Fricción por deslizamiento


### Fricción por Rodamiento
<br>
<br>
<br>
<br>
<br>
<br>
<br>

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

$$ u(t) - k_1 x_1(t) - k_2 (x_1(t) - x_2(t)) - b \cdot \frac{d(x_1(t) - x_2(t))}{dt} = m_1 \cdot \frac{d^2 x_1(t)}{dt^2} $$

$$ k_2 \cdot (x_1(t) - x_2(t)) + b \cdot \frac{d(x_1(t) - x_2(t))}{dt} - k_3 \cdot x_2(t) = m_2 \cdot \frac{d^2 x_2(t)}{dt^2} $$
