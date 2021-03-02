---
layout: post
use_math: true
---
# Seq2Seq with attention 
# Encoder-decoder architecture 
# Attention mechanism

## Recall: Type of Model

* ### Words sequence in many to many model

## Seq2Seq Model
---
* ### it takes a sequence 
* note: encoder and decoder not having sharing parameters

* RNN in detail took LSTM model
* final word taken by encoder -> output hidden state vector -> decoder take it to process each words

* first token is sos token in decoder. From time steps.
* last token is eos token in decoder. til time step to terminate.

## Seq2seq model with attention
---
* RNN accumulate hidden state vector which fixed dimension hidden state vector is full of information with limited vector dimension
* LSTM resoved long term memory issue, but it still have some loss from the beginning of time . e.g. when "I go home" is being tranllateed, it's poss to loss "I " ( three was trial that reversed the order in times)
* If we use attention, each hidden state vector can delivered to decoder from each time step that is favorable to decoder process selected in favor

* sequence of Encoder RNN can be vector inner producted to the out hidden vector of decoder RNN.
* each attention distrivution can be assessed by applyin softmax function to attention score
* 가중평균 ed vector can bring out context vector from attention output.
* Concat between attention output(encoder hidden state vector) and decoder hidden state vector
* After first word anticipation from decoder, it passes hidden state to next decoder rnn (next time step)
* Attention module can be used with next decoder hiddenstate vector, which will be producete dinner with attention scores , which eventually put out 가중평균
* 어텐션 벡터 ,. weighted sum is 1 -> vector definition
* These step set will be repeated.
note : hiddenstate vector does two role (output word anticipation and selected weight proeces to score)
* backprop
    * bakcprop goes two way : attention output & decoder Rnn
    * decoder each time step has each input word / if previous expectation was wrong, inference word (first one) is passed to next timestep.
    * Replace next weird output with accurate input is called teacher forcing(feasible). 
    * non teacher forcing is close to real world. 
    * teacher forcing in the begging and change method as training model develops. 

# Different Attention Mechanisms
---
$$\textrm{score}(h_t, \bar{h}_s) = 
    \begin{cases}
        h_1^{\top}\bar{h}_s & \quad \textit{dot}\\
        h_1^{\top}\textrm{W}_{\alpha}\bar{h}_s &\quad \textit{general}\\
        v_{\alpha}^{\top}tanh(\textrm{W}_{\alpha}[h_t;\bar{h}_s])  & \quad \textit{concat}
    \end{cases}
$$
