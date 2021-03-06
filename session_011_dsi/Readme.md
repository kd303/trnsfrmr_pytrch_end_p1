# Transformer Memory as a Differentialble Search Index

Google research paper published on [arXiv:2202.06991v2 16 Feb 2022](https://arxiv.org/pdf/2202.06991.pdf), all content, images credits to quoted paper, unless mentioned otherwise.

## Basic Understanding

Fundamental difference in traditional search approach is to encode-retrieve & rank as opposed this paper is mapping query to the doc, so basically encode and rank, thus removing the need for retrieval mechanisms like MIPS

![image](https://user-images.githubusercontent.com/16409185/156111474-25fe0258-f344-47ab-bfdb-ea1646e73057.png)

## DSI Architecture

From the Paper, Page 2, _Paragraph on indexing_: 

> In DSI, the **index is stored in the model parameters**, and _**indexing is simply another kind of model training.**_ Figure 1
> suggests one approach to indexing a corpus: namely, to train on:
>
>  1. examples (d<sub>j</sub> , j) that pair document **d<sub>j</sub>** with its **docid j**, in addition to 
>  2. examples (q, j) that pair a query **q** with a relevant **docid j**. 

> In this setup the examples of type (1) are “indexing” examples.

> We also explore a number of alternative multi-task optimization and curriculum learning schemes for combining these types of examples.

Section **3.3 Training and Optimization**

> We explored two main strategies for training DSI models
> 1.  is to first train a model to perform indexing (memorization), followed by a fine-tuning stage where the trained model is used to map queries to docids (e.g., retrieval).
> 2.  to train them together in a multi-task setup. To this end, we frame co-training tasks in similar fashion to T5-style co-training (e.g., using task prompts to differentiate them)


## Tasks for information retrival

This is something which we will concentrate on, for solving the code. How various tasks are used in Machine Learning are equivalent to IR - information retrieval

![image](https://user-images.githubusercontent.com/16409185/156112405-751de3ad-9645-4956-8025-c7fec1b6b064.png)

So following are the main tasks for which we need to solve for:
## Tasks
0. [Understanding Data](/session_011_dsi/nq_datasets.md)
1. [Doc (d) and Query (q) represetnation](/session_011_dsi/doc_representation.md)
2. [Docid(j) representation](/session_011_dsi/docid_representation.md)
3. [Train the model (mapping document d to docid j)](/session_011_dsi/T5_training.md)
4. Infer the trained model to find argmax Pr(j|q) - basically query q to docid j
5. Optionally apply ranking - using beam search

### Expected outcome

A **unified model** consisting following:

**indexing** : A DSI model should learn the associate the content of each document d with its corrospinding docid j - straight-forward seq2seq approach, take document token   as inputs and generate identifiers as output (task 3)

**Retrieval** : given a query, a DSI model should return a ranked list of candidate docids, achieved via [Autoregressive generation](https://www.georgeho.org/deep-autoregressive-models/)


## Limitations

- It is not clear how the incremental update will work - as in the model updates, one approach is as suggested in the [paper](https://proceedings.mlr.press/v119/sun20b.html)
- It is not clear how well the model will scale or large corpora, as current one is tested for 320k sort of documents (also makes a good case for limited closed book searches?)
- 
### Side Notes

Differentialble Search Index(DSI), a paradigm that learns a text-to-text model that maps string queries directly to releavent docids
  - It answers the queries directly using it parameters, simplifying a whole process (think of a traditional search process - retrieve and rank)

Key objectives:
1. How documents and their identifiers are represented, variation in training process and the interplay between models and corpus sizes


Key Learnings:
1. [Contrastive learning](https://towardsdatascience.com/understanding-contrastive-learning-d5b19fd96607) 
2. [Latent space](https://hackernoon.com/latent-space-visualization-deep-learning-bits-2-bd09a46920df)
3. [Manifold Learning - An approach to dimensionality reduction](https://scikit-learn.org/stable/modules/manifold.html) <br/>
    a. PCA, LDA, Independent Component Analysis - linear projection of data - misses important **non-linear structure in data** <br/>
    b. Manifold is as an attempt to generalize linear frameworks like PCA {hint! : Isomaps - earth maps?}
4. 
  
