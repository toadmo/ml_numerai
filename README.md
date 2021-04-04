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


## Contributors
- CDT Edward Tang USMA '23
- CDT Mason Nunn USMA '23

## Purpose
This is the final project for **CS485: Applied Neural Networks AY21-2**. This porject not only gauges our understanding of Neural Networks but also how effectively we are able to apply them to real world problems.

### Goals
1. Understand neural networks at a deeper level.
2. Get a good grade on this project.
3. Develop a model which is capable of competing with other models at Numerai.
4. Make Money!!!

## Essential Tasks 
- [X] Importing Data.
- [ ] Feature Engineering
- [ ] Define Model
- [ ] Strengthen Model
- [ ] Validate Approach
- [ ] Prepare Predictions
- [ ] Upload Predictions
  
---
## The Numerai Tournament

### Website
[The Numerai Tournament](https://numer.ai/)

### Introduction
The Numerai Tournament is where you build machine learning models on abstract financial data to predict the stock market. Models will be stacked with the NMR cryptocurrency to earn rewards based on performance.

### Data
A new data set is given each each here are what the headers mean

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
  <dd>Binned teacher data. The target is also binned into 5 levels: 0,0.25,0.5,0.75,1. The target data is given in numerai_training_data.csv, but it is NAN in the test and live data of numerai_tournament_data.csv.</dd>
</dl>