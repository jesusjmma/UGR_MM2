> Apuntes tomados en colaboración con Andrés Quintana

# Metodología Docente

Modelo de evaluación:
1. Parcial 1 (3 puntos) -> Sobre el 15 de mayo;
2. Parcial 2 (1'5 puntos) -> Último/Penúltimo día de clase;
3. Ordinaria (hasta 7 puntos);
4. Participación/Ejercicios (0'5 puntos).

En la web de José Luis López (profesor de mañanas) hay exámenes corregidos y material complementario.

En la web de Cañizo también hay material.

No van a dar relaciones de ejercicios. Hay material de sobra en las webs antes mencionadas y con los ejemplos de clase.

Si queremos tutorías que se lo avisemos con algo de tiempo para que se organice, pero en la hora de tutorías vamos a tener preferencia.

---

> 21-02-2023

# Tema 1

**Principio de mínima acción en mecánica**: Las trayectorias de una partícula con masa sujeta a la acción de un potencial son los puntos críticos del funcional acción asociado.

Para explicar esto, necesitamos la siguiente información:

- **Trayectoria**: una curva parametrizada $x(t)$, $x:[t_0, t_1]\rightarrow \mathbb{R}^n$
- **Energía cinética**: $E_{kin}:\mathbb{R}^n\rightarrow \mathbb{R}^+_0$, $E_{kin}(x(t))=\frac{m}{2}(x'(t))^2$
- **Energía potencial**: $E_{pot}(x(t))$ solo depende de la posición de la partícula. $E_{pot}:\mathbb{R}^n\rightarrow \mathbb{R}$
- **Lagrangiano**: $L(x,p) = E_{kin}(p) - E_{pot}(x)$
- **Funcional acción**: $A(x(t))=\int_{t_0}^{t_1} L(x(t), x'(t)) dt = \int_{t_0}^{t_1} \frac{m}{2}(x'(t))^2 - E_{pot}(x(t))dt$

Planteamos problemas de optimización del siguiente tipo:

$$\min_{y \in D} \mathcal{F}[y] = \int_{x_0}^{x_1} F(x,\ y(x),\ y'(x))\ dx$$

- $\mathcal{F}$ está definido sobre un espacio de funciones $X$ adecuado
- $y: [x_0, x_1]\rightarrow \mathbb{R}^n$
- $F: [x_0, x_1] \times \mathbb{R}^n \times \mathbb{R}^n \longrightarrow \mathbb{R}$ con suficiente regularidad
- $D \subset X$ subconjunto que incorpora restricciones adicionales

Diremos que $y_0 \in D$ es un **mínimo global** si $\mathcal{F}[y_0] \le \mathcal{F}[y]\ \ \forall y \in D$.

El valor del mínimo es el número $\mathcal{F}[y] \in \mathbb{R}$. En esta circunstancia, $y_0 \in argmin\ \mathcal{F}$.

Diremos que $y_0 \in D$ es **mínimo local** si existe algún entorno $\mathcal{U}_{y_0}$ de $y_0$ tal que $\mathcal{F}[y_0] \le \mathcal{F}[y]\ \ \forall y \in \mathcal{U}_{y_0}$.

Si $D=C^k(I)$, podemos definir $B_{\varepsilon}(\tilde y) = \{ y \in C^k(I)\ :\ d_k(y,\tilde y) < \varepsilon \}$. En esta situación, $y_0 \in D$ es un mínimo local si $\exists \varepsilon > 0$ tal que $\mathcal{F}[y_0] \le \mathcal{F}[y]\ \forall y \in B_{\varepsilon}(y_0)$.

---

> 22-02-2023

## Condiciones necesarias de extremo relativo: ecuaciones de Euler-Lagrange

Queremos calcular los extremos relativos de un funcional:

$$\mathcal{F}[y] = \int_{x_0}^{x_1} F(x,\ y(x),\ y'(x))\ dx$$

para $y \in \mathcal{D} = \{ C^1[I]\ :\ y(x_0)=y_0,\ y(x_1)=y_1 \}$, donde $I=[x_0,\ x_1]$, $F:[x_0, x_1]\times D$, donde $D \subset \mathbb{R}\times\mathbb{R}$, y $y:[x_0,x_1]\rightarrow \mathbb{R}$.

Nota: $y(x_0)=y_0$ y $y(x_1)=y_1$ son condiciones de contorno de tipo Dirichlet.

Vamos a introducir notación:
- $F := F(x,y,p)$
- $F_y := \frac{\partial F}{\partial y}$, $F_p := \frac{\partial F}{\partial p}$, $F_{yp} := \frac{\partial^2 F}{\partial y \partial p}$, ...

## Teorema: Condición necesaria de extremo relativo (ecuación de Euler-Lagrange)

Supongamos que $F \in C^2([x_0,x_1]\times D)$.

Cualquier extremo relativo $y \in \mathcal{D} \cap C^2(I)$ satisface la ecuacióno de Euler-Lagrange:

$$F_y(x, y(x), y'(x)) - \frac{d}{d x}[F_p(x,y(x),y'(x))]=0$$

### Demostración

Supongamos que $y$ es un mínimo local. Entonces $\exists R>0$ tal que $\mathcal{F}[y]\le\mathcal{F}[\tilde y]\ \ \forall \tilde y \in B_R(y)$
 
Dado $\varepsilon \in \mathbb{R}$, podemos introducir una perturbación/variación:

$$y_{\varepsilon}:=y+\varepsilon \varphi$$

donde $\varphi \in C^2(I)\cap C_0(I) \\$
con $C_0(I):=\{ y \in C(I)\ :\ y(x_0)=y(x_1)=0 \}$

Entonces tenemos:

$$||y_{\varepsilon}-y||_{C'(I)} = ||\varepsilon\varphi||_{C'(I)} = |\varepsilon| ||\varphi||_{C'(I)}$$

Fijada $\varphi$, $\exists {\varepsilon}_0$ con $0<{\varepsilon}_0<\frac{R}{||\varphi||_{C'(I)}}$ de forma que $y_{\varepsilon}\in B_R(y)\ \ \forall \varepsilon\in (-{\varepsilon}_0, {\varepsilon}_0)$.

La aplicación $\varepsilon \mapsto \int_{x_0}^{x_1} F(x,\ y_{\varepsilon},\ y'_{\varepsilon})\ dx$ tiene un mínimo local en $\varepsilon = 0$.

Por tanto, la derivada de un mínimo local es 0:

$$\frac{d}{d\varepsilon} \int_{x_0}^{x_1} F(x,\ y_{\varepsilon},\ y'_{\varepsilon})\ dx \vert_{\varepsilon=0} = 0$$

Por otro lado:

$$\int_{x_0}^{x_1} F_y(x,\ y_{\varepsilon},\ y'_{\varepsilon})\cdot\frac{dy_{\varepsilon}}{d\varepsilon}\ +\ F_p(x,\ y_{\varepsilon},\ y'_{\varepsilon})\cdot\frac{dy'_{\varepsilon}}{d\varepsilon}\ dx \vert_{\varepsilon=0} = $$

$$= \int_{x_0}^{x_1} F_y(x,\ y_{\varepsilon},\ y'_{\varepsilon})\cdot\varphi\ +\ F_p(x,\ y_{\varepsilon},\ y'_{\varepsilon})\cdot\varphi'\ dx \vert_{\varepsilon=0} = $$

$$= \int_{x_0}^{x_1} F_y(x,\ y,\ y')\cdot\varphi\ +\ F_p(x,\ y,\ y')\cdot\varphi'\ dx = $$

$$= \int_{x_0}^{x_1} F_y(x,\ y,\ y')\cdot\varphi(x)\ -\ \frac{d}{dx}[F_p(x,\ y,\ y')]\cdot\varphi(x)\ dx\ +\ F_p(x,y_1,y'(x_1))\cdot\varphi(x_1)\ -\ F_p(x,y_0,y'(x_0))\cdot\varphi(x_0)$$

Los dos últimos términos son $0$, ya que $\varphi$ vale $0$ en $x_0$ y en $x_1$.

Deducimos que $\forall\varphi\in C^2(I)\cup C_0(I)$ se cumple que:

$$\int_{x_0}^{x_1} (F_y(x,y(x),y'(x)) - \frac{d}{dx}[F_p(x,y(x),y'(x))])\cdot\varphi(x)\ dx = 0$$

Y por el Lema Fundamental del Cálculo de Variaciones podemos asegurar que lo que hemos puesto entre paréntesis es $0$, es decir, se cumple *Euler-Lagrange* $\forall x\in I$. $\ \ \square$

## Lema Fundamental del Cálculo de Variaciones

Sea $f(x)\in C(I)$. Si $\int_I f(x)\varphi(x)\ dx = 0$ $\ \forall\varphi\in C_0(I)$,

entonces $f(x)=0$ $\forall x\in I$.

### Demostración (por contradicción)

Supongamos que $\exists \bar{x}\in\mathring{I}$ tal que $f(\bar{x})>0$.

Como $f\in C(I)$, existe un entorno $(x_-,x_+)\subset I$ tal que $f(x)>0$ $\ \forall x\in(x_-,x_+)$.

Tomamos $\varphi$ tal que $\varphi = 0$ fuera de $(x_-,x_+)$ y $\varphi>0$ dentro de $(x_-,x_+)$.

Para esa $\varphi$, tenemos $\int_I f(x)\varphi(x)\ dx = \int_{x_-}^{x_+}f(x)\varphi(x)>0$.

¡Contradicción! $\ \ \square$

---

> 23-02-2023

## Geodésicas en el plano

Dados dos puntos $A,B \in \mathbb{R}$, determinemos la curva más corta que los une.

Digamos que $A=(x_0, y_0)$, $B=(x_1,y_1)$. Supondremos que $x_0 < x_1$.

Consideremos que las curvas $\gamma$ que unen los dos puntos se pueden describir con una gráfica:

$$\gamma = \{ (x,y(x)) : x\in [x_0,x_1],\ y=[x_0,x_1]\rightarrow\mathbb{R},\ y(x_0)=y_0,\ y(x_1)=y_1 \}$$

Supondremos además que $y\in C^2(I)$.

Tomemos $\vec{v}$ el vector tangente, que viene dado por $\vec{v}=(1,y'(x))$.

Calculamos la longitud de la curva:

$$longitud = \int_{x_0}^{x_1} \sqrt{1+(y'(x))^2} dx$$

**Nota**: Para calcular la longitud se integra el módulo del vector tangente a lo largo de la curva.

Consideramos el funcional longitud $L[y] = \int_{x_0}^{x_1} \sqrt{1+(y'(x))^2} dx$. En este caso $F(x,y,p) = \sqrt{1+p^2}$.

En este caso la ecuación de Euler-Lagrange es:

$$\frac{d}{dx}\left[\frac{y'(x)}{\sqrt{1+(y'(x))^2}}\right] = 0,\ \ \ \forall x \in I$$

Existe cierto $c_1\in\mathbb{R}$ tal que $r'(x) = c_1 \sqrt{1+(y'(x))^2}$. Despejamos $y'(x)$._

$$(y'(x))^2 = c_1^2 (1+(y'(x))^2 \Rightarrow (y'(x))^2 = \frac{c_1^2}{1-c_1^2} \in \mathbb{R}\ \ \ (\textup{Necesariamente}\ c_1 \neq \pm 1)$$

Existe cierto $c_2 \in \mathbb{R}$ tal que $y'(x)=c_2\ \ \forall x \in I$. Entonces $y(x)=c_2x+c_3$, para ciertos $c_2,c_3 \in \mathbb{R}$.

Usando las condiciones de contorno obtenemos que $c_2$ y $c_3$ son fijos y únicos.

Tenemos un candidato a extremo relativo y no tenemos las herramientas necesarias para saber si es mínimo, máximo o punto de silla. Aunque por intuición y geométricamente vemos que es un mínimo global.

## Variante 1: Condición necesaria de extremo relativo (1 extremo libre)

Supongamos ahora que $\mathcal{D} = \{ y\in C^1{I} : y(x_0)=y_0 \}$ (falta 1 condición de contorno).

Supuesto que $F\in C^2(I\times\mathcal{D})$, todo extremo local $y\in\mathcal{D}\cap C^2(I)$ del funcional $\mathcal{F}[y] = \int_{x_0}^{x_1} F(x,y(x),y'(x)) dx$ ha de satisfacer la ecuación de Euler-Lagrange y, además, la condición:

$$F_p (x_1,y(x_1),y'(x_1)) = 0$$

### Demostración
[pendiente]

[//]: # (Añadir la demostración que me pasó Andrés)

## Variante 2: Condición necesaria de extremo relativo (2 extremos libres)

Supongamos ahora que $\mathcal{D} = \{ y\in C^1{I} \}$ (faltan las 2 condiciones de contorno).

Supuesto que $F\in C^2(I\times\mathcal{D})$, todo extremo local $y\in\mathcal{D}\cap C^2(I)$ del funcional $\mathcal{F}[y] = \int_{x_0}^{x_1} F(x,y(x),y'(x)) dx$ ha de satisfacer la ecuación de Euler-Lagrange y, además, las condiciones:

$$F_p (x_0,y(x_0),y'(x_0)) = 0$$

$$F_p (x_1,y(x_1),y'(x_1)) = 0$$

### Demostración
[pendiente]

[//]: # (Añadir la demostración que me pasó Andrés)

## Geodésicas en el plano (continuación)

Volviendo al ejemplo de las geodésicas pero aplicando la variante 1: $y(x_0)=y_0$ y a $y(x_1)$ no le exigimos nada. Tenemos:

$$\textup{\textbf{Ecuación de Euler-Lagrange}: } \frac{d}{dx}\left[\frac{y'(x)}{\sqrt{1+(y'(x))^2}}\right] = 0$$

$$\textup{\textbf{Extremo libre}: }\left[F_p (x_1,y(x_1),y'(x_1)) = 0\right] \equiv \left[ \frac{y'(x_1)}{1+(y'(x_1))^2} = 0 \right]$$

Por la segunda ecuación $y'(x_1)=0$, por lo que $y$ es una recta con pendiente 0 y, por tanto, $y(x)=k \in \mathbb{R}$ (constante).

Ahora vemos de nuevo el problema pero esta vez sin condiciones en los extremos (variante 2). Se satisfacen:

- $\frac{d}{dx}\left[\frac{y'(x)}{\sqrt{1+(y'(x))^2}}\right] = 0 \Rightarrow y$ es una recta.

- $\frac{y'(x_0)}{\sqrt{1+(y'(x_0))^2}}=0 \Rightarrow y'(x_0)=0$

- $\frac{y'(x_1)}{\sqrt{1+(y'(x_1))^2}}=0 \Rightarrow y'(x_1)=0$

Por lo tanto, cualquier recta horizontal es un extremo relativo.

---

> 27-02-2023

Al funcional $\mathcal{F}[y]=\int_{x_0}^{x_1}F(x,y(x),y'(x))\ dx$ podríamos hacerlo depender de otras cosas como $y''(x)$ y, siguiendo los mismos pasos de las demostraciones de la clase anterior, no sería un problema.

Podemos poner también $y:[x_0,x_1]\rightarrow\mathbb{R}^N$ como, por ejemplo, $N=2$ con $y(x)=(y_1(x),y_2(x))$ y sería todo similar:

$$F(x,y,y')=F(x,(y_1(x),y_2(x)),(y'_1(x),y'_2(x)))$$

 $y_\varepsilon(x)=y(x)+\varepsilon\varphi(x)=(y_1(x)+\varepsilon\varphi_1(x),y_2(x)+\varepsilon\varphi_2(x))$, con $\varphi(x)=(\varphi_1(x),\varphi_2(x))$.

 $ \frac{d}{d\varepsilon}\int_{x_0}^{x_1}F(x,y_\varepsilon,y'_\varepsilon)\ dx = \int_{x_0}^{x_1}F_{y_1}(x,y_\varepsilon,y'_\varepsilon)\varphi_1(x) + F_{y_2}(x,y_\varepsilon,y'_\varepsilon)\varphi_2(x) + F_{p_1}(x,y_\varepsilon,y'_\varepsilon)\varphi'_1(x) + F_{p_2}(x,y_\varepsilon,y'_\varepsilon)\varphi'_2(x) + ... $ 

Para el caso general con imagen en $\mathbb{R}^N$ la ecuación de Euler-Lagrange son $N$ ecuaciones diferenciales ordinarias.

## Condiciones suficientes para extremo: Convexidad

Dado $X$ un espacio vectorial, $\mathcal{U}\subset X$ es convexo si $\forall u,v \in \mathcal{U}$:

$$\theta u + (1-\theta)v\in\mathcal{U}\ \ \ \ \ \ \forall\theta\in[0,1]$$

Dado $\mathcal{F}:D\rightarrow\mathbb{R}$ con $D$ convexi, diremos que el funcional es convexo si $\forall u,v\in D$, se cumple que:

$$\mathcal{F}[\theta u + (1-\theta)v] \le \theta \mathcal{F}[u] + (1-\theta)\mathcal{F}[v]\ \ \ \ \ \ \forall\theta\in[0,1]$$

Notas:
- $\mathcal{F}$ es estrictamente convexi si lo anterior se cumple con $<$ para $u\ne v$ y $\theta \ne 0,1$.
- $\mathcal{F}$ es cóncavo si $-\mathcal{F}$ es convexo.
- Todo funcional lineal es convexo (y cóncavo).
- Ejemplos de funcionales convexos: $e^x$, $x^2$, $x log(x)$, $|x|$, ...
- Dada $A$ una matriz definida positiva, la forma cuadrática asociada $q_A(x) = x^TAx$ es estrictamente convexa.
- Dado $\mathcal{F}[y] = \int_{x_0}^{x_1}F(x,y,y')\ dx$, si para cada $x\in[x_0,x_1]$ la función $(y,p)\mapsto F(x,y,p)$ es convexa, entonces $\mathcal{F}$ es convexo.
- El recíproco de lo anterior no es cierto. A continuación se muestra un ejemplo:

$\mathcal{F}[y] = \int_{x_0}^{x_1} (y(x))^2(1-y'(x))\ dx$ definido sobre:

$D=C_0^1([x_0,x_1])$

$F(y,p) = y^2(1-p)$ no es convexa, pero podemos hacer un truquito:

$\mathcal{F}[y] = \int_{x_0}^{x_1} (y(x))^2\ dx - \int_{x_0}^{x_1} (y(x))^2y'(x)\ dx = \int_{x_0}^{x_1} (y(x))^2\ dx - \frac{1}{3} \int_{x_0}^{x_1} \frac{d}{dx} (y(x))^3\ dx = \int_{x_0}^{x_1} (y(x))^2\ dx - \frac{1}{3}((y(x_1))^3-(y(x_0))^3) = \int_{x_0}^{x_1} (y(x))^2\ dx$

---

> 1-03-2023



---

> 6-03-2023

# Resolución del problema de la braquistócrona

$\mathcal{F}[y] = \int_0^{x_1} \sqrt{\frac{1+(y'(x))^2}{-2gy(x)}}\ dx\ $ definido en $\mathcal{D}=\{ y\in C^1([0,x_1]) : y(0)=0, y(x_1)=y_1 \}$

Podemos suponer que $2g=1 \Rightarrow F(x,y,p)=\sqrt{\frac{1+p^2}{-y}}$

La ecuación se Euler-Lagrange sería:

$$\frac{1}{2y}\sqrt{\frac{1+p^2}{-y}} + \frac{d}{dp}\left( \frac{p}{y \sqrt{\frac{1+p^2}{-y}}}  \right) = 0$$

Equivalentemente, $2y''y+(y')^2+1=0$.

Multiplicando por $y'$, resulta: $(y(y')^2+y)'$.

Por tanto, $\sqrt{\frac{y}{c_1 - y}}\cdot y' = -1$, para $c_1 < 0$.

Integrando entre $0$ y $x$:

$$\int_0^x -1\ dx = \int_0^x \sqrt{\frac{y(x)}{c_1 - y(x)}}\cdot y(x)'\ dx = \int_{y(0)}^{y(x)} \sqrt{\frac{z}{c_1-z}}\ dz =$$

$$=\int_{0}^{x} \sqrt{\frac{z}{c_1-z}}\ dz = \int_0^{2 arcsen(\sqrt{\frac{y'(x)}{c_1}})}c_1 sen^2(\frac{\alpha}{2})\ d\alpha = \left[ \frac{c_1}{2} \alpha - \frac{c_1}{2} sen(\alpha) \right]$$

Para esto hemos utilizado:

1. $z = sen^2(\frac{\alpha}{2})$
2. $sen^2(\frac{\alpha}{2}) = \frac{1}{2}(1-cos(\alpha))$

Definimos $\theta := 2 arcsen(\sqrt{\frac{y(x)}{c_1}}) \in [0,\theta_1]\subset[0,\pi]$. Entonces:

$$x(\theta) \equiv x = -\frac{c_1}{2}\theta + \frac{c_1}{2} sen(\theta)$$

Hemos descrito la definición como una curva parametrizada.

Despejando de la definición de $\theta$:

$$y(x) = c_1 sen^2\left(\frac{\theta}{2}\right)$$

Con esto que hemos obtenido tenemos: $x(0)= 0$ y $y(0)= 0$. Pasamos por $A$.

Para pasar por $B$ necesitamos:

- $x(\theta_1) = x_1 = \frac{c_1}{2}\theta_1 + \frac{c_1}{2} sen(\theta_1)$
- $y(\theta_1) = y_1 = c_1 sen^2\left(\frac{\theta_1}{2}\right)$

De esto determinamos tanto $c1$ como $\theta_1$.

# Caso particular de la ecución de Euler-Lagrange: $F$ no depende de $x$

$$\frac{d}{dx}F_p = \frac{d}{dx}F_p(y(x), y'(x)) = F_{py}y' + F_{pp}y''$$

Multiplicando la ecución de Euler-Lagrange por $y'$, resulta:

$$\frac{d}{dx}\left[  F(y,y') - y' F_p(y, y') \right] = 0$$

Por tanto, vemos que $F(y(x),y'(x))-y'(x)F_p(y(x),y'(x)) = C \in \mathbb{R}$

Ejemplo:

$F(y,p) = \sqrt{\frac{1+p^2}{-y}}$

$\sqrt{\frac{1+(y')^2}{-y}} = \frac{(y')^2}{\sqrt{-y}\sqrt{1+(y')^2}} = C \in \mathbb{R}$

Se puede obtener $y(x)=\frac{k_1}{1+(y'(x))^2}$ para $k_1<0$.

$$\tilde{y}(t) = y(x(t)) = \frac{k_1}{1+(\frac{d}{dx}y(x(t)))^2} = \frac{k_1}{1+\left(\frac{\frac{d}{dt}\tilde{y}(t)}{\frac{d}{dt}x(t)}\right)^2}$$

$F_y - \frac{d}{dx} F_p = 0$

$F_y - F_{py} y' - F_{pp} y'' = 0$

$x \mapsto (x,y(x))$

$t \mapsto (x(t), \tilde{y}(t))$

$\tilde{y}(t) = y(x(t)) \Longrightarrow \frac{d}{dt}\tilde{y}(t) = \frac{d}{dx} y(x(t)) \cdot \frac{d}{dt}x(t)$

Escogemos:

$$\frac{\frac{d}{dt}\tilde{y}(t)}{\frac{d}{dt}x(t)} = - cotan(t)$$

Resulta $\tilde{y}(t) = k_1 sen^2(t) = \frac{k_1}{2}(1-cos(2t))$

$$\frac{2\cdot k_1\cdot sen(t)\cdot cos(t)}{\frac{d}{dt}x(t)} = - cotan(t)$$

$$rx(t) = x(0) + \int_0^t \frac{2\cdot k_1\cdot sen(s)\cdot cos(s)}{- cotan(s)}\ ds = \int_0^t -2\cdot k_1\cdot sen^2(s)\ ds =$$

$$= -k_1 \cdot t + \frac{k_1}{2}sen(2t)$$

---

> 7-03-2023


---

> 8-03-2023


---

> 9-03-2023

# Problema de los N cuerpos en gravitación

Consideramos $N$ partículas con masa $m_i>0$ y trayectorias $x_i : [t_0, t_1]\rightarrow\mathbb{R}^3$ con $i=1,...,N$.

Consideramos el funcional acción

$$\mathcal{A} = \int_{t_0}^{t_1} E_{kin} - E_{pot}\ dt$$

donde:
- $E_{kin} = \sum \frac{m_i}{2} |x_i'(t)|^2$
- $E_{pot} = -G \sum_{1\le i \lt j \le N} \frac{m_i \cdot m_j}{|x_i(t) - x_j(t)|}$

Las escuaciones de Euler-Lagrange para $i=1,...,N$ serían:

$$-G \sum_{\substack{j>1 \\ j\ne i}} \frac{m_i \cdot m_j}{|x_i(t) - x_j(t)|^3} (x_i(t) - x_j(t)) -  m_i x_i''(t) = 0$$

En general es muy complicado decir algo de lo que pasa con estas ecuaciones.

## Caso de dos cuerpos ($N=2$)

$E_{tot} = E_{kin}+E_{pot} = \frac{m_1}{2} |x_1'(t)|^2 + \frac{m_2}{2} |x_2'(t)|^2 -G \frac{m_1 \cdot m_2}{|x_1(t) - x_2(t)|}$

Sabemos que la energía total se conserva, por lo que $\frac{d}{dt}E_{tot} = 0$

Con la energía total hay 3 casos posibles:
1. $E_{tot} > 0 \longrightarrow$ Caso hiperbólico
2. $E_{tot} = 0 \longrightarrow$ Caso parabólico
3. $E_{tot} < 0 \longrightarrow$ Caso elíptico

En los casos 1 y 2 el sistema se desacopla (las partículas cada vez están más separadas). En el caso 3 el sistema se queda ligado y las órbitas son elípticas.

Las ecuaciones de Euler-Lagrange son:

$m_1 x_1''(t) = -G \frac{m_1 \cdot m_2}{|x_1(t) - x_2(t)|^3} (x_1(t) - x_2(t))$


$m_1 x_1''(t) = -G \frac{m_1 \cdot m_2}{|x_1(t) - x_2(t)|^3} (x_2(t) - x_1(t))$

Coordenadas de Jacobi:

- Centro de masas: $Y = \frac{m_1x_1+m_2x_2}{m_1+m_2} \Rightarrow Y''=0$
- $y = x_2-x_1 \Rightarrow y'' = -G \frac{m_1m_2}{|y|^3}y$

Como $Y''=0$ el centro de masas se desplaza linealmente en el tiempo: $Y(t) = \vec{v_1}t+\vec{v_2}$

$\frac{d}{dt}(y \land y) = \frac{d}{dt} (y \times y') = 0 \Longrightarrow$ el momento angular se conserva, las trayectorias se mueven en un plano.

# Lema Fundamental del Cálculo de Variaciones

Sea $\Omega \in \mathbb{R}$ un dominio. Sea $f\in C(\Omega)$.

Si $\int_\Omega f \varphi\ dx = 0$ para cualquier $\varphi\in C_0(\Omega)$, entonces $f=0$ en $\Omega$

Función de prueba (*bump function*):

$$\varphi(x)= \left \{ \begin{array}{ccc}
    \frac{1}{|x|^2-1} &   si  & |x|<1 \\
    0 &  si & |x| \ge 1
    \end{array}
\right \}$$

En $B(0,1)$ es de clase $C^\infty$.

Pongamos $F = F(x,y,u,P_x,P_y)$ y consideremos $u=u(x,y)$ con $P_x = \frac{\partial}{\partial x} u(x,y)$ y con $P_y = \frac{\partial}{\partial y} u(x,y)$

$$\mathcal{F}[u] = \int_\Omega F(x,y,u(x,y), \frac{\partial}{\partial x} u(x,y),\frac{\partial}{\partial y} u(x,y))\ dx\ dy$$

Definido sobre $D = \{ u \in C^1(\Omega) : u\vert_{\partial\Omega}=\varphi(x,y) \}$ con $\varphi : \Omega\rightarrow\Omega$ dada.

### Teorema

Supongamos que $F\in C^2(\Omega\times\mathbb{R}^3)$. Entonces todo extremo relativo $u\in C^2(\Omega) \cap D$ de $\mathcal{F}$ satisface:

$$F_u(-) - \frac{d}{dx} [ F_{P_x}(-)] - \frac{d}{dy} [ F_{P_y}(-)]$$

---

> 13-03-2023

Demostración del Teorema:

$u_\varepsilon = u_\varepsilon(x,y) = u(x,y) + \varepsilon \varphi (x,y)$, con $\varphi\in C_0^1(\Omega)\Rightarrow u_\varepsilon \in D$

Fijado $\varphi$, existe un rango $(-\varepsilon_0, \varepsilon_0)$ tal que $\varepsilon\mapsto\mathcal{F}[u_\varepsilon]$ tiene un extremo local para $\varepsilon=0$.

Por tanto, $\frac{d}{d\varepsilon}(\mathcal{F}[u_\varepsilon])\vert_{\varepsilon=0} = 0$.

$$\frac{d}{d\varepsilon}(\mathcal{F}[u_\varepsilon])\vert_{\varepsilon=0} = (\int_\Omega \frac{d}{d\varepsilon}(F(x,y,u_\varepsilon,\frac{\partial}{\partial x} u_\varepsilon,\frac{\partial}{\partial y} u_\varepsilon))\ dx\ dy)\vert_{\varepsilon=0} = $$

$$= (\int_\Omega (F_u(-\space_\varepsilon)\varphi+F_{P_x}(-\space_\varepsilon)\frac{\partial\varphi}{\partial x}+F_{P_y}(-\space_\varepsilon)\frac{\partial\varphi}{\partial y})\ dx\ dy)\vert_{\varepsilon=0 }$$

$$= \int_\Omega (F_u(-)\varphi+F_{P_x}(-)\frac{\partial\varphi}{\partial x}+F_{P_y}(-)\frac{\partial\varphi}{\partial y})\ dx\ dy$$

Con esto queremos llegar a que si $\int_\Omega f\varphi\ dx = 0,\ \forall \varphi\in C_0^1(\Omega) \Rightarrow f=0$

Para obtener una integral de la forma deseada para aplicar esto integramos por partes.

$$0 = \int_\Omega (F_u - \frac{d}{dx}F_{Px} - \frac{d}{dy}F_{Py})\varphi(x,y)\ dx\ dy$$

De ahí tenemos que:

$$F_u(-) - \frac{d}{dx}F_{Px}(-) - \frac{d}{dy}F_{Py}(-) = 0,\ \forall(x,y)\in\Omega$$

$\square$

Ejemplo 1: Superficie descrita como grafo.

$(x,y)\mapsto(x,y,u(x,y))$, con $(x,y)\in\Omega\subset\mathbb{R}^2$ un dominio.

Borde fijado: $u\vert_{\partial\Omega} = \varphi(x,y)\in\mathbb{R}$ dada.

Área asociada para $D=\{ u\in C^1(\Omega) :  u\vert_{\partial\Omega} = \varphi \}$

$$\mathcal{A}[u]=\int_\Omega \sqrt{1+u_x^2+u_y^2}\ dx\ dy$$

En este caso $F(x,y,u,P_x,P_y)=\sqrt{1+P_x^2+P_y^2}$. Y calculamos la ecuación de Euler-Lagrange que viene dada por:

$$F_u - \frac{\partial}{\partial x}(F_{P_x}) - \frac{\partial}{\partial y}(F_{P_y}) = 0$$

Y cada una de esas tres partes se corresponde con:
- $F_u=0$
- $F_{P_x} = \frac{P_x}{\sqrt{1+P_x^2+P_y^2}}$
- $F_{P_y} = \frac{P_y}{\sqrt{1+P_x^2+P_y^2}}$

Entonces la ecuación de Euler-Lagrange queda:

$$\frac{\partial}{\partial x}\left(\frac{\frac{\partial}{\partial x}u}{\sqrt{1+(\frac{\partial}{\partial x}u)^2+(\frac{\partial}{\partial y}u)^2}}\right) +\frac{\partial}{\partial y}\left(\frac{\frac{\partial}{\partial y}u}{\sqrt{1+(\frac{\partial}{\partial x}u)^2+(\frac{\partial}{\partial y}u)^2}}\right) = 0\ \ \ \ \forall (x,y)\in\Omega$$

Esta ecuación también la podemos escribir así:

$$div\left( \frac{\nabla u}{\sqrt{1+|\nabla u|^2}} \right) = 0$$

que es la ecuación de las superficies mínimas (no vamos a resolver esta ecuación).

> ### Divergencia de una función
> $$\begin{array}{rcl}
> F:\mathbb{R}^N & \longrightarrow & \mathbb{R}^N \\
> (x_1, ..., x_n) & \longmapsto & F=(F_1(x_1, ..., x_n),...,F_N (x_1, ..., x_n))
> \end{array}$$
> $div F = \frac{\partial}{\partial x_1}F_1 + ... + \frac{\partial}{\partial x_N}F_N$

La ecuación de Euler-Lagrange también puede escribirse como $F_N - div_x(F_p) = 0$

Si $|\nabla u| \simeq 0 \Rightarrow div\left( \frac{\nabla u}{\sqrt{1+|\nabla u|^2}} \right) \simeq div(\nabla u) = \Delta u$ (Laplaciano de $u$)

$\Delta u = 0$ (Ecuación de Laplace)

Ejemplo 2:

Sea $\Omega\in\mathbb{R}$ dominio acotado que representa la membrana en reposo.

Sea $u_[o,\tau]\times\Omega\rightarrow\mathbb{R}$ desplazamiento vertical bajo perturbaciones.

Consideramos la densidad de masa de la membrana $\rho(x)>0,\ x\in\Omega$

Sea $F:\Omega\rightarrow\mathbb{R}$ una fuerza vertical aplicada

Consideramos la tensión de la membrana $\tau(x)$, $x\in\Omega$, que tiende a restituirla al equilibrio. Trabajo proporcional a la variación de área.

El medio opone una resistencia al movimiento proporcional a la magnitud del desplazamiento (constante).

Trabajamos en $D=\{ u\in C^1([0,\tau]\times\Omega) : u(t,\cdot)\vert_{\partial\Omega} \}$

$$E_{kin} = \int_\Omega \frac{\rho(x,y)}{2}\cdot\left(\frac{\partial u}{\partial t}\right)^2\ dx\ dy\ \ \ \ \ \forall (x,y)\in\Omega$$

$$E_{pot} = \int_\Omega dx\ dy \int_O^{u(t,(x,y))} (F(x,y) - a(x,y)s\ ds) + \tau(x,y)(\sqrt{1+|\nabla u|^2}-1)$$

---

> 14-03-2023

$E_{kin} = \int_\Omega \frac{\rho(x)}{2}\cdot\left(\frac{\partial u}{\partial t}\right)^2\ dx\ \ \ \ \ \forall (x,y)\in\Omega$

$E_{pot} = \int_\Omega \left( \int_O^{u(t,x)} (F(x) - a(x)s\ ds) + \tau(x)(\sqrt{1+|\nabla u|^2}) \right)\ dx$

Con $\nabla u = \left( \frac{\partial}{\partial x} u,\frac{\partial}{\partial y}u \right)$

Consideramos el siguiente funcional:

$$\mathcal{A}[u] = \int_O^T E_{kin}-E_{pot}\ dt$$

Vemos cual es el integrando:

$F(t,x,y,u,P_t,P_x,P_y) = \frac{\rho(x,y)}{2}P_t^2 - f(x,y)u + \frac{a(x,y)}{2}u^2-\tau (x,y)(\sqrt{1+P_x^2+P_y^2} - 1)$

$\Rightarrow \mathcal{A}[u] = \int_0^T \int_\Omega F\ dx\ dt$

Calculamos la ecuación de Euler-Lagrange, que viene dada por:

$$F_u - div_x(F_p) = 0$$

$$F_u - \frac{\partial}{\partial t}(F_{P_t}) - \frac{\partial}{\partial x}(F_{P_x}) - \frac{\partial}{\partial y}(F_{P_y}) = 0$$

Entonces la ecuación de Euler-Lagrange de la membrana queda como:

$$-f + au - \frac{\partial}{\partial t}(\rho \frac{\partial}{\partial t} u)+\frac{\partial}{\partial x}(\frac{\tau \frac{\partial}{\partial x}u}{\sqrt{1+|\nabla u|^2}})+\frac{\partial}{\partial y}(\frac{\tau \frac{\partial}{\partial y_0}u}{\sqrt{1+|\nabla u|^2}}) = 0$$

Para esto no podemos calcular las soluciones.

Pongamos que $\rho$, $\tau$ y $a$ son  constantes.

NOTA: VER EL MODELO/PROBLEMA DE LA MEMBRANA ELÁSTICA

# Multiplicadores de Lagrange

Ahora queremos optimizar con algunas ligaduras.

Sean $\Omega\subset\mathbb{R}^d$ abierto y $F:\Omega\rightarrow\mathbb{R}$.

Sean las $m < d$ ligaduras $\Phi_i:\Omega\rightarrow\mathbb{R}$, $i=1,...,m$.

Condición de transversalidad: 






---

> 15-03-2023


---

> 16-03-2023


---

> 20-03-2023


---

> 21-03-2023


---

> 22-03-2023


---

> 23-03-2023


---

> 27-03-2023


---

> 28-03-2023


---

> 29-03-2023


---

> 30-03-2023


---