# Machine Learning and Data Science Framework

**Framework**: Template of how to work through problems

## Our Framework

[Blog Post Field Guide](https://www.mrdbourke.com/a-6-step-field-guide-for-building-machine-learning-projects/)

1. **Problem Definition**: What type of problem are we trying to solve? (Un/Supervised, Classification, Regression, etc.)
2. **Data**: What kind of data do we have? Structured (spreadsheets) vs Unstructured (images, audio)
3. **Evaluation**: Define what success means for the model.
4. **Features**: What do we already know about the data? Numerical, Categorical, Derived
5. **Modelling**: Based on our problem and data, what machine learning model should we use?
6. **Experimentation**: Try each of the steps multiple times to get to where you want to be

## Types of Machine Learning Problems (1. Problem Definition)

**When NOT to use ML**: if hand-coded instructions work

### Supervised Learning

---

- You have data and labels
- "I know my inputs and outputs"
- ML tries to use data to predict a label
- If guess is incorrect, the algorithm corrects itself and tries again

Types of Supervised Learning:

- **Classification**: Predicting if a point of data belongs to one class or another
  - **Binary**: only 2 class options
  - **Multi-class**: more than 2 options
- **Regression**: Trying to predict a number or continuous number (number that goes up or down)

### Unsupervised Learning

---

- You have data, but **no labels**
- "I have inputs but don't know what the outputs are"
- The ML algorithm inspects the data and attempts to apply the labels
- **Clustering**: putting groups of similar data together

### Transfer Learning

---

- Leverages what one ML model has learned in a different ML model
  - Example: Using a model that has learned to predict car make/model off a picture to predict dog breed off a picture
- "My problem may be similar to a different problem"

### Reinforcement Learning

---

- Computer program makes decisions in a defined space with defined actions and helping it learn with reinforcement (rewards vs punishments)
- A good example is to make a ML model that can get the highest score in a game

## Types of Data (2. Data)

**Static**: Data does not change over time (CSV files are a good example). You want a lot of static data
**Streaming**: Data that is constantly changing over time (news headlines, stock prices, etc.)
**Structured**: Something you'd expect to see in a spreadsheet. All data is in similar format (rows and columns)
**Unstructured**: Video files, audio files, natural language

### Common Workflow

---

- Start with Static Data (CSV file)
- Import to Jupyter Notebook (tool used for ML projects)
- Explore data and us Pandas to do data analysis
- Make visualizations with matplotlib
- Create a machine learning model on the data with SciKit Learn
- If your model is great, you may switch to use streaming data in live deployment to keep the model current and accurate

## Types of Evaluation (3. Evaluation)

- "What defines success for the ML model?"
  - Could be meeting a bar of % accuracy on predictions
- Different types of metrics for different kinds of problems

**Classification**: Accuracy, Precision, Recall

**Regression**: Mean absolute error (MAE), mean squared error (MSE), Room mean squared error (RMSE)

**Recommendation**: Precision at K

## Features in Data (4. Features)

- What do we already know about the data

What is a Feature?

- **Features**: different forms of data within structured or unstructured data
  - Columns in a spreadsheet. Different attributes a single data point has
  - AKA feature variables because they are used as inputs to try to predict output(s) (target variables)
  - **Numerical**: numbers
  - **Categorical**: meaning one thing or another. Classification
  - **Derived**: when someone looks at data and creates a new feature by analyzing the existing features
    - The process of creating Derived data is called **Feature Engineering**
- Features are most useful when most of the data has that feature
  - **Feature coverage**: you want >10% of the data to have a feature in order to consider using that feature

## Modelling (5. Modelling)

### Splitting Data

---

- Split your data into three sets: Training, Validation, Test
  - A given data point should not be in multiple splits
- **Generalization**: The ability of a ML model to perform well on data it hasn't seen before

**Training Set**: Trains the ML model
  - Should be a randomly selected 70-80% split of the data

**Validation Set**: Used to do model tuning on the ML model
  - Should be a 10-15% split of the data

**Test Set**: Used to test the model and see how it will perform on real, unseen data
  - Should be a 10-15% split of the data

### Picking the Model

---

- Goes with training set of data

**Structured Data**: Decisions trees often work best here
  - Random forests
  - Gradient boosting algorithms like CatBoost and XGBoost

**Unstructured Data**: Deep learning, Neural Networks, and Transfer Learning work best

- Once you've picked a model, use the data (x) to train the model to try to predict a label (y)
- Try to minimize time between experiments when training data
  - Maybe start with a small part of the training set to begin
  - Could start with a faster, less complicated model to see how well it works

### Tuning the Model

---

- Try to improve the ML model by tuning it specifically for your data
- Usually done on the validation set, but can be done on the training set as well
- The kinds of tuning that can be done depends on the model that was chosen
  - Example: random forest can tune the number of trees, neural network can tune the number of layers
  - The things that can be tuned on a model are called **hyperparameters**

### Comparing the Model

---

- **Generality**: performance on data that the ML model hasn't seen before
- Not uncommon to see differences in performance on the Test set
  - **Underfitting**: ML performs drastically worse on the test set
  - **Overfitting**: ML performs significantly better on the test set
  - **Balanced (Goldilocks Zone)**: Model does a good job predicting

**Data Leakage**: When data from the test set leaks into the training set. This will lead to **overfitting** because the model has already seen the data it will be tested on
  - Fixes: make sure test data is completely separate, collect more data, try a less advanced model (rarely a problem, but can be a thing)

**Data mismatch**: When the test data is structurally different (different labels) from the training data the model was trained on. This leads to **underfitting** because the model hasn't learned how to predict structurally different data
  - Fixes: try a more advanced model, increase model hyperparameters, reduce # of features, train more'

### Experimenting With the Model (6. Experimentation)

- What have we tried? What else can we try?
- Try a new model
- Try changing input labels
- Try changing output labels

## Tools and Fields

### Data Science

---

- Data Science is a broad term that encompasses all 6 steps of the framework discussed above
- Tools:
  - **Jupyter Notebooks**
  - **Anaconda**

### Data Analysis

---

- Analyzing data that exists without trying to do anything with new data
- Encompasses steps 2-4 of the above framework
- Tools:
  - **Pandas**
  - **matplotlib**
  - **NumPy**

### Machine Learning

---

- Making ML models from data to predict other data
- Step 5 of the above framework
- Tools:
  - **TensorFlow**
  - **PyTorch**
  - **SciKit Learn**
  - **CatBoost**
  - **XGBoost**
