---
layout: post
use_math: true
---
## Sequential Data
Sequence data shows contiguous data pattern such as sound, words in sentence, stock price.

## Autoregressive Models

* Input definition 
    - We need to set computationally tractable data amount.
    $x_{t-1}, \ldots, x_1$
* Estimation
    
    $P(x_t \mid x_{t-1}, \ldots, x_1)$
* Latent Autoregressive Model
    
    ![latent autoregressive models](https://d2l.ai/_images/sequence-model.svg)
    
    
    $\hat{x_t} = P(x_t \mid h_{t})$ 
    
    $h_t = g(h_{t-1}, x_{t-1})$

* Estimation (Entire sequence)

    $P(x_1, \ldots, x_T) = \prod_{t=1}^T P(x_t \mid x_{t-1}, \ldots, x_1).$

## Markov Models
When $x_{t-1}, x_{t-2}, \dots, x_{t-\tau}$ is the accurate approximation of $x_{t-1},\dots,x_1$, equation below describes Markov Models.

$P(x_1, \ldots, x_T) = \prod_{t=1}^T P(x_t \mid x_{t-1}) \text{ where } P(x_1 \mid x_0) = P(x_1).$

