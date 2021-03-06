## Evalution Matrics
**BLEU (BiLingual Evaluation Understudy)** is a metric for automatically evaluating machine-translated text. 
The BLEU score is a number between zero and one that measures the similarity of the machine-translated text to a set of high quality reference translations. 
A value of 0 means that the machine-translated output has no overlap with the reference translation (low quality) while a value of 1 means there is perfect overlap with the reference translations (high quality).

It has been shown that BLEU scores correlate well with human judgment of translation quality. Note that even human translators do not achieve a perfect score of 1.0.

[Source: Google](https://cloud.google.com/translate/automl/docs/evaluate#bleu)

** BLEU score = (Brevity Penalty)(n-gram overlap)

Where,
``` Brevity penalty = min(1, exp(1 - refence_length/output-length))``` - it penalizes the translataions are that too short, which compansates for recall (actual transalations identified correctly) - 

:scream_cat: **Recall**: Just considering length for counting true-positive - it does not take the meaning, grammer or word positioning in consideration 

:scream_cat: **Precision** : is basically matching uni, bi, tri and four grams in their matching counter part, so this may not work great for synomyms and it 

```

Translated (truth):  i am going down the stairs .
Translated (pred):  you you you you you you you you you

Translated (truth):  you re famous .
Translated (pred):  re you re you re you re you re

Translated (truth):  you re bad .
Translated (pred):  you you you you you you you you you

Translated (truth):  they re all against me .
Translated (pred):  re you re you re you re you re

Translated (truth):  he is poor at chemistry .
Translated (pred):  re s re s re s re s re

Translated (truth):  she s a tough woman .
Translated (pred):  we we we we we we we we we

Translated (truth):  he is on the team .
Translated (pred):  we we we we we we we we we

Translated (truth):  you are under arrest .
Translated (pred):  re you re you re you re you re

Translated (truth):  you re very understanding .
Translated (pred):  re we re we re we re we re

Translated (truth):  he s young and healthy .
Translated (pred):  he s he s he s he s he

Translated (truth):  i am good .
Translated (pred):  i i i i i i i i i

Translated (truth):  we re here to protect you .
Translated (pred):  we we we we we we we we we

Translated (truth):  he s not working much at the moment .
Translated (pred):  we we we we we we we we we

Translated (truth):  he s a good boy .
Translated (pred):  he s he s he s he s he

Translated (truth):  i m just following orders .
Translated (pred):  i i i i i i i i i

Translated (truth):  he s a hunk .
Translated (pred):  we we we we we we we we we

```
The above BLEU score is **0.2315131574869156**, considering about sentences it is quite poor (Even compariting uni and bi-grams with max_n=2, if Below table is to be referred it is not great - most sentences the gist is not clear. This is model is trained at 25k epochs only



BLEU Score |	Interpretation
---|---
< 10    |	Almost useless
10 - 19 |	Hard to get the gist
20 - 29	|The gist is clear, but has significant grammatical errors
30 - 40	| Understandable to good translations
40 - 50	| High quality translations
50 - 60	| Very high quality, adequate, and fluent translations
60	| Quality often better than human

**Following is the scale**
![Scale](/session_07_hyperparams/scale.jps.JPG)


## Perplexity(PPL)

*   Above Training iteration prints the ```exp(log_loss)``` is getting printed at every 5000th iteration.
*   We should note that the metric applies specifically to classical language models (sometimes called autoregressive or causal language models) and is not well defined for masked language models like BERT.
*   Also, for translation it is not evaluation, it just indicates how well a sentence is formed 
*   Perplexity is a measurement of how well a probability distribution or probability model predicts a sample. It may be used to compare probability models. 
*   In natural language processing, perplexity is a way of evaluating language models. A language model is a probability distribution over entire sentences or texts
[Explaination](https://www.youtube.com/watch?v=oaYsCVtHveQ&t=416s)
[Source: Huggingface](https://huggingface.co/docs/transformers/perplexity)

**A low perplexity indicates the probability distribution is good at predicting the sample.**

Equation
![PPLEquation](/session_07_hyperparams/ppl.jpg)



Sample Logs 

```
## prints (time) (epoch %epochs complete) loss PPL(exp(loss))
1m 56s (- 27m 6s) (5000 6%) 2.9732 19.5540
3m 46s (- 24m 30s) (10000 13%) 2.4703 11.8258
5m 35s (- 22m 21s) (15000 20%) 2.2577 9.5607
7m 25s (- 20m 24s) (20000 26%) 2.1209 8.3387
9m 15s (- 18m 30s) (25000 33%) 1.9935 7.3409
11m 3s (- 16m 35s) (30000 40%) 1.9347 6.9220
```

**where log function is the log-likelyhood of ith token conditioned on the preceding tokens.. below is the Visual representation**

![Scale](/session_07_hyperparams/ppl_full.gif)

## BERT Score
BERTScore leverages the pre-trained contextual embeddings from BERT and matches words in candidate and reference sentences by cosine similarity. It has been shown to correlate with human judgment on sentence-level and system-level evaluation. Moreover, BERTScore computes precision, recall, and F1 measure, which can be useful for evaluating different language generation tasks

It gives ```Pricision (P), Recall (R) and F1 scores for each pair given as inputs``` eventually a mean score can be calulated by calling ```mean()``` over the tensor

For a randomly selected 30 sentences, here is the score:

```
P, R, F1 , P.mean().item(), R.mean().item(), F1.mean().item()


(tensor([0.8241, 0.8008, 0.8118, 0.8094, 0.8173, 0.8402, 0.7852, 0.8336, 0.8435,
         0.8424, 0.8159, 0.8200, 0.8134, 0.8202, 0.8253, 0.8239, 0.8125, 0.7973,
         0.8298, 0.8139, 0.8074, 0.8159, 0.7920, 0.8616, 0.8208, 0.8167, 0.8240,
         0.8062, 0.8278, 0.7671]),
 tensor([0.7624, 0.7605, 0.0000, 0.7764, 0.7833, 0.7261, 0.7617, 0.8072, 0.7409,
         0.7395, 0.7836, 0.7429, 0.7780, 0.7664, 0.7975, 0.7614, 0.7322, 0.7220,
         0.7500, 0.7444, 0.7621, 0.7457, 0.7413, 0.7245, 0.7410, 0.7973, 0.7377,
         0.7310, 0.7609, 0.6966]),
 tensor([0.7920, 0.7802, 0.0000, 0.7926, 0.8000, 0.7790, 0.7733, 0.8202, 0.7889,
         0.7876, 0.7995, 0.7795, 0.7953, 0.7924, 0.8111, 0.7914, 0.7703, 0.7578,
         0.7879, 0.7776, 0.7841, 0.7792, 0.7658, 0.7871, 0.7788, 0.8069, 0.7785,
         0.7668, 0.7929, 0.7301]),
 0.8173344135284424,
 0.7291461825370789,
 0.7582226395606995)
 ```
 
 Similarity Matrix has some meaning, and can possibly a good way to visualize sentence formations etc.
 
 ![Image](/session_07_hyperparams/sim_matrix.PNG)
