# MeliDataChallenge


# Requirements 

This repository requires the following libraries to run: 
  - numpy
  - scipy
  - pytorch
  - sklearn
  - pandas
 
# Data

We only need two external files, [train.csv](https://meli-data-challenge.s3.amazonaws.com/train.csv.gz) and [test.csv](https://meli-data-challenge.s3.amazonaws.com/test.csv). Both files can be found [here](https://ml-challenge.mercadolibre.com/downloads). Also, we have the bash command to download both files in the preprocessing notebook. 

# Solution

We divide the solution in 3 steps:  **preprocessing**, **training** and **submissions** (predictions).

- data
-   preprocessing.ipynb
- training
    - training_0.0015.ipynb
    - training_0.0015_10.ipynb
    - training_0.0015_5.ipynb   
    - training_mytk_07.ipynb    
    - training_mytk_08.ipynb
    - training_mytk_09. pynb
    - training_mytk_20.ipynb
-  submissions
    - sub_0.0015.ipynb
    - sub_0.0015_10.ipynb
    - sub_0.0015_5.ipynb
    - sub_mytk_07.ipynb
    - sub_mytk_08.ipynb
    - sub_mytk_09.ipynb
    - sub_mytk_20.ipynb
-   final_submission.ipynb

## Preprocessing

First we have to do the preprocessing in `preprocessing.ipynb`. In this notebook we download `train.csv` and `test.csv`, make some directories and generate some vocabularies, subsets and dictionaries.

We make the following structure:
- data
    - train.csv
    - test.csv
    - datasets
    - vocabularies
    - models
    - submissions
    - stats
    - weights.pkl
    - classes_dict.pkl
 

We make 20 pandas dataframes and store them in `./data/datasets/`
We make 4 vocabulary dictionaries and store them in `./data/vocabularies/`
We make two pickle files containing some statistics about the classes, `classes_dict.pkl` and `class_weights.pkl` and store them in `./data/`

## Training

Then we train 7 similar models. Whose difference is either the vocabulary, the dataset, or the minibatch sample strategy. 

In the `./training/` folder we have 7 notebooks, one per model. Each model generate 1 or more copy of the model, whose difference is in the learning rate or the number of epoches. We store the models in `./data/models/`. Also we store some statistics in `./data/stats/`.

## Predictions

After that, we do the predictions and make the submission files. In the `./submissions/` folder we have 7 files, one per model. We make a prediction for each copy of the model for each model. Then we use all the predictions of each model and generate one prediction per model using a voting system. 



Finally, we use the 7 predictions (one per model) to make the final submission file. This file is generated from the `final_submission.ipynb` notebook. 

We use a vote system in which our best model **model_mytk_07** has a weight of 5 and all the others have a weight of 2. We make the `submission.csv` file and store it in `./data/submissions/`


License
----

MIT
