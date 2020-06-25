[//]: # (Image References)

[image1]: ./images/skin_disease_classes.png "Skin Disease Classes"
[image2]: ./images/cat_1.jpeg "Category 1 Rankings"
[image3]: ./images/cat_2.jpeg "Category 2 Rankings"
[image4]: ./images/cat_3.png "Category 3 Rankings"
[image5]: ./images/sample_ROC_curve.png "Sample ROC curve"
[image6]: ./images/sample_confusion_matrix.png "Sample confusion matrix"

# Melanoma Diagonser

This is a mid-project that was done as part of the Deep Learning course from Udacity that I attended after attaining a scholarship. It is part of my journey of figuring out the ML and DL world. I'm still learning so cut me some slack :sweat_smile:. This repo is based of [this one from Udacity](https://github.com/udacity/dermatologist-ai).

## A bit of background

This small project contains an algorithm (pre-trained) that visually diagnoses a **melanoma**, the deadliest form of skin cancer. It is meant to distinguish the latter from two other types of benign lesions: **nevi** and **seborrheic keratoses**. I know, the words are a mouthful, innit?

The data and main goals from this notebook are directly from the famous [2017 ISIC Challenge on Skin Lesion Analysis Towards Melanoma Detection](https://challenge.kitware.com/#challenge/583f126bcad3a51cc66c8d9a), where participants were tasked with diagnosing skin lesion images of the aforementioned. Many papers found out that using pre-trained models (such as ResNet) actually output great predictions, better than some medical experts!

![Skin Disease Classes][image1]

## Evaluation

Since this is inspired by the ISIC challenge, the algorithm is ranked according to three categories.

#### Category 1: ROC AUC for Melanoma Classification
Gauge the ability of the CNN to distinguish between a melanoma and the two benign skin lesions by calculating the area under the receiver operating characteristic curve corresponding to the binary classification task. If you have no idea what a ROC curve is, I suggest reading the [Wikipedia article](https://en.wikipedia.org/wiki/Receiver_operating_characteristic).

#### Category 2: ROC AUC for Melanocytic Classification
Melanomas and nevi are derived from *melanocytes* whereas seborrheic keratoses are derived from *keratinocytes*. These are two types of epidermal skin cells. In this category, the ability of the CNN to distinguish between these two skin lesions will be tested and calculating the area under the ROC curve.

#### Category 3: Mean ROC AUC
This refers to the average of the ROC values from the first two categories.

### My results

The corresponding **ROC curves** appear in a pop-up window, along with the **confusion matrix** corresponding to melanoma classification.  

![Sample ROC curve][image5]
![Sample confusion matrix][image6]

The code for generating the confusion matrix assumes that the threshold for classifying melanoma is set to 0.5.  To change this threshold, you need only supply an additional command-line argument when calling the `get_results.py` file.  For instance, to set the threshold at 0.4, you need only run:
```text
python get_results.py sample_predictions.csv 0.4
```

To test **your own** submission, change the code to instead include the path to **your** CSV file.

## I want to give this repo a whirl!
You're encouraged to want to try this for yourself! This notebook is my personal solution for the problem proposed by Udacity. If you want to try it and get your own results or share it with your friends, visit their and check the [**Getting started**](https://github.com/udacity/dermatologist-ai#getting-started) and [**Getting your results**](https://github.com/udacity/dermatologist-ai#getting-your-results) sections.


## License
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](http://unlicense.org/)


