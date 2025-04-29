# Sistema rotacional   

![image](https://github.com/user-attachments/assets/a2921009-9d9c-443b-8d46-4b656338c715)

Figura 1. Sistema rotacional 

>🔑 Es un fenómeno mecánico pero la naturaleza del movimiento cambia: ahora es *movimiento angular*.

## Se aplican leyes comparables al movimiento lineal:

### Leyes aplicables:

- Fuerza restauradora (resorte rotacional):

$$F_R = k \cdot \varphi \quad \rightarrow \quad \varphi \text{es el ángulo de torsión}$$

- Fuerza de fricción rotacional:

$$F_F = b \cdot \frac{d\varphi}{dt} \quad \rightarrow \quad \text{es la velocidad angular}$$

- Ley de Newton para movimiento rotacional:

$$T = J \cdot \frac{d^2\varphi}{dt^2} \quad \rightarrow \quad J \text{ es el momento de inercia}$$

- $$\( T(t) \)$$: Torque aplicado.
- $$\( \theta(t) \)$$: Ángulo de salida o desplazamiento angular.
- $$\( k \)$$: Constante del resorte de torsión.
- $$\( b \)$$: Coeficiente de fricción viscosa rotacional.
- $$\( J \)$$: Momento de inercia de la carga.

## Diagrama de cuerpo libre 

![image](https://github.com/user-attachments/assets/2c86ef3f-aef4-465b-9fa2-58c9a0795df6)

Figura 2. Diagrama de cuerpo de libre de un sistema rotacional 

$$T - F_R - F_F = J * \alpha \quad \rightarrow \quad \alpha \text{ aceleración angular}$$

$$T(t) - F_F = J * \alpha \quad \rightarrow \quad \alpha \text{ aceleración angular}$$

$$T(t) - k * \theta(t) - b * \frac{d\theta(t)}{dt} = J * \frac{d^2\theta(t)}{dt^2}$$

💡*Ejemplo 1:*
* Desarrollar un modelo para describir la posición angular. El eje es rigido.
  
![image](https://github.com/user-attachments/assets/ef75f0e6-9091-428a-8004-0b5859aba953)

Figura 3. Ejemplo 1

Aplicando la Segunda Ley de Newton para movimiento rotacional:

$$\text{Suma de torques} = \text{Momento de inercia} \times \text{Aceleración angular}$$

Es decir:

$$T(t) - F_F = J \cdot \alpha$$

donde:
- $$\(\alpha = \frac{d^2\theta(t)}{dt^2}\)$$ es la aceleración angular,
- $$\(F_F = b \cdot \frac{d\theta(t)}{dt}\)$$ es la fuerza de fricción rotacional.



##  Sustituyendo:
$$T(t) - b \cdot \frac{d\theta(t)}{dt} = J \cdot \frac{d^2\theta(t)}{dt^2}$$

##  Grados de Libertad 

- Es el número mínimo de coordenadas independientes requeridas para especificar las posiciones de todos los elementos de un sistema.

- **Ejemplo:** En el caso de un sistema de suspensión, solo se necesita **una coordenada (eje vertical)** para describir la posición.  
  Por lo tanto, es un sistema con un grado de libertad.

- Desde el punto de vista del modelo, se puede decir:

$$\text{DOF} = \text{Número de ecuaciones de movimiento} - \text{Número de ecuaciones de restricción}$$

![image](https://github.com/user-attachments/assets/fdb8b41a-e717-409f-b210-58c8b8f4974e)

 **Ecuación de movimiento:**

 $$m\ddot{x} + b\dot{x} + kx = 0$$

 **Grado de libertad:**

 $$\text{Grado de libertad} = 1 - 0 = 1$$

 ![image](https://github.com/user-attachments/assets/ae51af76-f6d2-4c20-bed4-ef7eb3f42b7f)

**Ecuaciones de movimiento:**

$$m\ddot{x}_1 + k_1(x_1 - x_2) + k_2x_1 = 0$$

$$k_1(x_1 - x_2) = b_1\dot{x}_2$$

**Grados de libertad:**

$$\text{Grados de libertad} = 2 - 0 = 2$$

![image](https://github.com/user-attachments/assets/69b36e3f-ec4b-4e39-a2de-9201b0b182d4)


$$m\ddot{x} = -T \sin(\theta)$$

$$m\ddot{y} = mg - T \cos(\theta)$$

**Ecuación de restricción (longitud constante del hilo):**

$$x^2 + y^2 = l^2$$

## 📚Ejercicio 1 (Propio):

