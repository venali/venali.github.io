---
layout: post
title: "Risk free rate"
date: 2026-01-04
description: "One Equation to Price Them All: A Plain-English Guide to Modern Asset Pricing"
img_url: assets/img/post-asset-1/img3.jpg
tags : [Generative AI in Asset Management]
---
![jpg](assets/img/post-asset-1/img3.jpg)

```md
# Understanding the Risk-Free Rate in Plain English

The **risk-free rate** is one of the most important numbers in finance. It represents the return you can earn with certainty — no risk, no surprises.

In modern asset pricing, the risk-free rate is tightly connected to how people value consumption today versus tomorrow.

At the core is a simple identity:

\[
R_f = \frac{1}{E(m)}
\]

Here:

- \( R_f \) = risk-free gross return  
- \( m \) = stochastic discount factor (how much we value future payoffs today)  
- \( E(m) \) = expected value of that discount factor  

If the expected discount factor is high (people value the future a lot), the risk-free rate is low.  
If people value the future less, the risk-free rate must be high.

---

# Step 1: The Simple (No Uncertainty) Case

Assume there is **no uncertainty** and people have *power utility*:

\[
u'(c) = c^{-\gamma}
\]

In that case, the risk-free rate becomes:

\[
R_f = \frac{1}{\beta} \left(\frac{c_{t+1}}{c_t}\right)^\gamma
\]

Where:

- \( \beta \) = patience parameter (how much we value the future)  
- \( \gamma \) = curvature of utility  
- \( c_{t+1}/c_t \) = consumption growth  

From this formula, three powerful insights emerge.

---

## 1️⃣ Impatience Raises Interest Rates

If people are impatient (low \( \beta \)), they prefer consuming today.

To convince them to save instead of consume, the economy must offer a **high interest rate**.

👉 More impatience → higher real interest rates.

---

## 2️⃣ High Expected Growth Raises Interest Rates

When consumption is expected to grow quickly:

- People are already going to be richer tomorrow.
- To shift consumption from today into tomorrow, the interest rate must be high.

👉 High expected consumption growth → high interest rates.

You can also read this backward:

High interest rates encourage saving today and more consumption tomorrow — which creates higher consumption growth.

---

## 3️⃣ Curvature (γ) Makes Rates More Sensitive

The parameter \( \gamma \) measures:

- Risk aversion  
- Aversion to uneven consumption over time  
- Strength of precautionary saving  

When \( \gamma \) is large:

- People dislike fluctuations in consumption.
- They resist shifting consumption across time.
- It takes a **larger interest rate change** to alter their behavior.

👉 Higher \( \gamma \) → interest rates react more strongly to growth changes.

---

# Step 2: Introducing Uncertainty

Now suppose consumption growth is uncertain and follows a **lognormal distribution**.

Then the log risk-free rate becomes:

\[
r_t^f = \delta + \gamma E_t \Delta \ln c_{t+1}
- \frac{\gamma^2}{2} \sigma_t^2(\Delta \ln c_{t+1})
\]

Where:

- \( r_t^f = \ln R_t^f \)  
- \( \delta \) = impatience (since \( \beta = e^{-\delta} \))  
- \( E_t \Delta \ln c_{t+1} \) = expected consumption growth  
- \( \sigma^2 \) = variance of consumption growth  

This adds something new.

---

# The New Ingredient: Precautionary Saving

The last term:

\[
- \frac{\gamma^2}{2} \sigma^2
\]

captures **precautionary savings**.

When consumption is volatile:

- People fear bad states more than they enjoy good states.
- They want to save more as protection.
- More saving pushes interest rates **down**.

👉 More uncertainty → lower risk-free rates.

---

# What Drives Real Interest Rates?

Putting everything together:

Real interest rates are high when:

- People are impatient (high \( \delta \))
- Expected consumption growth is high
- Risk (volatility) is low

Real interest rates are low when:

- People are patient
- Expected growth is weak
- Consumption is volatile (strong precautionary saving)

---

# One Utility Parameter Controls Three Things

With power utility, the same parameter \( \gamma \) controls:

1. **Intertemporal substitution**  
   (willingness to shift consumption over time)

2. **Risk aversion**  
   (dislike of uncertainty across states)

3. **Precautionary saving**  
   (extra saving due to uncertainty)

This tight connection is specific to the power utility assumption.  
More advanced models separate these effects.

---

# The Big Picture

The risk-free rate is not just a financial number.

It reflects:

- How impatient people are  
- How fast they expect the economy to grow  
- How risky that growth is  
- How much they dislike consumption fluctuations  

In short:

> Interest rates are a mirror of society’s preferences about time, growth, and risk.

And that’s why such a simple formula —  
\[
R_f = \frac{1}{E(m)}
\]
— carries so much economic meaning.
```
