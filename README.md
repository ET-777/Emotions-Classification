Emotions Classification (NLP)
-----------------------

Deep network to predict the emotion being expressed in a sentence or phrase from a dataset of english statements. This model is a Bidirectional LSTM (Long Short-Term Memory) model trained with tokenized text. The datasets are of 16k phrases for training and 2k for testing and validation. Dataset is [here](https://www.kaggle.com/datasets/praveengovi/emotions-dataset-for-nlp). You can see the data processing, model, code, and full explanations in the `EmotionClassification.ipynb` notebook above.

Quick Overview
----------------------

List of emotions: Sadness, Anger, Love, Surprise, Fear, Joy

A couple of statements and their emotions:

 Text | Emotion 
------------ | -------------
i found myself feeling a little discouraged that morning | sadness
i was stymied a little bit as i wrote feeling unsure that i might go somewhere with the story unintended | fear
i am now nearly finished the week detox and i feel amazing | surprise
i was feeling brave when i bought it and clearly when i was doing my makeup | joy
i drove dannika to school i was feeling a little bit rushed and this is what greeted me as i turned the corner | anger
i was ready to meet mom in the airport and feel her ever supportive arms around me | love

<br /><br />
The words from the texts are tokenized and each phrase is converted into a padded sequence.

Original text: i didnt feel humiliated

Tokenized text: [  1 138   2 678   0   0   0   0   0   0   0   0   0   0   0   0   0   0
   0   0   0   0   0   0   0   0   0   0   0   0   0   0   0   0   0   0
   0   0   0   0   0   0   0   0   0   0   0   0   0   0   0   0   0   0
   0   0   0   0   0   0   0   0   0   0   0   0]

The model is constructed sequentially with an input emdedding layer, two BLSTM layers with 256 neurons and an output Dense layer. The outpt layer has a linear activation with a SparseCategoricalCrossEntropy loss function, as it is better computationally than the softmax activation.

<p align="center">
<br />
Model
<br />
<br />
<img src="https://github.com/ET-777/Emotions-Classification/blob/master/images/model.jpg"/>
<br />
<br />
<br />
</p>

Results
----------------------

The model was trained for 10 epochs with a SparseCategoricalCrossEntropy loss function and an adam optimizer.

<p align="center">
<br />
Accuracy&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Loss
<br />
<img src="https://github.com/ET-777/Emotions-Classification/blob/master/images/graphs.png"/>
<br />
<br />
<br />   
Predictions
<br />
<br />
<img src="https://github.com/ET-777/Emotions-Classification/blob/master/images/predictions.jpg"/>
<br />
<br />
</p>

<br /><br />
 Data | Loss | Accuracy
------------ | ------------- | -------------
Training | 0.096 | 0.96
Validation | 0.170 | 0.93
Testing | 0.170 | 0.93

<br /><br />
The loss scores are all close for all datasets with no overfitting. With low loss and accuracies above 90%, It's an excellent model.
<br /><br />

Installation
----------------------

### Download the data

* Clone this repo to your computer.
* Create a `Data` folder in the project directory
* Download the data files from Kaggle into the `Data` folder.  
    * You can find the data [here](https://www.kaggle.com/datasets/praveengovi/emotions-dataset-for-nlp).
    * You'll need to register with Kaggle to download the data.
* Extract the `.zip` file you downloaded into the `Data` folder.

### Install the requirements
 
* Install the requirements with `anaconda` or with pip using `pip install -r requirements.txt`.
    * Make sure you use Python 3.
    * You may want to use a virtual environment for this.

Usage
-----------------------

* Open `EmotionClassification.ipynb` with `Jupyter Notebook`.
* Run the notebook
    * Make sure you are using running `tensorflow` with a `GPU`.
