---
layout: post
title: "Idiosyncratic risk does not affect prices"
date: 2026-03-11
description: "Why Idiosyncratic Risk Does Not Affect Asset Prices"
img_url: assets/img/post-asset-1/img6.jpg
tags : [Generative AI in Asset Management]
---
![jpg](assets/img/post-asset-1/img6.jpg)

# Why Idiosyncratic Risk Does Not Affect Asset Prices

In financial economics, not all types of risk influence the price of an asset. A key distinction exists between **systematic risk** and **idiosyncratic risk**. Understanding this difference helps explain why some risky assets earn higher returns while others do not.

## The Core Idea

Asset prices are determined by how their payoffs interact with the **stochastic discount factor**, often denoted as $m$.  

Only the portion of an asset’s payoff that is **correlated with the discount factor** affects its price and expected return.

In contrast, **idiosyncratic risk**—risk that is uncorrelated with $m$—does **not** influence asset prices.

## Pricing with the Discount Factor

In asset pricing theory, the price of an asset with payoff $x$ is given by:

$$
p = E(mx)
$$

where:

- $p$ = asset price  
- $x$ = payoff  
- $m$ = stochastic discount factor  
- $E(\cdot)$ = expectation operator  

This equation means that the price depends on the **expected product of the payoff and the discount factor**.

## When Idiosyncratic Risk Exists

Suppose the payoff $x$ is **uncorrelated** with the discount factor $m$:

$$
\text{cov}(m, x) = 0
$$

In this case, the pricing formula simplifies to:

$$
p = \frac{E(x)}{R_f}
$$

where $R_f$ is the **risk-free return**.

This result implies something surprising:

- Even if the payoff $x$ is **highly volatile**
- Even if investors are **highly risk-averse**

…the asset still earns an **expected return equal to the risk-free rate**.

### Why?

Because holding a small amount of such an asset does **not meaningfully change the risk of an investor’s overall consumption**. Since it does not affect consumption risk, markets do not demand extra compensation for it.

## Decomposing Payoffs

To understand this more clearly, we can decompose any payoff $x$ into two components:

$$
x = \text{proj}(x|m) + \varepsilon
$$

where:

- $\text{proj}(x|m)$ = the part of $x$ **correlated with $m$**  
- $\varepsilon$ = the **idiosyncratic component**, uncorrelated with $m$

The projection is defined as:

$$
\text{proj}(x|m) = \frac{E(mx)}{E(m^2)} m
$$

This expression comes from **linear regression without a constant**.

## Orthogonality of Idiosyncratic Risk

The regression residual $\varepsilon$ satisfies:

$$
E(m\varepsilon) = 0
$$

This means the idiosyncratic component has **zero covariance with the discount factor**, confirming that it carries **no price** in financial markets.

As a result:

$$
p(x) = p(\text{proj}(x|m))
$$

In other words, **the price of the asset depends only on the systematic component of its payoff**.

## Systematic vs. Idiosyncratic Risk

We can summarize the difference as follows:

| Type of Risk | Correlation with Discount Factor | Affects Price? |
|---|---|---|
| Systematic Risk | Yes | Yes |
| Idiosyncratic Risk | No | No |

Only **systematic risk**—risk that moves with the overall economy or consumption—earns a **risk premium**.

## A Note on Terminology

The terms **systematic** and **idiosyncratic** can mean slightly different things in different asset pricing models.

For example, in the **Arbitrage Pricing Theory (APT)** framework:

- Risk is decomposed into **factor exposures**
- “Idiosyncratic” risk refers to the portion **uncorrelated with all factors and other assets**

In contrast, in the **stochastic discount factor framework**, idiosyncratic risk simply means **uncorrelated with the discount factor $m$**.

## Key Takeaway

The fundamental insight is:

> **Markets only reward risk that affects overall economic consumption.**

If a risk is purely individual and does not influence aggregate consumption—no matter how volatile—it **does not earn a risk premium**.

This is why **diversification works**: by combining many assets, investors can eliminate idiosyncratic risk and focus only on the systematic risks that truly matter for pricing.

---

## Python Implementation of the Equation

### Mathematical Formulation

Consider the inequality:

$$
\left( \sum_{k=1}^n a_k b_k \right)^2
\le
\left( \sum_{k=1}^n a_k^2 \right)
\left( \sum_{k=1}^n b_k^2 \right)
$$

This is known as the **Cauchy–Schwarz inequality**.  
It states that the square of the dot product of two vectors is always less than or equal to the product of the sums of their squared components.

In simpler terms, if we have two vectors:

- $a = (a_1, a_2, ..., a_n)$  
- $b = (b_1, b_2, ..., b_n)$  

then their relationship must satisfy the inequality above.

---

## Python Implementation

Below is a simple Python implementation that verifies the inequality for two vectors.

```python
import numpy as np

def verify_cauchy_schwarz(a, b):
    a = np.array(a)
    b = np.array(b)

    left_side = (np.dot(a, b)) ** 2
    right_side = np.dot(a, a) * np.dot(b, b)

    return left_side <= right_side, left_side, right_side


# Example vectors
a = [1, 2, 3]
b = [4, 5, 6]

result, left, right = verify_cauchy_schwarz(a, b)

print("Left side (dot product squared):", left)
print("Right side (product of squared sums):", right)
print("Inequality satisfied:", result)
````

---

## Explanation

The Python function performs the following steps:

1. Converts the input lists into NumPy arrays.
2. Computes the **dot product** $a \cdot b$.
3. Squares the result to compute the left-hand side:

$$
(a \cdot b)^2
$$

4. Computes the right-hand side:

$$
(a \cdot a)(b \cdot b)
$$

5. Checks whether the inequality holds.

Because the **Cauchy–Schwarz inequality is mathematically guaranteed**, the function should always return `True` for real-valued vectors.

---
# How Generative AI Can Enhance the Understanding of Idiosyncratic vs Systematic Risk

Modern **Generative AI (GenAI)** systems can significantly extend how we analyze, interpret, and apply financial theories such as the distinction between **systematic risk** and **idiosyncratic risk**. By combining large-scale data processing, probabilistic modeling, and natural language reasoning, GenAI can help investors, researchers, and financial institutions better estimate the components of risk embedded in asset payoffs.

This article explores how Generative AI can enhance the core asset pricing concept that **only systematic risk affects prices**, while **idiosyncratic risk does not generate a risk premium**.

---

# 1. Automated Decomposition of Risk

In theory, any asset payoff $x$ can be decomposed into two parts:

$$
x = \text{proj}(x|m) + \varepsilon
$$

where

- $\text{proj}(x|m)$ = systematic component correlated with the stochastic discount factor $m$
- $\varepsilon$ = idiosyncratic component uncorrelated with $m$

The projection is given by

$$
\text{proj}(x|m) = \frac{E(mx)}{E(m^2)} m
$$

Generative AI can automate this decomposition using **machine learning regression models** that estimate the relationship between asset payoffs and macroeconomic factors approximating the discount factor.

### Example Applications

GenAI systems can:

- Identify hidden macroeconomic drivers of $m$
- Estimate systematic exposure of thousands of assets simultaneously
- Automatically separate systematic vs residual risk

This enables real-time **risk decomposition across large portfolios**.

---

# 2. Learning the Stochastic Discount Factor with AI

Traditional finance assumes the stochastic discount factor $m$ is known or approximated using consumption models. In practice, estimating $m$ is difficult.

Generative AI can learn an approximation of $m$ directly from data.

The fundamental pricing equation is:

$$
p = E(mx)
$$

AI models such as **deep neural networks** can learn functions that approximate $m$ by minimizing pricing errors across assets.

Example objective:

$$
\min_{m_\theta} \sum_i (p_i - E[m_\theta x_i])^2
$$

where

- $m_\theta$ = AI-parameterized discount factor
- $x_i$ = payoff of asset $i$
- $p_i$ = observed price

This approach allows AI to discover **nonlinear risk factors** that traditional models miss.

---

# 3. Generative Scenario Simulation

Generative AI models such as **diffusion models, VAEs, or generative transformers** can simulate realistic market scenarios.

This allows researchers to test the theory:

> Idiosyncratic risk does not affect prices.

AI can generate synthetic payoff distributions $x$ and evaluate how pricing behaves when:

- $\text{cov}(m, x) = 0$
- $\text{cov}(m, x) \neq 0$

If

$$
\text{cov}(m, x) = 0
$$

then the expected return should equal the risk-free rate:

$$
E[R] = R_f
$$

Generative simulations can validate whether real markets follow this prediction.

---

# 4. Portfolio Construction with AI

Since idiosyncratic risk does not earn a premium, optimal portfolios should diversify it away.

Generative AI can construct portfolios that minimize residual risk:

$$
x = \beta m + \varepsilon
$$

AI can optimize portfolios by:

- minimizing $Var(\varepsilon)$
- maximizing systematic factor exposure

Optimization objective:

$$
\max_w E[R_p] - \lambda Var(\varepsilon_p)
$$

where

- $w$ = portfolio weights
- $\varepsilon_p$ = portfolio idiosyncratic risk

This results in **AI-optimized diversified portfolios**.

---

# 5. Natural Language Financial Intelligence

Generative AI can also analyze **unstructured information**, such as:

- earnings calls
- financial reports
- macroeconomic news
- geopolitical events

Using NLP, AI can determine whether new information affects:

1. **Systematic risk** (macroeconomic shocks)
2. **Idiosyncratic firm-specific risk**

For example:

- recession news → systematic risk
- CEO scandal → idiosyncratic risk

Only systematic signals should influence expected returns.

---

# 6. AI-Driven Asset Pricing Research

Generative AI can help researchers explore new asset pricing theories by automatically:

- generating alternative factor models
- testing covariance structures
- identifying hidden systematic drivers

For example, AI can search for new risk factors that explain:

$$
E(R_i) - R_f
$$

as a function of exposure to systematic components.

This extends classical frameworks such as:

- consumption CAPM
- multi-factor models
- arbitrage pricing theory

---

# Key Insight

The core asset pricing insight remains:

> Only risk that covaries with the stochastic discount factor affects asset prices.

Mathematically,

$$
p = E(mx)
$$

If

$$
E(m\varepsilon) = 0
$$

then the idiosyncratic component $\varepsilon$ has **zero price**.

Generative AI does not change this principle — but it dramatically improves our ability to:

- estimate systematic risk
- decompose asset payoffs
- simulate financial markets
- build diversified portfolios

---

# Thought

Financial theory explains **why idiosyncratic risk is not priced**.  

Generative AI provides powerful tools to **measure, simulate, and operationalize this insight at scale**, enabling more accurate risk models and smarter investment strategies.
---



# Using Generative AI to Analyze Systematic vs Idiosyncratic Risk with Hugging Face

Generative AI can help **extract financial signals from text data** and determine whether new information affects **systematic risk** (market-wide) or **idiosyncratic risk** (firm-specific).

Recall the theoretical decomposition:

$$
x = \text{proj}(x|m) + \varepsilon
$$

where:

- $\text{proj}(x|m)$ → systematic component correlated with the discount factor $m$
- $\varepsilon$ → idiosyncratic component uncorrelated with $m$

Only the systematic component affects asset pricing because:

$$
p = E(mx)
$$

and

$$
E(m\varepsilon) = 0
$$

Thus, idiosyncratic risk $\varepsilon$ has **zero price**.

Generative AI can help identify **which information affects systematic vs idiosyncratic risk** by embedding financial news and comparing it to macroeconomic signals.

---

# Conceptual Approach

We use **Hugging Face sentence-transformers** to:

1. Convert financial text into embeddings.
2. Compare similarity between:
   - Macro risk signals
   - Firm-specific events
3. Estimate whether news contributes to **systematic** or **idiosyncratic** risk.

This approach approximates the covariance idea:

$$
\text{cov}(m, x)
$$

If a news signal is **similar to macroeconomic signals**, it likely contributes to systematic risk.

---

# Python Implementation

```python
# Install dependencies (if needed)
# pip install sentence-transformers torch numpy

from sentence_transformers import SentenceTransformer, util
import numpy as np

# Load a Hugging Face embedding model
model = SentenceTransformer("sentence-transformers/all-MiniLM-L6-v2")

# ---------------------------------------------------
# Example macroeconomic signals (approximate SDF drivers)
# ---------------------------------------------------

macro_signals = [
    "Global recession fears increase",
    "Central bank raises interest rates",
    "Inflation rises across major economies",
    "Economic growth slows worldwide",
]

# ---------------------------------------------------
# Example firm-specific news
# ---------------------------------------------------

asset_news = [
    "Apple releases a new iPhone model",
    "Tesla factory temporarily shuts down",
    "Global interest rate hikes impact tech stocks",
    "Company CEO resigns after controversy"
]

# Generate embeddings
macro_embeddings = model.encode(macro_signals, convert_to_tensor=True)
news_embeddings = model.encode(asset_news, convert_to_tensor=True)

# ---------------------------------------------------
# Compute similarity between asset news and macro signals
# ---------------------------------------------------

similarity_matrix = util.cos_sim(news_embeddings, macro_embeddings)

# ---------------------------------------------------
# Interpret similarity as systematic exposure
# ---------------------------------------------------

systematic_scores = similarity_matrix.mean(dim=1).cpu().numpy()

# Print results
for news, score in zip(asset_news, systematic_scores):

    if score > 0.35:
        risk_type = "Systematic Risk (correlated with macro factors)"
    else:
        risk_type = "Idiosyncratic Risk (firm-specific)"

    print(f"News: {news}")
    print(f"Systematic Score: {score:.3f}")
    print(f"Classification: {risk_type}")
    print("-" * 60)
````

---

# How This Connects to the Theory

Financial theory states that **only systematic risk matters for pricing**.

If

$$
\text{cov}(m, x) \neq 0
$$

then the asset earns a **risk premium**.

If

$$
\text{cov}(m, x) = 0
$$

then

$$
E[R] = R_f
$$

The AI model approximates this concept by detecting whether **news events align with macroeconomic risk drivers**.

High similarity → potential systematic risk.
Low similarity → likely idiosyncratic risk.

---

# Extending the Model

This prototype can be expanded by:

### 1. Learning the Discount Factor

Train a neural network $m_\theta$ that minimizes pricing error:

$$
\min_\theta \sum_i (p_i - E[m_\theta x_i])^2
$$

### 2. Multi-Factor Risk Detection

Use embeddings to discover latent risk factors similar to **Arbitrage Pricing Theory (APT)**.

### 3. Portfolio Construction

Use embeddings to minimize portfolio idiosyncratic risk:

$$
x = \beta m + \varepsilon
$$

and optimize weights to reduce $Var(\varepsilon)$.

---

# Key Insight

Generative AI enables **large-scale detection of systematic risk signals** from unstructured data such as:

* financial news
* earnings calls
* macroeconomic reports
* social sentiment

This enhances classical asset pricing theory by making the decomposition

$$
x = \text{proj}(x|m) + \varepsilon
$$

**computationally tractable using modern AI tools.**

---
