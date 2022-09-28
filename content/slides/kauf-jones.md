---
title: "Jones Polynomial"
date: "2022-02-06"
summary: "Defintion of the Jones Polynomial"
tags: [
    "index",
]
draft: false
slides:
  # Choose a theme from https://github.com/hakimel/reveal.js#theming
  theme: black
  # Choose a code highlighting style (if highlighting enabled in `params.toml`)
  #   Light style: github. Dark style: dracula (default).
  highlight_style: dracula
---

{{<mathjax_support>}}
{{<canvas_head>}}

$\newcommand{\N}{\mathbb{N}}$
$\newcommand{\Z}{\mathbb{Z}}$
$\newcommand{\Q}{\mathbb{Q}}$
$\newcommand{\R}{\mathbb{R}}$
$\newcommand{\LP}{\left(}$
$\newcommand{\RP}{\right)}$
$\newcommand{\LS}{\left\lbrace}$
$\newcommand{\RS}{\right\rbrace}$
$\newcommand{\LA}{\left\langle}$
$\newcommand{\RA}{\right\rangle}$
$\newcommand{\LB}{\left[}$
$\newcommand{\RB}{\right]}$
$\newcommand{\MM}{\ \middle|\ }$
$\newcommand{\abs}[1]{\left\vert#1\right\vert}$
$\newcommand{\msr}[1]{m\left(#1\right)}$

## Definition

The Jones polynomial $V\LP L\RP$ of an oriented link $L$
is the Laurent Polynomial in $t^{1/2}$, with integer coefficients, defined by
\\[ V\LP L\RP=\LP\LP-A\RP^{-3w(D)}\LA D\RA\RP _{t^{1/2}=A^{-2}} \\]
where $D$ is any oriented diagram for $L$.

---
Definition is in terms of some odd looking stuff

The Kauffman bracket of $D$
\\[\LA D\RA\\]

and

The writhe of $D$
\\[w(D)\\]

## Kauffman Bracket

The Kauffman Bracket is a function from unoriented link diagrams in the oriented plane to Laurent polynomials with integer coefficients in an indeterminate $A$. It maps a diagram $D$ to $\LA D\RA\in \Z\LB A^{-1},\ A\RB$
and is characterized by

1. \\(\LA \img{/unknot.png} \RA=1\\)
2. \\(\LA D \sqcup \img{/unknot.png} \RA=\LP-A^{-2}-A^2\RP \LA D\RA\\\)
3. \\(\LA \img{/bracket_plus.png}\RA=A\LA \img{/bracket_vert.png} \RA+A^{-1}\LA\img{/bracket_hor.png}\RA\\)

---

{{<canvas Kauf_ex>}}

&nbsp;
&nbsp;

<!-- <img style="max-width:1000px !important; height:auto !important" src="/bracket_1.png"/>

<br/>

<img style="max-width:1000px !important; height:auto !important" src="/bracket_2.png"/> -->

---

&nbsp;
&nbsp;

Natural now to ask, "Is the Kauffman Bracket a knot invariant?"
How to tell?

&nbsp;
&nbsp;

Check Reidemeister moves.

&nbsp;
&nbsp;

---

## Reidemeister moves

### Type 2 and 3

If a diagram $D$ is changed by Type II or Type III Reidemeister move, then
$\LA D\RA$ does not change. That is,

1. \\(\LA\img{/bracket_type2.png}\RA=\LA\img{/bracket_hor.png}\RA\\)
2. \\(\LA\img{/bracket_type3.png}\RA=\LA\img{/bracket_type3_out.png}\RA\\)

Hence $\LA D\RA$ is invariant under regular isotopy of $D$.
&nbsp;
&nbsp;
{{<canvas Type_II>}}
&nbsp;
&nbsp;
{{<canvas Type_III>}}
&nbsp;
&nbsp;

---

### Type 1

If a diagram is changed by a Type I Reidemeister move, its bracket polynomial
changes in the following way:

1. \\(\LA\img{/bracket_type1_1.png}\RA=-A^{3}\LA\img{/bracket_type1_out.png}\RA\\)
2. \\(\LA\img{/bracket_type1_2.png}\RA=-A^{-3}\LA\img{/bracket_type1_out.png}\RA\\)

&nbsp;
&nbsp;
{{<canvas Type_I>}}
&nbsp;
&nbsp;

---

&nbsp;
&nbsp;
This is a problem... How to resolve?
&nbsp;
&nbsp;

---
## Writhe

### Orientation of a crossing

A crossing can be either:

1. Positive $+1$ <br/> ![+1](/plus.png) <br/>
2. Negative $-1$ <br/> ![-1](/minus.png) <br/>

&nbsp;
&nbsp;

### Writhe of a knot

The write $w\LP D\RP$ of a diagram $D$ of an oriented link is the sum of the
signs of the crossings of D.

&nbsp;
&nbsp;
{{<canvas Writhe>}}
&nbsp;
&nbsp;

### Writhe + Bracket

Let $D$ be a diagram of an oriented link $L$. Then the expression
\\[\LP -A\RP^{-3w\LP D\RP}\LA D\RA\\]
is an invariant of the oriented link $L$.

&nbsp;
&nbsp;
{{<canvas Writhe_Bracket>}}
&nbsp;
&nbsp;

## Definition of the Jones Polynomial

The Jones polynomial $V\LP L\RP$ of an oriented link $L$
is the Laurent Polynomial in $t^{1/2}$, with integer coefficients, defined by
\\[ V\LP L\RP=\LP\LP-A\RP^{-3w(D)}\LA D\RA\RP _{t^{1/2}=A^{-2}} \\]
where $D$ is any oriented diagram for $L$.

## Jones Polynomial is a function

The Jones polynomial invariant is a function
\\[V:\LS \text{Oriented links in }S^3\to \Z\LB t^{-\frac{1}{2}},\ t^{-\frac{1}{2}}\RB\RS\\]
such that

1. \\(V\LP\text{unknot}\RP=1\\)
2. Whenever three oriented links $L_+$, $L_-$, and $L_0$ are the same, except in the neighborhood of a point as follows  <br/> ![+1](/plus.png )   ![-1](/minus.png) ![-1](/skein_vert.png) <br/> Then \\[t^{-1}V\LP L_+\RP-t^V\LP L_-\RP+\LP t^{-\frac{1}{2}}-t^{\frac{1}{2}}\RP V\LP L_0\RP=0\\]

&nbsp;
&nbsp;
{{<canvas jp_funct>}}
&nbsp;
&nbsp;
