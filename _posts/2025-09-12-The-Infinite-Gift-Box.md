---
layout: post
author: Rashid Alawadhi
title:  "The Infinite Gift Box"
date:   2025-09-12
categories: maths, limits, infinite, series, area, volume
---

Suppose you have an infinite amount of cube boxes. Each box has side-length $\frac{1}{\sqrt{n}}$ where $n$ starts from 1. So the side length of the first box is 1, the second box is $1/\sqrt{2}$ and so on.
Now let us calculate the total area and volume of all the boxes. Each box has an area of $\frac{6}{n}$ where the number 6 is due to the cube having six faces. Therefore the total area of all the boxes can be represented as the summation

$$A_{\text{total}} = \sum_{n=1}^{\infty}\frac{6}{n}.$$

This sum actually diverges which means the total area of the boxes is infinite. The surprising thing is that when we try to calculate the total volume of the boxes, we get a different result. Each box has a volume of $(\frac{1}{\sqrt{n}})^3 = \frac{1}{n^{1.5}}$. Therefore the total volume of the boxes is again given by the summation

$$V_{\text{total}} = \sum_{n=1}^{\infty} \frac{1}{n^{1.5}}.$$

This is actually the definition of the Riemann zeta function $\zeta(s)$ for $s = 1.5$. We do not know the value of this function exactly but we can approximate it. To a few decimal places then the total volume is equal to the finite values of $\zeta(1.5) \approx 2.612$.

So the infinite gift box has infinite area but finite length. Another object with similar properties is Gabriel's horn.