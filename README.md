# Translation-with-attention-GRU
 Machine Translation with attention-based GRU   
 Conduct comprehensive study and tuning on different parts of the attention-based GRU architecture.   

## Dataset
<p align="justify"> A multilingual parallel dataset from ACL 2014 NINTH WORKSHOP ON STATISTICAL MACHINE TRANSLATION is used in this project. In particular, the News Commentary category is used. There are in total 4 language pairs in this dataset and all are bidirectional:    </p>

•	CS-EN     
•	DE-EN      
•	FR-EN      
•	RU-EN 


<p align="justify">In this project, all 4 language pairs' performances will be examined, but English will always be fixed as the target language to predict.   
More information about the dataset can be found here: http://www.statmt.org/wmt14/translation-task.html#download      </p>

## Experiment Setup
<p align="justify">All the experiments below will be based on the BLEU scores evaluated from the nltk.translate.bleu_score's corpus_bleu() function. BLEU scores generated from this function are typically decimal values all smaller than 1. Each training session takes 75000 iterations.    </p>


### Experiment 1: Compare the model performance between the greedy decoding and beam search decoding
<p align="justify">In this section, the greedy decoding performance will be used as the comparison baseline, which is clearer to see whether switching to beam search decoding actually improves the performance or not.   
In terms of the beam search decoding setup, the stopping criterion adopted here is the number of completed hypotheses collected. On top of that, there're some tweaks to the specific detailed settings:   </p>

•	**Default setting**: Apply length normalization when calculating each hypothesis score and No limitation on the max sequence length   
•	**N MAX L**:  Apply length normalization when calculating each hypothesis score but there's a limitation on the max sequence length   
•	**NO N NO MAX L**:  Not apply length normalization when calculating each hypothesis score and there's a limitation on the max sequence length    

<p align="justify">The four language pairs' results are shown as followed:      </p>

![table1](https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/a71e648f-3caa-4d2b-ba14-0ef8a101b7fa)

![table2](https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/4ebe0328-8f3f-4da0-a408-87c162132edc)


![table3](https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/71dc9bf1-9552-46a0-a0bd-6c36ca1a45d4)


![table4](https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/8c1a6fc8-2e10-4751-bf55-053bcb060d41)

### Experiment 2: Compare the model performance between random initialized embedding and pretrained embedding layer
<p align="justify">The loaded embedding layer is pretrained by Word2Vec from gensim.models package. The pretraining data is monolingual training data which can be downloaded from the link: http://www.statmt.org/wmt14/translation-task.html#download.   </p>

The comparison results are:   

![table21](https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/c9971bfa-7295-4c4d-b2f9-5fa77acdb947)

![table22](https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/6e2692ea-28d2-4155-91aa-11f8865fef24)

![table23](https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/d632af66-db57-49c7-98db-8a18c8ba2c4e)

![table24](https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/103c3d76-121f-4bc6-a1e3-65968d4848a9)


### Experiment 3: Compare the model performance between different attention mechanisms
In details, besides the default dot-product attention mechanism, two other attention variants are also being examined:   

<img src="https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/49a0b893-3f79-4a48-8bd6-dad6e0e2bedc" width="500" />

<img src="https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/431b2e73-504f-4479-bc16-bbdb8393eb2e" width="500" />


The comparison results are:

![table31111](https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/1979a093-9413-42f0-8dfb-f00c3a4f35a9)


![table32](https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/48a84520-7e2e-4812-998f-fbe11970238b)

![table33](https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/989d52da-1f19-430b-9a2b-bb812fe268b5)

![table34](https://github.com/zhangziyi1996/Translation-with-attention-GRU/assets/143377198/8c717067-40d5-4ccf-bc4b-828f12580b00)






   
