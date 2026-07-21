---
layout: post
author: Rashid Alawadhi
title:  "The Heat equation and the Theta Function"
date:   2026-07-21
categories: maths, physics, PDE, infinite, sum
---

While brushing up on topics related to PDEs, initial values, and boundary conditions, I have come across the problem of solving the heat equation for the case of a ball immersed in water. I got to know that a function arises from considering the temperature at the centre of the ball; the [[Theta function]]. Here is how it arises from the problem.

Suppose we have a solid ball of radius $a$ heated to a uniform constant temperature $u(r, t)=1$ inside the ball and then immersing it in water to cool it down. The phenomenon is described by the heat equation in spherical polar coordinates:

$$\frac{\partial u(r, t)}{\partial t} = D \frac{\partial^2 u(r, t)}{\partial^2 r} + \frac{2D}{r}\frac{\partial u(r, t)}{\partial r} ,$$

where $D$ is assumed to be constant. The boundary conditions are

$$u(a, t) = 0,\quad u(r, 0)=1, \quad 0<r<a.$$

A few points to clarify is in order. The problem is spherical symmetric; hence the absence of angles in the equation. Outside the ball the temperature is zero and the ball starts with its temperature being uniform and constant at time zero.

Now we can use the method of separation of variables, $u(r, t) = R(r)T(t)$ to decouple the radial and temporal parts of the equation. Once we do that we set both sides of the equation equal to $-\lambda$ which is a constant. We find two sets of ODEs

$$\frac{\partial T}{\partial t} = -\lambda D T,$$

and

$$\frac{\partial^2 R}{\partial^2 r} + \frac{2}{r}\frac{\partial R}{\partial r} = -\lambda R.$$

The first equation is solved by $T(t) = T_0 e^{-\lambda D t}$. The second equation turns out to be solved by a linear combination of Bessel functions

$$R(r) = \frac{1}{\sqrt{r}}\Big[ C_1 J_{1/2}(\sqrt{\lambda }r) + C_2Y_{1/2}(\sqrt{\lambda} r) \Big],$$

where $C_1, C_2$ are constants.

Now we substitute the expressions for the Bessel functions, and using the spatial boundary conditions to find the values for the constants and $\lambda = \frac{n^2\pi^2}{a^2}$ . We can now simply reconstruct the full solution $u = RT$ while also invoking the fact that any reasonable function can be expressed in terms of a Fourier series to satisfy the initial condition we find:

$$u(r, t) = \sum_{n=0}^{\infty}C_n \frac{sin(\frac{n\pi r}{a})}{r}e^{-Dn^2\pi^2t/a^2}.$$

We can find the constants $C_n$ by using the $sin$ orthogonality identity:

$$
  \begin{equation}
    \int_0^a \sin(\frac{m\pi r}{a}) \sin(\frac{n\pi r}{a})dr=
    \begin{cases}
      \frac{a}{2}, & \text{if}\ m=n \\
      0, & \text{otherwise}
    \end{cases}
  \end{equation}
$$

Then using the initial condition $u(r, 0) = 1$ and multiplying both sides with $\sin(\frac{m\pi r}{a})$

we find

$$C_n = \frac{-2a}{\pi n}(-1)^n.$$

Then finally we can write down out full solution

$$u(r, t) = \sum_{n=0}^{\infty}\frac{-2a}{\pi n}(-1)^n \frac{sin(\frac{n\pi r}{a})}{r}e^{-Dn^2\pi^2t/a^2}.$$

We can now take the limit $r\rightarrow 0$ to find the expression for the temperature at the centre of the ball

$$u(0, t)= \lim_{r\rightarrow 0} u(r, t) = -2\sum^\infty_{n=1}(-1)^ne^{Dn^2\pi^2t/a^2}.$$

We are left with an interesting looking infinite sum. Before going further let us plot the temperature and see how it behaves

![coolingBall.png](/assets/images/heatEquation/coolingBall.png#center)

Notice that at the beginning of the cooling the temperature remains relatively constant. After some time a rapid period of cooling. This shows that the thickness of the ball slows down the loss of heat to the surrounding water.

Let us now clean the expression for the temperature by redefining the variable $t$ via $x = D\pi^2t/a^2$ and then further by $y = e^x$:

$$S = -2 \sum^\infty_{n=1}(-1)^ny^{-n^2}.$$

In fact it turns out that this sum is related to the Theta function of which the following is an example

$$\theta(z, q) = \sum^\infty_{n=-\infty} q^{n^2}e^{2\pi i n z},$$

where $z$ and $q$ are complex numbers. Now if we set $z=1/2$ and $q\equiv y^{-1}\in \mathbb{R}$ we find

$$\theta(1/2, y^{-1}) = \sum^{\infty}_{n=-\infty}y^{-n^2}(-1)^n.$$

This can be written entirely in terms of positive values of $n$ if we evaluate the $n=0$ case:

$$\theta(1/2, y^{-1}) = 1 + 2\sum^{\infty}_{n=1}y^{-n^2}(-1)^n.$$

The second term is simply the sum $S$ we obtained from solving the heat equation at the centre of the ball!

$$\theta(1/2, y^{-1}) = 1 - S.$$

I just find it absolutely beautiful how things that we study in nature can lead to mathematical object from fields that are seemingly unrelated to the problem at hand. The theta function shows up in elliptic functions, quantum physics, and number theory.
