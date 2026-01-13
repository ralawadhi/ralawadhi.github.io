---
layout: post
author: Rashid Alawadhi
title:  "Recouping losses"
date:   2026-01-13
categories: maths, finance, economics
---

Suppose you are investing in some stock and it suffers a 5% loss. By how much does it have to rise to gain back the loss? The first thought that some of us might have is that the stock has to rise by 5%; however, this is not the case. In fact, the stock price has to increase by approximately 5.26%. Now you might think that the difference between our initial guess and this is small but see what happens when the loss gets larger and larger.

Say the current stock value is $P$. The stock will suffer an $\ell ( \{ 0\leq\ell<1\|\mathbb{R} \} )$ percent loss and then gain a $g$ percent increase back to its original value of $P$. As an equation this reads

$$(P - \ell P) + (P - \ell P) g = P.$$

Solving for $g$, which is the increase in percentage needed to recoup the loss, we have

$$g = \frac{\ell}{1-\ell}.$$

So if our stock loses 30% of its value, a much catasrophic loss than our earlier example, it needs to gain $g = 42.9\%$ to recoup the loss. For $\ell=50\%$ the gain needs to be $g=100\%$!

The require gain increases exponentially with respect to the loss. For small value of $\ell$ the gain increases mostly linearly, hence $\ell = 5\%\approx g$. This can be shown by Taylor expanding the equation for $g$

$$g = \ell + \ell^2 + \mathcal{O}(\ell^3).$$

This is why some people would advise you to sell if the losses reach a certain percentage. It is much more difficult to recoup losses, especially the bigger the loss is.
