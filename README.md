# Predicting Spotify Songs Popularity Before their Release

This project was developed as part of the Advanced Analytics Edge class at MIT. It is a collaborative effort by team members [Maxime Wolf](https://www.linkedin.com/in/maxime-wolf/), [Sanya Chauhan](https://www.linkedin.com/in/sanya-chauhan/), [Vidushi Gupta](https://www.linkedin.com/in/vidushi-gupta07/), and [Xidan Xu](https://www.linkedin.com/in/xidan-xu/)

## Objective

There are two main objectives of the project: one, to predict the potential popularity of songs before their release using Spotify data and song attributes; second, similar songs are generated based on features like danceability, tempo, and musical characteristics by clustering songs using intrinsic features, tailoring recommendations to user preferences.

## Final Product - Graphic User Interface Demo

https://github.com/maxime7770/Analytics-Edge/assets/58089609/c75f0fce-b9b4-4ce9-bf39-c60735d04416

## Data, Preprocessing, and EDA

Utilizing the ‘Spotify 1 Million Tracks’ dataset, exploratory data analysis was conducted, focusing on genre distribution, numerical attribute analysis, and popularity metrics. Feature selection analysis involved Principal Component Analysis (PCA), Lasso Regression, and Random Forest models to identify influential attributes.


## Analytical Techniques

### Regression to Predict Popularity

Various regression techniques, including XGBoost, Random Forest, AdaBoost, Linear Regression, Generalized Linear Models, K-Nearest Neighbors, and Support Vector Machines, were explored for predicting song popularity. The results are shown below. An ensemble method (training a neural network on the stacked predictions) was used to get the final prediction. As seen in the table below, XGBoost performs the best compared to other models. 

| Model                    | MAE      | R2     |
| ------------------------ | -------- | ------ |
| XGBoost Regressor        | 0.73632  | 0.5462 |
| Random Forest            | 0.99698  | 0.2545 |
| AdaBoost                 | 1.04349  | 0.1987 |
| Linear Regression        | 0.80339  | 0.4715 |
| Generalized Linear Model | 0.91371  | 0.3837 |
| K-Nearest Neighbors      | 0.78927  | 0.4800 |
| Support Vector Machine   | 0.75059  | 0.5011 |
| Ensemble Method using NN | 0.722885 | 0.5578 |

Ensemble methods were used to average out the predictions from the models and accordingly display one predicted value for popularity. Specifically, we use a Neural Network model trained on the stacked predictions from the previous models. This new approach leads to an improvement in the MAE and the R2 scores. It is also better than standard ensembling methods, such as taking the average of the predictions.

### Clustering and Song Recommendation
k-means clustering is applied with k=60, based on song features and track name embedding. Using PCA, the clusters in 2D are visualized. The song similarity clustering identifies a song's cluster and suggests the three closest songs based on Euclidean distances.

### Feature importance
XGBoost’s force-shape plot is used to illustrate the impact of different song features on the predicted popularity score. Specifically, it shows the features contributing to an increase or decrease in popularity score.

## Impact

- The culmination of our project was presented in an interactive Streamlit application, designed to offer both ease of use and insightful analytics for predicting song popularity.
- A unique feature of the app is its transparency in model workings. It provides a detailed breakdown of each model's prediction process, enhancing user understanding and trust in the system.
- The impact of this project extends far beyond its technical achievements. This tool offers artists and record labels a data-driven approach to gauge potential audience reception, enabling them to make more informed decisions about song production and marketing strategies. It provides a predictive lens through which artists can anticipate market reception, potentially influencing their creative decisions. For the music industry, this represents a significant step towards harnessing the power of data analytics, blending the art of music with the science of data to better navigate the ever-evolving landscape of audience preferences and market trends.

## For more details
Read the detailed report and presentation deck [here](https://drive.google.com/drive/folders/1SBUQMDE3O4p_TxhOoEk5k6bTXMk4u897?usp=sharing).
