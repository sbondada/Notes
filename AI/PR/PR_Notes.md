## 1 Introduction

**Pattern Recognition**  - Pattern recognition is the act of taking in raw data and taking an action based on the category" of the pattern

Examples of patter recognitions 

* Hand-Written Digit Recognition
* Computational Finance and the Stock Market
* Bioinformatics and Gene Expression Analysis
* Biometrics

The main steps involved in PR are

* Preprocessing
* Feature Extraction
* Classification

### 1.1 Preprocessing

This step involves improving the raw data so that the further steps can be improved

* **image** Noise Removal, segment extraction, wavelet transformation etc
* **text** 1 of B vector space conversions

### 1.2 Feature Extraction

Ideally a object lets say in this case sea bass or Solomon may have different features (weight, texture
etc) with all those feature space the objects may be widely separated but when we use only those features 
which can be extracted by the camera(weight ) so we reduce our feature space to much smaller features in 
this space they may be mixed up. 

So selection of the **features** are very important.

Feature Combinations are usually useful because it allows better classification. But then how many
features are required? Here comes the ** Curse Of Dimensionality ** 

* **Bias** Complex decision boundaries seem to lock onto the idiosyncrasies of the training data set
* **variance** simple decision boundaries (e.g., linear) seem to miss some obvious trends in the data

### 1.3 Classification 

To assign an category to the object based on the feature vector provided during feature extraction

** Choosing a model **

* Testing your Model by Analysis by Synthesis
* Classifier ensemble

## 2 Decision Trees


