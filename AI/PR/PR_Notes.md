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
features are required? Here comes the **Curse Of Dimensionality** 

* **Bias** Complex decision boundaries seem to lock onto the idiosyncrasies of the training data set
* **variance** simple decision boundaries (e.g., linear) seem to miss some obvious trends in the data

### 1.3 Classification 

To assign an category to the object based on the feature vector provided during feature extraction

**Choosing a model**

* Testing your Model by Analysis by Synthesis
* Classifier ensemble

## 2 Decision Trees

Benefits of Decision Trees

* classification for nominal data --data that are discrete and without an natural notion of similarity or even ordering
* Decision trees have a particularly high degree of interpretability  

When to consider a Decision Tree

* Instances are wholly or partly described by attribute-value pairs.
* Target function is discrete valued
* Possibly noisy training data.
* Examples
    * Equipment or medical diagnosis.
    * Credit risk analysis.
    * Modeling calendar scheduling preferences

Types of Decision Trees

* CART
* ID3

### 2.1 CART

Any Decision tree will progressively split the data into subsets, If at any point all of the elements of
a particular subset are of the same category, then we say this node is pure and we can stop splitting.

6 things which are important while construction of a decision tree

* **Number of splits**
    * There can be any no of splits called **branching factor**. Any split with a factor greater than 2 can
      easily be **converted to binary** unless its inference is computationally costly
* **Query Selection and node purity** - : we prefer decisions that lead to a simple, compact tree with few nodes
    * i(N) denotes the impurity- its 0 if node has all the objects of same categories 
    * Types of Impurities
        * Entropy Impurity - i(N) =  - sum(P(wj) log P(wj))  ***j**= total categories* 
        * Variance Impurity - i(N) = P(w1)P(w2) *for two category case*
        * Gini Impurity - i(N) = 0.5(1-sum(p(wj)^2))
        * Misclassification Impurity - i(N) = 1-max(p(wj))
    * The obvious heuristic is to choose the feature that yields as big a decrease in the impurity as possible
        * this is called **impurity gain**
        * delta(i) = i(N) -Pl(i(Nl))-(1-Pl)(i(Nr))
* **when to stop splitting** 
    * if the tree is let grown till the leaf of impurity 0 then it would be over trained and hard to
      genralise
    * if it is pruned earlier then is under trained and has performance issues
    * ways to stop splitting
        * Set a threshold - stop the splitting if the impurity gain of the best condition is less than
          the threshold 
        * setting a complexity term - perform the splitting to minimize the complexity of the tree and
          stop the splitting if you cannot further minimise the complexity ( a*size + sum(I(nleaf)) )
          *a = constant,  size = no of edges or nodes, I(nleaf) = impurity of the leaf
        * Chi-square signiicance
    * All the above methods are finding the localized best solution. None of them are looking ahead in
      the future. so the **pruning** gurantees the global minimum 
        * Pruning - let the whole tree grow until the leafs are completely pure and then start to prune
          the leafs which do not provide a significant improvements in impurity gain.
* **Assigning the leaf Node** - label assignment depends on the decision theory.

Differences

threshold setting | complexity term | chi square significance | pruning
------------------|-----------------|-------------------------|--------
**benefits|benefits|benefits|benefits|benefits**
trained on whole data|trained on whole data|trained on whole data|trained on whole data|trained on whole data
allows different levels of leafs|allows different levels of leafs|allows different levels of leafs|allows different levels of leafs|allows different levels of leafs
 | | |selects global minima's
**Drawbacks|Drawbacks|Drawbacks|Drawbacks|Drawbacks**
need to select threshold| need to select a| |additional computation 
selects local minima's|selects local minima's|selects local minima's|




Importance of feature choice - selecting multiple feature for the condition is better in terms of
accuracy and performance

### 2.2 ID3

This is another tree growing methods accepting nominal data with some significant difference  
* every node has branching factor as the no of distinct attribute values of a variable
* number of levels is equal to the total no of variables
* algorithm progresses till  all leaf are pure node or no more variables to select
* can handle real values values
* pruning is performed based on statistical significance
