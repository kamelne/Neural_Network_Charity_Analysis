# Neural Network Charity Analysis

## Overview

Creating Neural Network to predict successful campaigns from the donation recipient's applications to help Alphabet Soup donate to organization that will use the money properly.

## Results
### Data Preprocessing
From the raw data CSV, there were a not of excess data and noise in certain columns. First, we identify the data dtype of each column looking for ones that are not integers, neural networks can only work with numbers. Columns 'EIN' and 'NAME' are both objects and are only identification columns, they are dropped as they do not provide useful information for the neural network. The object columns are then examined for unique values and bucketed as necessary.

Our target variable is the 'IS_SUCCESSFUL' COLUMN
The features are the remaining columns which have not been dropped.

### Compiling, Training and Evaluating the Model
For my first neural network, Deliverable 2 in the table below, I built a network with 2 layers using relu activation, the first having 30 neurons and the second having 15, and the output layer having 1 neuron and using the sigmoid activation. I went with two layers and activation functions based on previous models I built while learning about neural networks. The number of neurons was chosen using a 'rule-of-thumb'[^1]. This model resulted in an accuracy of 72.58%

Many attempts were taken to increase the accuracy to the target of 75% or greater but none were successful. The attempts are summarized below, and results are in Summary section. 

  * Optimization 1: three activation layers with same neurons in first two and third having half of the second (7), same activation functions used
  * Optimization 2: same model as deliverable 2 but using the tanh activation instead of relu
  * Optimization 3: used keras tuner to find test many models and find optimal, 4 hidden layers, 5,7,5,7 neurons respectively all using tanh activation and output using sigmoid
  * Optimization 4: single hidden layer with 30 neurons and using tanh activation
  * Optimization 5: repeat of Optimization 3 except using 30,15,8,4 neurons respectively



## Summary

| Attempt         | Loss   | Accuracy |
| --------------- |:------:| --------:|
| Deliverable 2   | 0.5592 | 0.7258   |
| Optimization 1  | 0.5558 | 0.7275   |
| Optimization 2  | 0.5569 | 0.7262   |
| Optimization 3 (20 epochs) | 0.5608| 0.7272 |
| Optimization 3 (100 epochs) | 0.5578| 0.7266 |
| Optimization 4 | 0.5559| 0.7252 |
| Optimization 5 | 0.5571| 0.7297 |

Overall trying to predict which charities Alphabet Soup should donate to is a tough model to create. There are many inputs and variables to try to create an accurate neural network. One consideration I did not take in my optimization was the way data was removed and bucketed. A recommendation I have is to look further into each data column and test if removing more or bucketing different could results in a more accurate model.



[^1]: https://www.heatonresearch.com/2017/06/01/hidden-layers.html
