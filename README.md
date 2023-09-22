# Coding Task AgriAku
Imagine that you are being approached by the researchers to help them analyzing the raw data.
## Question 1.
Before you build any model, you want first to explore the raw data. What kind of analyses you would do? What kind of data pre-processing you would do? Please explain your logic and show the result of your preparatory analyses. [Point 7]
<br><br><u><b>Answer.</u></b><br>
- What kind of analyses I would do?
  * **Exploratory Data Analysis (EDA)**: Before diving into any specific analysis, it's crucial to explore our data to gain a better understanding of its characteristics. EDA involves **summary statistics** (to describe central tendency and spread of our data) and **data Visualization** (create various plots and charts). In this case, I did research on data understanding about why all of the features' values are always negative, how distribution of each feature looks like, how one feature relates to another, etc.
  * **Descriptive Statistics**: Continue to analyze our data using statistical techniques, but only using visualization for to do outlier checking, distribution of each feature, and relationship between variables.
  * **Correlation analysis**: Examine correlations between variables to understand how they are related, for example like how all of the features are highly positive correlated to another, except for the target data (since it's label encoded).
  * **Classification Analysis**: Efficiently pick up some of classification algorithms and techniques such as logistic regression, decision trees, or support vector machines. Also, use techniques like cross validation to choose our best base model.
- What kind of preprocessing I would do?
  * **Feature Engineering**: Create new features or transform existing ones to make the data more suitable for modeling. In this case, I use one-hot encoding, standardization, and add new feature, such as "Ratio of MIP : NP".
  * **Handling Categorical Data**: Convert categorical variables into numerical format through techniques like one-hot encoding or label encoding.
  * **Feature Selection**: Choose the most relevant features for your analysis, potentially using techniques like feature importance and correlation analysis.
  * **Data Splitting**: Split your dataset into training and testing sets for model evaluation and training.
## Question 2.
Can you build a Machine Learning model (not Artificial Neural Network) to categorize the alcohol molecule given readings from the electronic nose? (Please consider the MIP: NP ratio as one of the features as well) Please justify your choice of algorithm and walk us through your logic as you develop the model. What is the accuracy, precision, and recall of the model? [Point 10]
<br><br><u><b>Answer.</u></b><br>
Looking at all the problems contained at this dataset, I hypothesize that we need non-linear models, like Decision Tree and Random Forest. To be more concise, I also use standardization which most of cases, it can give the best performance on model. However, it seems that my previous hypothesis is right, as Logistic Regression and Support Vector Machine don't give good performance. Therefore, I use Random Forest to be my chosen model, since its performance is very good.

Surprisingly, Random Forest algorithm give 100% accuracy, 100% precision, and 100% recall on test dataset.
## Question 3.
Can you build an Artificial Neural Network (ANN) model to categorize the alcohol molecule given readings from the electronic nose? (Please consider the MIP:NP ratio as one of the features as well) Please justify your choice of algorithm and walk us through your logic as you develop the model. What is the accuracy, precision, and recall of the model? [Point 10]
<br><br><u><b>Answer.</u></b><br>
The reason is the same as before. In brief, we want a model that's non-linear. We know that ANN has activation function which gives our output to be non-linear.

Thanks for that, we get the same result which gives the best overall performance on our dataset. ANN give 100% accuracy, 100% precision, and 100% recall on test dataset**.
## Question 4.
You were asked to convert your model to API, so that the researchers can perform the alcohol identification in real-time. How would you do this (you don’t have to make the actual API)? [Point 8]
<br><br><u><b>Answer.</u></b><br>
1. **Choose a framework and hosting**: Select the software framework (e.g., Flask, FastAPI) for building your API and choose a hosting platform (e.g., AWS, Google Cloud) to run it.

2. **Serialize and load the language model**: Prepare your pre-trained language model for deployment by serializing it into a format that can be loaded quickly when the API starts.

3. **Create an API to receive requests**: Develop the API with endpoints that can receive incoming requests. Define the expected input format (e.g., JSON).

4. **Process input, use the model for identification**: In the API, parse and preprocess the incoming data (e.g., text input). Utilize the loaded language model to perform alcohol identification on the input.

5. **Format and send back results**: Format the model's output (e.g., identification results) into a structured response (e.g., JSON) and send it back to the requester.

6. **Test, deploy, and maintain the API with security and monitoring**: Thoroughly test the API, deploy it to a production environment, and ensure it's secure (e.g., rate limiting, input validation) and monitored for performance, errors, and usage patterns. Continuously maintain and update the API as needed.
