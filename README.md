# Feedback Prize - Evaluating Student Writing

This is a collection of my some of the code from the [Feedback Prize - Evaluating Student Writing](https://www.kaggle.com/c/feedback-prize-2021/) Kaggle competition.


#### Preprocessing

| File        | Comment     |
| ----------- | ----------- |
|  [preprocessing.ipynb](preprocessing.ipynb)  | various code for preprocessing the original data provided by the competition organizers.|

#### Models

| File        | Comment     |
| ----------- | ----------- |
| [fbp_train.ipynb](fbp_train.ipynb) | The code to train the model. The model is a Token Classification model with [roberta-base](https://huggingface.co/roberta-base) (`LB: 0.631`) as the backbone. I also tried the [longformer-base](https://huggingface.co/allenai/longformer-base-4096) (`LB: 0.631`) and used gradient accumulation to fit a single batch of size 4 into RTX 3070ti's memory. |


#### Other 

| File        | Comment     |
| ----------- | ----------- |
| [LDA Topic Modeling](topic_modeling.ipynb)      | I had an idea of creating folds based on topics extracted using LDA. The logic was that documents of a similar topic would be structurally similar. Unfortunately, this had a negative impact on the model's overall performance. The parameters for the LDA model were not optimized and were chosen randomly such that the model returned topic clusters similar to that of what other users had shared on the forums.|
| [stopwords.txt](stopwords.txt)      | Compiled list of stopswords from various sites. I also manually added additional words based on experimentation.|