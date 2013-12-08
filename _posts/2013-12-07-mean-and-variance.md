---
layout: post
title: Mean, Variance and Something about Sample
---
OK，I must clear the concept of those terms because this is the third time I review my notes.

## Description of Data

If one wants to descript a collection of data, the Mode, Median and Mean are the first three terms to be learned. They are used to show the whole data in one parameter. And yes, one value is enough and the most important property of a dataset is the center. So where do the center come from? Here, our formula could be written as a distance between a parameter and the every values in the dataset. 

So the Mode could be written as 

$$ 
\sum_{}^{}(M_{para} - x_{i})^0 
$$

And the Median could be written as 

$$
\sum_{}^{}(M_{para} - x_{i})^1 
$$

Then the Mean could be written as

$$
\sum_{}^{}(M_{para} - x_{i})^2 
$$

Eh, I think the solution of the formula will show the Mean which make the distance smallest and yes, just make a diff. So here the description of the data is finished or just begin. Change the uppercase as you like. The origin idea came from [John Myles White](http://www.johnmyleswhite.com/notebook/2013/03/22/modes-medians-and-means-an-unifying-perspective/).

## Mean

Here we get Mean to show the center of dataset. And mean of discrete random variable X could be wright in the following formula:

$$
E[X] = \sum_x xp(x) 
$$

For a continuous random variable,

$$
E[X] = \int_{-\infty}^\infty t f(t)dt 
$$

Mean tell us the center of the distribution because we just use the smallest distance. Now we want to known the spread of the data. So we use variance.

## Variance

Here, we need to talk about moment in another view. The mean or the expected values is the first raw moment and the second central moment is variance. The [moment](http://en.wikipedia.org/wiki/Moment_(mathematics)) is another discription method of the distribution. Here we only use the formula of variance:

$$
Var(X) = E[(X - \mu)^2] 
$$

And the variance could be written as:

$$
Var(X) = E[X^2] - E[X]^2 
$$

So how to understand the variance in probability?

### Chebyshev’s inequality

$$
P(|X - \mu| \geq k\sigma) \leq \frac{1}{k^2} 
$$

Here we found the variance actually show the probaliblity of a observation in a distribution. That is just a description of spread of the distribution.

Ok, we talk enough about the distribution itself. Next we will see the sample.

## Sample

The independent and identically distributed random variables are the default model for random samples. Under iid, we could use the probaliblity to give out the description of sample. So if the values of variables is uncorrelated, then the variance of the sum is the sum of the variances.

$$
Var\left(\sum_{i=1}^n X_i \right) = \sum_{i=1}^n Var(X_i) 
$$

So we will get the variance of the mean of the sample:

$$
\begin{align}
Var(\bar X) & = & Var \left( \frac{1}{n}\sum_{i=1}^n X_i \right)\\ \\
    & = & \frac{1}{n^2} Var\left(\sum_{i=1}^n X_i \right)\\ \\
    & = & \frac{1}{n^2} \sum_{i=1}^n Var(X_i) \\ \\
    & = & \frac{1}{n^2} \times n\sigma^2 \\ \\
    & = & \frac{\sigma^2}{n} 
\end{align}
$$

We also get the standard error of the sample mean: $$ \sigma/\sqrt{n} $$,the sample mean has to be less variable than a single observation, therefore its standard deviation is divided.

For the sample mean which is the unbiased estimator of the population, nothing could be discussed. But for the sample variance need more attentions:

$$
S^2 =   \frac{\sum_{i=1}^n (X_i - \bar X)^2}{n-1} 
$$

We proof it:

$$
\begin{align}
E\left[\sum_{i=1}^n (X_i - \bar X)^2\right] & = & \sum_{i=1}^n E\left[X_i^2\right] - n E\left[\bar X^2\right] \\ \\
    & = & \sum_{i=1}^n \left\{Var(X_i) + \mu^2\right\} - n \left\{Var(\bar X) + \mu^2\right\} \\ \\
    & = & \sum_{i=1}^n \left\{\sigma^2 + \mu^2\right\} - n \left\{\sigma^2 / n + \mu^2\right\} \\ \\
    & = & n \sigma^2 + n \mu ^ 2 - \sigma^2 - n \mu^2 \\ \\
    & = & (n - 1) \sigma^2
\end{align}
$$

For the estimator $$ S^2 $$ of $$ \sigma^2 $$ is unbiased, the calculation of sample variance $$ S^2 $$ involves dividing by $$ n-1 $$. And $$ S / \sqrt{n} $$ is called the sample standard error of the mean.

## Mean Again

If I want to descript a collection of samples, the mean is esay to get. But if we want to know the population behind the samples, we will use S as a description of the spread. But if we only care the mean, the $$ S / \sqrt{n} $$ will show the description of the error when we calculate the mean. When the n is large enough, we will get a precise mean with small error. But this error have no effect of S, which is the description of the spread behind the sample. If you want an interval estimation of the sample mean instead of a point estimation, you may need to consider that t-value multiply the standard error.

Ok, finally I sort out those terms. I cite the work done by [Professor Brian Caffo](https://github.com/bcaffo/Caffo-Coursera), thank you very much.