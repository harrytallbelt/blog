---
date: 2017-08-16
published: true
status: publish
title: Equations of Motion for Inverted Pendulum
type: post
---

TODO: Free body diagram

## The Newtonian Method

Horizontal forces on the cart:

$$ \begin{aligned}
  M \frac{d^2}{dt^2}(x) & = F - T \sin \theta
\\
  M \ddot{x} & = F - T \sin \theta
\end{aligned} $$ (1)

Horizontal forces on the pendulum

$$ \begin{aligned}
  m \frac{d^2}{dt^2}(x + l \sin \theta) &= T \sin \theta
\\
  m \frac{d}{dt}(\dot{x} + l \dot \theta \cos \theta) &= T \sin \theta
\\
  m (\ddot{x} + l \ddot{\theta} \cos \theta - l \dot{\theta}^2 \sin \theta) &= T \sin \theta
\\
  m \ddot{x} + ml \ddot{\theta} \cos \theta - ml \dot{\theta}^2 \sin \theta &= T \sin \theta
\end{aligned} $$ (2)

Vertical forces on the pendulum

$$ \begin{aligned}
  m \frac{d^2}{dt^2}(l \cos \theta)  &= T \cos \theta - mg
\\
  m \frac{d}{dt}(-l \dot \theta \sin \theta)  &= T \cos \theta - mg
\\
  m(-l \ddot{\theta} \sin \theta - l \dot{\theta}^2 \cos \theta) &= T \cos \theta - mg
\\
  -ml \ddot{\theta} \sin \theta - ml \dot{\theta}^2 \cos \theta &= T \cos \theta - mg
\\
  -mg + ml \ddot{\theta} \sin \theta + ml \dot{\theta}^2 \cos \theta &= -T \cos \theta
\end{aligned} $$ (3)

To get our equations of motion, we need to solve for $\ddot{x}$ and $\ddot{\theta}$ in terms of $m, M, F, x, \dot{x}, \theta$, and $\dot{\theta}$.

We have 3 equations and three unknowns: $\ddot{x}, \ddot{\theta}, T$

Let's start by eliminating $T$.

Let $(4) = (2)\cos \theta + (3) \sin \theta$

$$ \begin{aligned}
  \begin{matrix}
    (m \ddot{x} + ml \ddot{\theta} \cos \theta - ml \dot{\theta}^2 \sin \theta )
      \cos \theta \\ + \\
    (-mg + ml \ddot{\theta} \sin \theta + ml \dot{\theta}^2 \cos \theta) \sin \theta
  \end{matrix}
    &=
  \begin{matrix}
    &(T \sin \theta \cos \theta) \\ &+ \\
    &(-T \cos \theta \sin \theta)
  \end{matrix}
\end{aligned} $$

Collecting like terms, we're left with:

$$ \begin{aligned}
  -mg \sin \theta + m \ddot x  \cos \theta +
    ml \ddot{\theta} (\cos^2 \theta + \sin^2 \theta)
     - ml \ddot{\theta} (\sin \theta \cos \theta - \cos \theta \sin \theta)
    &= 0
\\
  -g \sin \theta + \ddot x  \cos \theta +
    l \ddot{\theta}
    &= 0
\end{aligned} $$ (4)

Substituting (2) into (1)

$$ \begin{aligned}
  M \ddot x = F -
    m \ddot{x} + ml \ddot{\theta} \cos \theta - ml \dot{\theta}^2 \sin \theta
\end{aligned} $$ (5)

Solving (4) for $\ddot \theta$, then subsituting into (5):

$$ \begin{aligned}
  M \ddot x &= F -
    m \ddot{x} + ml \frac{-g \sin \theta - \ddot x \cos \theta}{l} \cos \theta - ml \dot{\theta}^2 \sin \theta
\\[1em]
  M \ddot x &= F -
    m \ddot{x} + m(-g \sin \theta - \ddot x \cos \theta) \cos \theta - ml \dot{\theta}^2 \sin \theta
\\[1em]
  M \ddot x &= F -
    m \ddot{x} - mg \sin \theta \cos \theta - m\ddot x \cos^2 \theta - ml \dot{\theta}^2 \sin \theta
\\[1em]
  M \ddot x + m \ddot x + m \ddot x \cos^2 \theta &= F -
    mg \sin \theta \cos \theta - ml \dot{\theta}^2 \sin \theta
\\[1em]
  \ddot x &=
    \frac
      {F - mg \sin \theta \cos \theta - ml \dot{\theta}^2 \sin \theta}
      {M + m + m \cos^2 \theta}
\\[2em]
  \ddot x &=
    \frac
      {F - m \sin \theta (g \cos \theta - l \dot{\theta}^2)}
      {M + m(1 + \cos^2 \theta)}
\end{aligned} $$ (6)

Solving (4) and (5) for $\ddot x$, setting them equal:

$$ \begin{aligned}
  \frac
    {g \sin \theta - l \ddot \theta}
    {\cos \theta}
  &=
  \frac
    {F + ml \ddot \theta cos \theta - ml \dot \theta^2 \sin \theta}
    {M + m}
\\[2em]
  (M +m)(g \sin \theta - l \ddot \theta)
  &=
  (cos \theta)(F + ml \ddot \theta cos \theta - ml \dot \theta^2 \sin \theta)
\\[2em]
  (M + m) g \sin \theta - (M + m) l \ddot \theta
  &=
  F cos \theta + ml \ddot \theta cos^2 \theta - ml \dot \theta^2 \sin \theta \cos \theta
\\[2em]
  - (M + m) l \ddot \theta - ml \ddot \theta \cos ^2 \theta
  &=
  F cos \theta - ml \dot \theta^2 \sin \theta cos \theta + (M + m)g \sin \theta
\\[2em]
  - (M + m + m \cos^2 \theta) l \ddot \theta
  &=
  F cos \theta - ml \dot \theta^2 \sin \theta cos \theta + (M + m)g \sin \theta
\\[2em]
  \ddot \theta
  &=
  \frac
    {F cos \theta - ml \dot \theta^2 \sin \theta cos \theta + (M + m)g \sin \theta}
    {-l(M + m + m \cos^2 \theta)}
\\[2em]
  \ddot \theta
  &=
  \frac
    {F cos \theta - ml \dot \theta^2 \sin \theta cos \theta + (M + m)g \sin \theta}
    {-l(M + m(1 + \cos^2 \theta))}
\end{aligned} $$ (7)

Final equations of motion are (6) and (7):

$$ \begin{aligned}
  \ddot x &=
    \frac
      {F - m \sin \theta (g \cos \theta - l \dot{\theta}^2)}
      {M + m(1 + \cos^2 \theta)}
\\[2em]
  \ddot \theta
  &=
  \frac
    {F cos \theta - ml \dot \theta^2 \sin \theta cos \theta + (M + m)g \sin \theta}
    {-l(M + m(1 + \cos^2 \theta))}
\end{aligned}$$

## The Lagrangian Method

### The Euler-Lagrange equation

Calculus of Variations

$$
J(y) = \int_a^b F(x, y, y_x) dx
$$

The function $u = u(x)$ which extremizes the functional $J$ necessarily satisfies
the Euler-Lagrange equation on $[a,b]$:

$$
\frac{\partial F}{\partial u} - \frac{d}{dx}\left(\frac{\partial F}{\partial u_x}\right)
 = 0
$$

### Hamilton's Principle

Classical Mechanics

Given $L = T - V$ where $T$ is total kinetic energy and $U$ is potential energy,
the "action" of the system is the functional $A$.

$$
A(\bold q) := \int_{t_1}^{t_2} L(\bold q, \dot \bold q, t) dt
$$

The path $\bold q(t)$ that minimizes action will satisfy:

$$
\frac{\partial L}{\partial q_i} - \frac{d}{dt}\left(\frac{\partial F}{\partial \dot q_i}\right)
 = 0
$$

### Application to inverted pendulum

Kinetic energy of the system:

$$ \begin{aligned}
  T & = \sum \frac{1}{2} mv^2
\\[1.5em]
  & = \frac{1}{2} M \dot x^2 +
    \frac{1}{2} m \left( \sqrt{
      (\dot x + l \dot \theta \cos \theta)^2
      + (l \dot \theta \sin \theta)^2
    } \right)^2
\\[1.5em]
  & = \frac{1}{2} M \dot x^2 +
    \frac{1}{2} m \left(
      (\dot x + l \dot \theta \cos \theta)^2
      + (l \dot \theta \sin \theta)^2
    \right)
\\[1.5em]
  & = \frac{1}{2} M \dot x^2 +
    \frac{1}{2} m \left(
      \dot x^2 + 2 \dot x l \dot \theta \cos \theta + l^2 \dot \theta ^2 cos^2 \theta
      +
      l^2 \dot \theta^2 \sin ^2 \theta
    \right)
\\[1.5em]
  & = \frac{1}{2} M \dot x^2 +
    \frac{1}{2} m \left(
      \dot x^2 + 2 \dot x l \dot \theta \cos \theta +
      l^2 \dot \theta^2
    \right)
\\[1.5em]
  & = \frac{1}{2} M \dot x^2 +
    \frac{1}{2} m \dot x^2 +
    m \dot x l \dot \theta \cos \theta +
    \frac{1}{2} m l^2 \dot \theta^2
\\[1.5em]
  & = \frac{1}{2} (M + m) \dot x^2 +
    m \dot x l \dot \theta \cos \theta +
    \frac{1}{2} m l^2 \dot \theta^2
\end{aligned} $$

Potential energy of the system

$$ \begin{aligned}
  U & = mgl \cos \theta
\end{aligned} $$

Lagrangian $L$

$$ \begin{aligned}
  L &= T - U
\\
  & = \frac{1}{2} (M + m) \dot x^2 +
    m \dot x l \dot \theta \cos \theta +
    \frac{1}{2} m l^2 \dot \theta^2  -
    mgl \cos \theta
\end{aligned} $$

Applying Hamilton's principle to our system, we need to solve the 2
differential equations:

$$ \begin{aligned}
  \frac{\partial L}{\partial x} - \frac{d}{dt}\left(\frac{\partial L}{\partial \dot x}\right)
  = F \cdot \hat{\partial \dot x}
\end{aligned} $$ (2.1)

$$ \begin{aligned}
  \frac{\partial L}{\partial \theta} -
  \frac{d}{dt}\left(\frac{\partial L}{\partial \dot \theta}\right)
  = F \cdot \hat{\partial \dot \theta}
\end{aligned} $$ (2.2)

To make calculation easier, we'll compute the derivatives separately:

$$ \begin{aligned}
  \frac{\partial L}{\partial x} = 0
\end{aligned} $$ (2.3)

$$ \begin{aligned}
\\[0.5em]
  \frac{d}{dt} \left(
    \frac{\partial L}{\partial \dot x}
  \right)
  &=
  \frac{d}{dt} \left(
    (M + m) \dot x +
    m l \dot \theta \cos \theta
  \right)
\\[0.5em]
  &=
    (M + m) \ddot x +
    m l ( \ddot \theta \cos \theta - \dot \theta^2 \sin \theta )
\end{aligned} $$ (2.4)

Substituting (2.4) and (2.3) into (2.1)

$$ \begin{aligned}
    0 -
    \left(
      (M + m) \ddot x +
      m l ( \ddot \theta \cos \theta - \dot \theta^2 \sin \theta )
    \right)
    &=
    F
\\
    - (M + m) \ddot x
    - m l ( \ddot \theta \cos \theta - \dot \theta^2 \sin \theta )
    &=
    F
\\
    -
    (M + m) \ddot x
    &=
    F +
    m l ( \ddot \theta \cos \theta - \dot \theta^2 \sin \theta )
\\
    -
    (M + m) \ddot x
    &=
    F +
    m l \ddot \theta \cos \theta - ml \dot \theta^2 \sin \theta
\end{aligned} $$ (2.5)

Now we'll repeat for $\theta$:

$$\begin{aligned}
\frac{\partial L}{\partial \theta} =
  - m \dot x l \dot \theta \sin \theta
  + mgl \sin \theta
\end{aligned}$$ (2.6)

$$\begin{aligned}
  \frac{d}{dt} \left(
    \frac{\partial L}{\partial \dot \theta}
  \right)
  &=
  \frac{d}{dt} \left(
    m \dot x l \cos \theta + ml^2 \dot \theta
  \right)
\\
  &=
    m \ddot x l \cos \theta
    - m \dot x \dot \theta \sin \theta
    + ml^2 \ddot \theta
\end{aligned}$$ (2.7)

Subsituting (2.6) and (2.7) into (2.2)

$$\begin{aligned}
  - m \dot x l \dot \theta \sin \theta
  + mgl \sin \theta
  - \left(
    m \ddot x l \cos \theta
    - m \dot x \dot \theta \sin \theta
    + ml^2 \ddot \theta
  \right)
&=
  F \cos \theta
\\
  - m \dot x l \dot \theta \sin \theta
  + mgl \sin \theta
  - m \ddot x l \cos \theta
  + m \dot x \dot \theta \sin \theta
  - ml^2 \ddot \theta
&=
  F \cos \theta
\\
  - m \dot x l \dot \theta \sin \theta
  + mgl \sin \theta
  + m \dot x \dot \theta \sin \theta
  - ml^2 \ddot \theta
  - F \cos \theta
&=
  m \ddot x l \cos \theta
\\
  \frac{
    - m \dot x l \dot \theta \sin \theta
    + mgl \sin \theta
    + m \dot x \dot \theta \sin \theta
    - ml^2 \ddot \theta
    - F \cos \theta
  }{
    m l \cos \theta
  }
&=
  \ddot x
\end{aligned}$$ (2.7)

Solving (2.5) for $\ddot x$ and setting equal to (2.7):

$$\begin{aligned}
  \frac{
    - m \dot x l \dot \theta \sin \theta
    + mgl \sin \theta
    + m \dot x \dot \theta \sin \theta
    - ml^2 \ddot \theta
    - F \cos \theta
  }{
    m l \cos \theta
  }
&=
  \frac{
    F + ml \ddot \theta \cos \theta - ml \dot \theta ^2 \sin \theta
  }{-(M + m)}
\end{aligned}$$ (2.7)