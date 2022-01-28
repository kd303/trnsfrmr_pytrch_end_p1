# BERT & BART

## 1. Task 1 : Replicating BERT Training

[Notebook](/session_09_bert/bert_qna/BERT_Tutorial_How_To_Build_a_Question_Answering_Bot.ipynb) for building Q&A bot using BERT

Training Logs
```
Epoch:   0%|          | 0/1 [00:00<?, ?it/s]
Iteration:   0%|          | 0/4508 [00:00<?, ?it/s]
Iteration:   3%|▎         | 145/4508 [00:00<00:03, 1443.89it/s]
Iteration:   6%|▋         | 290/4508 [00:00<00:02, 1437.29it/s]
Iteration:  10%|▉         | 434/4508 [00:00<00:02, 1409.51it/s]
Iteration:  13%|█▎        | 581/4508 [00:00<00:02, 1429.76it/s]
Iteration:  16%|█▌        | 730/4508 [00:00<00:02, 1448.95it/s]
Iteration:  19%|█▉        | 875/4508 [00:00<00:02, 1446.91it/s]
Iteration:  23%|██▎       | 1045/4508 [00:37<06:51,  8.41it/s]
Iteration: 100%|█████████▉| 4507/4508 [49:59<00:00,  1.17it/s]
Iteration: 100%|██████████| 4508/4508 [50:00<00:00,  1.50it/s]

Epoch: 100%|██████████| 1/1 [50:00<00:00, 3000.47s/it]

```
### Samples output

```
"56ddde6b9a695914005b9628": "France",
"56ddde6b9a695914005b9629": "10th and 11th centuries",
"56ddde6b9a695914005b962a": "Denmark, Iceland and Norway",
"56ddde6b9a695914005b962b": "Rollo",
"56ddde6b9a695914005b962c": "10th",
```

### Evaluation Output

```
***** Running evaluation *****
  Num examples = 13600
  Batch size = 32
Evaluating: 100%|██████████| 425/425 [02:01<00:00,  3.50it/s]
{
  "exact": 70.3697464836183,
  "f1": 73.58668968300192,
  "total": 11873,
  "HasAns_exact": 64.49055330634278,
  "HasAns_f1": 70.93366508203107,
  "HasAns_total": 5928,
  "NoAns_exact": 76.23212783851976,
  "NoAns_f1": 76.23212783851976,
  "NoAns_total": 5945,
  "best_exact": 70.54661837783206,
  "best_exact_thresh": -0.3960533142089844,
  "best_f1": 73.61606612222818,
  "best_f1_thresh": -0.23991966247558594
}
```

## 2. Task 2 : Fine Tunning BERT for classification

[NoteBook](/session_09_bert/classification_bert/BERT_Fine_Tuning_Sentence_Classification_v4.ipynb)
Credit to [Chris McCormick and Nick Ryan](https://mccormickml.com/2019/07/22/BERT-fine-tuning/) for producing original work, I have only added the predictor part to the notebook, bit lazily :) , yet managed

```
Text                                                                                                	     Predicted      	       Actual       
Somebody just left - guess who.                                                                     	         1          	         1          
They claimed they had settled on something, but it wasn't clear what they had settled on.           	         1          	         1          
If Sam was going, Sally would know where.                                                           	         1          	         1          
They're going to serve the guests something, but it's unclear what.                                 	         1          	         1          
She's reading. I can't imagine what.                                                                	         1          	         1          
John said Joan saw someone from her graduating class.                                               	         1          	         1          
John ate dinner but I don't know who.                                                               	         1          	         0          
She mailed John a letter, but I don't know to whom.                                                 	         1          	         0          
I served leek soup to my guests.                                                                    	         1          	         1          
I served my guests.                                                                                 	         1          	         1   
```
