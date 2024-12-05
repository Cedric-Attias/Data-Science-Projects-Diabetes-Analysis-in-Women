# Analysis of Risk Factors for the Onset of Diabetes in Women

The primary goal of this analysis is to explore and understand the factors contributing to diabetes
onset among female patients using a comprehensive dataset of diagnostic health measurements.
This focus is especially important given the historical underrepresentation of this demographic in
medical research and clinical trials. Women possess unique physiological characteristics and risk
factors that differ from men, yet many studies have traditionally generalized findings across
genders without considering these differences. This often results in a lack of tailored healthcare
recommendations and less effective prevention strategies.
By centering our analysis on data from female patients, we aim to fill a critical gap in diabetes
research, particularly in the context of diabetes. This includes:

    ● Identifying trends and patterns in the health measurements of women diagnosed with diabetes compared to those without the condition.

    ● Determining which diagnostic features, such as glucose levels, BMI, and blood pressure strongly correlate with the likelihood of developing diabetes.

    ● Exploring the relationship between family history, as represented by the diabetesPedigreeFunction, and diabetes risk within this dataset.

By answering these questions, this analysis seeks to contribute valuable insights to improve
healthcare strategies and outcomes for women.

# Objectives

The primary goal of our analysis is to use a detailed dataset of diagnostic health measurements to explore the health determinants that contribute to the onset of diabetes in female patients. 

# Data source

The dataset is an Open Data set sourced from Kaggle.com. You can access the data here (https://www.kaggle.com/datasets/hasibur013/diabetes-dataset). The dataset offers medical diagnostic measures for 768 female patients in order to analyze and predict the onset of diabetes based on a number of health characteristics. The dataset is organized, with rows representing specific patients and columns with attributes indicating their health indicators.

The dataset is especially significant since it contributes to the research on the correlation between diabetes risk and physiological and demographic parameters, offering a more profound comprehension of trends, risk factors, and the onset of diabetes on female patients, a demographic that is typically underrepresented in medical research. By offering gender-tailored insights, the dataset strengthens the influence of predictive analytics in medical research, assists in developing customized healthcare policies, and offers practical guidance for early diagnostic and intervention initiatives.

# Analysis

During the analysis of the dataset, we encountered several challenges, each of which was addressed using specific techniques to ensure the reliability of the findings.

The dataset has only 768 subjects, 268 of whom have diabetes, which is a relatively small sample size for analyzing the risk factors of the onset of diabetes and may limit the ability to robustly generalize the findings. To address this issue, we did not drop any missing or zero values to ensure the dataset remains meaningful and closely reflects the real-world distribution.

Several features including SkinThickness, BloodPressure, Glucose and Insulin contain a number of zero values, which are regarded as missing data since they are physiologically impossible. These zero values are replaced with meaningful surrogate values in order to minimize bias. For example, zero values in the Insulin column are replaced with the mean of the non-zero insulin values. Zero values in the BMI column are replaced with the median.  For BloodPressure and SkinThickness, the mean values of each age is used to replace the zeros, and for Glucose, we classify the data by the Outcome and replace the zeros using the mean of each category.

Outliers were found in factors like SkinThickness and Insulin. If ignored, these outliers have the potential to skew the analysis, weaken model accuracy, and yield inaccurate conclusions. A combination of visualization and statistical methods was used to systematically identify and handle these outliers.  By visualizing the data distribution, we used boxplots, histograms, and scatterplots to identify abnormalities. Besides, we also used the Interquartile Range (IQR) to identify and handle these outliers. These methods improve the reliability of the data while maintaining its integrity, minimizing the impact of extreme values, and preserving real-world applicability of the dataset.

Class imbalance is another challenge because the distribution of diabetic and non-diabetic cases is uneven, especially the dataset contains more non-diabetic cases than diabetic cases, which makes it difficult for machine learning models to work effectively on the minority class. In order to address this challenge, we used approaches including recall and feature weighting to ensure that the model does not overlook diabetic cases while preserving overall performance.

# Conclusions

Data exploration, correlation analysis, feature importance analysis, and clustering were used in the analysis to discover details on diabetes risk. We used statistical summaries, outlier detection, and visualizations to compare diabetic and non-diabetic groups. Correlation analysis and univariate logistic regression were then used to analyze associations and predictive power.  Methods like ANOVA and SVM were used to assess feature importance, and K-Means clustering identified patient subgroups with similar health profiles, enabling tailored interventions. 

Based on the results of correlation analysis and feature importance analysis, several key findings about the influencers of diabetes were obtained. Across all approaches, Glucose was consistently ranked as the strongest predictor, indicating its importance as a primary indicator of diabetes risk and highlighting its critical diagnostic basis. BMI was ranked as the second most influential attribute. This further confirms the connection between body weight and metabolic health, especially when combined with other features such as Glucose or Age.

DiabetesPedigreeFunction was less influential as a standalone factor but highly relevant in a multivariate context, emphasizing the significance of family history and genetic predisposition in determining diabetes risk. Pregnancies and Age were shown to have significant standalone impact and were associated with a higher risk of diabetes. However, in more complicated models, their significance diminished, indicating that they can be regarded as secondary factors. Features like BloodPressure, SkinThickness, and Insulin are less correlated to diabetes but play a role in more complex settings.

These results highlight the significance of using secondary predictors such as DiabetesPedigreeFunction and Pregnancies to improve model performance while prioritizing Glucose and BMI as key influencers in diabetes prediction models. Pairwise interactions, like Glucose and BMI, demonstrated that combining attributes enhances predictive power and highlighting the importance of multivariate techniques in creating reliable diabetes risk models. 

Besides, K-Means Clustering was used to detect patterns and classify individuals into different health profiles according to attributes such as family history, BMI, and glucose. These clusters offer a thorough evaluation of diabetes risk, allowing for more focused screening along with effective interventions for those at greater risk. Through these analytical approaches, it provides a helpful foundation for comprehending and managing the diabetes risk in women.

# Files
1) Jupyter notebook containing detailed code and explanation of results
2) Report write up for course project
