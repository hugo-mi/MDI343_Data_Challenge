# Data Challenge : Challenge Large Scale Machine Learning

## Data Challenge Description : Face Recognition

In recent years, face recognition systems have achieved extremely high levels of performance, opening the door to a wider range of applications where reliability levels were previously prohibitive to consider automation. This is mainly due to the adoption of deep learning techniques in computer vision. The most widely adopted paradigm is to train a $f: \mathcal{X} \rightarrow \mathbb{R}^d$ which, from a given image $im \in \mathcal{X}$, extracts a feature vector $z \in \mathbb{R}^d$ which synthesizes the relevant features of $im$. 

The recognition phase then consists, from two images $im_1, im_2$, in predicting whether or not they correspond to the same identity. This is done from the extracted features $z_1, z_2$.

## Goal

In this data challenge, the goal is to train a machine learning model that, given a vector $[z_1, z_2]$ consisting of the concatenation of two patterns $z_1$ and $z_2$, predicts whether or not these two images match the same identity.

## Training Data

The train set consists of two files ``train_data.npy`` and ```train_labels.txt```


The ```train_data.npy``` file contains one observation per line, which consists of the concatenation of two templates, each of **dimension 48**
    
The file ```train_labels.npy``` contains two classes labeled per line that indicate whether the image pair matches the same identity: 
    
- ```1``` => image pairs belonging to the same identity
- ```0``` => image pairs not belonging to the same identity

## Performance

For the evaluation of the performance of the models, the idea is to minimize the sum of the rate of **false positives rate** ```FPR``` and the rate of **false negatives rate** ```FNR```. The performance score of the model is calculated using the following equation.

$score = 1 - (FPR + FNR)$

## Results Summary

| Model | Feature Engineering | Hard Voting | Soft Voting |Score FNR+FPR rate (Valid Test) | 1-(FNR+FPR) (Valid Test) |
|-----------|-----------|-----------|-----------|-----------|-----------|
| Adaboost (baseline) | Features Selection | No | No | 0.52 | 0.48 |
| Gradient Boosting | Features Selection | No | No | 0.54 | 0.46 |
| XGBoost  | Features Selection | No | No | 0.45 | 0.55 |
| XGBoost  | Initial features | No | No | 0.40 | 0.60 |
| LightGBM | Initial features | No | No | 0.39 | 0.61 |
| CatBoost  | Initial features | No | No | 0.387 | 0.613 |
| XGBoost + LightGBM + CatBoost | Initial features | Yes | No | 0.382 | 0.618 |
| XGBoost + LightGBM + CatBoost | Initial features | No | Yes | 0.384 | 0.616 |
| XGBoost + LightGBM + CatBoost | Enlarged features | Yes | No | 0.379 | 0.621 |
| Neural Network | Initial features | No | No | 0.44 | 0.56 |
