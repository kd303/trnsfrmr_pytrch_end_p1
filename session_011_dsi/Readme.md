## Implementation of Transformer Memory as a Differentialble Search Index


Google research paper published on [arXiv:2202.06991v2 16 Feb 2022](https://arxiv.org/pdf/2202.06991.pdf)

# Key points to understand

Differentialble Search Index(DSI), a paradigm that learns a text-to-text model that maps string queries directly to releavent docids
  - It answers the queries directly using it parameters, simplifying a whole process (think of a traditional search process - retrieve and rank)

Key objectives:
1. How documents and their identifiers are represented, variation in training process and the interplay between models and corpus sizes


Key Learnings:
1. [Contrastive learning](https://towardsdatascience.com/understanding-contrastive-learning-d5b19fd96607) 
2. [Latent space](https://hackernoon.com/latent-space-visualization-deep-learning-bits-2-bd09a46920df)
3. [Manifold Learning - An approach to dimensionality reduction](https://scikit-learn.org/stable/modules/manifold.html) 
    a. PCA, LDA, Independent Component Analysis - linear projection of data - misses important **non-linear structure in data**
    b. Manifold is as an attempt to generalize linear frameworks like PCA {hint! : Isomaps - earth maps?}
4. 
