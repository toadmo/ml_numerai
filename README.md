# ml_numerai (CS485 Project)

## Table Of Contents
- [ml_numerai (CS485 Project)](#ml_numerai-cs485-project)
  - [Table Of Contents](#table-of-contents)
  - [Contributors](#contributors)
  - [Purpose](#purpose)
    - [Goals](#goals)
  - [Essential Tasks](#essential-tasks)
  - [The Numerai Tournament](#the-numerai-tournament)
    - [Website](#website)
    - [Introduction](#introduction)
    - [Data](#data)
    - [Scoring](#scoring)
    - [Feature Engineering:](#feature-engineering)
    - [Our Models:](#our-models)
    - [Sources:](#sources)


## Contributors
- CDT Edward Tang, USMA '23
  - *Github*: [toadmo](https://github.com/toadmo)
- CDT Mason Nunn, USMA '23
  - *Github*: [AOreoCookie](https://github.com/AOreoCookie)

## Purpose
This is the final project for **CS485: Applied Neural Networks, AY21-2**. This project not only gauges our understanding of neural networks but also how effectively we are able to apply them to real world problems. If all goes well with this project we plan to continue to compete at Numerai in the future. 

### Goals
1. Understand how to develop neural networks on a deeper level. Specifically applying them to real world problems that are still have not been solved.
2. Get a good grade (A+) on this project. :)
3. Develop a model that is capable of exceling past Numerai's baseline.
4. Use the skills MAJ Ruiz taught us to make money!!!
5. Learn how to use Github as developer.

## Essential Tasks 
- [X] Importing Data.
- [X] Data Exploration
- [X] Feature Engineering
- [X] Define Model
- [ ] Validate Approach
- [ ] Prepare Predictions
- [ ] Upload Predictions
  
---
## The Numerai Tournament

### Website
[Numerai Tournament](https://numer.ai/)

[Numerai Documentation](https://docs.numer.ai/tournament/learn)

### Introduction
The Numerai Tournament is where you build machine learning models on abstract financial data to predict the stock market. Models will be stacked with the NMR cryptocurrency to earn rewards based on performance.

### Data
The Numerai Tournamnet porvides a free dataset. It is made of high quality financial data that has been *cleaned*, *regularized* and *obfuscated*.

***Below are descriptions for the headers of the dataset:***

<dl>
  <dt><strong>id</strong></dt>
  <dd>Label for the encrypted stock.</dd>
  <dt><strong>era</strong></dt>
  <dd>A label about how long the data was collected. If the era is the same, it means that the data was collected during the same period.</dd>
  <dt><strong>data_type</strong></dt>
  <dd>There are four values: train, validation, test, live. train is the data for training, validation is the data for verification, test is the data for Numerai to test, and live is the data for the current round.</dd>
  <dt><strong>feature</strong></dt>
  <dd>Binned feature quantity. Features are binned into 5 levels: 0,0.25,0.5,0.75,1. Features are in groups labeled as: “feature_intelligence”, “feature_wisdom”, “feature_charisma”, “feature_dexterity”, “feature_strength”, “feature_constitution”.</dd>
  <dt><strong>target</strong></dt>
  <dd>Binned teacher data. The target is also binned into 5 levels: 0,0.25,0.5,0.75,1. An abstract measure of performance (4 weeks into the furture). The target data is given in numerai_training_data.csv, but it is NAN in the test and live data of numerai_tournament_data.csv.</dd>
</dl>

### Scoring
- **Correlation (corr)**: *The primary way users are scored.* Correlation between user predictions and targets. The higher the better.
- **Meta Model Contribution (mmc)**: *The secondary way users are scored.* The higher the better.
- **Feature Neutral Correlation (fnc)**: *The tertiary way users are scored.* The higher the better.
- ***Spearman Correlation***: How well the relationship between two variables can be defined with a monotonic function. The higher the better.

> Each submission will be scored over the ~4 week duration of the round. Submissions will receive its first score starting on the Thursday after the Monday deadline and final score on Wednesday 4 weeks later for a total of 20 scores. 

### Feature Engineering:
We anticipated that feature engineering would be our biggest challenge in this project for a few reasons. 

1. There is a significant amount of noise in the dataset: features that do not have a high correlation with our intended output, which could cause problems while training.
2. The obfuscation of the data results in the engineers not being able to handpick features that can be believed to be more highly correlated.

To combat this, we have implemented the following:

1. Feature correlation with target based on era
2. Dropping out features based on importance / correlation

### Our Models:

In an effort to cover more ground, we decided to each tackle a different type of model, letting us experiment with both a recurrent neural network model and a LightGBM model. 

**Recurrent Neural Network**

Due to the sequential nature of stock data, especially with different eras being present in the data set and the time-based fluctuation of a stock price being an integral determinant of whether to buy or sell a stock, we chose to implement a recurrent neural network as our model.

Specifically, we chose to use LSTMs, or Long Short Term Memory cells, that, when compared to their counterpart the GRU, take longer to train but often yield improved performance. Due to the nature of our project being throughout the cource of a semester, we figured that we would have enough time to tune an implementation with LSTMs.

**LightGBM Model**




### Sources:

- [Numer.ai Website](https://numer.ai/)
- 