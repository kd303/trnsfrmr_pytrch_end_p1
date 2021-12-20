## Notes on transformers (not the hugging ones ! :) )


1. [Attention is all you need](https://arxiv.org/pdf/1706.03762.pdf)
2. [Fundamental of Transformers & attention](http://peterbloem.nl/blog/transformers) - Possibly the best explaination, I found on attention and intution behind it
3. Best [Link](http://peterbloem.nl/blog/transformers) for understanding transformers

## Interesting Observations from Attention Paper:
### Desirdata

## Inutions

1. self attention - basically is for learning words and their relationships with other words, basically a high co-relation with words that are more likely to relate to each other, like nouns and verbs are likely to have better or positive dot product (if represented by some embedding vectors) than a verb and an article (the/a/an) as article will not help much in predicting the next word
2. Dot product in self-attention is determines how to vectors are "related" to each other - and by related meaning for a given task that is learnt.
3. Queries, keys and values define different role same input vector plays in defining the self attention:
      - Input **x<sub>i</sub>**, Vector use to calculate an output vector **y<sub>i</sub>**  - Query
      - Input vector **x<sub>i</sub>** used to cacluate an output vector **y<sub>j</sub>**  - Key
      - Input vector **x<sub>i</sub>** used to be part of the weighted sum  - Value
      - Applying linear transformations to the input vector, allows for some controllable parameters W<sub>q</sub>,W<sub>k</sub> and W<sub>v</sub>
     
     **q<sub>i</sub> = W<sub>q</sub>x<sub>i</sub>**    , **k<sub>i</sub> = W<sub>k</sub>x<sub>i</sub>**, **v<sub>i</sub> = W<sub>v</sub>x<sub>i</sub>**
     
     **w<sub>ij</sub><sup>'</sup> = q<sub>i</sub><sup>T</sup>k<sub>j</sub>**
     
     **w<sub>ij</sub> = Softmax(w<sub>ij</sub><sup>'</sup>)**
     
     **y<sub>i</sub> = &Sigma;<sub>j</sub>w<sub>ij</sub>v<sub>j</sub>**

4. Key-Value-Qeury is data structure analogy, where a unique Key is associated with a query and it returns a value. In Self-attention little libral/softer version is for every key in the store that matches the queries, all are returned and we take sum weighted by to which extent the query matches the key

### Questions:
- self-attention or attention layer in general does not care about sequences, infact the sequences are not learned. they learn about word relationships with other words in a sentence by that the given corpora - so how is this different from word2vec kind of model - just self-attention wrt to word2vec?
- 
