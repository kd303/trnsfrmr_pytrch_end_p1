## 2. Task 2 : Fine Tunning BERT for classification

[NoteBook](/session_09_bert/classification_bert/BERT_Fine_Tuning_Sentence_Classification_v4.ipynb)
Credit to [Chris McCormick and Nick Ryan](https://mccormickml.com/2019/07/22/BERT-fine-tuning/) for producing original work, I have only added the predictor part to the notebook, bit lazily :) , yet managed

### Training Logs

```
======== Epoch 3 / 4 ========
Training...
  Batch    40  of    241.    Elapsed: 0:00:08.
  Batch    80  of    241.    Elapsed: 0:00:16.
  Batch   120  of    241.    Elapsed: 0:00:25.
  Batch   160  of    241.    Elapsed: 0:00:33.
  Batch   200  of    241.    Elapsed: 0:00:41.
  Batch   240  of    241.    Elapsed: 0:00:49.

  Average training loss: 0.20
  Training epcoh took: 0:00:49

Running Validation...
  Accuracy: 0.84
  Validation Loss: 0.49
  Validation took: 0:00:02

======== Epoch 4 / 4 ========
Training...
  Batch    40  of    241.    Elapsed: 0:00:08.
  Batch    80  of    241.    Elapsed: 0:00:16.
  Batch   120  of    241.    Elapsed: 0:00:25.
  Batch   160  of    241.    Elapsed: 0:00:33.
  Batch   200  of    241.    Elapsed: 0:00:41.
  Batch   240  of    241.    Elapsed: 0:00:49.

  Average training loss: 0.15
  Training epcoh took: 0:00:49

Running Validation...
  Accuracy: 0.85
  Validation Loss: 0.50
  Validation took: 0:00:02

Training complete!
Total training took 0:03:25 (h:mm:ss)
```


### Evaluation outcome
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
