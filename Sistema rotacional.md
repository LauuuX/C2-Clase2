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

Aplicando la Segunda Ley de Newton para movimiento rotacional:

$$\text{Suma de torques} = \text{Momento de inercia} \times \text{Aceleración angular}$$

Es decir:

$$T(t) - F_F = J \cdot \alpha$$

donde:
- $$\(\alpha = \frac{d^2\theta(t)}{dt^2}\)$$ es la aceleración angular,
- $$\(F_F = b \cdot \frac{d\theta(t)}{dt}\)$$ es la fuerza de fricción rotacional.



##  Sustituyendo:
$$T(t) - b \cdot \frac{d\theta(t)}{dt} = J \cdot \frac{d^2\theta(t)}{dt^2}$$
