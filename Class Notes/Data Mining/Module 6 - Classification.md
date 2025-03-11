# Introduction to Data Mining: Classification (Module 6)

#data-mining #classification #supervised-learning #decision-trees #weka #data-analysis #machine-learning

**Course**: CAP4770 Introduction to Data Mining  
**Author**: Prof. A. Hernandez  
**Document Type**: Lecture Notes (Module 6)

## Module Objectives

This module continues examining principles and methods of data mining, focusing on classification as another important functionality of knowledge discovery. The lecture notes cover:

- Basic definitions of classification
- Application problems where classification is used
- A popular classifier: the decision tree
- Introduction to WEKA, a platform for data mining tools
- Practical implementation of classification using WEKA

## Introduction to Classification

> [!important] Definition Classification is a functionality of data mining that consists of categorizing given data objects into predefined classes. Objects from a dataset are assigned a label based on their attributes.

### Classification vs. Clustering

While [[Cluster Analysis|cluster analysis]] is an example of [[unsupervised learning]], classification is a form of [[supervised learning]]. The name "supervised" originates from the fact that classification algorithms know what the correct output categories are.

> [!example] Email Classification A common example is the classification of emails into 'non-spam' or 'spam'. If the first label is assigned, an incoming email goes to the Inbox folder; if the second is assigned, it goes to the Spam folder.

### Applications of Classification

Classification has numerous applications, including (but not limited to):

- Email spam filtering: determine whether an incoming email is spam or not
- Document classification: categorize documents for storage or analysis
- Pattern recognition: identify object types in images
- Sentiment analysis: classify text data into positive/negative opinions
- Image segmentation: divide and classify parts of an image
- Disease diagnosis: classify diseases based on patient data
- Speech recognition: categorize spoken messages

## The Classification Method

Classification consists of two main steps:

1. **Learning (Training) Step**:
    
    - A model (known as a classifier) is constructed
    - The algorithm receives a set of database tuples and their labels (training set)
    - Based on this set, the model is built
2. **Classification Step**:
    
    - The classifier is used to determine labels for objects with unknown labels

> [!note] Model Validation After the model is constructed and before it's used for classification, its accuracy is estimated. A test set (tuples with known labels that aren't part of the training set) is used. The accuracy of the model is the percentage of test set tuples that are classified correctly.

## Decision Trees

Decision trees are popular classifiers that adopt the shape of a tree:

- Each non-leaf node represents a test on an attribute
- Each leaf represents a class label

### Using Decision Trees in Classification

The lecture notes provide a sample dataset from WEKA that shows whether weather conditions are suitable for playing a certain game:

|Outlook|Temp|Humidity|Windy|Play|
|---|---|---|---|---|
|sunny|hot|high|FALSE|no|
|sunny|hot|high|TRUE|no|
|overcast|hot|high|FALSE|yes|
|rainy|mild|high|FALSE|yes|
|rainy|cool|normal|FALSE|yes|
|rainy|cool|normal|TRUE|no|
|overcast|cool|normal|TRUE|yes|
|sunny|mild|high|FALSE|no|
|sunny|cool|normal|FALSE|yes|
|rainy|mild|normal|FALSE|yes|
|sunny|mild|normal|TRUE|yes|
|overcast|mild|high|TRUE|yes|
|overcast|hot|normal|FALSE|yes|
|rainy|mild|high|TRUE|no|

> [!example] Decision Tree Example Based on the above data, a decision tree might look like:
> 
> ```
> outlook
> |-- overcast: YES
> |-- sunny:
>     |-- humidity:
>         |-- high: NO
>         |-- normal: YES
> |-- rainy:
>     |-- windy:
>         |-- TRUE: NO
>         |-- FALSE: YES
> ```

Using this decision tree:

- If weather conditions are sunny, cool, normal humidity, and windy, the game could be played (YES)
- If conditions were sunny, cool, high humidity, and windy, it could not be played (NO)

Note that these specific cases aren't in the original table, yet the algorithm can classify them.

### The Learning Algorithm (Decision Tree Induction)

The process of building a decision tree from data is called **decision tree induction**. Here's the essence of the algorithm:

1. Start with the root node representing the entire dataset
2. Construct the tree recursively by splitting nodes into two or more child nodes
3. Each split creates partitions of the parent node's dataset
4. To split data at a node:
    - Select an attribute based on a specific measure
    - The measure aims to minimize randomness in data distribution across partitions
    - Common measures: information gain, gain ratio, or Gini impurity
5. Once an attribute is associated with a node, it won't be considered in the node's children
6. Continue splitting until a stopping criterion is met (e.g., all tuples at a node belong to the same class)

At each node, the algorithm:

1. Uses a measure to determine the best attribute for splitting
2. Splits the dataset into sub-nodes
3. Recursively repeats for sub-nodes until stopping criteria are met

> [!info] Well-known Decision Tree Algorithms Popular decision tree induction algorithms include:
> 
> - ID3
> - C4.5 (also known as J48)
> - CART

## Other Classifiers

While decision trees have advantages (simple to understand, handle both numerical and categorical data), they also have disadvantages:

- Possibility of overfitting (accurate for training data but not for new data)
- Often less accurate than more complex models

Other types of classifiers include:

- [[Bayesian Classifiers]]
- [[Lazy Learners]]
- [[Linear Classifiers]]
- [[Support Vector Machines]]
- [[Rule-based Classifiers]]
- [[Pattern-based Classifiers]]

## WEKA Platform

> [!important] WEKA Introduction WEKA is an open software platform that allows the use of data mining tools. It's developed by the Machine Learning Group at the University of Waikato, New Zealand, and is issued under the GNU General Public License.

### Using WEKA for Classification

The lecture notes provide a step-by-step guide for using WEKA to solve a classification problem:

1. Go to https://ml.cms.waikato.ac.nz/weka (WEKA's main page)
2. Download WEKA (installation files available for Windows, Mac, Linux, and other platforms)
3. Install WEKA following the license agreement and default settings
4. Open WEKA from the Start menu and click on "Explorer"
5. Click on "Open File"
6. Locate and open sample .arff files (ASCII files describing instances with shared attributes)
    - Navigate to Weka-3-9-6/data under the installation folder
    - Open "weather.nominal.arff" (contains the weather example data)
7. Click on "Classify"
8. Click on "Choose" and select "J48" (the C4.5 decision tree algorithm implementation)
9. Click on "Percentage split" (default 66% training, 34% testing)
10. Click "Start" to run the classification
11. View classification results in the results pane
12. Visualize the decision tree by right-clicking on the item under "Result list" and selecting "Visualize tree"

> [!note] WEKA Results In the example, the accuracy of the model was 40% (see line "Correctly Classified Instances")

## Related Concepts & Potential Internal Links

- [[Supervised Learning]]
- [[Unsupervised Learning]]
- [[Classification Algorithms]]
- [[Decision Trees]]
- [[Information Gain]]
- [[Gain Ratio]]
- [[Gini Impurity]]
- [[Overfitting]]
- [[Model Validation]]
- [[Training and Test Sets]]
- [[WEKA Platform]]
- [[Data Mining]]
- [[Machine Learning]]
- [[J48 Algorithm]]
- [[ARFF Files]]

---

> [!tip] WEKA Resource For more in-depth exploration of WEKA, you can visit their official website and documentation at https://ml.cms.waikato.ac.nz/weka