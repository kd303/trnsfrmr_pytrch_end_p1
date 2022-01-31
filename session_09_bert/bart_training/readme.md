# BART for Paraphrasing with Simple Transformers

Thanks to original author [Thilina Rajapakse](www.linkedin.com/in/t-rajapakse/) for producing the original work
- [Notebook](session_09_bert/bart_training/bart_training_paraphrasing.ipynb)
- [WandDb Reports](session_09_bert/bart_training/WandDB_BART_Paraphrasing–WeightsBiases.pdf)
## Training Logs

```
Downloading: 100%
1.56k/1.56k [00:00<00:00, 34.2kB/s]
Downloading: 100%
971M/971M [00:28<00:00, 40.2MB/s]
Downloading: 100%
26.0/26.0 [00:00<00:00, 640B/s]
Downloading: 100%
878k/878k [00:01<00:00, 1.15MB/s]
Downloading: 100%
446k/446k [00:00<00:00, 652kB/s]
Downloading: 100%
1.29M/1.29M [00:01<00:00, 1.13MB/s]
INFO:simpletransformers.seq2seq.seq2seq_utils: Creating features from dataset file at cache_dir/
100%
11615/11615 [00:06<00:00, 1954.06it/s]
/usr/local/lib/python3.7/dist-packages/transformers/optimization.py:309: FutureWarning: This implementation of AdamW is deprecated and will be removed in a future version. Use thePyTorch implementation torch.optim.AdamW instead, or set `no_deprecation_warning=True` to disable this warning
  FutureWarning,
INFO:simpletransformers.seq2seq.seq2seq_model: Training started
Epoch 2 of 2: 100%
2/2 [33:09<00:00, 975.69s/it]
wandb: You can find your API key in your browser here: https://wandb.ai/authorize
wandb: Paste an API key from your profile and hit enter, or press ctrl+c to quit: ··········
wandb: Appending key for api.wandb.ai to your netrc file: /root/.netrc
Syncing run crimson-snow-3 to Weights & Biases (docs).
Epochs 1/2. Running Loss: 0.4896: 100%
726/726 [12:20<00:00, 1.01s/it]
INFO:simpletransformers.seq2seq.seq2seq_model:Saving model into outputs/checkpoint-726-epoch-1
INFO:simpletransformers.seq2seq.seq2seq_utils: Creating features from dataset file at cache_dir/
100%
3539/3539 [00:11<00:00, 197.25it/s]
INFO:simpletransformers.seq2seq.seq2seq_model:{'eval_loss': 0.5359137333459683}
INFO:simpletransformers.seq2seq.seq2seq_model:Saving model into outputs/best_model
Epochs 2/2. Running Loss: 0.3925: 100%
726/726 [12:09<00:00, 1.01it/s]
INFO:simpletransformers.seq2seq.seq2seq_model:Saving model into outputs/checkpoint-1452-epoch-2
INFO:simpletransformers.seq2seq.seq2seq_utils: Creating features from dataset file at cache_dir/
100%
3539/3539 [00:11<00:00, 201.38it/s]
INFO:simpletransformers.seq2seq.seq2seq_model:{'eval_loss': 0.5040417126975618}
INFO:simpletransformers.seq2seq.seq2seq_model:Saving model into outputs/best_model
INFO:simpletransformers.seq2seq.seq2seq_model:Saving model into outputs/
INFO:simpletransformers.seq2seq.seq2seq_model: Training of facebook/bart-large model complete. Saved to outputs/.
Generating outputs: 100%
222/222 [16:14<00:00, 3.39s/it]

```

## Inferencing



```
Generating outputs: 100%
222/222 [16:16<00:00, 3.37s/it]
/usr/local/lib/python3.7/dist-packages/transformers/generation_utils.py:2343: UserWarning: __floordiv__ is deprecated, and its behavior will change in a future version of pytorch. It currently rounds toward 0 (like the 'trunc' function NOT 'floor'). This results in incorrect rounding for negative values. To keep the current behavior, use torch.div(a, b, rounding_mode='trunc'), or for actual floor division, use torch.div(a, b, rounding_mode='floor').
  next_indices = next_tokens // vocab_size
Truth:  They were there for us to enjoy and they were there for us to pray.

 Prediction: 

Paraphrase : They were there to enjoy us and they were there for us to pray.

Paraphrase : They were there to enjoy us and they were there for us to pray.

Paraphrase : They were there to enjoy us, and they were there for us to pray.

________________________________________________________________________________

Truth:  In August, after the end of the war in June 1902, Higgins Southampton left the `` SSBavarian '' and returned to Cape Town the following month.

 Prediction: 

Paraphrase : After the end of the war in June 1902, Higgins left Southampton in the `` SSBavarian '' in August, returning to Cape Town the following month.

Paraphrase : After the end of the war in June 1902, Higgins left Southampton in the `` SSBavarian '' in August, returning to Cape Town the following month.

Paraphrase : After the end of the war in June 1902, Higgins left Southampton in the `` SSBavarian '' in August, returning to Cape Town the following month.

________________________________________________________________________________

Truth:  Shawnee Trails Council was formed from the merger of the Four Rivers Council and the Audubon Council.

 Prediction: 

Paraphrase : From the merger of the Four Rivers Council and the Audubon Council, the Shawnee Trails Council was born.

Paraphrase : From the merger of the Four Rivers Council and the Audubon Council, the Shawnee Trails Council was born.

Paraphrase : From the merger of the Four Rivers Council and the Audubon Council, the Shawnee Trails Council was born.

________________________________________________________________________________

Truth:  The group toured extensively and was famous in Israel and even played in New York City in 2007.

 Prediction: 

Paraphrase : The group toured extensively and became famous in Israel and even played in New York City in 2007.

Paraphrase : The group toured extensively and became famous in Israel and even played in New York City in 2007.

Paraphrase : The group toured extensively and became famous in Israel and even played in New York City in 2007.

________________________________________________________________________________

Truth:  Kathy and her husband Peter Dean ( Pete Beale ) are financially stable.

 Prediction: 

Paraphrase : Kathy and her husband Pete Beale ( Peter Dean ) are financially stable.

Paraphrase : Kathy and her husband Pete Beale ( Peter Dean ) are financially stable.

Paraphrase : Kathy and her husband Pete Beale ( Peter Dean ) are financially stable.

________________________________________________________________________________
```
