---
title: Mathjax Examples
author: helicron
date: "2025-12-11"
keywords: [markdown, mathjax]
---

# Mathjax support

Markdown pages like this one can include specially crafted section hat will be rendered as mathematical expressions. these are based on the well established $\LaTeX$ standards.

To do this, you simply surround your mathematical expressions with special symbols and the browser takes care of the rest. Different setups use different marker symbols but this document uses the $ symbol.

A number of examples are shown below for easy reference.

Further references:

 - [https://www.cmor-faculty.rice.edu/~heinken/latex/symbols.pdf](https://www.cmor-faculty.rice.edu/~heinken/latex/symbols.pdf)
 - [https://kapeli.com/cheat_sheets/LaTeX_Math_Symbols.docset/Contents/Resources/Documents/index](https://kapeli.com/cheat_sheets/LaTeX_Math_Symbols.docset/Contents/Resources/Documents/index)

### Inline Expressions

To insert an expression *within a line of text*, enclose it in single dollar signs (`$`). This is handy for simple expressions like $\sqrt{3x-1}+(1+x)^2$ or the use of greek letters like $\pi$.

* **Markdown:** ```The equation is $E = mc^2$ for any mass $m$.```
* **Appearance:** The equation is $E = mc^2$ for any mass $m$.
* Complex equation can be put inline if you want: $x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$

**NOTE**: you may need to escape the dollar symbol, $34.67,  to use it outside of maths if it appears in a pair


### Display Equations

To display a large, complex equation on its own line, centered, enclose it in double dollar signs (`$$`).

* **Markdown:**

```
$$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$
```

* **Appearance:**
    $$
    x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
    $$

You can have multile equations aligned on, typically, the $=$ sign. Note that you need to explicitly mark the line breaks. For example, Lorenz Equations:
```
$$
\begin{align}
\dot{x} & = \sigma(y-x) \\\
\dot{y} & = \rho x - y - xz \\\
\dot{z} & = -\beta z + xy \\\
\end{align}
$$    

```
becomes
$$
\begin{align}
\dot{x} & = \sigma(y-x) \\\
\dot{y} & = \rho x - y - xz \\\
\dot{z} & = -\beta z + xy \\\
\end{align}
$$    


### Numbered equations
Equations will need to be manually tagged because the mathjax support seems limited.
Tags are not automatically sequenced. On the other hand, you can choose whatever you like:
$$
   x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}   \tag{1}
$$

### Subscripts/Superscripts: 

 `x_i`      -> $x_{i}$     
 `x^2`      -> $x^2$       
 `x_{i+1}`  -> $x_{i+1}$   
 `x^{y}`    -> $x^{y}$     

### Fractions: 

 - `\frac{a}{b}` -> $\frac{a}{b}$
 - `\dfrac{a}{b}` -> $\dfrac{a}{b}$
 - `$y = {x+1 \over x+2}$` -> $y = {x+1 \over x+2}$
 - `$y = \frac{x+1}{x+2}$` -> $y = \frac{x+1}{x+2}$

### Fonts

 - bold: `\mathbf{x}` -> $\mathbf{x}$
 - blackboard: `\mathbb{R} ` -> $\mathbb{RECTANGLE}$
 - calligraphic `\mathcal{C} ` -> $\mathcal{Calligraphic}$
 - Fractur: `\mathfrak{g} ` -> $\mathfrak{g}$


### Matrices

$$
   \begin{pmatrix}
     1 & 2 \\\
     3 & 4 \\\
   \end{pmatrix}
$$

$$
   \begin{bmatrix}
     1 & 2 \\\
     3 & 4 \\\
   \end{bmatrix}
$$

$$
   \begin{Bmatrix}
     1 & 2 \\\
     3 & 4 \\\
   \end{Bmatrix}
$$

$$
   \begin{vmatrix}
     1 & 2 \\\
     3 & 4 \\\
   \end{vmatrix}
$$

$$
   \begin{pmatrix}
     1      & a_1    & \cdots & a_n    \\\
     1      & b_1    & \cdots & b_n    \\\
     \vdots & \vdots & \ddots & \vdots \\\
     1      & z_1    & \cdots & z_n    \\\
   \end{pmatrix}
$$

### Align and group

$$
\begin{align}
  f(x)   &= \frac{x+1}{x-2} \\\
  f'(x)  &= \frac{(x-2) - (x+1)}{(x-2)^2} \\\
         &= - \frac{3}{x^2 - 4x + 4}
\end{align}
$$

Inline collected equations: 
  $\begin{cases}
     2x	+	y	−	2z  &=	3   \\\
     x	−	y	−	z    &=	0   \\\
     x	+	y	+	3z   &=	12
  \end{cases}$

And centred with everything else
  $$
  \begin{cases}
     2x	+	y	−	2z  &=	3   \\\
     x	−	y	−	z    &=	0   \\\
     x	+	y	+	3z   &=	12
  \end{cases}
  $$

  

$$  f(n) =
\begin{cases}
  \dfrac{n+1}{2} & \text{if n is even} \\\ \\\
  \dfrac{n}{2}   & \text{if n is odd}
\end{cases}
\qquad \forall n \in \mathbb N
$$

### Vectors

$$ \vec{u} + \vec{v} = \vec{w} $$

$$ \overrightarrow{AB} + \overrightarrow{BC} = \overrightarrow{AC} $$

### Decorations
$$ \vec{i} \hat{i} \bar{i} \dot{x} \ddot{x} \dddot{x} $$

### Other constructs
$$ \lim \limits_{ x \to 2^+ } { \dfrac{x+1}{x-2} } $$

$$ \sum_{n=1}^\infty \frac{1}{n^2} $$

$$ \int_o^\infty e^x dx $$