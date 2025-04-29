## Sistemas electricos
>🔑los sistemas eléctricos se analizan como un conjunto de componentes y conexiones que interactúan para generar, transportar y distribuir energía eléctrica. Se utilizan modelos matemáticos, como ecuaciones diferenciales y funciones de transferencia, para comprender el comportamiento temporal de estos sistemas bajo diferentes condiciones y cargas. Este análisis permite predecir cómo el sistema eléctrico se comportará ante eventos como la conexión o desconexión de cargas, o fallas en la red.

## Circuito RLC
>🔑 Los circuitos RLC son circuitos eléctricos en los que resistencias , inductores y condensadores se conectan en serie o en paralelo. Su nombre deriva de los símbolos utilizados para representar estos elementos en los diagramas de circuitos: «R» para resistencias, «L» para inductores y «C» para condensadores.<br>

El fenomeno fisico que modela este comportamiento es las leyes de kirchoff para cada circuito de la siguiente manera:

Ley de Ohm: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Carga de un condensador:
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;
Carga de un inductor:

![image](Imagenes/f.png) &nbsp;  $$R = \frac{v(t)}{i(t)}$$
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ![image](Imagenes/g.png) &nbsp;  $$i(t) = C\frac{dv(t)}{dt}$$
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ![image](Imagenes/h.png) &nbsp;  $$v(t) = L\frac{di(t)}{dt}$$
<br>


### 💡*Ejemplo 1:*

![image](Imagenes/i.png) 

### Aplicando ley de Kirchhoff

$$
-u(t) + v_R + v_L + v_C = 0
$$

$$
-u(t) + i(t) \cdot R + L \frac{di(t)}{dt} + y(t) = 0
$$

 Aún no está en términos de la variable \( y \)

$$
i(t) = C \frac{dy(t)}{dt}
$$

Sustituyendo en la ecuación:

$$
-u(t) + C \frac{dy(t)}{dt} \cdot R + L \frac{d}{dt} \left( C \frac{dy(t)}{dt} \right) + y(t) = 0
$$

Y simplificando:

$$
-u(t) + RC \frac{dy(t)}{dt} + LC \frac{d^2 y(t)}{dt^2} + y(t) = 0
$$

### 💡*Ejemplo 2:*
Obtener el modelo para el circuito de la figura:

![image](Imagenes/j.png) 

$$ Y=V_{R_2}+V_c $$
$$ -u(t)+V_{R_1}+V_{R 2}+V_c=0 $$
$$ -u(t) I\left(R_1+R_2\right)+V_c=0 $$
$$ I=I_c+C \frac{d V_c}{d t} $$
$$ -u(t)+\left(R_1+R_2\right) c \frac{d V_c}{d t}+V_c=0 $$


Para poder simplipicar más Vc realizamos nodos.<br>

$$ \frac{U-Y}{R_1}=\frac{Y-V_c}{R_2} \Rightarrow \frac{V_c}{R_2}=y\left(\frac{1}{R_1}+\frac{1}{R_2}\right)-\frac{u}{R_1} $$

$$ v_c=y\left(\frac{R_2}{R_1}+1\right)-\frac{R_2}{R_1} u$$
$$ \frac{d v_c}{d t}=\frac{d y}{d t}\left(\frac{R_2}{R_1}+1\right)-\frac{R_2}{R_1} \cdot \frac{d u}{d t} $$

Reemplazando:

$$ -u(t)+\left(R_1+R_2\right) c \frac{d y}{d t}\left(\frac{R_2}{R_2}+1\right)-\frac{R_2}{R_1} \frac{du}{d_t}+y\left(\frac{R_2}{R_1}+1\right)-\frac{R_2}{R_1} u=0 $$






