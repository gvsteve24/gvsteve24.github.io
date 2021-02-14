---
layout: post
use_math: true
---
# Latent Variable Models
#### D.Kingma, "Variational Inference and Deep Learning: A New Synthesis," Ph.D. Thesis

# Question
### Is an autoencoder a generative model?

- Many people knows variational autoencoder is a generative model. So is autoencoder.
- However, it's not true.

# Variational Auto-encoder

* Variational Inference (VI)
    * The goal of VI is to optimize the **variational distribution** that best matches the **posterior distribution**.
        * **Posterior distribution**: $p_\theta(z\|x)$
        * **Variational distribution**: $q_{\phi}(z\|x)$
    * In particular, we want to find the **variational distribution** that minimizes the KL divergence between the true posterior.

* But how?

    ![variational-autoencoder](../images/VarAutoEncoder.png)

* **ELBO** can further be decomposed into

    ![ELBO-Incresement](../images/ELBO.png)

# Various GAN
- **DCGAN**
- **Info-GAN**
- **Text2Image**
- **Puzzle-GAN**
- **CycleGAN**
- **Star-GAN**
- **Progressive-GAN** 