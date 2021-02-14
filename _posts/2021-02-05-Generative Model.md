---
layout: post
use_math: true
---

## Focused on trend and methodology

> What I cannot create, I do not understand.
>
> by Richard Feynman (1918-1988)

* What is the Generative Model ?
* GAN in what category in Generative model?

# Learning a Generative Model
* Suppose we are given images of dogs.
* We want to learn a probability distribution $p(x)$ such that
    * **Generation**: If we sample $x_{new}\sim p(x), x_{new}$ should look like a dog (sampling).
    * **Density estimation**: $p(x)$ should be high if $x$ looks like a dog, and low otherwise(anomaly detection).
        * Also known as, explicit models.
    * **Unsupervised representation learning**: We should be able to learn what these images have in common, e.g., ears, tall, etc (feature learning)
    * Then, how can we represent $p(x)$? 

If we have values that are finite set, and are in our interest,

# Basic Discrete Distributions
* **Bernoulli distribution**:(biased) coin flip
    * $D=\\{Heads,Tails\\}$
    * Specify $P(X = Heads) = p$. Then $P(X=Tails) = 1 - p$.
    * Write: $X \\sim Ber(p)$.
* **Categorical distribution**:(biased) m-sided dice
    * $D = \\{1,\cdots,m\\}$
    * Specify $P(Y = i)=p_i$, such that $\sum^m_{i=1}p_i=1$.
    * Write: $Y\\sim Cat(p_1,\cdots,p_m)$

## Example
* Modeling an RGB joint distribution ( of a single pixel)
    * $(r, g, b) \\sim p(R, G, B)$
    * Number of cases?

        256 x 256 x 256
    * How many parameters do we need to specify?

        255 x 255 x 255

## Example (simplified)
* Suppose we have $X_1,\dots,X_n$ of $n$ binary pixels (a binary image).
* How many possible states?
    $2\times2\times\cdots\times2 = 2^n$
* Sampling from $p(x_1,\dots,x_n)$ generates an image.
* How many parameters to specify $p(x_1,\dots,x_n)$?

# Structure Through Independence
* What if $X_1,\dots,X_n$ are independent, then

    $p(x_1,\dots,x_n)=p(x_1)p(x_2)\cdots p(x_n)$
* How many possible states?

    $2^n$
* How many parameters to specify $p(x_1,\dots,x_n)$?

    $n$
* $2^n$ entries can be described by just n numbers! But this independence assumption is too strong to model useful distributions.

# Conditional Independence
* Three important rules
    * **Chaing rule**:

        $p(x_1,\dots,x_n)=p(x_1)p(x_2\|x_1)p(x_3\|x_1,x_2)\cdots p(x_n\|x_1,\cdots,x_{n-1})$
    * **Bayes' rule**:

        $p(x\|y) = \frac{p(x,y)}{p(y)}=\frac{p(y\|x)p(x)}{p(y)}$
    * **Conditional Independence**:

        If $x\bot y\|z$, then $p(x\|y,z)=p(x\|z)$

* Using the chain rule,

    $p(x_1,\dots,x_n)=p(x_1)p(x_2\|x_1)p(x_3\|x_1,x_2)\cdots p(x_n\|x_1,\cdots,x_{n-1})$
* How many parameters?

    * $p(x_1)$: 1 parameter
    * $p(x_2\|x_1)$: 2 parameters (one per $p(x_2\|x_1=0)$ and one per $p(x_2\|x_1=1)$)
    * $p(x_3\|x_1,x_2)$: 4 parameters
    * Hence, $1+2+2^2+\dots+2^{n-1}=2^n-1$, which is the same as before.
* Now, suppose $X_{i+1}\bot X_i,\dots,X_{i-1}\|X_i$(Markov assumption), then

    $p(x_1,\dots,x_n)=p(x_1)p(x_2\|x_1)p(x_3\|x_2)\cdots p(x_n\|x_{n-1})$
* How many parameters?

    $2n-1$
* Hence, by leveraging the Markov assumption, we get exponential reduction on the number of parameters.
* **Auto-regressive models** leverage this conditional independency.