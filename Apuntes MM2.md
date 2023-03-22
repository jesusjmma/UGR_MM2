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

# Tema 1

> 21-02-2023

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

Si $D=C^k(I)$, podemos definir $B_{\varepsilon}(\tilde y) = \{ y \in C^k(I)\ :\ d_k(y,\tilde y) < \varepsilon \}$. En esta situación, $y_0 \in D$ es un mínimo local si $\exist \varepsilon > 0$ tal que $\mathcal{F}[y_0] \le \mathcal{F}[y]\ \forall y \in B_{\varepsilon}(y_0)$.

---

> 22-02-2023

## Condiciones necesarias de extremo relativo: ecuaciones de Euler-Lagrange

Queremos calcular los extremos relativos de un funcional
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

Supongamos que $y$ es un mínimo local. Entonces $\exist R>0$ tal que $\mathcal{F}[y]\le\mathcal{F}[\tilde y]\ \ \forall \tilde y \in B_R(y)$
 
Dado $\varepsilon \in \mathbb{R}$, podemos introducir una perturbación/variación
$$y_{\varepsilon}:=y+\varepsilon \varphi $$
donde $\varphi \in C^2(I)\cap C_0(I) \\$
con $C_0(I):=\{ y \in C(I)\ :\ y(x_0)=y(x_1)=0 \}$

Entonces tenemos:
$$||y_{\varepsilon}-y||_{C'(I)} = ||\varepsilon\varphi||_{C'(I)} = |\varepsilon| ||\varphi||_{C'(I)}$$

Fijada $\varphi$, $\exist {\varepsilon}_0$ con $0<{\varepsilon}_0<\frac{R}{||\varphi||_{C'(I)}}$ de forma que $y_{\varepsilon}\in B_R(y)\ \ \forall \varepsilon\in (-{\varepsilon}_0, {\varepsilon}_0)$.

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

Supongamos que $\exist\bar{x}\in\mathring{I}$ tal que $f(\bar{x})>0$.

Como $f\in C(I)$, existe un entorno $(x_-,x_+)\subset I$ tal que $f(x)>0$ $\ \forall x\in(x_-,x_+)$.

Tomamos $\varphi$ tal que $\varphi = 0$ fuera de $(x_-,x_+)$ y $\varphi>0$ dentro de $(x_-,x_+)$.

Para esa $\varphi$, tenemos $\int_I f(x)\varphi(x)\ dx = \int_{x_-}^{x_+}f(x)\varphi(x)>0$.

¡Contradicción! $\ \ \square$

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

$$(y'(x))^2 = c_1^2 (1+(y'(x))^2 \Rightarrow (y'(x))^2 = \frac{c_1^2}{1-c_1^2} \in \mathbb{R}\ \ \ (\textup{Necesariamente}\ c_1 \neq \plusmn 1)$$

Existe cierto $c_2 \in \mathbb{R}$ tal que $y'(x)=c_2\ \ \forall x \in I$. Entonces $y(x)=c_2x+c_3$, para ciertos $c_2,c_3 \in \mathbb{R}$.

Usando las condiciones de contorno obtenemos que $c_2$ y $c_3$ son fijos y únicos.

Tenemos un candidato a extremo relativo y no tenemos las herramientas necesarias para saber si es mínimo, máximo o punto de silla. Aunque por intuición y geométricamente vemos que es un mínimo global.

## Variante 1: Condición necesaria de extremo relativo (1 extremo libre)

Supongamos ahora que $\mathcal{D} = \{ y\in C^1{I} : y(x_0)=y_0 \}$ (falta 1 condición de contorno).

Supuesto que $F\in C^2(I\times\mathcal{D})$, todo extremo local $y\in\mathcal{D}\cap C^2(I)$ del funcional $\mathcal{F}[y] = \int_{x_0}^{x_1} F(x,y(x),y'(x)) dx$ ha de satisfacer la ecuación de Euler-Lagrange y, además, la condición
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

> 27-02-2023

Al funcional $\mathcal{F}[y]=\int_{x_0}^{x_1}F(x,y(x),y'(x))\ dx$ podríamos hacerlo depender de otras cosas como $y''(x)$ y, siguiendo los mismos pasos de las demostraciones de la clase anterior, no sería un problema.

Podemos poner también $y:[x_0,x_1]\rightarrow\mathbb{R}^N$ como, por ejemplo, $N=2$ con $y(x)=(y_1(x),y_2(x))$ y sería todo similar:
$$F(x,y,y')=F(x,(y_1(x),y_2(x)),(y'_1(x),y'_2(x)))$$

$y_\varepsilon(x)=y(x)+\varepsilon\varphi(x)=(y_1(x)+\varepsilon\varphi_1(x),y_2(x)+\varepsilon\varphi_2(x))$, con $\varphi(x)=(\varphi_1(x),\varphi_2(x))$.

$\frac{d}{d\varepsilon}\int_{x_0}^{x_1}F(x,y_\varepsilon,y'_\varepsilon)\ dx = \int_{x_0}^{x_1}F_{y_1}(x,y_\varepsilon,y'_\varepsilon)\varphi_1(x) + F_{y_2}(x,y_\varepsilon,y'_\varepsilon)\varphi_2(x) + F_{p_1}(x,y_\varepsilon,y'_\varepsilon)\varphi'_1(x) + F_{p_2}(x,y_\varepsilon,y'_\varepsilon)\varphi'_2(x) + ...$

Para el caso general con imagen en $\mathbb{R}^N$ la ecuación de Euler-Lagrange son $N$ ecuaciones diferenciales ordinarias.

## Condiciones suficientes para extremo: Convexidad

Dado $X$ un espacio vectorial, $\mathcal{U}\subset X$ es convexo si $\forall u,v \in \mathcal{U}:$
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

> 1-03-2023



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
$$=\int_{0}^{x} \sqrt{\frac{z}{c_1-z}}\ dz = \int_0^{2 arcsen(\sqrt{\frac{y'(x)}{c_1}})}c_1 sen^2(\frac{\alpha}{2})\ d\alpha = \left[ \frac{c_1}{2} \alpha - \frac{c_1}{2} sen(\alpha) \right] $$

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









> 7-03-2023

> 8-03-2023

> 9-03-2023

> 13-03-2023

> 14-03-2023

> 15-03-2023

> 16-03-2023

> 20-03-2023

> 21-03-2023

> 22-03-2023

> 23-03-2023