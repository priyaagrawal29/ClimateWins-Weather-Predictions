# ClimateWins-Weather-Predictions
## Project Summary
This project involves the the use of machine learning algorithms to predict the effects of climate change in Europe for ClimateWins, a fictional European non-profit organization. Three supervised machine learning algorithms (K-Nearest Neighbour, Decision Tree, and Artificial Neural Network) were used in this project to predict days with pleasant and unpleasant weather at 15 weather stations in Europe. The objective of this project is to determine which algorithm would best predict future weather.
## Key Questions
- How is machine learning used? Is it applicable to weather data?
- Are there any ethical concerns specific to this project?
- Historically, what have the maximums and minimums in temperature been?
- Can machine learning be used to predict whether weather conditions will be favourable on a certain day?
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
## Techniques
The following techniques were used in this project:
- Data cleaning
- Data scaling
- Gradient descent
- K-Nearest Neighbour
- Decision Tree
- Artificial Neural Network
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

## Results and Recommendations
- The KNN algorithm has the highest accuracy rate of the three supervised machine learning algorithms with an accuracy rate of 89%.
- Additionally, KNN's accuracy rate is significantly higher than the accuracy rates for the Decision Tree and ANN algorithms.
- To make weather predictions in Europe, ClimateWins should use the KNN algorithm.
## Contact
If you would like more details about the project, or if you have any questions, please feel free to contact me through [LinkedIn](https://www.linkedin.com/in/priya-agrawal-0929) or [email](mailto:priya.agrawal0929@gmail.com).
