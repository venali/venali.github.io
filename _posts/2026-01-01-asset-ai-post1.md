---
layout: post
title: "The Basic Pricing Equation"
date: 2026-01-01
description: "The Basic Pricing Equation, Explained Like You’re Not in a PhD Seminar“"
img_url: assets/img/post-asset-1/img1.jpg
tags : [Generative AI in Asset Management]
---
![jpg](assets/img/post-asset-1/img1.jpg)

# The Basic Pricing Equation, Explained Like You’re Not in a PhD Seminar

When people say “finance is about pricing risk,” it can sound abstract—until you see the one equation that quietly powers a huge chunk of modern asset pricing.

Here’s the idea in plain English:

> **An asset’s price today equals the expected value of its future payoff, discounted not just for time, but for how valuable that payoff is to you in the states of the world when it arrives.**

That’s the *consumption-based* view of pricing. Let’s unpack it.

***

## What exactly are we trying to price?

Suppose there’s an investment you can buy today at price **$$p_t$$**. Next period, it will pay you **$$x_{t+1}$$**.

*   For a **stock**, that payoff is usually:
    $$
    x_{t+1} = p_{t+1} + d_{t+1}
    $$
    (next period’s price plus dividend)

Crucially, **$$x_{t+1}$$** is **uncertain**. You don’t know the exact payoff, but you have beliefs (probabilities) about what could happen.

Also note: **payoff is not the same as return**. The payoff is the raw amount you receive in the future. Return adjusts for what you paid today (e.g., $$(x_{t+1}-p_t)/p_t$$). Here we’re pricing the payoff stream directly.

***

## Investors don’t “love returns”—they love consumption

The model starts with a simple but powerful assumption:

People ultimately care about **consumption**—what they get to eat, enjoy, and use—not “portfolio statistics” like mean and variance.

So we represent preferences with a utility function:

$$
U(c_t, c_{t+1}) = u(c_t) + \beta \, E_t[u(c_{t+1})]
$$

Where:

*   **$$c_t$$** = consumption today
*   **$$c_{t+1}$$** = consumption tomorrow (uncertain)
*   **$$u(\cdot)$$** = utility from consumption
*   **$$\beta$$** = subjective discount factor (how patient you are)
*   **$$E_t[\cdot]$$** = expectation based on what you know at time $$t$$

A popular choice for $$u(\cdot)$$ is **power utility**:

$$
u(c) = \frac{c^{1-\gamma}}{1-\gamma}
$$

*   **$$\gamma$$** controls curvature:
    *   Higher $$\gamma$$ → more risk aversion
    *   More curvature → you really dislike consumption swings
*   As $$\gamma \to 1$$, this approaches **log utility**: $$u(c)=\ln(c)$$

The key intuition:  
 **Utility rises with consumption** (more is better)  
 **Utility is concave** (each extra unit helps less than the previous one)

> “The last bite is never as satisfying as the first.”

That concavity is what makes people **risk averse**.

***

## The investor’s trade-off: give up some consumption now to get more later

Imagine you can buy **$$\xi$$** units of the asset.

*   If you buy more today, you spend more today:
    $$
    c_t = e_t - p_t \xi
    $$
*   But you get more payoff tomorrow:
    $$
    c_{t+1} = e_{t+1} + x_{t+1}\xi
    $$

Here **$$e_t$$** and **$$e_{t+1}$$** are your “baseline” resources (income/endowment) without the trade.

So the investor chooses $$\xi$$ to maximize expected utility.

***

## The “first-order condition”: the marginal cost must equal the marginal benefit

At the optimum, buying *one more unit* of the asset shouldn’t make you better or worse off. That gives the key condition:

$$
p_t u'(c_t) = E_t\left[\beta u'(c_{t+1}) x_{t+1}\right]
$$

Read it like this:

*   **Left side**: the utility *cost* of paying $$p_t$$ today
    *   Paying $$p_t$$ reduces consumption today
    *   The pain of that reduction is scaled by **marginal utility** $$u'(c_t)$$

*   **Right side**: the discounted expected utility *gain* from tomorrow’s payoff
    *   More payoff tomorrow means more consumption tomorrow
    *   The benefit depends on how valuable consumption is tomorrow, $$u'(c_{t+1})$$
    *   And we discount the future by $$\beta$$

Rearranging yields the “central” pricing formula:

$$
p_t = E_t\left[\beta \frac{u'(c_{t+1})}{u'(c_t)} x_{t+1}\right]
$$

This is the **basic pricing equation**.

***

## The starring character: the “stochastic discount factor”

That ugly-looking term

$$
\beta \frac{u'(c_{t+1})}{u'(c_t)}
$$

shows up everywhere in asset pricing. It’s so important it gets a name:

> **Stochastic Discount Factor (SDF)**, sometimes called the **pricing kernel**

Let:

$$
m_{t+1} = \beta \frac{u'(c_{t+1})}{u'(c_t)}
$$

Then the pricing equation becomes beautifully simple:

$$
p_t = E_t[m_{t+1} x_{t+1}]
$$

**Interpretation:**  
You don’t just discount cash flows by time. You discount them by **states of the world**.

***

## Why risk matters: $1 is not always worth $1

Here’s the punchline.

A payoff is more valuable when it arrives in “bad times”—when you’re poor, stressed, and consumption is low—because **marginal utility is high** then.

*   In recessions, extra consumption feels incredibly valuable.
*   In booms, extra consumption feels less valuable.

So assets that pay off in bad times are worth more today.  
Assets that pay off mainly in good times are worth less (you demand a “risk premium” to hold them).

That’s risk pricing in one sentence.

***

## What this equation does—and doesn’t—solve

This formula is **powerful**, but notice what’s on the right-hand side:

*   future payoff $$x_{t+1}$$ (uncertain)
*   future consumption $$c_{t+1}$$ (also uncertain)
*   current consumption $$c_t$$

Consumption is **endogenous**—it depends on the whole economy, income, and what assets exist.

So at this stage, we’ve related:

> **Price** to **payoffs** and **consumption dynamics**

To fully “solve the model,” you’d specify the rest of the environment (income process, available assets, equilibrium behavior). But even without fully solving it, the equation generates a lot of insight:

*   Why some risks are rewarded and others aren’t
*   Why “insurance-like” assets can have low expected returns
*   How preferences (risk aversion $$\gamma$$, patience $$\beta$$) shape prices

***

## Key takeaways (the blog-friendly version)

*   **Prices come from optimal behavior**, not magic.
*   The price today is an **expected discounted payoff**, but the discounting depends on **how painful or helpful** that payoff is when it arrives.
*   The core object is the **stochastic discount factor**:
    $$
    m_{t+1}=\beta \frac{u'(c_{t+1})}{u'(c_t)}
    $$
*   Assets that pay when you most need it (bad times) get **higher prices** and typically **lower average returns**.
*   Assets that pay mostly in good times are “less helpful” and must offer **higher expected returns** to be held.


***

Below is a **simple Python implementation** of the basic pricing equation:

$$
p_t \;=\; \mathbb{E}_t\left[\beta \frac{u'(c_{t+1})}{u'(c_t)}\, x_{t+1}\right]
\quad\text{where}\quad
u'(c)=c^{-\gamma}\;(\text{CRRA / power utility})
$$



## Minimal implementation (NumPy)

```python
import numpy as np

def marginal_utility(c, gamma):
    """
    CRRA marginal utility u'(c) for u(c) = c^(1-gamma)/(1-gamma).
    => u'(c) = c^(-gamma)
    (This also covers log utility when gamma=1: u'(c)=1/c.)
    """
    c = np.asarray(c, dtype=float)
    if np.any(c <= 0):
        raise ValueError("Consumption must be positive.")
    return c ** (-gamma)

def price_basic_equation(ct, ctp1, x_tp1, beta=0.99, gamma=2.0):
    """
    Implements: p_t = E[ beta * u'(c_{t+1})/u'(c_t) * x_{t+1} ].

    ct   : scalar (consumption today)
    ctp1 : array of possible consumption tomorrow across states/simulations
    x_tp1: array of payoffs across the same states/simulations
    """
    ct   = float(ct)
    ctp1 = np.asarray(ctp1, dtype=float)
    x_tp1 = np.asarray(x_tp1, dtype=float)

    m = beta * (marginal_utility(ctp1, gamma) / marginal_utility(ct, gamma))  # SDF
    p = np.mean(m * x_tp1)  # Monte Carlo / equally-likely states

    return p, m
```

***

## Example (Monte Carlo simulation)

```python
np.random.seed(0)
N = 200_000
beta  = 0.99
gamma = 2.0

ct = 1.0

# Simulate consumption growth shocks, then consumption tomorrow
g = np.random.normal(loc=0.02, scale=0.10, size=N)
ctp1 = ct * np.exp(g)

# Simulate a payoff x_{t+1} correlated with consumption growth
noise = np.random.normal(0, 0.05, size=N)
x_tp1 = 1.05 + 0.8 * g + noise

p_hat, m = price_basic_equation(ct, ctp1, x_tp1, beta=beta, gamma=gamma)
print("Estimated price p_t =", p_hat)
```

This prints an estimated price (from my run): **\~ 1.0185**.

***

## Discrete “states with probabilities” version 

If you have a small set of states with explicit probabilities $$\pi_i$$, use a weighted expectation:

```python
def price_with_probabilities(ct, ctp1, x_tp1, probs, beta=0.99, gamma=2.0):
    ct = float(ct)
    ctp1 = np.asarray(ctp1, dtype=float)
    x_tp1 = np.asarray(x_tp1, dtype=float)
    probs = np.asarray(probs, dtype=float)

    probs = probs / probs.sum()  # normalize just in case

    m = beta * (marginal_utility(ctp1, gamma) / marginal_utility(ct, gamma))
    p = np.sum(probs * m * x_tp1)
    return p, m
```

***


Generative AI can **enhance the consumption-based pricing equation** (and the intuition behind it) in ways that are practical for **learning, research, and implementation**—even though the core economics stays the same:

$$
p_t = \mathbb{E}_t\left[m_{t+1}x_{t+1}\right],\quad 
m_{t+1}=\beta\frac{u'(c_{t+1})}{u'(c_t)}
$$

Below are concrete, high-impact ways GenAI helps—without changing the model’s theory.

> **Quick disclaimer:** This is educational/analytical guidance, not investment advice.

***

## Make the equation *understandable* to more people (explainability at scale)

The pricing equation is simple to write but hard to internalize. GenAI shines at converting math into **multiple layers of explanation**:

*   **Plain-English translation:** “Price equals expected payoff, discounted more in states where extra consumption is less valuable.”
*   **Intuition bridges:** Tie $$u'(c)$$ to “how much you value an extra dollar when you’re already doing well vs. struggling.”
*   **Alternative framings:** Convert to the covariance form to highlight “priced risk”:
    $$
    p_t = \mathbb{E}[x_{t+1}]\,\mathbb{E}[m_{t+1}] + \text{Cov}(m_{t+1},x_{t+1})
    $$
*   **Audience-specific versions:** A CEO-friendly version vs. a quant-research version vs. a student-friendly version.

**Why it matters:** Most failures in applying asset-pricing concepts are *communication* failures—GenAI reduces friction.

***

## Turn the model into an interactive “sandbox” (learning by simulation)

The equation is easiest to grasp when you can *play with it*:

*   Generate **toy economies** (2-state, 3-state, recession/boom) and show how price changes when payoffs shift into “bad states.”
*   Run **Monte Carlo experiments** with different:
    *   risk aversion $$\gamma$$
    *   patience $$\beta$$
    *   correlation between payoff $$x_{t+1}$$ and consumption growth
*   Produce **interactive notebooks** (Jupyter) where sliders control parameters and plots update.

GenAI can generate:

*   notebook scaffolding
*   simulation code
*   visualization code
*   commentary explaining what changed and why

**Result:** You move from “I can recite the formula” to “I understand what drives prices.”

***

## Accelerate empirical implementation (estimation + diagnostics)

In real data, the challenge is not writing $$p_t = E[mx]$$. It’s estimating it.

GenAI helps you build and debug pipelines for:

### A) Constructing consumption measures

*   cleaning and aligning time series (frequency mismatch, seasonality, deflation)
*   handling missing values and outliers
*   consistent transformations (levels vs. growth, per capita, real terms)

### B) Estimating the SDF or implied moments

Common empirical routes include:

*   **GMM / Euler equation estimation**
*   calibrating $$\beta, \gamma$$
*   testing moment conditions $$E[mR]=1$$ with asset returns $$R$$

GenAI can:

*   draft GMM objective functions
*   generate sanity-check tests (e.g., “does $$E[mR_f]\approx 1$$ hold?”)
*   propose robustness checks (subsamples, alternative consumption proxies)

### C) Diagnostics & model risk checks

*   catch unit errors (nominal vs. real)
*   detect look-ahead bias
*   ensure stationarity assumptions
*   run sensitivity analysis (how stable are estimates to small spec changes?)

**Net effect:** Less time wrestling with plumbing; more time thinking about economics.

***

## Create “scenario narratives” that connect states of the world to payoffs

A big conceptual leap is: **risk is about *when* you get paid**, not just how much you get paid on average.

GenAI can help by generating consistent scenario narratives that map to:

*   low $$c_{t+1}$$ (“bad times”) → high $$u'(c_{t+1})$$ → higher $$m_{t+1}$$
*   high $$c_{t+1}$$ (“good times”) → low marginal utility → lower $$m_{t+1}$$

Examples GenAI can generate (for teaching, model communication, stress tests):

*   recession shocks, job loss probabilities, consumption drops
*   inflation/real-income squeezes
*   “insurance-like” vs “procyclical” asset cash flows

**Important:** These are narratives to *interpret* states—not substitutes for calibrated macro models.

***

## Improve documentation, reproducibility, and “model governance”

If you’re implementing this in a team setting, GenAI can generate:

*   **Clear documentation**: what each variable means, expected shapes, units
*   **Model cards**: assumptions, limitations, known failure modes
*   **Automated reports**: tables/plots summarizing estimates and stability checks
*   **Readable code comments** aligned with the economics

This is especially useful for:

*   handoffs between researchers and engineers
*   audit trails
*   ensuring the model is interpretable outside the quant team

***

## Bridge theory → modern ML without losing economics

A powerful use is **hybrid modeling**:

*   Keep the economic structure $$m_{t+1}$$ as the *pricing object*
*   Use ML/GenAI-inspired tools to model components or conditioning information, e.g.:
    *   nonlinear forecasting of consumption growth
    *   richer state variables (macro indicators)
    *   flexible approximation of $$E_t[\cdot]$$

The key is: **don’t replace the equation—enhance the conditional expectation and measurement.**

***

## Common pitfalls GenAI helps you avoid (but also can cause)

### Helps avoid:

*   algebra mistakes in derivations
*   incorrect transformations (log vs level consumption)
*   code bugs (broadcasting errors, misaligned arrays)
*   “explainability gaps” when presenting to stakeholders

### Can cause (must guard against):

*   hallucinated “facts” or wrong formulas
*   plausible-but-wrong code
*   overconfident interpretation of empirical results
*   privacy/compliance issues if sensitive data enters prompts

**Best practice:** Treat GenAI as a *copilot*, not an oracle—validate with tests, unit checks, and economic sanity checks.

***

# A simple, practical workflow (high leverage)

1.  **Explain:** Ask GenAI to restate the equation + intuition for your audience
2.  **Prototype:** Generate a notebook to simulate $$c_{t+1}$$, $$x_{t+1}$$, compute $$m_{t+1}$$, estimate $$p_t$$
3.  **Empirics:** Build a pipeline to clean real consumption + asset data
4.  **Estimate:** Implement Euler/GMM moment conditions and compare models
5.  **Report:** Auto-generate a short writeup with plots + sensitivity checks

***

Below is a **practical “Hugging Face (Transformers) implementation** of the basic pricing equation

$$
p_t = \mathbb{E}_t\left[\beta\frac{u'(c_{t+1})}{u'(c_t)}x_{t+1}\right]
\quad\text{with CRRA } u'(c)=c^{-\gamma}
$$

### How Hugging Face fits in (what we’re doing)

We’ll use a **probabilistic time-series Transformer** to learn the **conditional joint distribution** of next-period **consumption** $$c_{t+1}$$ and **payoff** $$x_{t+1}$$ given information at time $$t$$. Hugging Face’s `TimeSeriesTransformerForPrediction` is designed exactly for this: an **encoder-decoder** model that takes `past_values` as context and predicts `future_values`, and it is **probabilistic** (it learns a distribution you can sample from, not just a point forecast). [\[huggingface.co\]](https://huggingface.co/docs/transformers/v4.52.2/en/model_doc/time_series_transformer), [\[colab.rese...google.com\]](https://colab.research.google.com/github/huggingface/notebooks/blob/main/examples/time-series-transformers.ipynb)

Once we have many sampled scenarios $$(c_{t+1}^{(s)}, x_{t+1}^{(s)})$$, we compute the SDF in each scenario:

$$
m_{t+1}^{(s)}=\beta\left(\frac{c_{t+1}^{(s)}}{c_t}\right)^{-\gamma}
$$

and approximate the expectation with a Monte Carlo mean:

$$
p_t \approx \frac{1}{S}\sum_{s=1}^S m_{t+1}^{(s)}x_{t+1}^{(s)}.
$$

***

## Install (typical notebook setup)

The official HF time-series notebook uses **Transformers + Accelerate + Datasets + GluonTS** tooling for time features/windows. [\[colab.rese...google.com\]](https://colab.research.google.com/github/huggingface/notebooks/blob/main/examples/time-series-transformers.ipynb)

```bash
pip install -U transformers accelerate datasets gluonts torch
```

***

## End-to-end example (synthetic data → train → sample → price)

> This is intentionally “small & readable.” Replace the synthetic data section with your real $$c_t$$ and $$x_t$$ time series.

```python
import math
import numpy as np
import torch
from torch.utils.data import Dataset, DataLoader

from transformers import TimeSeriesTransformerConfig, TimeSeriesTransformerForPrediction


# -----------------------------
# A) Utility / pricing helpers
# -----------------------------
def sdf_crra(ct, ctp1, beta=0.99, gamma=2.0):
    """
    m_{t+1} = beta * u'(c_{t+1}) / u'(c_t)
            = beta * (c_{t+1}/c_t)^(-gamma)  for CRRA
    """
    return beta * (ctp1 / ct).pow(-gamma)

def price_from_samples(ct, ctp1_samples, x_samples, beta=0.99, gamma=2.0):
    """
    p_t ≈ mean_s [ m_{t+1}^s * x_{t+1}^s ]
    """
    m = sdf_crra(ct, ctp1_samples, beta=beta, gamma=gamma)
    return (m * x_samples).mean()


# -----------------------------
# B) Create synthetic joint data
#    (c_t and x_t correlated)
# -----------------------------
def make_synthetic_series(T=600, seed=0):
    rng = np.random.default_rng(seed)
    c = np.zeros(T, dtype=np.float32)
    x = np.zeros(T, dtype=np.float32)

    c[0] = 1.0
    x[0] = 1.0

    for t in range(1, T):
        # consumption growth shock
        g = rng.normal(loc=0.002, scale=0.03)        # ~ monthly-ish
        c[t] = c[t-1] * float(np.exp(g))

        # payoff correlated with the same shock + noise
        x[t] = 1.02 + 0.8 * g + rng.normal(0, 0.02)

    # Ensure positivity
    x = np.clip(x, 1e-3, None)
    return c, x


# -----------------------------
# C) Windowed Dataset
#    Multivariate target: [c, x]
# -----------------------------
class CXWindowDataset(Dataset):
    def __init__(self, c, x, context_length=64, prediction_length=1):
        self.context_length = context_length
        self.prediction_length = prediction_length

        values = np.stack([c, x], axis=-1)  # (T, 2)
        self.values = torch.tensor(values, dtype=torch.float32)

        # Simple "age" time feature (monotonic index) as positional encoding.
        # HF time-series models typically expect time features. 
        age = np.arange(len(c), dtype=np.float32) / len(c)
        self.time_feat = torch.tensor(age[:, None], dtype=torch.float32)  # (T, 1)

        # observed masks (no missing here)
        self.obs = torch.ones(len(c), 2, dtype=torch.float32)

        # Build valid window start indices
        self.starts = []
        T = len(c)
        Lp = context_length
        Lf = prediction_length
        for s in range(0, T - (Lp + Lf) + 1):
            self.starts.append(s)

    def __len__(self):
        return len(self.starts)

    def __getitem__(self, idx):
        s = self.starts[idx]
        Lp = self.context_length
        Lf = self.prediction_length

        past_values = self.values[s : s + Lp]                 # (Lp, 2)
        future_values = self.values[s + Lp : s + Lp + Lf]     # (Lf, 2)

        past_time_features = self.time_feat[s : s + Lp]       # (Lp, 1)
        future_time_features = self.time_feat[s + Lp : s + Lp + Lf]  # (Lf, 1)

        past_observed_mask = self.obs[s : s + Lp]             # (Lp, 2)
        future_observed_mask = self.obs[s + Lp : s + Lp + Lf] # (Lf, 2)

        return {
            "past_values": past_values,
            "future_values": future_values,
            "past_time_features": past_time_features,
            "future_time_features": future_time_features,
            "past_observed_mask": past_observed_mask,
            "future_observed_mask": future_observed_mask,
        }


def collate(batch):
    # Stack to (B, L, dim)
    out = {}
    for k in batch[0].keys():
        out[k] = torch.stack([b[k] for b in batch], dim=0)
    return out


# -----------------------------
# D) Define HF model
# -----------------------------
device = "cuda" if torch.cuda.is_available() else "cpu"

context_length = 64
prediction_length = 1

config = TimeSeriesTransformerConfig(
    prediction_length=prediction_length,
    context_length=context_length,
    input_size=2,              # multivariate target: [consumption, payoff]
    num_time_features=1,       # our "age" feature
    num_dynamic_real_features=0,
    num_static_categorical_features=0,
    num_static_real_features=0,
    # probabilistic output (default is student_t in HF docs) 
    distribution_output="student_t",
    loss="nll",
    d_model=64,
    encoder_layers=2,
    decoder_layers=2,
    encoder_attention_heads=4,
    decoder_attention_heads=4,
    num_parallel_samples=500,  # number of scenario samples at inference
)

model = TimeSeriesTransformerForPrediction(config).to(device)


# -----------------------------
# E) Train (tiny demo loop)
# -----------------------------
c, x = make_synthetic_series(T=700, seed=42)
ds = CXWindowDataset(c, x, context_length=context_length, prediction_length=prediction_length)
dl = DataLoader(ds, batch_size=32, shuffle=True, collate_fn=collate)

optimizer = torch.optim.AdamW(model.parameters(), lr=3e-4)

model.train()
for epoch in range(3):
    total = 0.0
    for batch in dl:
        batch = {k: v.to(device) for k, v in batch.items()}
        out = model(**batch)
        loss = out.loss
        optimizer.zero_grad()
        loss.backward()
        optimizer.step()
        total += loss.item()
    print(f"epoch {epoch+1} | loss {total/len(dl):.4f}")


# -----------------------------
# F) Inference: sample scenarios
#    and compute p_t
# -----------------------------
model.eval()

# Pick one "current time" window (last window in series)
t0 = len(c) - (context_length + prediction_length)
sample = ds[t0]
batch = {k: sample[k].unsqueeze(0).to(device) for k in sample}  # add batch dim

# current consumption c_t = last observed consumption in past window
ct = batch["past_values"][:, -1, 0]  # shape (1,)

with torch.no_grad():
    # Many HF time-series models can produce probabilistic samples via generate/autoregressive sampling. 
    # Depending on your transformers version, output structure may differ.
    gen = model.generate(
        past_values=batch["past_values"],
        past_time_features=batch["past_time_features"],
        past_observed_mask=batch["past_observed_mask"],
        future_time_features=batch["future_time_features"],
    )

# Most commonly you'll get something like:
# gen.sequences or gen (tensor) containing samples of shape (B, num_samples, prediction_length, input_size)
# We'll handle both.
samples = getattr(gen, "sequences", gen)

# Ensure tensor
if not torch.is_tensor(samples):
    samples = torch.tensor(samples)

# If shape is (B, num_samples, prediction_length, input_size), take t+1 and split:
ctp1_samples = samples[0, :, 0, 0].cpu()  # (num_samples,)
x_samples    = samples[0, :, 0, 1].cpu()  # (num_samples,)

p_hat = price_from_samples(ct.cpu().squeeze(0), ctp1_samples, x_samples, beta=0.99, gamma=2.0)
print("Estimated price p_t =", float(p_hat))
```

### Why this is a faithful “HF implementation” of the equation

*   HF TimeSeriesTransformer is **encoder-decoder**, consumes `past_values`/`past_time_features`, predicts `future_values`, and is **probabilistic** (learns a distribution to sample from). [\[huggingface.co\]](https://huggingface.co/docs/transformers/v4.52.2/en/model_doc/time_series_transformer), [\[colab.rese...google.com\]](https://colab.research.google.com/github/huggingface/notebooks/blob/main/examples/time-series-transformers.ipynb)
*   We use those samples as the “states of the world” in the expectation $$\mathbb{E}_t[\cdot]$$ and compute $$p_t$$ as a sample mean.

***

## Adapting to your real data (quick checklist)

### Data you need

*   A time series for **consumption** (or a proxy) $$c_t$$
*   A time series for **asset payoff** $$x_{t+1}$$ (e.g., price+dividend, or gross return times price)

### Practical modeling choices

*   **One-step** vs **multi-step** horizon: set `prediction_length=1` (one-step) or longer.
*   Multivariate: keep `input_size=2` and model $$[c, x]$$ jointly (so the model captures their dependence).
*   Time features: HF’s time-series transformer expects time features as “positional encodings” (month/day/age etc.). [\[huggingface.co\]](https://huggingface.co/docs/transformers/v4.52.2/en/model_doc/time_series_transformer), [\[colab.rese...google.com\]](https://colab.research.google.com/github/huggingface/notebooks/blob/main/examples/time-series-transformers.ipynb)
    *   In production, you’d usually use GluonTS time features (month-of-year, day-of-week, age), like the official notebook does. [\[colab.rese...google.com\]](https://colab.research.google.com/github/huggingface/notebooks/blob/main/examples/time-series-transformers.ipynb)

***
