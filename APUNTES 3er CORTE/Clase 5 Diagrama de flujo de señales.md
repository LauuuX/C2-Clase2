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

## 🧮 Ejemplo 3

!![image](https://github.com/user-attachments/assets/8419300a-4fcc-4df3-ba10-21b533d2695c)

**Ganancia de trayectoria directa:**

$$P_1 = 1 \cdot E_{R1} \cdot G_1 \cdot I_1 \cdot 1 \cdot E_{C1} \cdot 1 \cdot E_{R2} \cdot G_3 \cdot I_2 \cdot G_4 = E_{R1} G_1 I_1 E_{C1} E_{R2} G_3 I_2 G_4$$

**Ganancias de lazo:**

$$L_1 = -E_{C1} G_2$$

$$L_2 = -G_3 I_2$$

$$L_3 = -E_{R1} G_1 I_1 E_{C1}$$

**Determinante:**

$$\Delta = 1 - (L_1 + L_2 + L_3)$$

**Cofactor:**

$$\Delta_1 = 1 \quad \text{(los lazos tocan la trayectoria)}$$

**Función de transferencia total:**

$$\frac{E_0(s)}{E_1(s)} = \frac{P_1 \cdot \Delta_1}{\Delta}$$

**Expresión final desarrollada:**

$$\frac{E_{R1} G_1 I_1 E_{C1} E_{R2} G_3 I_2 G_4}{1 + E_{C1} G_2 + G_3 I_2 + E_{R1} G_1 I_1 E_{C1}}$$

## Actividad 

![image](https://github.com/user-attachments/assets/be2ab9da-5528-4ad4-839d-bcedd1952c03)

### Trayectorias directas

Se identifica 3 trayectorias directas desde $$R(s)$$ hasta $$Y(s)$$:

- **$$P_1$$**: Camino superior

  $$P_1 = 1 \cdot \frac{1}{s+5} \cdot \frac{1}{s^2+8} \cdot \frac{2}{s+7} \cdot \frac{s}{s+9} \cdot 1 = \frac{2s}{(s+5)(s^2+8)(s+7)(s+9)}$$

- **$$P_2$$**: Camino inferior

  $$P_2 = 1 \cdot \frac{1}{s+2} \cdot \frac{0.5}{s+6} \cdot 25 \cdot \frac{1}{s^2+s} \cdot \frac{1}{s} = \frac{12.5}{(s+2)(s+6)(s^2+s)s}$$

- **$$P_3$$**: Ruta intermedia cruzada entre la parte inferior y superior (por simetría, se evalúa con Mason si tiene contribución.

---

### Lazos cerrados

Identificamos 5 lazos cerrados:

- **$$L_1$$**: Auto-lazo en nodo 1:
  $$L_1 = -10$$

- **$$L_2$$**: Auto-lazo en nodo 4:
  $$L_2 = -3$$

- **$$L_3$$**: Rama inferior de nodo 2 a 6:
  $$L_3 = -12$$

- **$$L_4$$**: Rama inferior desde nodo 3 a 6:
  $$L_4 = -4$$

- **$$L_5$$**: Desde nodo 2 a 5, pasando por 3 y 4:
  $$L_5 = 25 \cdot \frac{1}{s^2 + s} \cdot \frac{1}{s} \cdot (-4) = -\frac{100}{s(s^2+s)}$$

---

### Determinante total $$\Delta$$

No hay lazos que no se toquen entre sí, entonces:

$$\Delta = 1 - (L_1 + L_2 + L_3 + L_4 + L_5)$$

Sustituyendo:

$$\Delta = 1 - (-10 - 3 -12 -4 - \frac{100}{s(s^2+s)}) = 1 + 29 + \frac{100}{s(s^2+s)}$$

---

### Cofactores $$\Delta_k$$

- **$$\Delta_1$$**: Lazos que no tocan $$P_1$$ → ninguno →
  $$\Delta_1 = 1$$

- **$$\Delta_2$$**: Lazos que no tocan $$P_2$$ → ninguno →
  $$\Delta_2 = 1$$

---

### Fórmula de Mason

$$\frac{Y(s)}{R(s)} = \frac{1}{\Delta} \left( P_1 \Delta_1 + P_2 \Delta_2 \right)$$

Sustituyendo:

$$\frac{Y(s)}{R(s)} = \frac{1}{1 + 29 + \frac{100}{s(s^2+s)}} \left( \frac{2s}{(s+5)(s^2+8)(s+7)(s+9)} + \frac{12.5}{(s+2)(s+6)(s^2+s)s} \right)$$

---

### ✅ Resultado final (simplificado)

$$\frac{Y(s)}{R(s)} = \frac{ \frac{2s}{(s+5)(s^2+8)(s+7)(s+9)} + \frac{12.5}{(s+2)(s+6)(s^2+s)s} }{30 + \frac{100}{s(s^2+s)}}$$

Este resultado representa la **función de transferencia** del sistema representado en el diagrama de flujo original.

# Ejercicios adicionales 
---

## ✅ Ejercicio 1
Función de transferencia por fórmula de Mason

![image](https://github.com/user-attachments/assets/d932bcd2-1cae-454c-94b9-454da60bbe0d)

---

### ✨ Trayectoria directa

Existe una única trayectoria desde $$R$$ hasta $$C$$:

- $$T_1 = G_3 \cdot G_8 \cdot G_2 \cdot G_5 \cdot G_1$$

---

### 🔁 Lazos cerrados

Se identifican los siguientes lazos:

- $$\lambda_1 = -G_3 \cdot G_8 \cdot G_2 \cdot G_5 \cdot G_1$$
- $$\lambda_2 = -G_8 \cdot G_7 \cdot G_6$
- $$\lambda_3 = -G_8 \cdot G_2 \cdot G_5 \cdot G_4 \cdot G_6$$

La suma de los lazos es:

$$\sum \lambda_i = \lambda_1 + \lambda_2 + \lambda_3 = -G_3 G_8 G_2 G_5 G_1 - G_8 G_7 G_6 - G_8 G_2 G_5 G_4 G_6$$

---

### 🧮 Determinante $$\Delta$$

Como no existen lazos disjuntos:

$$\Delta = 1 - \sum \lambda_i = 1 + G_3 G_8 G_2 G_5 G_1 + G_8 G_7 G_6 + G_8 G_2 G_5 G_4 G_6$$

---

### 🧩 Cofactores

- $$\Delta_1 = 1$$ porque no hay lazos que no toquen la trayectoria directa.

---

### 🧠 Aplicando fórmula de Mason

$$\frac{C(s)}{R(s)} = \frac{T_1 \cdot \Delta_1}{\Delta}$$

$$\frac{C(s)}{R(s)} = \frac{G_3 G_8 G_2 G_5 G_1}{1 + G_3 G_8 G_2 G_5 G_1 + G_8 G_7 G_6 + G_8 G_2 G_5 G_4 G_6}$$


## ✅ Ejercicio 2

Calcular la función de transferencia $$ \frac{Y(s)}{R(s)} $$ del siguiente flujograma:

![image](https://github.com/user-attachments/assets/816a4da4-4c00-4c94-8935-8d143775d3b4)


---

## 🔁 Trayectorias Directas

- $$P_1 = \frac{3s}{(s+1)(s+2)}$$
- $$P_2 = \frac{-4}{(s+1)}$$
- $$P_3 = 6$$

---

## 🔁 Lazos Independientes

- $$L_1 = \frac{-3}{s+1}$$
- $$L_2 = \frac{-5s}{s+2}$$

### Producto de lazos independientes:

- $$L_1 L_2 = \frac{15s}{(s+1)(s+2)}$$

---

## 🧮 Determinante

La fórmula del determinante es:

$$\Delta = 1 - \sum L_a + \sum L_b L_c - \sum L_d L_e L_f + \dots$$

Aplicamos:

$$\Delta = 1 - \left( \frac{-3}{s+1} + \frac{-5s}{s+2} \right) + \frac{15s}{(s+1)(s+2)}$$

---

## 🧩 Cofactores

- $$\Delta_1 = 1$$  
- $$\Delta_2 = 1 + \frac{5s}{s+2}$$  
- $$\Delta_3 = \Delta$$  

---

## 🎯 Función de Transferencia Final

Usamos la fórmula de Mason:

$$M(s) = \frac{1}{\Delta} \sum_k P_k \Delta_k$$

Sustituimos:

$$M(s) = \frac{\left( \frac{3s}{(s+1)(s+2)} \right)(1) + \left( \frac{-4}{s+1} \right)\left(1 + \frac{5s}{s+2} \right) + 6\left(1 + \frac{3}{s+1} + \frac{5s}{s+2} + \frac{15s}{(s+1)(s+2)} \right)}{1 - \left( \frac{-3}{s+1} + \frac{-5s}{s+2} \right) + \frac{15s}{(s+1)(s+2)}}$$

Simplificando, obtenemos:

$$M(s) = \frac{36s^2 + 135s + 40}{6s^2 + 26s + 8}$$

## ✅ Ejercicio 3

Calcular la función de transferencia $$ \frac{Y(s)}{R(s)} $$ del siguiente flujograma:

![image](https://github.com/user-attachments/assets/86e9d2ea-414d-4954-95d5-fe5b0259cbb4)

### Trayectorias Directas:

- $$P_1 = G_1 G_2 G_3 G_4$$
- $$P_2 = G_5 G_6 G_7 G_8$$

### Lazos Independientes:

- $$L_1 = G_2 H_1$$
- $$L_2 = G_3 H_2$$
- $$L_3 = G_6 H_3$$
- $$L_4 = G_7 H_4$$

### Pares de lazos:

- $$L_1 L_4 = G_2 H_1 G_7 H_4$$
- $$L_2 L_3 = G_3 H_2 G_6 H_3$$

### Determinante:

$$\Delta = 1 - (G_2 H_1 + G_3 H_2 + G_6 H_3 + G_7 H_4) + (G_2 H_1 G_7 H_4 + G_3 H_2 G_6 H_3)$$

### Cofactores:

- $$\Delta_1 = 1 - (G_6 H_3 + G_7 H_4)$$
- $$\Delta_2 = 1 - (G_2 H_1 + G_3 H_2)$$

### Resultado final:

Fórmula general:

$$M(s) = \frac{1}{\Delta} \sum_k P_k \Delta_k$$

Desarrollado:

$$M(s) = \frac{(G_1 G_2 G_3 G_4)(1 - (G_6 H_3 + G_7 H_4)) + (G_5 G_6 G_7 G_8)(1 - (G_2 H_1 + G_3 H_2))}{1 - (G_2 H_1 + G_3 H_2 + G_6 H_3 + G_7 H_4) + (G_2 H_1 G_7 H_4 + G_3 H_2 G_6 H_3)}$$
