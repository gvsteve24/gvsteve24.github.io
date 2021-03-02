---
layout: post
use_math: true
---
## Transformer: High-level view
---
* ### No more RNN or CNN modules





## RNN: Long-term dependency
---
* hidden state vector is being used to make output of each decoder
* e.g. the third time step home has information in that it gives assumption that repetitive path of hidden vector loses some information through.

## Bidirectional RNNs
---
* ### Forward RNN
* ### BAckward RNN (separate h from forward)
    * " I go home" 
        - after rnn passing go includes "I" (forward rnn)
        - after rnn passing go includes " home" (backward rnn)

## Transformer: Long-Term Dependency
---
* attention sets same input output vector
* decoder takes in the output hidden vector of encoding 
* Query vector : criteria from encoder input vector of inner product operand
* in sequence encoding , one value does three roles ( Queries, Kys, Values)
* Linear transforamtion matrix will be given to apply to three different roles
* Linear trnasformation matrix
* key vector and value vector will be same number of itself
* one query vector would have inner product with keys -> softmax(output) -> second query vector applied to second input of "go" 
* anotehr expampel
    - "Thinking Machines"

    - input low vector and
    - Value vector in weighted sum  -> h1 vector 

## Transformer: Scaled Dot-Product Attention
---
* ##### Inputs: a query *q* and a set of key-value (*k,v*) pairs to an output
* ##### Query, key, value and output is all vectors
* Output is weighted sum of values
* Weight of each value is computed by an inner product of query and corresponding key
* Queries and keys have dimensionality $d_k$, and dimensionality of value is $d_v$

    $A(q, K, V) = \sum_i \frac{\text{exp}(q\cdot k_i)}{\sum_j\text{exp}(q\cdot k_j)}$

* When we have multiple queries *q*, we can stack them in a matrix *Q*:

    $A(q, K, V) = \sum_i \frac{\text{exp}(q\cdot k_i)}{\sum_j\text{exp}(q\cdot k_j)}$
* Becomes:

    $A(Q, K, V) = \textit{softmax}({QK^T})V$
    
    $(\|Q\| \times d_k) \times (d_k \times \|K\|)\times (\|V\|\times d_v) = (\|Q\|\times d_v)$
 
* softmax is multiplied in row-wise

## Transformaer : 
* ### Query Key Value
* these are passed to softmax and then depended on dimension of query and key. so we have put denominator as $d_k$(demension)

* ### Problem
    * As $d_k$ gets large, the variance of q^Tk increases
    * Some values inside the softmax get large
    * The softmax gets very peaked
    * Hence, its gradient gets smaller

* variance and mean of $ax, by$ will be assumed that a, x and b,y are independent.
* e.g. when their varience, mean = (1, 0), we would know linear combination $\textrm{ax+by}$'s v and m are (2, 0)
* variance will be maintained 

* ### Solution
    * Scaled by the length of query / key vectors:
        
        $A(Q, K, V) = \textit{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V$


## Transformer: Multi-Head Attention
---
#### The input word vectors are the queries, keys and values
#### In other words, the word vectors themselves select each other
### Problem of single attention
* #### Only one way for words to interact with one another
### Solution
* #### Multi-head attention maps Q, K, V into the h number of lower-dimensional spaces via W matrices.
#### Then apply attention, then concatenate outputs and pipe through linear layer

* ### k, v, q will passed to $W_k, W_v, W_q$
* ### Encoding vector will be attained 

# Transformer: Layer Normalization
---
* #### Layer normalization changes input to have zero mean and unit variance, per layer and per training point (and adds two more parameters)
    * Batch Norm
    * Layer Norm
    * Instance Norm
    * Group Norm
    $\mu^l = \frac{1}{H}\sum_{i=1}^{H}a_i^l$

