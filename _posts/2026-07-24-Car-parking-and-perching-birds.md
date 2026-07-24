---
layout: post
author: Rashid Alawadhi
title:  "Parking Cars and Perching Birds "
date:   2026-07-24
categories: maths, physics, probability, distribution, eigenvalues
---

In his [paper](https://arxiv.org/abs/0907.1914), Petr Seba shows that humans parking their cars and birds perching on a power line make use of the same psychophysical principles. More specifically, the way humans and birds decide whether the space between cars is wide enough for them to park(or perch) result in the same distribution of said gaps. The idea is in a straight line of parking space cars either come to park or leave their parking space. The car that comes to park has to decide which available space to fill; will it park closer to the car at the front bumper or to the rear bumper. Once filled we record the remaining gap between the parked cars. Similarly we do the same for birds perching and record the gaps between the birds. Once we have the data and plot the gaps as a probability distributions, we see that both humans parking and birds' gaps follow the same probability distribution. This distribution is also related to the distribution of the [[random matrices and eigen values]].

Assume the parking lot is one-dimensional and of length $L$. Each car is of length $\ell_0$; however, one needs a little bit more space to park, say $1.2\ell_0$. The total number of cars is then $N\approx L/1.2\ell_0$. Now if we add the distances of all the gaps with get

$$\sum_{k=1}^{N}D_k = L - N\ell_0.$$

We treat the individual $D_k$'s as random variables. While the distances are not statistically independent, we can treat them as such by assuming $L>>\ell_0$. Now suppose a car is parked in a space between two cars. The distance from its front bumper to the next car is $D_n$, similarly for the rear bumper its $D_{n+1}$. Now if the car leaves, the resulting empty space is the car length $\ell_0$ plus the previous gaps. We represent the new gap by

$$D = D_n + D_{n+1} + \ell_0.$$

A new car shows up and parks in the newly made space and splits the gap differently than before; therefore we have

$$\tilde{D}_n = a(D - \ell_0)$$

and

$$\tilde{D}_{n+1} = (1-a)(D-\ell_0),$$

where $a\in [0,1]$ and represents the tendency of the driver to park closer to the car on either sides. The variable $a$ follows a probability distribution of some sort which we will get to shortly.

We can substitute $D$ into the new gaps equations

$$\tilde{D}_n = a(D_n + D_{n+1})$$

and

$$\tilde{D}_{n+1} = (1-a)(D_n + D_{n+1}).$$

We think of this as a transformation $D_n \rightarrow \tilde{D}_n$ induced by filling or leaving a parking space. Now the idea is to find the probability density of individual gaps $p_k(D_k)$. We can find that by integrating the joint probability density function with respect to the variables except for one. Since all cars are identical and divers have the same parking habit, the joint probability distribution is invariant under the exchange of variables and under the transformation $D\rightarrow \tilde{D}$. We have

$$p_k(D_k) = p(D_k) = \int_{D_1+D_2+\ldots+D_N=L-N\ell_0}p(D_1, D_2,\ldots, D_k)dD_1\ldots dD_{k-1}dD_{k+1}\ldots dD_N.$$

Lets say the variable $a$ follows a probability distribution given by $q(a)$ which is symmetric, i.e., $q(a) = q(1-a)$ and has a minimum at $a=1/2$. The symmetry means that the drivers have equal tendencies of parking closer to either adjacent cars. Now the objective is finding, for a given $q(a)$, a solution to the distributional equation

$$D\triangleq a(D+D').$$

That is to say; both sides have the same probability density distribution. There is a class of distribution functions that can describe $q(a)$ and also satisfy the above distributional equation: the beta probability distribution function, $\beta(g_1,g_2)$. According to (CITE), let $D_1, D_2$ and $a$ be independent random variables with the distributions: $D_1 \sim \Gamma(a_1, 1), D_2\sim \Gamma(a_2, 1)$ and $a\sim \beta(a_1, a_2)$. Then $a(D_1+D_2)\sim \Gamma(a_1, 1)$.

Since we decided that $q(a)$ is symmetric we take $a_1=a_2=g$ in the beta distribution. We take $g$ as a free parameter now and fix it later using psychophysical arguments. We will see that for small $a$ the distribution $q(a)$ represents the ability of the driver(or bird) to estimate small distances and avoid collision in the process of parking(perching).

Petr cites other works regarding the ability of humans and animals to avoid collisions and introduces the time to collision $\tau(t)$ and the retinal angular size of the object the animal( or human) is approaching by $\theta(t)$ at any given moment. The hypotheses approved by current research is that the time to collision is inversely proportional to the rate of angular expansion, meaning:

$$\tau(t) = \frac{\theta(t)}{d\theta/dt}.$$

Using elementary trigonometry we have the following equation for the instantaneous angular size of the object being approached, $\theta(t) = 2\tan^{-1}(\frac{L_0}{2D(t)})$; where $L_0$ is the width of the object and $D(t)$ is the instantaneous distance to the object. Solving the above ordinary differential equation we find

$$\tau(t) = -\frac{L_0^2+4D(t)^2}{2L_0(dD(t)/dt)} \tan^{-1}(\frac{L_0}{2D(t)}).$$
Notice that small distances, meaning $D(t)<<L_0$, we have

$$\tau(t)\approx \frac{D^2}{vL_0},$$

for constant velocity $v=dD/dt$. This tells us that the time to collision reduces quadratically with distance to the object. Assuming that the drivers' aim to exploit small distances is directly proportional to the time to contact variable $\tau$; and given the fact that $q(a)$ models the ability of the driver to estimate small distances, we set $q(a)\approx a^2$. This means that when the crash is impeding, any further movement is slowed down quadratically. Now since we determined that $q(a) = \beta(a, g,g)$, for small $a$ we find that $a=3$. Therefore, the normalised distance distribution is simply

$$p(D) = \Gamma(D, 3,1/3) = \frac{27}{2}D^2e^{-3D}.$$

This is a very interesting result. It predicts that the cars(or bird) repel each other.  The probability of finding cars parked very close to each other is exceedingly small( $p(D)\approx D^2$ for small $D$.) This deep result is related to the problem of finding the eigenvalues of a random matrix!
