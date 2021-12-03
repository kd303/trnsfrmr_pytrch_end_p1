## Evalution Matrixs
**BLEU (BiLingual Evaluation Understudy)** is a metric for automatically evaluating machine-translated text. The BLEU score is a number between zero and one that measures the similarity of the machine-translated text to a set of high quality reference translations. A value of 0 means that the machine-translated output has no overlap with the reference translation (low quality) while a value of 1 means there is perfect overlap with the reference translations (high quality).

It has been shown that BLEU scores correlate well with human judgment of translation quality. Note that even human translators do not achieve a perfect score of 1.0.

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
![Scale](./session_07_hyperparams/images/scale.jpg)
