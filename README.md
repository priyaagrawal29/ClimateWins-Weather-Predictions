# ClimateWins-Weather-Predictions
## Project Summary
This project involves the the use of machine learning algorithms to predict the effects of climate change in Europe for ClimateWins, a fictional European non-profit organization. Supervised machine learning algorithms (K-Nearest Neighbour, Decision Tree, and Artificial Neural Network) and unsupervised machine learning algorithms (Hierarchical Clustering, Recurrent Neural Networks, Convolutional Neural Networks, Long Short-Term Memory, Random Forests, and Generative Adversarial Networks) were used in this project to predict days with pleasant and unpleasant weather at 15 weather stations in Europe. The objective of this project is to determine which algorithm would best predict future weather.
## Key Questions
- How is machine learning used? Is it applicable to weather data?
- Are there any ethical concerns specific to this project?
- Historically, what have the maximums and minimums in temperature been?
- Can machine learning be used to predict whether weather conditions will be favourable on a certain day?
## Project Goals
- Identify weather patterns that deviate from Europe's normal weather patterns
- Ascertain if there is an increase in frequency of unusual weather patterns
- Determine what weather conditions may look like over the next 25-50 years using current trends
- Identify the safest-to-live areas in Europe over the next 25-50 years
## Hypotheses
- If temperatures increase every year, then extreme weather events will also increase.
- Machine learning algorithms will accurately predict if the weather on a day is pleasant or unpleasant.
- The accuracy of weather predictions will differ for the European regions because of the differences in climate.
## Data
Datasets used for this project:
- [Temperature](https://s3.amazonaws.com/coach-courses-us/public/courses/da-spec-ml/Scripts/A1/Dataset-weather-prediction-dataset-processed.csv)
- [Pleasant weather](https://images.careerfoundry.com/public/courses/da-spec-ml/Scripts/A1/Dataset-Answers-Weather_Prediction_Pleasant_Weather.csv)
### Temperature Dataset
This dataset includes variables such as global radiation, snow, wind speed, temperature, and more for 18 weather stations in Europe from the late 1800s to 2022. The data was collected by the European Climate Assessment & Data Set Project.
### Pleasant Weather Dataset
This dataset contains data indicating if the weather on each date was pleasant or unpleasant for 15 weather stations in Europe from 1960 to 2022.
## Tools Used
- Python and Jupyter Notebooks: To write and execute code.
- Numpy: For numerical operations.
- Pandas: For data analysis, cleaning, and manipulation.
- OS: For connecting with the device's operating system.
- Matplotlib.pyplot: For creating various types of visualizations.
- Seaborn: For creating statistical visualizations.
- Scipy: For more complicated numerical operations.
- Sklearn: For running machine learning algorithms.
- Operator: For using more efficient functions.
- Mpl_toolkits: For creating more interactive visualizations.
- Plotly: For creating various types of interactive visualizations.
- Graphviz: For creating graph diagrams.
- Keras: For creating deep neural networks.
- Tensorflow: For creating and training neural networks.
- Time: For performing time-related functions.
- Scikeras: For using Sklearn with Keras/Tensorflow.
- Math: For giving access to standard mathematical constants and functions.
- Bayes_opt: For running Bayesian Optimization.
- PIL: For image processing and manipulation.
## Techniques
The following techniques were used in this project:
- Data cleaning
- Data scaling
- Gradient descent
- K-Nearest Neighbour
- Decision Tree
- Artificial Neural Networks
- Hierarchical Clustering
- Recurrent Neural Networks
- Convolutional Neural Networks
- Long Short-Term Memory
- Random Forests
- Generative Adversarial Networks
## Utilizing Machine Learning Algorithms
First, I scaled all the columns in the temperature dataset except for the "Date" and "Month" columns to remove large differences in the values. I used Gradient Descent to optimize the data which involved making many changes to the parameters to minimize the loss function. The iterations to the parameters brought the loss function closer to 0. Here is a visualization of the loss function, theta0, and theta1 for the mean temperature of Roma in 2020:

<img width="767" height="573" alt="image" src="https://github.com/user-attachments/assets/17fa2054-c2e2-48a8-b3be-f712a561f361" />

To determine which of the three supervised machine learning algorithms (K-Nearest Neighbour, Decision Tree, and Artificial Neural Network) would be the best one for ClimateWins to use to predict future weather, I started by testing the K-Nearest Neighbour (KNN) algorithm. For this algorithm, I split the data into training and testing sets, used a k value of 3, and ran the code. The following table shows the results of the KNN model along with the accuracy rates:

<img width="749" height="440" alt="image" src="https://github.com/user-attachments/assets/f31fd07d-ce6c-4070-8799-63485cafe0a6" />

Based on the results obtained from the KNN algorithm, it can be seen that the average accuracy rate of 89% is quite good and the accuracy rate of 100% for Sonnblick, a weather station, indicates that overfitting is likely happening.

Next, I tested the Decision Tree algorithm. For this algorithm, I split the data into training and testing sets and ran the decision tree classifier. The following image shows the decision tree that was generated:

<img width="707" height="690" alt="image" src="https://github.com/user-attachments/assets/3e877839-c2d3-433e-baa7-692f9ab73b33" />

For the Decision Tree algorithm, the accuracy for the training data is 46% and for the testing data is 47%. The decision tree generated is very intricate as it has too many branches and leaves and needs to be pruned.

Following this, I tested the Artificial Neural Network (ANN) algorithm. For this algorithm, I split the data into training and testing sets and created three ANNs with different hidden layer sizes, iterations, and tolerances. Of the three ANNs, the one with the best accuracy rates had an accuracy of 52% for the training data and 49% for the testing data. This ANN had hidden layer sizes of (100, 50, 25), max iterations of 500, and a tolerance of 0.0001. The following is an illustration of the confusion matrices for the training data for the ANN with the best accuracy rates:

<img width="975" height="595" alt="image" src="https://github.com/user-attachments/assets/02489074-f545-44fc-a0de-6eac577b025b" />

From supervised machine learning algorithms, I moved onto unsupervised machine learning algorithms. I used Hierarchical Clustering. For this algorithm, I reduced the data set to include data for only 2015 and then scaled the data. I created four dendrograms comparing the Heathrow and Budapest weather stations using the single, complete, average, and ward methods. I also created four dendrograms comparing all weather stations using the single, complete, average, and ward methods. The 2015 climate data was then reduced using Principal Component analysis and dendrograms were produced using the single, complete, average, and ward methods. The ward method produced clusters that were easy to differentiate between and the differences in the clusters may be due to different climate conditions at the different European weather stations. The following is an illustration of a dendrogram comparing all weather stations using the single method:

<img width="1660" height="661" alt="image" src="https://github.com/user-attachments/assets/0cb4cb07-309a-4e2c-ad6f-408a0218644e" />

Then, I used the Recurrent Neural Networks model. Prior to running this model, I removed all columns for Gdansk, Roma, and Tours from the temperature data set to match the pleasant weather data set, removed all columns for wind speed and snow depth since most weather stations did not have these columns, and created the Kassel_cloud_cover, Stockholm_humidity, and Munchenb_pressure columns by copying columns from nearby weather stations with similar climates. To run this model, I reshaped it, split the data into training and testing sets, created the Keras model, compiled the model, ran the model, and generated confusion matrices. I ran 12 tests on the model using different hyperparameters until the model converged (accuracy increased and loss decreased). The accuracy of the model was 25.4% and loss was 8.8765. The following image shows the final confusion matrix which recognized 7 out of 15 weather stations:

<img width="811" height="449" alt="image" src="https://github.com/user-attachments/assets/537e3575-cd3a-4326-8763-d2b70efc1209" />

I then used the Random Forests algorithm. To implement this algorithm, I reshaped the data, split the data into training and testing sets, ran the model, and obtained the feature importances of the whole data set, and of each of the top three most important weather stations (Kassel, Belgrade, and Valentia). The following image shows a bar chart with the feature importances for the whole data set:

<img width="648" height="600" alt="image" src="https://github.com/user-attachments/assets/201086ae-a46e-402e-a42d-c9d5941d03ec" />

To obtain optimized hyperparameters for the Random Forests model, I reduced the temperature and pleasant weather data sets to only include data from 2011-2021, reshaped the data, split the data into training and testing sets, then ran Grid Search and Random Search to see which one had the best score. I used the hyperparameters from the search method with the highest score to run the Random Forests model and obtain feature importances of the data set. Munchenb, Ljubljana, and Budapest were the top three most important weather stations, which was different than before optimization. The following image shows a bar chart with the feature importances of the data set from 2011-2021 after optimization:

<img width="689" height="599" alt="image" src="https://github.com/user-attachments/assets/ce7e51c3-b325-4813-9db3-59a8f575ff95" />

To obtain optimized hyperparameters for the Deep Learning model, I reshaped the data, split it into training and testing sets, ran Bayesian Optimization, ran the Recurrent Neural Networks model using the optimized hyperparameters, and generated a confusion matrix. The accuracy of the model after optimization was 8.3% which was lower than the accuracy before optimization. The following image shows the confusion matrix which recognized 14 out of 15 weather stations:

<img width="520" height="787" alt="image" src="https://github.com/user-attachments/assets/0ceb0195-e042-4907-9dc8-ac5255d2a132" />

The last algorithm that was used was Convolutional Neural Networks. For this model, I used a collection of photos which were separated into four categories: cloudy, rain, shine, and sunrise. I then compiled and ran this model, then tested to see how it would categorize a random number of photos.

## Results and Recommendations
Unsupervised Machine Learning Algorithms:
- The KNN algorithm has the highest accuracy rate of the three supervised machine learning algorithms with an accuracy rate of 89%.
- Additionally, KNN's accuracy rate is significantly higher than the accuracy rates for the Decision Tree and ANN algorithms.
- To make weather predictions in Europe, ClimateWins should use the KNN algorithm.

I generated three thought experiments that can be used to achieve ClimateWins' goals of using machine learning to predict the consequences of climate change in Europe:
- Identifying the safest places in Europe using Random Forests: Integrate data on sea levels, extreme weather events, and injuries and deaths due to extreme weather. Model will categorize regions by safety for the next 25-50 years.
- Predicting future weather conditions using LSTM: Obtain weather predictions for the next 25-50 years by training an LSTM model using past and current weather data including extreme weather event data.
- Identifying unusual weather patterns using Hierarchical Clustering: Current and past weather data and extreme weather event data can be used to identify any anomalies in weather patterns across Europe.

Of these three thought experiments, I recommend using the first one which will identify the safest places in Europe to live in within the next 25-50 years using Random Forests. I believe this thought experiment has the most potential because Random Forests prevents overfitting, it will not only fulfill ClimateWins’ goal of identifying the safest regions for people to live in within the next 25-50 years, but will also give an idea of which regions are affected the most by climate change, and it will likely produce the most accurate results as it will likely have the highest accuracy rate.
## Contact
If you would like more details about the project, or if you have any questions, please feel free to contact me through [LinkedIn](https://www.linkedin.com/in/priya-agrawal-0929) or [email](mailto:priya.agrawal0929@gmail.com).
