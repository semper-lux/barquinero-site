---
title: "Discrete Morse Theory"
date: "2022-09-02"
summary: "Brief overview of Discrete Morse Theory"
tags: [
    "Talks",
]
draft: false
slides:
  # Choose a theme from https://github.com/hakimel/reveal.js#theming
  theme: cus_dracula
  # Choose a code highlighting style (if highlighting enabled in `params.toml`)
  #   Light style: github. Dark style: dracula (default).
  highlight_style: dracula
---

{{<mathjax_support>}}

<p hidden>
`\(\newcommand{\N}{\mathbb{N}}
\newcommand{\Z}{\mathbb{Z}}
\newcommand{\Q}{\mathbb{Q}}
\newcommand{\R}{\mathbb{R}}
\newcommand{\LP}{\left(}
\newcommand{\RP}{\right)}
\newcommand{\LS}{\left\lbrace}
\newcommand{\RS}{\right\rbrace}
\newcommand{\LA}{\left\langle}
\newcommand{\RA}{\right\rangle}
\newcommand{\LB}{\left[}
\newcommand{\RB}{\right]}
\newcommand{\MM}{\ \middle|\ }
\newcommand{\abs}[1]{\left\vert#1\right\vert}
\newcommand{\msr}[1]{m\left(#1\right)}
\require{color}\)`
</p>


# Discrete Morse Theory

---

### Simplicial Complex

---

### Simplex

A simplex is just an \\(n\\)-dimensional "triangle"
{{<centerimg "/DiscMorse/Simplex.png" 500>}}

---
formally

\\[\Delta^n=\LS x \in \R^k: x_0+\cdots+x_{k-1}=1, x_i \geq 0 \text { for } i=0, \ldots, k-1\RS\\]

---

We can also describe an \\(n\\) simplex combinatorially as a
list of the vertices of the simplex
\\[\sigma = \LB e_0,\ e_1,\ \cdots e_n\RB\\]

---

### Face of a Simplex

We define a face of a simplex as a proper subset of \\(\sigma\\) that is

\\[
  \tau < \sigma
\\]
when
\\[
  \LB a,b\RB \subset \LB a, \ b,\ c\RB
\\]

---

### Simplicial complex

A Simplicial complex is a space \\(K\\) built of glued together simplices and must satisfy

1. If \\(\tau\\) is the face of a simplex $\sigma \in K$ then \\(\tau\in K\\)
2. If \\(\sigma, \tau \in K\\) then \\(\sigma\cap \tau\\) is a face of \\(\sigma\\) and \\(\tau\\).

---

{{<centerimg "/DiscMorse/Torus.png" 600>}}

---

{{<centerimg "/DiscMorse/Complex.png" 500>}}

---

It's convenient to have a combinatorial description for \\(K\\).
This description is called an "abstract simplicial complex" and is just the
collection of combinatorial descriptions of simplices of \\(K\\)

---

{{<centerimg "/DiscMorse/Complex.png" 500>}}

\\[\LS
\LB b,c,d\RB,
\LB b,c\RB,
\LB b,d\RB,
\LB c,d\RB,
\LB a,c\RB,
\LB a,b\RB,
\LB d,e\RB,
\LB a\RB,
\LB b\RB,
\LB c\RB,
\LB d\RB,
\LB e\RB\RS
  \\]

---

### Definition of a "Discrete function"

A discrete function \\(f\\) on a simplicial complex \\(K\\) assigns a number to each simplex

---

<div class="sliderow">
<div class="slidecollumn">
{{<centerimg "/DiscMorse/Complex_f.png" 400>}}
</div>
<div class="slidecollumn" style="font-size: xx-large;">
\(
\begin{aligned}
f\LP\LB b,c,d\RB\RP &= 5\\
f\LP\LB b,c\RB\RP &= 4  \\
f\LP\LB b,d\RB\RP &= 5  \\
f\LP\LB c,d\RB\RP &= 3  \\
f\LP\LB a,c\RB\RP &= 1  \\
f\LP\LB a,b\RB\RP &= 1  \\
f\LP\LB d,e\RB\RP &= 5  \\
f\LP\LB a\RB\RP &= 0    \\
f\LP\LB b\RB\RP &= 2    \\
f\LP\LB c\RB\RP &= 2    \\
f\LP\LB d\RB\RP &= 4    \\
f\LP\LB e\RB\RP &= 6    \\
\end{aligned}
\)
</div>
</div>

---

### Definition of a "Discrete Morse function"

<!-- @@@ Def box -->
A discrete function
\\[f:K\to \R\\]
is called a discrete morse function if for every \\(\alpha \in K\\) of
degree \\(n\\) the following are true

1. \\(\\#\LS \alpha^n<\beta^{n+1} \MM f\LP\beta\RP\leq f\LP\alpha\RP\RS\leq 1\\)
2. \\(\\#\LS \alpha^n>\gamma^{n-1} \MM f\LP\gamma\RP\geq f\LP\alpha\RP\RS\leq 1\\)
<!-- endbox -->

---

<div class="sliderow">
<div class="slidecollumn">
{{<centerimg "/DiscMorse/Complex_f.png" 400>}}
  </div>
<div class="slidecollumn">
{{<centerimg "/DiscMorse/Complex_f_Not_Morse.png" 400>}}
  </div>
</div>

---

### Definition of a Critical simplex

<!-- @@@ Def box -->
An \\(n-\\)simplex \\(\alpha^n\\) is critical if the following are true

1. \\(\\#\LS \alpha^n<\beta^{n+1} \MM f\LP\beta\RP\leq f\LP\alpha\RP\RS=0\\)
2. \\(\\#\LS \alpha^n>\gamma^{n-1} \MM f\LP\gamma\RP\geq f\LP\alpha\RP\RS=0\\)

We should note that for all the \\(\alpha\in K\\) at least one of \\(1.\\) and \\(2.\\) must be true.

---

{{<centerimg "/DiscMorse/Complex_crit.png" 500>}}

---
<!-- {{<canvas jp_funct>}} -->

### Discrete Gradient Vector Field

<!-- @@@ Def box -->
A discrete gradient vector field on a simplicial complex \\(K\\)
is a collection of pairs \\(V=\LS\tau^n<\sigma^{n+1}\RS\\) of
simplices in \\(K\\) such that each simplex is in at most one pair of \\(V\\).
<!-- endbox -->

---

A discrete morse function induces a gradient vector field on \\(K\\). If \\(\alpha\\) is a non-critical simplex, and \\(\alpha<\beta\\) with \\(f\LP\beta\RP<f\LP\alpha\RP\\). We draw
an arrow from \\(\alpha\\) to \\(\beta\\).

---

{{<centerimg "/DiscMorse/Complex_grad.png" 500>}}

---

### Main result of discrete Morse Theory

Suppose \\(K\\) is a simplicial complex with a discrete Morse function. Then \\(K\\) is homotopy equivalent to a CW complex with exactly one cell of dimension \\(n\\) for each critical simplex of dimension \\(n\\).

---

### Simplicial collapse

The simplicial equivalent of a deformation retraction is called a
simplicial collapse.

---

### Maximal Face (Facet)

A face \\(\sigma\in K\\) is called maximal if there is no \\(\beta\in K\\) so that \\(\sigma<\beta\\).

---

{{<centerimg "/DiscMorse/Facets.png" 500>}}

---

### Free face

A simplex \\(\tau\\) of a simplicial complex \\(K\\) is called a free face if \\(\tau\\) is a face of exactly one maximal face.

---

{{<centerimg "/DiscMorse/Free_face.png" 500>}}

---

### Collapse

If \\(\tau\\) is a free face of \\(\sigma\\) we can collapse \\(K_1 \searrow K_2\\) by removing \\(\gamma\\) where \\(\tau<\gamma<\sigma\\).

---

{{<centerimg "/DiscMorse/Collapse.png" 600>}}

---

### Collapsing A Vector Field

Given a vector field we can simplicially collapse following the arrows.

---

{{<centerimg "/DiscMorse/Complex_collapse.png" 500>}}

---

### Sphere Theorems

---

### Combinatorial \\(d\\)-ball

A complex \\(K\\) is a combinatorial d-ball if \\(K\\) and \\(\Delta^d\\) have isomorphic subdivisions.

A combinatorial \\(\LP d-1\RP\\)-sphere is the boundary of a \\(d\\)-ball

---

### combinatorial \\(d\\)-manifold

A complex is a \\(d\\)-manifold if the link of every vertex is either a \\(d\\)-ball or \\(d\\)-sphere.

---