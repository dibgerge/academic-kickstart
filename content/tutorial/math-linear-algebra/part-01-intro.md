+++
title = "The geometry of linear equations"

date = 2019-08-01T00:00:00
# lastmod = 2018-09-09T00:00:00

draft = false  # Is this a draft? true/false
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.

# Add menu entry to sidebar.
linktitle = "The geometry of linear equations"
[menu.math-linear-algebra]
  parent = "1. AX = B"
  weight = 1
+++

The fundamental problem of linear algebra is to solve $n$ linear equations in $n$ unknowns, for example: 

$$
\begin{align}
& 2x - y &= 0 \\\\\\
& \text{--}x + 2y &= 3
\end{align}
$$

In linear algebra, we view this problem in three ways.

## Row picture

Plot the points that satisfy each equation. In the above example, each equation represents a line in a 2-D space. The intersection of the two plots represent the solution to this system of equations. Figure 1 shows the plot for the two equations above, and they intersect at one point ($x=1$, $y=2$), which is the system's solution.

<center>
{{<figure src="/tutorials/math-linear-algebra/Figures/part-01-row-picture.png" link="/tutorials/math-linear-algebra/Figures/part-01-row-picture.png" caption="Figure 1: The lines $2x -y = 0$ and $-x+2y=3$ intersect at the point (1, 2)." >}}
</center>

## Column picture

We rewrite the system of linear equations as a single equation by turning the coefficients in the columns of the system into vectors: 
$$
x \begin{bmatrix} 2 \\\\\\ \text{--}1 \end{bmatrix} + y \begin{bmatrix} \text{--}1 \\\\\\ 2 \end{bmatrix} = \begin{bmatrix} 0 \\\\\\ 3 \end{bmatrix}
$$
where we view the right  hand side as a linear combinations of the coefficients on the left hand side. Geometrically, we want to find numbers $x$ and $y$ so that $x$ so that the combinations of the two columns vectors equals $\begin{bmatrix} 0 \\\\\\ 3 \end{bmatrix}$. Figure 2 shows that for $x=1$ and $y=2$, we get the correct combination to give us the right hand side.

<center>
  {{<figure src="/tutorials/math-linear-algebra/Figures/part-01-column-picture.png" link="/tutorials/math-linear-algebra/Figures/part-01-column-picture.png" caption="Figure 2: A linear combination of the column vectors equals the vector $\mathbf{b}$. ">}}
</center>

## Matrix picture

We write the system of equations as a single equation by using matrices and vectors. The above equation is: 

$$
\begin{bmatrix}
2 & \text{--}1 \\\\\\
\text{--} 1 & 2
\end{bmatrix}
\begin{bmatrix}
x \\\\\\ y
\end{bmatrix}=
\begin{bmatrix}
0 \\\\\\ 3
\end{bmatrix}
$$

The matrix $A = \begin{bmatrix}2 & \text{--}1 \\\\\\ \text{--} 1 & 2\end{bmatrix}$ is called the *coefficient matrix*. The vector $\mathbf{x} = \begin{bmatrix} x \\\\\\ y \end{bmatrix}$ is the vector of unknowns. The values on the right hand side of the equations form the vector $\mathbf{b}$:
$$
A \mathbf{x} = \mathbf{b}
$$
