---
title:  "Advanced Examples"
layout: post
tags: MathJax Gists
categories: posts
---

## MathJax

[Euler's formula](https://en.wikipedia.org/wiki/Euler%27s_formula) relates the  complex exponential function to the trigonometric functions.

\\[ e^{i\theta}=\cos(\theta)+i\sin(\theta) \\]

The [Euler-Lagrange](https://en.wikipedia.org/wiki/Lagrangian_mechanics) differential equation is the fundamental equation of calculus of variations.

$$ \frac{\mathrm{d}}{\mathrm{d}t} \left ( \frac{\partial L}{\partial \dot{q}} \right ) = \frac{\partial L}{\partial q} $$

The [Schrödinger equation](https://en.wikipedia.org/wiki/Schr%C3%B6dinger_equation) describes how the quantum state of a quantum system changes with time.

$$ i\hbar\frac{\partial}{\partial t} \Psi(\mathbf{r},t) = \left [ \frac{-\hbar^2}{2\mu}\nabla^2 + V(\mathbf{r},t)\right ] \Psi(\mathbf{r},t) $$


## Code

{% highlight python linenos %}

def safe_prime(nbits):
    q = getPrime(nbits)
    i = 1
    while 1:
        p = 2 * i * q + 1
        i = i + 1
        if isPrime(p): break
    return p, q

{% endhighlight %}

## Gists

{% gist f0c6334af28f60d244fa054f5a1c22d2 MOV.sage %}
