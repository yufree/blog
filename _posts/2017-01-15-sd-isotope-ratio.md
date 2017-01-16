---
layout: post
title: Statistical uncertainty of Isotope Ratio
---

In Analytical Chemistry, the measurements of isotope ratios are commons. However, I found the uncertainty of ratios are always shown in the format of standard deviation of independant vairiable, which is inappropriate in statistic. You accually measure at least two values to get one measurement.

In fact, if you want to use the differences of isotope ratios as a measurement for certain process, you need to accept the assumption that the intensities of different isotopes are independant. Then we could make the Taylor series expansion of the ratio x/y around the mean of x and y:

$$
\begin{split} 
\frac{x}{y} \approx \frac{x}{y}\Big|_{\mu_x,\mu_y}&+(x-\mu_x)\frac{\partial}{\partial x}\Big(\frac{x}{y}\Big)\Big|_{\mu_x,\mu_y}+(y-\mu_y)\frac{\partial}{\partial y}\Big(\frac{x}{y}\Big)\Big|_{\mu_x,\mu_y}\\&+\frac{1}{2}(x-\mu_x)^2\frac{\partial^2}{\partial x^2}\Big(\frac{x}{y}\Big)\Big|_{\mu_x,\mu_y}+\frac{1}{2}(y-\mu_y)^2\frac{\partial^2}{\partial y^2}\Big(\frac{x}{y}\Big)\Big|_{\mu_x,\mu_y}+(x-\mu_x)(y-\mu_y)\frac{\partial^2}{\partial x \partial y}\Big(\frac{x}{y}\Big)\Big|_{\mu_x,\mu_y}\\&+\mathcal{O}\Big(\Big((x-\mu_x)\frac{\partial}{\partial x}+(y-\mu_y)\frac{\partial}{\partial y}\Big)^3\Big(\frac{x}{y}\Big)\Big)
\end{split}
$$

The expectation of the ratio is 

$$
\mathbb{E}[r] = \mathbb{E}\Big[\frac{\bar x}{\bar y}\Big] = \frac{\mu_x}{\mu_y} + Var(\bar y)\frac{\mu_x}{\mu_y^3} - \frac{Cov(\bar x,\bar y)}{\mu_y^2} \approx \frac{\mu_x}{\mu_y} + \frac{1}{n}\Big(Var(y)\frac{\mu_x}{\mu_y^3} - \frac{Cov(x,y)}{\mu_y^2}\Big)
$$

The variance of the ratio is

$$
\begin{split}
Var(r) &= Var\Big( \frac{\bar x}{\bar y} \Big) = \mathbb{E}\Big[\Big(\frac{\bar x}{\bar y} - \mathbb{E}\Big[\frac{\bar x}{\bar y}\Big]\Big)^2\Big] \\&\approx \mathbb{E}\Big[\Big(\frac{\bar x}{\bar y} - \frac{\mu_x}{\mu_y}\Big)^2\Big]\\&\approx \mathbb{E}\Big[\Big((\bar x-\mu_x)\frac{\partial}{\partial \bar x}\Big(\frac{\bar x}{\bar y}\Big)\Big|_{\mu_x,\mu_y} + (\bar y - \mu_y)\frac{\partial}{\partial \bar y}\Big(\frac{\bar x}{\bar y}\Big)\Big|_{\mu_x,\mu_y}\Big)^2\Big]\\&\approx\frac{Var(\bar x)}{\mu^2_y} + \frac{\mu^2_x Var(\bar y)}{\mu^4_y} - \frac{2\mu_x Cov(\bar x, \bar y)}{\mu^3_y}\\&\approx\frac{1}{n}\Big(\frac{Var(x)}{\mu^2_y} + \frac{\mu_x^2 Var(y)}{\mu^4_y} - \frac{2\mu_x Cov(x,y)}{\mu^3_y}\Big)
\end{split}
$$

Such values could be used as the uncertainty of the isotope ratios instead of the standard deviation of the ratios themselves.
