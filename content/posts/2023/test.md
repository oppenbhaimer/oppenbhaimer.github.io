---
title: "Testing"
date: 2023-09-10T16:37:44+05:30
draft: false
---

Usual new blog test.

the five boxing wizards jump quickly.

THE FIVE BOXING WIZARDS JUMP QUICKLY.

The **five** *boxing* ~~wizards~~ jump <u>quickly</u>.

```c++
float Q_rsqrt( float number )
{
 long i;
 float x2, y;
 const float threehalfs = 1.5F;

 x2 = number * 0.5F;
 y  = number;
 i  = * ( long * ) &y;                       // evil floating point bit level hacking
 i  = 0x5f3759df - ( i >> 1 );               // what the fuck?
 y  = * ( float * ) &i;
 y  = y * ( threehalfs - ( x2 * y * y ) );   // 1st iteration
// y  = y * ( threehalfs - ( x2 * y * y ) );   // 2nd iteration, this can be removed

 return y;
}
```

# Heading 1 
## Heading 2 
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

How to integrate $\int\_C \frac{\log z}{z} dz$, $C = [i, 1]$? (Taken from [This 
MSE thread](https://math.stackexchange.com/questions/2753732/complex-integration-example))

$$
\newcommand{\bbx}[1]{\\,\bbox[15px,border:1px groove navy]{\displaystyle{#1}}\\,}
\newcommand{\braces}[1]{\left\lbrace\\,{#1}\\,\right\rbrace}
\newcommand{\bracks}[1]{\left\lbrack\\,{#1}\\,\right\rbrack}
\newcommand{\dd}{\mathrm{d}}
\newcommand{\ds}[1]{\displaystyle{#1}}
\newcommand{\expo}[1]{\\,\mathrm{e}^{#1}\\,}
\newcommand{\ic}{\mathrm{i}}
\newcommand{\mc}[1]{\mathcal{#1}}
\newcommand{\mrm}[1]{\mathrm{#1}}
\newcommand{\pars}[1]{\left(\\,{#1}\\,\right)}
\newcommand{\partiald}[3]{\frac{\partial^{#1} #2}{\partial #3^{#1}}}
\newcommand{\root}[2]{\\,\sqrt[#1]{\\,{#2}\\,}\\,}
\newcommand{\totald}[3]{\frac{\mathrm{d}^{#1} #2}{\mathrm{d} #3^{#1}}}
\newcommand{\verts}[1]{\left\vert\\,{#1}\\,\right\vert}
\begin{align}
& \stackrel{\mrm{as}\ \epsilon\ \to\ 0^{+}}{\sim}\\,\\,\\,
-\ \overbrace{\int\_{1}^{\epsilon}{\ln\pars{x} \over x}\\,\dd x}
^{\ds{\text{over}\\,\\,\\, \pars{1,\epsilon}}}\\ -\\
\overbrace{\int\_{0}^{\pi/2}
{\ln\pars{\epsilon} + \ic\theta \over \epsilon\expo{\ic\theta}}\\,
\epsilon\expo{\ic\theta}\ic\\,\dd\theta}
^{\ds{\text{over}\\,\\,\\, \epsilon\expo{\ic\pars{0,\pi/2}}}}\\ -\\
\overbrace{\int\_{\epsilon}^{1}{\ln\pars{y} + \ic\pi/2 \over \ic y}\\,\ic\\,\dd y}
^{\ds{\text{over}\\,\\,\\,\pars{\ic\epsilon,\ic}}}
\\\\[5mm] = &\\
-\\,{1 \over 2}\\,\ln^{2}\pars{\epsilon} -
\bracks{\ic\ln\pars{\epsilon}\\,{\pi \over 2} -
\color{#f00}{\pi^{2} \over 8}} - \bracks{-\\,{1 \over 2}\\,\ln^{2}\pars{\epsilon} -\ic\ln\pars{\epsilon}\\,{\pi \over 2}}
\\,\\,\\,\stackrel{\mrm{as}\ \epsilon\ \to\ 0^{+}}{\Large \to}\\,\\,\\,
\boxed{\pi^{2} \over 8}
\end{align}
$$

Nice. How do you decompose the ELBO? (Taken from [Understanding Diffusion Models:
A Unified Perspective](https://calvinyluo.com/2022/08/26/diffusion-tutorial.html))

$$
\begin{align}
\log p(\boldsymbol{x})
&\geq \mathbb{E}\_{q(\boldsymbol{x}\_{1:T}\mid\boldsymbol{x}\_0)}\left[\log \frac{p(\boldsymbol{x}\_{0:T})}{q(\boldsymbol{x}\_{1:T}\mid\boldsymbol{x}\_0)}\right]\\\\
&=  \begin{aligned}
      \underbrace{\mathbb{E}\_{q(\boldsymbol{x}\_{1}\mid\boldsymbol{x}\_0)}\left[\log p\_{\boldsymbol{\theta}}(\boldsymbol{x}\_0\mid\boldsymbol{x}\_1)\right]}\_\text{reconstruction term} &- \underbrace{\mathcal{D}\_{\text{KL}}(q(\boldsymbol{x}\_T\mid\boldsymbol{x}\_0) \mid\mid p(\boldsymbol{x}\_T))}\_\text{prior matching term} \\\\
      &- \sum\_{t=2}^{T} \underbrace{\mathbb{E}\_{q(\boldsymbol{x}\_{t}\mid\boldsymbol{x}\_0)}\left[\mathcal{D}\_{\text{KL}}(q(\boldsymbol{x}\_{t-1}\mid\boldsymbol{x}\_t, \boldsymbol{x}\_0) \mid\mid p\_{\boldsymbol{\theta}}(\boldsymbol{x}\_{t-1}\mid\boldsymbol{x}\_t))\right]}\_\text{denoising matching term}
    \end{aligned}
\end{align}
$$

I think that's it. Maybe a hint tag, but I'll add that on my own. Embedding 
HTML works here, so iframes/embeds can be added as pleased.

<center><blockquote class="twitter-tweet" data-theme="dark"><p lang="en" dir="ltr">Making a good GitHub pages blog is so much effort smh I’ll probably just use substack from now on</p>&mdash; Oppenbhaimer (@oppenbhaimer) <a href="https://twitter.com/oppenbhaimer/status/1684909995841003520?ref_src=twsrc%5Etfw">July 28, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script></center>

<center><sub>Look how well that aged, huh</sub></center>
