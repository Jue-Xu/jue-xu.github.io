---
layout: post
title: Review of "Partitions and the grand canonical ensemble"   
date: 2017-10-22
categories: blog
tags: [Review]
catalog: true
description: Latex
header-img: "img/semantic.jpg"
---

> [PDF version](https://github.com/JackXu1993/Paper_Ma/blob/master/review/review.pdf)

## A physical model for partitions
### Energy and the number to be partitioned

The model is the Grand Canonical Ensemble,
used to describe physical systems with a variable number of particles.
Each part in the partition is regarded as a particle in the model.
For each integer $k$, there is a separate species of particle of energy $k$.
The particles are emitted and absorbed like the photons in a cavity filled with thermal radiation.
The states of the entire system are labeled by the numbers $[m_1,m_2,m_3,\dots]$,
where $m_k$ is the number of particles of energy $k$.
So each state describes a partition with sum
\begin{equation}
    n = \sum_k k m_k.
    \label{eq: npartition}
\end{equation}

>
In the language and notation in physics, the number $n$ to be partitioned is the energy of a system $E$
\begin{equation}
    E = \sum_{i} n_i \varepsilon_i,
    \label{eq: mpartition}
\end{equation}
with $n_i$ is the particle number of energy level $l$ and
$\varepsilon_i$ is the energy of the $i$-th state.
For photons, its energy level can be viewed as consecutive positive integers
\begin{equation}
    \varepsilon_i = i ,\quad i=1,2,\dots,
\end{equation}
so the \cref{eq: mpartition} becomes
\begin{equation}
    E = \sum_{i} i\cdot n_i ,
    \label{eq: energy partition}
\end{equation}
which exactly equals \ref{eq: npartition}.


### Generating function and partition function
In the physical model, $n$ is the energy of the state.
The model is the thermal equilibrium with temperature $T$,
so the probability of the state $[m_k]$ is
\begin{equation}
    f(m_k) = Z^{-1} \prod_k \exp(-bkm_k),
\end{equation}
with
\begin{equation}
    Z = \sum_{m} \prod_{k} \exp(-bkm_k)
    = \prod_k (1-x^k)^{-1}
    = \sum_n p(n) x^n,
\end{equation}
and
\begin{equation}
    x = \exp(-b), \quad  b=T^{-1}, \quad
\end{equation}

>
Use the notation we familiar with in statistical mechanics,
the probability of certain configuration $[n_i]$ is
\begin{equation}
    P([n_i]) = \frac{\prod_l \exp(-\beta n_i \varepsilon_i)}{Z},
\end{equation}
with the canonical partition function $Z$
\begin{equation}
    \begin{aligned}
        Z
        &= \sum_{[n_i]} \prod_i \exp(-\beta n_i \varepsilon_i)\\
        &= \sum_{E} \Omega(E) \exp(-\beta E)\\
        &= \sum_{E} p(E) x^E,
    \end{aligned}
    \label{eq: def of partition function}
\end{equation}
with $x = e^{-\beta}$, $\beta = 1/T$ and the Boltzman constant $k_B = 1$.
Let me explain \cref{eq: def of partition function},
    the first line is the orginal definition of canonical partition function which means the sum over all possible configurations.
However, the sum over all possible configurations is hard to tackle with in mathematics because there is no trick.
So, we rearrange the method of sum by categorying all configurations with the same total energy $E$.
Then, the quantity $\Omega(E)$ in the second line is number of configurations with the same energy $E$
which is called microcanonical partition function.
Recall that microcanonical ensemble is a closed system with fixed particle number $N$ and fixed energy $E$.
Therefore, microcanonical partition function is the number of configurations with fixed total system energy $E$.
Recall \cref{eq: energy partition}, we can find the microcanonical partition $\Omega(E)$ is exactly the partition function $p(n)$ with $E=n$ for photons.
So, the canonical partition function is the generating function of partition function in number theory
\begin{equation}
        G(x)
        = (1+x+x^2\dots)
        \cdot (1+x^2+x^4\dots)\cdot
        (1+x^3+x^6\dots)\cdots(1+x^l+x^{2l}+\dots)\dots
\end{equation}
\begin{equation}
        G(x)
        = \prod_{i=1}^{\infty} \sum_{j=0} x^{i j}
        = \prod_{i=1}^{\infty} \frac{1}{1-x^i}
        = \sum_{E} p(E) x^E
\end{equation}
where $i$ is the energy of energy level $\varepsilon_i  =i$ for photons
and $j$ is the particle number on the energy level $\varepsilon_i$.
\textbf{Generating function is a method to simulate all possible configurations by producting infinite geometric series.
The process that one item $x^{mn}$ in a series times the other items $x^{pq}$ in each other series will get a item $x^E=x^{mn+\dots +pq}$ represents one configuration with energy $E$.
At last, the expansion coefficients of the final polynominal is the number of configurations with the same order $x^E$, exactly the partition function $p(E)$.}
--
The name "partition function" is given by physicists to the sum $Z$
and mathematicians to the coefficients $p(n)$.
For mathematicians, $p(n)$ is the number of partitions of $n$.
For physicists, the mean value of the energy of the ensemble is
\begin{equation}
    E = -Z^{-1} dZ/db = \sum_{k} k (\exp(bk)-1)^{-1},
\end{equation}
the free energy is
\begin{equation}
    F = -b^{-1} \log Z = b^{-1} = b^{-1} \sum_{k} \log(1-\exp(-bk)),
\end{equation}
and the entropy is
\begin{equation}
    S = b(E-F).
\end{equation}

### Grand canonical ensemble
In the grand cononical ensemble, the mean number of parts of size $k$ is
\begin{equation}
    a(k) = [\exp(bk) - 1]^{-1}
\end{equation}

The mean number of parts of size $k$ actually means the distribution of particle numbers at certain energy level $\varepsilon_i$.
For photons, they obey Bose-Einstein distribution
\begin{equation}
        \bar{n}_i(\varepsilon_i)
        = \frac{g_i}{e^{(\varepsilon_i-\mu)/kT}-1}
        = \frac{1}{e^{(\varepsilon_i-\mu)/kT}-1}
\end{equation}
where $g_i$ is the degeneracy of energy level $\varepsilon_i$ that can be considered as 1 in this case
and $\mu$ is chemical potential.
