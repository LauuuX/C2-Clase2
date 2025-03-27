# Solucion puntos correspondientes del parcial:
## 📚Ejercicio 1: 
$$ 2x''+2x'+x=1$$ $$x(0)=0$$ $$x'(0)=2 $$

$$ 2L\left[ x'' \right]+2L\left[ x' \right]+L\left[ x \right]=L\left[ 1 \right] $$

$$ 2s^2L\left[ x \right]-x_{0}s-x_{0}^{'}+2sL\left[ x \right]-x_{0}+L\left[ x \right]=\frac{1}{s} $$


$$
\begin{aligned}
& 2\left(s^2L[x]-2\right)+2 s L[x]+L[x]=\frac{1}{s} \\
& 2 s^2 L[x]-4+2 s L[x]+L[x]=\frac{1}{s} \\
& L[x]\left(2 s^2+2 s+1\right)=\frac{1}{s}+4 \\
& L[x]=\frac{1}{s\left(2 s^2+2 s+1\right)}+\frac{4}{2 s^2+2 s+1}
\end{aligned}
$$

Se realiza fracciones parciales para despejar terminos.

$$
\begin{aligned}
& \frac{1}{s\left(2 s^2+2 s+1\right)}=\frac{A}{s}+\frac{B s+C}{2 s^2+2 s+1} \\
& 1=A\left(2 s^2+2 s+1\right)+(B s+C)(s) \\
& s=0
\end{aligned}
$$
$$
\begin{aligned}
& \left.1=A(2(0)^2+2(0)+1\right)+(B(0)+C)(0) \\
& A=1 
\end{aligned}
$$

$$ 1=2s^2+2s+1+Bs^2+Cs $$

$$ 0=2+B $$
$$ B=-2 $$
$$ 0=2+C $$
$$ C=-2 $$

$$ \frac{1}{s}-\frac{2s-2}{2s^2+2s+1} $$
$$ \frac{1}{s}-\frac{2(s+1)}{2(s^2+s+\frac{1}{2})} $$
$$ \frac{1}{s}-\frac{(s+\frac{1}{2})}{(s^2+s+\frac{1}{2})} $$
$$ \frac{1}{s}-\frac{(s+\frac{1}{2})}{(s^2+s+\frac{1}{2})}-\frac{1}{2}.\frac{1}{(s+\frac{1}{2})^{2}+\frac{1}{4}}+\frac{4}{2(s+\frac{1}{2})^{2}+\frac{1}{4}} $$


$$L[x]=\frac{1}{s}-\frac{s+\frac{1}{2}}{\left(s+\frac{1}{2}\right)^2+\frac{1}{4}}-\frac{1}{2} \cdot \frac{1}{\left(s+\frac{1}{2}\right)^2+\frac{1}{4}}+\frac{2}{\left(s+\frac{1}{2}\right)^2+\frac{1}{4}}$$
$$ x=L^{-1}\left[\frac{1}{s}\right]-L^{-1}\left[\frac{s+\frac{1}{2}}{\left(s+\frac{1}{2}\right)^2+\frac{1}{4}}\right]-\frac{1}{2} L^{-1}\left[\frac{1}{\left(s+\frac{1}{2}\right)^2+\frac{1}{4}}\right]+2 L^{-1}\left[\frac{1}{\left(s+\frac{1}{2}\right)^2+\frac{1}{4}}\right] $$

$$
x(t)= 1 - e^{-\frac{t}{2}} \cos\left(\frac{t}{2}\right) - \frac{1}{2} e^{-\frac{t}{2}} \cdot \sin\left(\frac{t}{2}\right) + 2 e^{-\frac{t}{2}} \cdot 2 \sin\left(\frac{t}{2}\right)
$$
### Resultado final:
$$
x(t)= 1 - e^{-\frac{t}{2}} \cos\left(\frac{t}{2}\right) - 3 e^{-\frac{t}{2}} \cdot \sin\left(\frac{t}{2}\right)
$$

## 📚Ejercicio 2: 

$$ F(s)=\frac{6 s}{\left(s-\frac{5}{2}\right)^{\left(s^2-4 s+8\right)}} $$
$$ =\frac{A}{s-\frac{5}{2}}+\frac{B s+C}{s^2-4 s+8} $$
$$ A=\left.\frac{6 s}{s^2-4 s+8}\right|_{s=5 / 2}=\frac{15}{\frac{17}{4}}=\frac{60}{17} $$
$$ 6 s=A\left(s^2-4 s+8\right)+B s+C\left(s-\frac{5}{2}\right) $$
$$ 6 s=A s^2-4 A S+8 A+B s^2-\frac{5}{2} B s+C S-\frac{5 C}{2} $$
$$ 0=A+B $$
$$ B=-A $$
$$ B=-\frac{60}{17} $$
$$ 0=8 A-\frac{5}{2} C $$
$$ 6=-4 A-\frac{5}{2} B+C $$
$$ C=6+4 A+\frac{5}{2} B $$
$$ C=6+4\left(\frac{60}{17}\right)+\frac{5}{2}\left(\frac{-60}{17}\right) $$
$$ C=\frac{192}{17} $$
$$ \frac{\frac{60}{17}}{s-\frac{5}{2}}-\frac{\frac{60}{17} s+\frac{192}{17}}{s^2-4 s+8} $$
$$ F(s)=\frac{\frac{60}{17}}{s-\frac{5}{2}}-\frac{60}{17} \cdot \frac{s-2}{(s-2)^2+4}+\frac{72}{17} \cdot \frac{1}{(s-2)^2+4} $$


$$ =\frac{60}{17} L^{-1}\left[\frac{1}{s-\frac{5}{2}}\right]-\frac{60}{17} L^{-1}\left[\frac{s-2}{(s-2)^2+4}\right]+\frac{72}{17} L^{-1}\left[\frac{1}{(s-2)^2+4}\right] $$


### Resultado final:
$$ f(t)=\frac{60}{17} \cdot e^{\left(\frac{5}{2} t\right)}-\frac{60}{17} e^{2 t} \cdot \cos (2 t)+\frac{36}{17} e^{2 t} {sen}(2 t) $$



# Ejercicios de practica:
## 📚Ejercicio 1: 

$$\ddot{x} + 4x = 5 \quad x(0) = 5, \quad \dot{x}(0) = 0$$  

$$s^2 X(s) - 5s + 4 X(s) = \frac{5}{s}$$  

$$X(s)(s^2 + 4) = \frac{5}{s} + 5s$$  

$$X(s) = \frac{5 + 5s^2}{s(s^2 + 4)}$$  

$$\frac{5 + 5s^2}{s(s^2 + 4)} = \frac{A}{s} + \frac{Bs + C}{s^2 + 4}$$  

$$A(s^2 + 4) + Bs^2 + Cs = 5 + 5s^2$$  

$$A + B = 5 \quad 4A = 5 \quad C = 0$$  

$$A = \frac{5}{4} \quad B = \frac{15}{4}$$  

$$X(s) = \frac{5/4}{s} + \frac{15s/4}{s^2 + 4}$$  
### Resultado final:
$$x(t) = \frac{5}{4} + \frac{15}{4} \cos(2t)$$  

## 📚Ejercicio 2: 

$$F(s) = \frac{5(s+2)}{s^2 (s^2 - 4s + 8)} = \frac{A}{s} + \frac{B}{s^2} + \frac{Cs + D}{s^2 - 4s + 8}$$  

$$5(s+2) = A s (s^2 - 4s + 8) + B (s^2 - 4s + 8) + (Cs + D)(s^2)$$  

$$5s + 10 = A s^3 - 4A s^2 + 8A s + B s^2 - 4B s + 8B + C s^3 + D s^2$$  

$$0 = A + C$$  

$$0 = -4A + B + D$$  

$$5 = 8A - 4B$$  

$$10 = 8B$$  

$$B = \frac{10}{8} = \frac{5}{4}$$  

$$5 = 8A - 5$$  

$$10 = 8A$$  

$$A = \frac{5}{4}$$  

$$0 = \frac{5}{4} + C \quad \Rightarrow \quad C = -\frac{5}{4}$$  

$$0 = -4\left(\frac{5}{4}\right) + \frac{5}{4} + D$$  

$$0 = -5 + \frac{5}{4} + D$$  

$$D = \frac{15}{4}$$  

$$F(s) = \frac{5}{4} \left(\frac{1}{s}\right) + \frac{5}{4} \left(\frac{1}{s^2}\right) + \frac{5(s - 2)}{4(s - 2)^2 + 4} + \frac{5}{4} \left(\frac{1}{(s - 2)^2 + 4}\right)$$  

$$= \frac{5}{4} \mathcal{L}^{-1}\left[\frac{1}{s}\right] + \frac{5}{4} \mathcal{L}^{-1}\left[\frac{1}{s^2}\right] - \frac{5}{4} \mathcal{L}^{-1}\left[\frac{s - 2}{(s - 2)^2 + 4}\right] + \frac{5}{4} \mathcal{L}^{-1}\left[\frac{1}{(s - 2)^2 + 4}\right]$$  

$$f(t)= \frac{5}{4} + \frac{5t}{4} - \frac{5}{4} e^{2t} \cos(2t) + \frac{5}{4} e^{2t} \frac{sin(2t)}{2}$$  

### Resultado final:
$$f(t)= \frac{5}{4} + \frac{5 t}{4} - \frac{5}{4} e^{2t} \cos(2t) + \frac{5}{8} e^{2t} \sin(2t)$$  
