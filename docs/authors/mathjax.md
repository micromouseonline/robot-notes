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
* More complex equations can be put inline if you want: $x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$

**NOTE**: you may need to escape the dollar symbol, $34.67,  to use it outside of maths if it appears in a pair.



### Display Equations

To display a large, complex equation on its own line, centered, enclose it in double dollar signs (`$$`).


<div class="grid grid-2" style="grid-template-columns: 60% 40%;">
  <div>
  ``` { .markdown .no-copy .no-select }
  $$
  x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
  $$
  ```
  </div>

  <div>
  $$
  x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
  $$
  </div>
</div>

### Numbered equations
If you want equations to be tagged with a reference, that will need to be done manually because 
the mathjax support seems limited.
Tags are not automatically sequenced. On the other hand, you can choose whatever you like:

<div class="grid grid-2" style="grid-template-columns: 60% 40%;">
  <div>
  ``` { .markdown .no-copy .no-select }
  $$
     d = \sqrt{b^2 - 4ac}   \tag{1}
  $$
  ```
  </div>

  <div>
  $$
     d = \sqrt{b^2 - 4ac}   \tag{1}
  $$
  </div>
</div>


### Subscripts/Superscripts: 

  - `x_i`      -> $x_{i}$     
  - `x^2`      -> $x^2$       
  - `x_{i+1}`  -> $x_{i+1}$   
  - `x^{y}`    -> $x^{y}$     


### Fractions: 

 - `\frac{a}{b}` -> $\frac{a}{b}$
 - `\dfrac{a}{b}` -> $\dfrac{a}{b}$
 - `y = {x+1 \over x+2}` -> $y = {x+1 \over x+2}$
 - `y = \frac{x+1}{x+2}` -> $y = \frac{x+1}{x+2}$

### Fonts

 - bold: `\mathbf{x}` -> $\mathbf{x}$
 - blackboard: `\mathbb{R} ` -> $\mathbb{RECTANGLE}$
 - calligraphic `\mathcal{C} ` -> $\mathcal{Calligraphic}$
 - Fractur: `\mathfrak{g} ` -> $\mathfrak{g}$


### Matrices

<div class="grid grid-2" style="grid-template-columns: 60% 40%;">
  <div>
  ``` { .markdown .no-copy .no-select }
    $$
       \begin{pmatrix}
         1 & 2 \\\
         3 & 4 
       \end{pmatrix}
    $$
  ```
  </div>

  <div>
    $$
       \begin{pmatrix}
         1 & 2 \\\
         3 & 4 
       \end{pmatrix}
    $$
  </div>
</div>

<div class="grid grid-2" style="grid-template-columns: 60% 40%;">
  <div>
  ``` { .markdown .no-copy .no-select }
    $$
       \begin{bmatrix}
         1 & 2 \\\
         3 & 4 
       \end{bmatrix}
    $$
  ```
  </div>

  <div>
    $$
       \begin{bmatrix}
         1 & 2 \\\
         3 & 4 
       \end{bmatrix}
    $$
  </div>
</div>

<div class="grid grid-2" style="grid-template-columns: 60% 40%;">
  <div>
  ``` { .markdown .no-copy .no-select }
    $$
       \begin{Bmatrix}
         1 & 2 \\\
         3 & 4 
       \end{Bmatrix}
    $$
  ```
  </div>

  <div>
    $$
       \begin{Bmatrix}
         1 & 2 \\\
         3 & 4 
       \end{Bmatrix}
    $$
  </div>
</div>

<div class="grid grid-2" style="grid-template-columns: 60% 40%;">
  <div>
  ``` { .markdown .no-copy .no-select }
    $$
       \begin{vmatrix}
         1 & 2 \\\
         3 & 4 
       \end{vmatrix}
    $$
  ```
  </div>

  <div>
    $$
       \begin{vmatrix}
         1 & 2 \\\
         3 & 4 
       \end{vmatrix}
    $$
  </div>
</div>

<div class="grid grid-2" style="grid-template-columns: 60% 40%;">
  <div>
  ``` { .markdown .no-copy .no-select }
    $$
     \begin{pmatrix}
       1      & a_1    & \cdots & a_n    \\\
       1      & b_1    & \cdots & b_n    \\\
       \vdots & \vdots & \ddots & \vdots \\\
       1      & z_1    & \cdots & z_n    \\\
     \end{pmatrix}
    $$
  ```
  </div>

  <div>
    $$
   \begin{pmatrix}
     1      & a_1    & \cdots & a_n    \\\
     1      & b_1    & \cdots & b_n    \\\
     \vdots & \vdots & \ddots & \vdots \\\
     1      & z_1    & \cdots & z_n    \\\
   \end{pmatrix}
    $$
  </div>
</div>

### Align and group

#### Aligned on $=$
<div class="grid grid-2" style="grid-template-columns: 60% 40%;" markdown>
  <div>
  ``` { .markdown .no-copy .no-select }
  $$
  \begin{align}
    f(x)   &= \frac{x+1}{x-2} \\\
    f'(x)  &= \frac{(x-2) - (x+1)}{(x-2)^2} \\\
           &= - \frac{3}{x^2 - 4x + 4}
  \end{align}
  $$
  ```
  </div>

  <div>
  $$
  \begin{align}
    f(x)   &= \frac{x+1}{x-2} \\\
    f'(x)  &= \frac{(x-2) - (x+1)}{(x-2)^2} \\\
           &= - \frac{3}{x^2 - 4x + 4}
  \end{align}
  $$
  </div>
</div>

#### collected equations: 

<div class="grid grid-2" style="grid-template-columns: 60% 40%;">
  <div>
  ``` { .markdown .no-copy .no-select }
    $$
    \begin{cases}
       2x	+	y	−	2z  &=	3   \\\
       x	−	y	−	z    &=	0   \\\
       x	+	y	+	3z   &=	12
    \end{cases}
  $$
  ```
  </div>

  <div>
    $$
    \begin{cases}
       2x	+	y	−	2z  &=	3   \\\
       x	−	y	−	z    &=	0   \\\
       x	+	y	+	3z   &=	12
    \end{cases}
    $$
  </div>
</div>
  

<div class="grid grid-2" style="grid-template-columns: 60% 40%;">
  <div>
  ``` { .markdown .no-copy .no-select }
  $$  f(n) =
  \begin{cases}
    \dfrac{n+1}{2} & \text{if n is even} \\\ \\\
    \dfrac{n}{2}   & \text{if n is odd}
  \end{cases}
  $$
  ```
  </div>

  <div>
  $$  f(n) =
   \begin{cases}
     \dfrac{n+1}{2} & \text{if n is even} \\\ \\\
     \dfrac{n}{2}   & \text{if n is odd}
   \end{cases}
   $$
  </div>
</div>




### Vectors

<div class="grid grid-2" style="grid-template-columns: 70% 30%;">
  <div>
  ``` { .markdown .no-copy .no-select }
  $$ \vec{u} + \vec{v} = \vec{w} $$
  ```
  </div>

  <div>
  $$ \vec{u} + \vec{v} = \vec{w} $$
  </div>
</div>


<div class="grid grid-2" style="grid-template-columns: 70% 30%;">
  <div>
  ``` { .markdown .no-copy .no-select }
  $$ \overrightarrow{AB} \ge \overrightarrow{AC} $$
  ```
  </div>

  <div>
  $$ \overrightarrow{AB} \ge \overrightarrow{AC} $$
  </div>
</div>

### Decorations

<div class="grid grid-2" style="grid-template-columns: 70% 30%;">
  <div>
  ``` { .markdown .no-copy .no-select }
  $$ 
  \vec{i} 
  \hat{i} 
  \bar{i} 
  \dot{x} 
  \ddot{x} 
  \dddot{x} 
  $$
  ```
  </div>

  <div>
  $$ 
  \vec{i} \\\
  \hat{i} \\\
  \bar{i} \\\
  \dot{x} \\\
  \ddot{x} \\\
  \dddot{x} $$
  </div>
</div>


### Other constructs


<div class="grid grid-2" style="grid-template-columns: 70% 30%;">
  <div>
  ``` { .markdown .no-copy .no-select }
  $$ \lim \limits_{ x \to 2^+ } { \dfrac{x+1}{x-2} } $$
  ```
  </div>

  <div>
  $$ \lim \limits_{ x \to 2^+ } { \dfrac{x+1}{x-2} } $$
  </div>
</div>



<div class="grid grid-2" style="grid-template-columns: 70% 30%;">
  <div>
  ``` { .markdown .no-copy .no-select }
  $$ \sum_{n=1}^\infty \frac{1}{n^2} $$
  ```
  </div>

  <div>
  $$ \sum_{n=1}^\infty \frac{1}{n^2} $$
  </div>
</div>


<div class="grid grid-2" style="grid-template-columns: 70% 30%;">
  <div>
  ``` { .markdown .no-copy .no-select }
  $$
  \int_0^\infty e^{-x^2} dx = \frac{\sqrt{\pi}}{2}
  $$
  ```
  </div>

  <div>
  $$
  \int_0^\infty e^{-x^2} dx = \frac{\sqrt{\pi}}{2}
  $$
  </div>
</div>
