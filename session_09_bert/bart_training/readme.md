# BART for Paraphrasing with Simple Transformers

Thanks to original author [Thilina Rajapakse](www.linkedin.com/in/t-rajapakse/) for producing the original work
[Notebook](session_09_bert/bart_training)
[WandDb Reports][]
## Training Logs

```
Run history:

Training loss	█▂▃▄▄▄▅▃▄▃▃▃▂▂▃▃▃▄▃▁▂▂▂▃▂▃▃▂▂▄▂▂▃▂▂▂▃▂▂▃
global_step	▁▁▁▁▂▂▂▂▂▃▃▃▃▃▃▄▄▄▄▄▅▅▅▅▅▅▆▆▆▆▆▆▇▇▇▇▇███
lr		▁▂▄▅▇██████▇▇▇▇▇▇▇▇▇▆▆▆▆▆▆▆▆▆▆▅▅▅▅▅▅▅▅▅▅

Run summary:

Training loss	0.63239
global_step	2500
lr	3e-05
Synced 5 W&B file(s), 0 media file(s), 0 artifact file(s) and 0 other file(s)
Synced peachy-eon-1: https://wandb.ai/kd-tensor/Paraphrasing%20with%20BART/runs/18ah7dfj
Find logs at: ./wandb/run-20220128_225009-18ah7dfj/logs
Successfully finished last run (ID:18ah7dfj). Initializing new run:
huggingface/tokenizers: The current process just got forked, after parallelism has already been used. Disabling parallelism to avoid deadlocks...
To disable this warning, you can either:
	- Avoid using `tokenizers` before the fork if possible
	- Explicitly set the environment variable TOKENIZERS_PARALLELISM=(true | false)
Syncing run young-oath-2 to Weights & Biases (docs).
Epochs 1/2. Running Loss: 0.5045: 100%
1452/1452 [13:37<00:00, 1.87it/s]
INFO:simpletransformers.seq2seq.seq2seq_model:Saving model into outputs/checkpoint-1452-epoch-1

```

## Inferencing



```
```
