# Wine-Variety-Prediction
Predicting Wine Variety based on Wine Reviews

> Dataset is taken from [kaggle](https://www.kaggle.com/zynicide/wine-reviews) : (*HOWEVER, this repository consists of a different train and test set as it is required for a submission*)

## The Wine Land

> This dataset is an imbalanced dataset consisting of over 28 varieties of wine and *82,687* reviews of different wines

### Prediction of wine variety

    * Model used : SVM classifier
    
    * Features used for training: Columns `review_description` and `review_title`
    
    * Accuracy attained: 96.3% on the training set
    
    * Submission test set with predicted varieties is *submission.csv*
    
    * Parameters Used (Hypertuning): `C=1, kernel='linear'
    
### Insights from Data

1. Correlation coefficient between Price and Points is 0.44, signifying moderate strength. The scatter plot clears shows a positive direction

![ScatterPlot](scatter_plot_point_price.png)

2. The top rated wineries, countries and varieties are

| Countries        | Wineries           | Varieties  |
| ---------------- |:------------------:| -----:|
| England          | Araujo             | Nebbiolo |
| Australia        | Ovid               | Gruner Veltliner |
| Germany          | J.L. Chave         | Champagne Blend |

![Country by ratings](top_countries_rating.png)

3. The graph of countries by review is as follows:

![Country by reviews](country_review_count.png)

4. The notion that top varieties of wine come from the topmost wineries is possibly false as either of the top 3 rated varieties of wine are not grown in the top rated winery "Araujo"

5. Most number of anonymous reviews have been registered on wines originating from the USA

![Country by reviews](anon_review_count.png)


# Limitations of the code

* The SVM algorithm is extremely inefficient when the input data exceeds a certain dimension. This dataset consists of mostly string columns, which cannot be used as an input to the model, hence converting each string to a vector using encoding or tokenization shoots the dimensionality of the data to such an extent that using it for training becomes computationally expensive

* I have usef IF-IDF for vectorizing the `review_description` column, limiting it to a maximum of 15,000 features.

* Due to restrictions in computational power, the other feature columns could not be considered, which would have been a more practical and realistic scenario to consider and implement.
