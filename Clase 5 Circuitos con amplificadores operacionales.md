## Amplificadores operacionales
>🔑Un amplificador operacional (AOP o op-amp) es un circuito integrado electrónico de alta ganancia con dos entradas y una salida. Se utiliza para amplificar señales, realizar operaciones matemáticas (suma, resta, integración, diferenciación) y otras tareas en circuitos analógicos y digitales.


## Amplificador no inversor:

>🔑Este tipo de configuración se caracteriza por tener conectado la señal de entrada (voltaje) a la terminal no inversora, esto nos indica que la ganancia será positiva (al contrario del inversor). También tiene como característica una realimentación negativa (conocida normalmente como Rf ). En esta configuración la entrada está en fase con la salida, es decir, no hay desfase en señal alterna, a diferencia de la configuración inversora. Otra característica es que la ganancia siempre será mayor a 1.

![image](Imagenes/m.png) 

La tension en ambas entradas del amplificador son iguales V+ = V-.
La corriente a las entradas del amplificador es 0.
La impedancia de entrada es muy grande.
La impedancia de salida es muy pequeña.

![image](Imagenes/ñ.png) 

$$ i_1-i_2=0 $$
$$ \frac{e_o-e_i}{R_2}-\frac{e_i}{R_1}=0 $$
$$ \frac{e_o}{R_2}=e_i\left(\frac{1}{R_2}+\frac{1}{R_1}\right) $$
$$ e_o=e_i\left(1+\frac{R_2}{R_1}\right) $$

## ahora se muestra un circuito con elementos que almacenan energía:<br>

![image](Imagenes/O.png) 

$$
i_1-i_2-i_3=0
$$
$$
\begin{gathered}
\frac{e_i-e^{\prime}}{R_1}-\frac{e^{\prime}-e_o}{R_2}-C \frac{d\left(e^{\prime}-e_o\right)}{d t}=0 \\
e^{\prime}=0 \\
\frac{e_i}{R_1}-\frac{-e_o}{R_2}-C \frac{d\left(-e_o\right)}{d t}=0 \\
\frac{e_i}{R_1}=-\frac{e_o}{R_2}-C \frac{d\left(e_o\right)}{d t}
\end{gathered}
$$

### 💡*Ejemplo 1:*
Obtener el modelo matematico para el circuito de la figura:<br>
![image](Imagenes/p.png) 

Se realiza la sumatoria de corrientes:

$$ I_1+I_2-I_3-I_4=0 $$

Se sustituyen valores:

$$ C_1 \frac{d\left(E_i-V_x\right)}{d t}+\frac{E_i-V_x}{R_1}-C_2 \frac{d\left(V_x-E_{(s)}\right)}{d t}-\frac{V_x-E_s}{R_2}=0 $$

Ecuación resultante:

$$ C_1 \frac{d E_i}{d t}+\frac{E_i}{R_1}+ C_2 d \frac{E_s}{dt}+\frac{E_s}{R_2}=0 $$

#  Sistemas Hidráulicos de Tanques
> 🔑 Son  aquellos  sistemas  en  los  que  seproduce  una  circulación  de  líquido  a  lolargo  de  los  elementos  que  forman  elsistema bajo la acción de diferencias depresión.  Los  caudales  de  líquido  y  ladiferencia  de  presiones  son  lasmagnitudes  que  se  pretenden  modelar.Las  ecuaciones  de  balance  surgen  de  laley de conservación de masa.


##  Parámetros y Variables

- $$qi$$: Flujo de entrada al tanque.  
- $$q1$$: Flujo de salida del tanque.  
- $$R1$$: Resistencia hidráulica al flujo.  
- $$A1$$: Área transversal del tanque.  
- $$h1$$: Altura o nivel de líquido en el tanque.
  
![image](https://github.com/user-attachments/assets/4faa108c-c720-41ab-a5c4-3ae896fdb929)

- Flujo de salida del tanque
$$q_1 = \frac{h_1}{R_1}$$

- Intercambio de energía

$$A_1 \frac{dh_1}{dt} = q_i - q_1$$

## Modelado de un Tanque Hidráulico

### Modelo con $$q_i$$ como entrada y $$h_1$$ como salida

- Flujo de salida del tanque:

  $$q_1 = \frac{h_1}{R_1}$$

- Intercambio de energía:

  $$A_1 \frac{dh_1}{dt} = q_i - q_1$$

- Reemplazando:

  $$A_1 \frac{dh_1}{dt} = q_i - \frac{h_1}{R_1}$$

  $$q_1 = \frac{h_1}{R_1}$$

  $$A_1 \frac{dh_1}{dt} = q_i - q_1$$

- Se despeja $$h_1$$:

  $$h_1 = q_1 \cdot R_1$$

  $$\frac{dh_1}{dt} = R_1 \frac{dq_1}{dt}$$

- Reemplazando:

  $$R_1 A_1 \frac{dq_1}{dt} = q_i - q_1$$







