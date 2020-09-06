+++
title = "Differentiation"

date = 2019-02-15T00:00:00
# lastmod = 2018-09-09T00:00:00

draft = false  # Is this a draft? true/false
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.

# Add menu entry to sidebar.
linktitle = "Definition"
[menu.mit1801]
  parent = "1. Differentiation"
  weight = 1
+++

## Definition of a Derivative

Consider a function $f(x)$ represented by the curve in Figure 1. The derivative of $f(x)$ at a point $x=x_0$, denoted by $f'(x_0)$, is the slope of the tangent line to the graph of $f(x)$ at the point $(x_0, f(x_0))$. A tangent line is the *limit* of the secant lines joining points $P=(x_0, f(x_0))$ and $Q$ on the graph of $f(x)$ as $Q$ approaches $P​$.

<center>
{{<figure src="../Figures/session-001-differentiation.png" link="../Figures/session-001-differentiation.png" caption="Figure 1: A graph with secant and tangent lines.">}}
</center>

<center>
{{<figure src="../Figures/session-001-secant.png" link="../Figures/session-001-secant.png" caption="Figure 2: Geometric definition of the derivative.">}}
</center>

The slope of secant $PQ$ is rise divided by run, or the ratio $\frac{\Delta f}{\Delta x}$ as shown in Figure 2. As $Q$ gets closer to $P$, the distance $\Delta x$ goes to zero. Then, the derivate which is equivalent to the slope of tangent, can be expressed mathematically as:

{{% alert note %}}
$$\begin{align}
m &= f'(x_0) \\\\\\
&= \lim\_{Q \rightarrow P} \frac{\Delta f}{\Delta x} \nonumber \\\\\\
&= \lim\_{\Delta x \rightarrow 0} \frac{\Delta f}{\Delta x} \\\\\\
&= \lim\_{\Delta x \rightarrow 0} \frac{f(x_0 + \Delta x) - f(x_0)}{\Delta x}
\end{align}$$
{{% /alert %}}

The last equation above is the algebraic definition of a derivative.


<canvas id="myCanvas" width="200" height="100"
style="border:1px solid #c3c3c3;">
Your browser does not support the canvas element.
</canvas>

<script>
var canvas = document.getElementById("myCanvas");
var ctx = canvas.getContext("2d");
ctx.fillStyle = "#FF0000";
ctx.fillRect(0,0,150,75);
</script>


### Common derivative properties

- When you take the derivative of an odd function, you always get an even function and vice versa.
- Differentiable implies continuous: If $f$ is differentiable at $x\_0$, then $f$ is continuous at $x\_0$.

*Proof*

A function is continuous if $\lim\_{x \rightarrow x\_0} f(x) - f(x_0) = 0$. We multiply and divide this by the same value: 

$$
\begin{align}
\lim\_{x \rightarrow x\_0} f(x) - f(x\_0) &= \lim\_{x \rightarrow x_0} \frac{f(x)- f(x\_0)}{x - x\_0} \left(x - x\_0\right) \\\\\\
&= f'(x) \cdot 0 \\\\\\
&= 0
\end{align}
$$

## Notations

In calculus, as in the English language, there are many ways to express the same thing. Here we mention two notations most commonly used in calculus: Leibniz' and Newton's notations. Newton and Leibniz both invented calculus independently, and there has been anonymity between them, in addition to controversy about [who has first invented calculus](https://en.wikipedia.org/wiki/Leibniz%E2%80%93Newton_calculus_controversy).

We let $y = f(x)$, where $y$ is a variable representing the function $f$ at any given $x$. From the formula for the derivative, we represent "the change in $y$" as $\Delta y = \Delta f = f(x\_0 + \Delta x) - f(x\_0)$. On the other hand, the "change in $x$" is $\Delta x = x - x\_0$.

### Leibniz' notation

{{% alert note %}}
$$\lim\_{\Delta x \rightarrow 0} \frac{\Delta y}{\Delta x} \equiv \frac{dy}{dx}$$
{{% /alert %}}

Using Leibniz' notation, we might also represent the derivative as $\frac{df}{dx}$, $\frac{d}{dx}f$, $\frac{d}{dx}y$. Notice that Leibniz' notation does not specify where the derivative is being evaluated (e.g. at $x\_0$). However, it expresses the derivative as a ratio, which is more convenient than Newton's notation in certain situations.

### Newton's notation

The advantage of Newton's nation is that is compact representation of the derivative:

{{% alert note %}}
$$\lim\_{\Delta x \rightarrow 0} \frac{\Delta f}{\Delta x} \equiv f^\prime(x_0)$$
{{% /alert %}}
