+++
title = "Differentiation Rules"

date = 2019-02-15T00:00:00
# lastmod = 2018-09-09T00:00:00

draft = false  # Is this a draft? true/false
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.

# Add menu entry to sidebar.
linktitle = "Rules"
[menu.mit1801]
  parent = "1. Differentiation"
  weight = 2
+++

## Derivative of a sum
The derivative of the sum of two functions is the sum of the derivatives:
{{% alert note %}}
$$ (u + v)^\prime(x) = u^\prime(x) + v^\prime(x) $$
{{% /alert %}}

Where the function $(u+v)(x)$ is just a shorthand for $u(x) + v(x)$.

### Proof

Applying the definition of the derivative to $(u + v)(x)$, we get: 

$$
\begin{align}
(u+v)^\prime(x) &= \lim\_{\Delta x \rightarrow 0} \frac{(u+v)(x+\Delta x) - (u+v)(x)}{\Delta x} \\\\\\
&= \lim\_{\Delta x \rightarrow 0} \frac{u(x+\Delta x) + v(x + \Delta x) - u(x) - v(x)}{\Delta x} \\\\\\
&= \lim\_{\Delta x \rightarrow 0} \frac{u(x + \Delta x) - u(x)}{\Delta x} + \lim\_{\Delta x \rightarrow 0} \frac{v(x + \Delta x) - v(x)}{\Delta x} \\\\\\
&= u^\prime(x) + v^\prime(x)
\end{align}
$$

## Derivative of $\sin x$

{{% alert note %}}
$$ \sin^\prime x = \cos x $$
{{% /alert %}}

### Proof

Begin with the definition of the derivative: 

$$ \frac{d}{dx} \sin x = \lim\_{\Delta x \rightarrow 0} \frac{\sin (x + \Delta x) - \sin x}{\Delta x} $$

Then, using the trigonometric identity:

$$\sin(a + b) = \sin a \cos b + \sin b \cos a$$

We untangle the $x$ from the $\Delta x$ as follows:

$$\begin{align}
\frac{d}{dx} \sin x &= \lim\_{\Delta x \rightarrow 0} \frac{\sin x \cos \Delta x + \sin \Delta x \cos x - \sin x}{\Delta x}\\\\\\
&= \lim\_{\Delta x \rightarrow 0} \left[ \frac{\sin x \cos\Delta x - \sin x}{\Delta x} + \frac{\cos x \sin \Delta x}{\Delta x}\right] \\\\\\
&= \lim\_{\Delta x \rightarrow 0} \left[ \frac{\sin x \left( \cos \Delta x - 1\right)}{\Delta x} + \frac{\cos x \sin \Delta x}{\Delta x} \right] \\\\\\
&= \lim\_{\Delta x \rightarrow 0} \sin x \left( \frac{\cos \Delta x - 1}{\Delta x} \right) + \lim\_{\Delta x \rightarrow 0} \cos x \left( \frac{\sin \Delta x}{\Delta x} \right)
\end{align}
$$

Now, we have the limits:

$$\begin{align}
& \lim\_{\Delta x \rightarrow 0} \frac{\cos \Delta x - 1}{\Delta x} &= 0 \\\\\\
& \lim\_{\Delta x \rightarrow 0} \frac{\sin\Delta x}{\Delta x} &= 1
\end{align}$$

Where a geometric proof of the limits can be found [here for $\frac{\sin x}{x}$](https://ocw.mit.edu/courses/mathematics/18-01sc-single-variable-calculus-fall-2010/1.-differentiation/part-a-definition-and-basic-rules/session-8-limits-of-sine-and-cosine/MIT18_01SCF10_Ses8a.pdf) and [here for $\frac{1 - \cos x}{x}$](https://ocw.mit.edu/courses/mathematics/18-01sc-single-variable-calculus-fall-2010/1.-differentiation/part-a-definition-and-basic-rules/session-8-limits-of-sine-and-cosine/MIT18_01SCF10_Ses8b.pdf).

and thus the derivative becomes:

$$
\frac{d}{dx}\sin x =  \sin x \cdot 0 + \cos x \cdot 1 = \cos x
$$

The above proof is based on the algebraic formula for the derivative. Another way to proof the derivative on $\sin x$ is geometrically, using the unit circle. [This document provides a geometric proof](https://ocw.mit.edu/courses/mathematics/18-01sc-single-variable-calculus-fall-2010/1.-differentiation/part-a-definition-and-basic-rules/session-8-limits-of-sine-and-cosine/MIT18_01SCF10_Ses8d.pdf) for the derivative of $\sin x$.

## Derivative of $\cos x$

{{% alert note %}}
$$ \cos^\prime x = -\sin x $$
{{% /alert %}}

### Proof

The proof is very similar to that of the derivative of $\sin x$. Starting from the definition of the derivative: 

$$\frac{d}{dx} \cos x = \lim\_{\Delta x \rightarrow 0} \frac{\cos(x + \Delta x) - \cos(x)}{\Delta x}$$

Using the trigonometric identity:

$$ \cos(a+b) = \cos a \cos b - \sin a \sin b$$

we simplify the derivative equation:

$$\begin{align}
\frac{d}{dx} \cos x &= \lim\_{\Delta x \rightarrow 0} \frac{\cos x \cos \Delta x - \sin x \sin \Delta x - \cos x}{\Delta x} \\\\\\
&= \lim\_{\Delta x \rightarrow 0} \left[ \frac{\cos x \cos \Delta x - \cos x}{\Delta x} + \frac{-\sin x \sin\Delta x}{\Delta x}\right] \\\\\\
&= \lim\_{\Delta x \rightarrow 0} \left[ \cos x \left( \frac{\cos \Delta x - 1}{\Delta x} \right) - \sin x \frac{\sin \Delta x}{\Delta x} \right] \\\\\\
&= \cos x \cdot 0 - \sin x \cdot 1 \\\\\\
&= -\sin x
\end{align}$$

where in fourth equation, we have used the limits properties mentioned in the proof for $\sin x $ derivative.

## Product rule

The product rule tells us how to compute the derivative of the product of two functions: 

{{% alert note %}}
$$ (uv)^\prime = u^\prime v + uv^\prime $$
{{% /alert %}}

### Proof

Using the formula for the derivative: 

$$\begin{align}
(uv)^\prime &= \lim\_{\Delta x \rightarrow 0} \frac{(uv)(x + \Delta x) - (uv)(x)}{\Delta x} \\\\\\
&= \lim\_{\Delta x \rightarrow 0} \frac{u(x + \Delta x)v(x + \Delta x) - u(x)v(x)}{\Delta x} \\\\\\
\end{align}$$

Then, we add and subtract the term $u(x+\Delta x)v(x)$ to the derivative equation: 
<font size="2">
$$\begin{align}
(uv)^\prime &= \lim\_{\Delta x \rightarrow 0} \frac{u(x + \Delta x)v(x + \Delta x) - u(x)v(x) + u(x + \Delta x)v(x) - u(x + \Delta x)v(x)}{\Delta x} \\\\\\
&= \lim\_{\Delta x \rightarrow 0} \left[ \frac{u(x+\Delta x) - u(x)}{\Delta x} v(x) + u(x + \Delta x) \frac{v(x + \Delta x) - v(x)}{\Delta x} \right] \\\\\\
&= u^\prime v + u v^\prime
\end{align}$$
</font>

Note that we have used the fact that $\lim\_{\Delta x \rightarrow 0} u(x + \Delta x) = u(x)$, since $u$ is differentiable and therefore continuous.

## Quotient rule

The formula for differentiating quotients (or fractions) is: 

{{% alert note %}}
$$\left( \frac{u}{v} \right)^\prime = \frac{u^\prime v - uv^\prime}{v^2}$$
{{% /alert %}}

### Proof

Again, starting from the main formula for a derivative, we have:

$$\begin{align}
\left( \frac{u}{v} \right)^\prime &= \lim\_{\Delta x \rightarrow 0} \frac{\frac{u(x + \Delta x)}{v(x + \Delta x)} - \frac{u(x)}{v(x)}}{\Delta x} \\\\\\
\end{align}$$

Let $\Delta u = u(x + \Delta x) - u(x)$ and $\Delta v = v(x + \Delta x) - v(x)$, then we simplify the numerator:

$$\begin{align}
\frac{u(x + \Delta x)}{v(x + \Delta x)} - \frac{u(x)}{v(x)} &= \frac{u + \Delta u}{v + \Delta v} - \frac{u}{v} \\\\\\
&= \frac{(u + \Delta u)v - u(v + \Delta v)}{(v + \Delta v)v} \\\\\\
&= \frac{uv + (\Delta u)v - uv + u\Delta v}{(v + \Delta v)v} \\\\\\
&= \frac{(\Delta u)v - u(\Delta v)}{(v + \Delta v)v}
\end{align}$$

Now that we have simplified the numerator, we can use it to simplify the difference quotient:

$$\begin{align}
\frac{\frac{u(x + \Delta x)}{v(x+\Delta x)} - \frac{u(x)}{v(x)}}{\Delta x} &= \frac{\frac{(\Delta u)v - u(\Delta v)}{(v + \Delta v)v}}{\Delta x} \\\\\\
&= \frac{1}{\Delta x} \frac{(\Delta u)v - u(\Delta v)}{(v + \Delta v)v} \\\\\\
&= \frac{\left( \frac{\Delta u}{\Delta x} \right) v - u \left( \frac{\Delta v}{\Delta x} \right)}{(v + \Delta v)v}
\end{align}$$

since $v$ is differentiable (and therefore continuous), then $\lim\_{x \rightarrow 0} v(x + \Delta x) = v(x)$, and we have that:

$$
\lim\_{\Delta x \rightarrow 0}  \frac{\left( \frac{\Delta u}{\Delta x} \right) v - u \left( \frac{\Delta v}{\Delta x} \right)}{(v + \Delta v)v} = \frac{v \frac{du}{dx} - u \frac{dv}{dx}}{v^2}
$$

## Chain rule

The chain rule tells us how to find the derivative of a composition of functions like $(f \circ g)(x) = f(g(x))$. To find the derivative of $f$ with respect to $x$, we use the chain rule: 
{{% alert note %}}
$$ \frac{df}{dx} = \frac{df}{dz}\frac{dz}{dx}$$
{{% /alert %}}

where we have set $z = g(x)$.

