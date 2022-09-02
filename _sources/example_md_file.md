# In-line math
To insert in-line math use the $\int$ symbol within a Markdown cell. For example, the text $this_{is}^{inline}$ will produce math.

## Math blocks
You can also include math blocks for separate equations. This allows you to focus attention on more complex or longer equations, as well as link to them in your pages. To use a block equation, wrap the equation in either $x^2+5$ or begin statements.

For example,

$$
  \int_0^\infty \frac{x^3}{e^x-1}\,dx = \frac{\pi^4}{15}
$$
results in math.

Here's another example: ${1, 2, 3, 4}$.

If ams math is enabled, the following should work:
\begin{align}
a_{11}& =b_{11}&
  a_{12}& =b_{12}\\
a_{21}& =b_{21}&
  a_{22}& =b_{22}+c_{22}
\end{align}


<!-- Here is a proposition
```{prf:proposition}
:label: my-proposition

This is a dummy proposition directive.
```

Here is a definition.
```{prf:definition}
:label: my-definition

The *economical expansion problem* (EEP) for
$(A,B)$ is to find a semi-positive $n$-vector $p>0$
and a number $\beta\in\mathbb{R}$, such that

$$
&\min_{\beta} \hspace{2mm} \beta \\
&\text{s.t. }\hspace{2mm}Bp \leq \beta Ap
$$
``` -->

