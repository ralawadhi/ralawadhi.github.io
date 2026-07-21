---
layout: post
author: Rashid Alawadhi
title:  "The Shift Operator and its Generalisation"
date:   2024-12-17
categories: maths, physics, operator, quantum
---

During my undergrad I took several quantum mechanics modules. Things got very interesting when we started learning the modern formulation of quantum mechanics which involved operators, matrices, bra-kets and the like. The idea that we could take the exponential of a matrix or an operator seemed like magic to me. I just thought of making this post to remind myself in the future of such memories.

The shift operator was once such object we were taught about in my course. Suppose we have a function $f:\mathbb{R}\rightarrow \mathbb{R}$. Physically it could indicate some property of a particle at position $x$ by writing $f(x)$. Now suppose we have the operator $\partial_x$ such that $\partial_x f(x) = \frac{d}{dx}f(x)$. The shift operator is such that

\begin{align}
\hat{T}(a)f(x) = f(x+a),
\end{align}
where $a$ is a real consonant. This notation for $\hat{T}(a)$ means that it shifts the function by $a$. One can define the shift operator by $\hat{T}(a) = e^{a\partial_x}$ where $e$ is the exponential map. We can check that this is the correct expression for $\hat{T}(a)$ by expanding both the operator and function

\begin{align}\label{eq:shift}
e^{a\partial_x}f(x) = \sum_{n=0}\frac{(a\partial_x)^n}{n!} \sum_{i=0}f^{(i)}(0)\frac{x^i}{i!},
\end{align}
let us writing down the first few terms,

\begin{align}
\big(   1+a\partial_x+\frac{1}{2}a^2\partial^2_x + \cdots   \big)\big( f(0) + f'(0)x + f^{\prime\prime}(0)\frac{x^2}{2} + \cdots   \big),
\end{align}
multiplying out and collecting terms in each derivative order we have,
\begin{align}
f(0) + f'(0)(x+a) + f^{\prime\prime}(0)(x+a)^2 + \cdots = f(x+a),
\end{align}
which as indicated by the equality is just the taylor expansion of $f(x+a)$ around the point $x+a=0$. Therefore, the operator $\hat{T}(a)$ has shifted the original function by a constant value $a$. Magical stuff.

Now, suppose we are not content with our lives and `promote' the constant $a$ to a full-fledged function that depends on $x$; namely, $a(x)$. In fact, let us start with simply setting $x=\phi(y)$ and leaving $a$ constant. This implies that $\partial_x = \frac{1}{\phi'(y)}\partial_y$, where the prime indicated a derivative with respect to the variable $y$. Also notes that

\begin{align}
f(x) = f(\phi(y)) = g(y) = g(\phi^{-1}(x)).
\end{align}
Let us substitute our new variables in the left hand side of \eqref{eq:shift},

\begin{align}
e^{\frac{a}{\phi'(y)}\partial_y}g(y) = g(\phi^{-1}(\phi(y) + a)).
\end{align}
This is the generalised form of the Shift operator. Finding the right hand side is just a matter of solving the differential equation $\phi'(y)=\text{function of y}$. For example choosing
$\phi'(y) = 1/y$ results in scaling $g(y)\rightarrow g(\lambda y)$ where $\lambda$ can be written in terms of $a$. You can read more about this generalised operator and its effects in this wikipedia [article](https://en.wikipedia.org/wiki/Shift_operator).