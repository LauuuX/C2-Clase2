# Diagrama de flujos de señales 
> 🔑 Los diagramas de flujo de señal son una representación visual alternativa de sistemas complejos. A diferencia de los diagramas de bloques convencionales, permiten visualizar claramente caminos de señal, lazos de retroalimentación y múltiples trayectorias de señal dentro de un sistema.

- Este tipo de diagramas permite otra forma de representación de los sistemas más complejos  
- Se utilizan para obtener de una manera más sencilla la función de transferencia total del Sistema  
- La fórmula de Mason permite calcular la función de transferencia de sistemas muy complejos

## 🔄 Elementos de los diagramas de flujo de señal

## **Nodo**: Representan las señales de entrada o salida del Sistema  
  - Se representa por medio de un **círculo con una etiqueta** que indique el nombre de la señal

Ejemplo:

- $$V(s)$$ ⭘  
- $$T(s)$$ ⬤

## ➤ Flecha:
Representa la relación entre las variables del sistema:

- Se representa por medio de flechas que indican el sentido de la relación.
- La flecha sale de la señal (Nodo) de entrada y llega a la señal de salida (Nodo).
- Se agrega una etiqueta a la flecha para indicar la función de transferencia que relaciona la entrada y la salida.

![image](https://github.com/user-attachments/assets/55b51900-8c58-4cdf-b862-97caa78f3e61)

## Comparación diagramas de bloques y flujos de señales 
**Diagrama de Bloques**: Se basa en cajas funcionales (bloques) que representan funciones de transferencia conectadas por sumadores y líneas de señal.
- **Diagrama de Flujo de Señal**: Usa nodos (señales) y flechas (funciones de transferencia) para representar las relaciones entre variables de forma más compacta y útil para aplicar la fórmula de ganancia de Mason.

Ambas representaciones son equivalentes, pero el flujo de señales es ideal para análisis algorítmicos.

![image](https://github.com/user-attachments/assets/538eeb45-837e-4ab6-a496-025d91f1dd1a)

## 📚 Definiciones importantes

- **Camino o trayectoria**: secuencia de ramas conectadas en el sentido de las flechas.
- **Camino abierto**: si ningún nodo se repite.
- **Camino cerrado**: si finaliza en el nodo inicial y no repite ningún nodo intermedio.
- **Ganancia de lazo**: producto de las ganancias de todas las ramas en un lazo cerrado.
- **Camino directo**: camino del nodo de entrada al de salida sin repetir nodos.
- **Ganancia de camino directo**: producto de las ganancias de las ramas en ese camino.
- **Lazo**: camino cerrado que parte y termina en el mismo nodo sin repetir nodos intermedios.

## 🧮 Fórmula de Mason

La fórmula de Mason se utiliza para calcular la **función de transferencia total** en un sistema representado por un diagrama de flujo de señal. Se define así:

$$P = \frac{1}{\Delta} \sum_k P_k \Delta_k$$

Donde:

- $$P_k$$: Ganancia del camino directo $$k$$.
- $$Delta$$: Determinante del sistema, calculado como:

$$\Delta = 1 - \sum (\text{lazos individuales}) + \sum (\text{pares de lazos que no se tocan}) - \sum (\text{ternas de lazos que no se tocan}) + \cdots$$

- $$\Delta_k$$: Igual que $$\Delta$$, pero **excluyendo** cualquier lazo que toque el camino directo $$P_k$$:

$$\Delta_k = 1 - \sum (\text{lazos que no toquen } P_k) + \sum (\text{pares de lazos que no se toquen entre sí ni toquen } P_k) - \cdots$$

Esta fórmula es especialmente útil en sistemas complejos donde los métodos tradicionales serían muy largos.

## ✏️ Ejemplo 1

![image](https://github.com/user-attachments/assets/39279c17-02f4-4ebe-ad87-a44861a5ba94)

**Trayectoria directa:**

$$P_1 = 1 \cdot 1 \cdot G_1 \cdot G_2 \cdot G_3 \cdot 1 = G_1 G_2 G_3$$

**Lazos cerrados:**

$$L_1 = G_1 G_2 H_1$$

$$L_2 = -G_2 G_3 H_2$$

$$L_3 = -G_1 G_2 G_3$$

**Determinante del sistema:**

$$\Delta = 1 - (L_1 + L_2 + L_3)$$

**Cofactor asociado al camino directo:**

$$\Delta_1 = 1$$

**Función de transferencia total:**

$$\frac{C(s)}{R(s)} = \frac{P_1 \Delta_1}{\Delta} = \frac{G_1 G_2 G_3}{1 - G_1 G_2 H_1 + G_2 G_3 H_2 + G_1 G_2 G_3}$$

## 🔁 Ejemplo 2

![image](https://github.com/user-attachments/assets/170e56e8-eb1f-4168-ba71-c81d0c1770c7)

**Ganancias de trayectoria directa:**

$$P_1 = G_1 G_2 G_3 G_4 G_5$$

$$P_2 = G_1 G_6 G_4 G_5$$

$$P_3 = G_1 G_2 G_7$$

**Ganancias de lazo:**

$$L_1 = -G_4 H_1$$

$$L_2 = -G_2 G_7 H_2$$

$$L_3 = -G_6 G_4 G_5 H_2$$

$$L_4 = -G_2 G_3 G_4 G_5 H_2$$

**Determinante:**

$$\Delta = 1 - (L_1 + L_2 + L_3 + L_4) + L_1 L_2$$

**Cofactores:**

$$
\Delta_1 = 1 \\
\Delta_2 = 1 \\
\Delta_3 = 1 - L_1
$$

> Nota: $$L_1$$ no toca la trayectoria  $$P_3$$

**Función de transferencia total:**

$$\frac{C(s)}{R(s)} = \frac{1}{\Delta} \left( P_1 \Delta_1 + P_2 \Delta_2 + P_3 \Delta_3 \right)$$

**Expresión final desarrollada:**

$$\frac{G_1 G_2 G_3 G_4 G_5 + G_1 G_6 G_4 G_5 + G_1 G_2 G_7 (1 + G_4 H_1)}{1 + G_4 H_1 + G_2 G_7 H_2 + G_6 G_4 G_5 H_2 + G_2 G_3 G_4 G_5 H_2 + G_4 H_1 G_2 G_7 H_2}$$

