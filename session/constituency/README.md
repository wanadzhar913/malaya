# how-to

Original implementation at https://github.com/nikitakit/self-attentive-parser. We adapted same algorithms and changed a bit tree structure to adapt bahasa structure.

**This directory is very lack of comments, understand Tensorflow, Tensorflow estimator, Tensorflow Dataset really helpful**.

## Table of contents
  * [prepare dataset](#prepare-dataset)
  * [training pretrained models](#training-pretrained-models)
  * [test and export the models](#test-and-export-the-models)

## prepare dataset

1. Get the dataset at, [malay-dataset/parsing/constituency](https://github.com/huseinzol05/Malay-Dataset/tree/master/parsing/constituency).

2. Split the dataset into train and test set, after that augment the dataset, [malay-dataset/parsing/constituency/augmented.ipynb](https://github.com/huseinzol05/Malay-Dataset/blob/master/parsing/constituency/augmented.ipynb).

## training pretrained models

1. Run any pretrained model you want, example as below,

**BERT-BASE**

```
python3 src/main_bert_base.py train --use-bert --model-path-base models/en_bert --bert-model "bert-large-uncased" --num-layers 2 --learning-rate 0.00005 --batch-size 32 --eval-batch-size 16 --subbatch-max-tokens 500 --predict-tags --train-path train.txt --dev-path test.txt
```

**TINY-BERT**

```
python3 src/main_tiny_bert.py train --use-bert --model-path-base models/en_bert --bert-model "bert-large-uncased" --num-layers 2 --learning-rate 0.00005 --batch-size 32 --eval-batch-size 16 --subbatch-max-tokens 500 --predict-tags --train-path train.txt --dev-path test.txt
```

**ALBERT-BASE**

```
python3 src/main_albert_base.py train --use-bert --model-path-base models/en_bert --bert-model "bert-large-uncased" --num-layers 2 --learning-rate 0.00005 --batch-size 32 --eval-batch-size 16 --subbatch-max-tokens 500 --predict-tags --train-path train.txt --dev-path test.txt
```

**ALBERT-TINY**

```
python3 src/main_albert_tiny.py train --use-bert --model-path-base models/en_bert --bert-model "bert-large-uncased" --num-layers 2 --learning-rate 0.00005 --batch-size 32 --eval-batch-size 16 --subbatch-max-tokens 500 --predict-tags --train-path train.txt --dev-path test.txt
```

**XLNET-BASE**

```
python3 src/main_xlnet_base.py train --use-bert --model-path-base models/en_bert --bert-model "bert-large-uncased" --num-layers 2 --learning-rate 0.00005 --batch-size 32 --eval-batch-size 16 --subbatch-max-tokens 500 --predict-tags --train-path train.txt --dev-path test.txt
```

**ALXLNET-BASE**

```
python3 src/main_alxlnet_base.py train --use-bert --model-path-base models/en_bert --bert-model "bert-large-uncased" --num-layers 2 --learning-rate 0.00005 --batch-size 32 --eval-batch-size 16 --subbatch-max-tokens 500 --predict-tags --train-path train.txt --dev-path test.txt
```

## test and export the models

1. Testing finetunes model, example for ALBERT-BASE, [predict-albert-base.ipynb](predict-albert-base.ipynb).

2. Calculate accuracy using test set and freeze the graph, example for ALBERT-BASE, [export-albert-base.ipynb](export-albert-base.ipynb).