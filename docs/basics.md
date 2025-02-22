---
layout: default
title: Basics
nav_order: 2
permalink: docs/basics
---

## Basics Review 

Before jumping into any actual content, we have to be familiar with the following aspects: 
- Rates Conversion
- Fundamental Theorem of Asset Pricing

Each aspect will be crucial for us to set up a universe with stable assumptions to solve differential equations and derive any analytical formulas. 

From my understanding, rates conversion is needed when you want a pricing formula with a rate function. Fundamental Theorem is definitely used to ensure arbitrage free so we can solve the functions by change of risk-neutral measure. Ito's formulas are the foundations for us to solve any differentials. 

### Rates Conversion 


Zero Coupon Bond Price

$$
P(t, T) = exp(R(t, T) \cdot (T-t))
$$

ZCB YTM/Spot Rate

$$
R(t, T) = \frac{-log P(t, T)}{T-t} = \frac{1}{T-t} \int_{t}^{T} f(t, u)du
$$

Short Rate

$$
\begin{align*}
    r(t) &= \lim_{T \to t}R(t, T) = \lim_{T \to t} f(t, T)\\
    dC(t) &= r(t)C(t)dt\\
    C(T) &= C(0)e^{\int_{0}^{t} r(u)du}
\end{align*}
$$

Forward Rate

$$
F(t, T, S) = \frac{log (\frac{P(t, T)}{P(t, S)})}{S-T}
$$

Instantaneous Forward Rate

$$
f(t, T) = \lim_{S \to T} F(t, T, S) = -\frac{d}{dT}logP(t, T) = -\frac{1}{P(t, T)}\frac{dP(t, T)}{dT} = \frac{d}{dT}(T-t)R(t, T) = R(t, T)+(T-t) \frac{dR(t, T)}{dT}
$$

Par Yield

$$P_n(t)$$ is n-period Coupon Bond

$$
P_n(t) = 100 = p(t, t+n) \sum_{i=1}^{n} P(t, t+i) +100 P(t, t+n)
$$ 

$$
p(t, t+n) \text{(Par Yield)} = 100 \frac{1-P(t, t+n)} {\sum_{i=1}^{n} P(t, t+i)} \text{(for bootstrapping)}
$$

LIBOR/SOFR Rate

For tenor $$\tau$$, 

$$
1+\tau \cdot L(t, t+\tau)= \frac{1}{P(t, t+\tau)} = e^{R(t, t+\tau)}
$$


Swap Rate

$$
\begin{tikzpicture}
  \draw [|-|] [thick] (0,0) node[below] {$t$} -- (2,0) node[below] {$t+1$}
  -- (2,0) -- (4,0)   node[below] {$t+2$}
  -- (4,0) -- (10,0) node[midway, below] {$\ldots$} node[below] {$t+n$};
  \coordinate[label=center:$\text{Pay fix rate S(t, t+n)}$] (A) at (1.5,0.5);
  \coordinate[label=left:$\text{Receive float rate L(t+i-1, t+i)}$] (A) at (4.5,-0.75);
\end{tikzpicture}
$$


### Fundamental Theorem of Asset Pricing 

1. Arbitrage Free $$\leftrightarrow$$ There exists an equivalent local Martingale/risk-neutral measure

2. Complete Market $$\leftrightarrow$$ This equivalent local Martingale/risk-neutral measure is unique

Get familiar with the change of numeraire as it is the key to change the PDE from probability measure to risk-neutral measure to achieve the Martingale form where we can solve for the analytical formula for calibration. This is not only useful for the valuation of Interest Rate, but also for Fixed Income and many other asset classes in general. 

