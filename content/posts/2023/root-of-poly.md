---
title: "Any real root of a polynomial"
date: 2023-11-19T15:18:00+05:30
categories:
- Math 
tags:
- polynomials
- miniatures
---

A nice polynomial problem: 

> Find a real root of the equation 
> $$(x^2 - 9x - 1)^{10} + 99x^{10} = 10x^9(x^2-1)$$

Looks scary with the tenth powers, but move $90x^9$ to the right to get 

$$(x^2 - 9x - 1)^{10} + 9x^{10} = 10x^9(x^2 - 9x - 1)$$

Now get the terms to the left. A pattern begins to emerge.

$$(x^2 - 9x - 1)^{10} - 10x^9(x^2 - 9x - 1) + 9x^{10} = 0$$

Split the middle term with coefficients of $9$ and $1$:

$$(x^2 - 9x - 1)^{10} - 9x^9(x^2 - 9x - 1) - x^9(x^2 - 9x - 1) + 9x^{10} = 0$$

Factoring this is a bit tricky. We could do either of these:

{{< math >}}
\begin{align}
(x^2 - 9x - 1)[(x^2 - 9x - 1)^9 - 9x^9] - x^9[(x^2 - 9x - 1) - 9x] &= 0 \label{a}\tag{1} \\
(x^2 - 9x - 1)[(x^2 - 9x - 1)^9 - x^9] - 9x^9[(x^2 - 9x - 1) - x] &= 0 \label{b}\tag{2}
\end{align}
{{</ math >}}

Note that $[(x^2 - 9x - 1)^9 - x^9] = (x^2 - 10x - 1)g(x)$, where $g(x)$ is some 
polynomial in x. Trying to do the same with $9x^9$ gives us the ninth root of 
nine, which gets messy. Let's continue with $\ref{b}$.

$$(x^2 - 9x - 1)(x^2 - 10x - 1)g(x) - 9x^9(x^2 - 10x - 1) = 0$$

And we have a factor! Th roots of $x^2 - 10x - 1$ are $5 \pm \sqrt{26}$, giving 
us two real roots of the original equation.

