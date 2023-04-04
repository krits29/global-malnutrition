# Analysis of Malnutrition Around the Globe

Malnutrition is a universal problem that threatens progress and limits global development. It
splits into two broad subgroups: (1) undernutrition (includes stunting, wasting, and underweight)
and (2) overweight, obesity, and diet-related non-communicable diseases. All types of
malnutrition lead to poor health outcomes and are correlated with higher death rates.

Undernutrition, specifically, explains forty-five percent of deaths among children under five.
Moreover, many factors outside of poor diets, such as food insecurity and political situations, can
cause malnutrition. The social determinants and disproportionate impact of malnutrition make it
a global health issue. Proper nutrition is vital for good health, and due to changing infrastructure
and technological improvements, some countries are experiencing a double burden of
malnutrition. It is imperative to understand which countries are most impacted by malnutrition;
future solutions and policy changes can target those populations to begin limiting its impact.


### Summary of Research Questions
1. In which countries are the forms of malnutrition (stunting, wasting, overweight, and
underweight) most prevalent? Are there regional or income-level similarities between
these countries?


After plotting the top ten percentages for each form of malnutrition, we found that most
of the countries tend to have lower income classifications, like 0 (low income) or 1
(low-middle income). Also, percent stunting (low height-for-age), underweight (low
weight-for-age), and wasting (low weight-for-height) tend to be most prevalent in
Sub-Saharan Africa and South Asia, while percent overweight (high weight-for-height) is
greatest in northern Africa.


2. Which countries have the highest and lowest rates of malnutrition, and how do the costs
of a healthy diet vary across these countries?


India has the highest average malnutrition of 77 percent, and Germany has the lowest at 5
percent. Furthermore, Senegal, Australia, Azerbaijan, Kazakhstan, Moldova, and Belize
have the lowest cost of a healthy diet (2 PPP dollars).


3. Can we train an accurate model to predict the malnutrition trends of a country based on
data such as income classification or location?


The mean accuracy of the multi-layer perceptron classifier was about 0.95, which varied
based on training/testing data. The tree mean-squared-error (MSE) was around 30 and the
MLP mean-squared-error was about 4.


### The Dataset

[Malnutrition Across the Globe](https://www.kaggle.com/datasets/ruchi798/malnutrition-across-the-globe?select=malnutrition-estimates.csv)


[Cost and Affordability of Healthy Diet](https://www.fao.org/faostat/en/?#data/CAHD)


For the purpose of this project, we used the Malnutrition Across the Globe dataset from Kaggle.
This data is from UNICEF, WHO & World Bank’s Joint global database and seeks to measure
country-level child malnutrition trends using 4 key indicators – wasting, stunting, underweight
and overweight. The data presents the percentage of children from 0-59 months (under 5 years
old) belonging to each weight category. Each row in this dataset represents a country and
information such as income classification and the size of the under 5 years old population is
included.


The second dataset that we used for the purpose of this analysis is the Cost and Affordability of a
Healthy Diet dataset from the Food and Agriculture Organization of the United Nations (FAO).
The dataset contains estimates of indicators regarding each country’s physical and economic
access to the most inexpensive local foods to meet healthy diet requirements. The cost is given in
purchasing power parities (PPP) to eliminate differences in price levels between countries. This
dataset has clear description and standards for its metadata. For our analysis it is important to
understand the following indicators:

*Percentage of the population unable to afford a healthy diet*
  
> This indicator shows the percentage of the population unable to afford a healthy diet. A healthy diet is deemed unaffordable when its cost goes over 52% of household income.
  
  
*Cost of a healthy diet*
  
> This indicator displays the cost of purchasing the most inexpensive locally available food to meet dietary guidelines per person per day.


Retrieving these datasets is straightforward and accessible. For the malnutrition dataset, we
downloaded country-wise-estimates straight from Kaggle as a csv (we did not use the second
dataset from Kaggle in our analysis). The cost dataset had options to filter down the data and
choose subsets of the data. For this project, we downloaded all data from the FAOSTAT website
as a csv and filtered it using Python as needed.


## Research Question 1

To determine where the forms of malnutrition are most prevalent, we plotted the ten countries
with the highest levels for each stunting, wasting, overweight, and underweight, colored by
income classification. Regardless, some limitations we need to consider are that the dataset did
not include data for every country (for instance, Russia and Canada were not in the sample).
Also, because it would be difficult to truly determine the percentage of any form of malnutrition
for an entire country’s under-five population, the percentages we plotted may not be exactly
correct.

The ten countries with the highest percentage of stunting (low height-for-age of the under-five
population) are Burundi, Timor-Leste, Bangladesh, Guatemala, Eritrea, Madagascar, Nepal,
Yemen, Malawi, and India. Out of these ten countries, 6 have an income classification of 0 (low),
3 have a classification of 1 (lower-middle), and one has an income classification of 2
(upper-middle). Looking at the graphs, it seems that stunting is higher in countries with a lower
income classification. We were surprised that most of these countries had stunting percentages
about 50%, implying that the majority of the under-five population has a low height for their age.
This reveals the overwhelming prevalence and impact of malnutrition in some countries.

![Plotted global malnutrition](https://user-images.githubusercontent.com/31025768/225978189-25d6df45-9b8b-492f-b591-77d12d262287.png)



## Research Question 2

For this question, our focus was comparing cost and affordability of healthy diets with malnutrition rates around the globe to determine possible correlations. First, we assessed the “Overall Malnutrition Rates” around the globe by looking at the average malnutrition across all categories. 

We found that the top 10 countries with the highest malnutrition rates are *India, Timor-Leste, Bangladesh, Yemen, South Sudan, Niger, Eritrea, Pakistan, Nepal, and Chad*.

<img width="1294" alt="image" src="https://user-images.githubusercontent.com/31025768/225980391-168221e7-3ddc-4af0-a2c9-f1e753e7e795.png">

On the other hand the 10 countries where malnutrition is least prevalent are *Germany, Japan, South Korea, USA, Singapore, Czechia, Samoa, Saint Lucia, Tuvalu and Kuwait*. 

<img width="1294" alt="image" src="https://user-images.githubusercontent.com/31025768/225980577-e413002d-9161-4291-8b46-4c3d7b9b1ccb.png">

Here, we can see that regionally, malnutrition seems to be most prevalent in South Asian and Sub-Saharan African countries. To deepen our analysis, we investigated how accessible healthy diets are across the globe and whether they correlate with malnutrition rates. We visualized the countries with the highest and lowest cost of diets.

<img width="1288" alt="image" src="https://user-images.githubusercontent.com/31025768/227321400-7909bde4-109e-4ea2-80dd-5d1daa93d409.png">

From these graphs we can see that the cost of diet may not necessarily correlate with malnutrition as countries in regions where malnutrition is prevalent also seem to have low costs; however, we can’t conclude that there is no correlation simply by looking at these graphs. 

<img width="1065" alt="image" src="https://user-images.githubusercontent.com/31025768/229890936-b0d4a9f0-9108-4ecb-944d-694fd7352c37.png">

<img width="1069" alt="image" src="https://user-images.githubusercontent.com/31025768/229891113-6357e085-c00d-4bd0-89c8-3224a67372b1.png">


As seen by these graphs, the percentage of the population unable to afford a healthy diet seems to have a stronger positive correlation with malnutrition than the cost of a healthy diet itself. As seen in previous charts, income level seems to be a factor in malnutrition rates, and so it makes sense that affordability plays a role here at a higher level than just cost per day. We don’t see much of a correlation between the cost of a healthy diet and malnutrition, but further analysis may be needed here to draw a conclusion. 

Overall the insights gained here can help us address larger societal issues such as poverty and unequal access to food resources. By investigating and comparing the systems in the countries with high rates of malnutrition with those of lower rates, we may propose solutions to mitigate the issue. 

## Research Question 3

In the last research question we wanted to train a model that would predict overall malnutrition rates based on given income levels, cost of healthy diet, and the percentage of population unable to afford a healthy diet in a particular area. To accomplish this, we used a library that would help us create a regressor model, since there were multiple numerical inputs. We utilized a decision tree regressor along with a multi-layer perceptron regressor. The reason we used neural networks was because it is better for interpreting many different features (inputs), as it creates multiple hidden layers which interpret all the different features better than a singular tree would. 


After splitting the data into 80% training and 20% testing data, we ran both the models which resulted in an average of 98% accuracy predicting overall malnutrition levels. Additionally, since we used a multi-layer perceptron, we were able to plot the partial dependence curves which show the features that played the largest role in determining the overall output (malnutrition levels) and at what numerical ranges they were most accurate.
Looking at the graphs, we are able to see the tendencies of the models and analyze any inconsistencies. For the decision tree partial dependence curves, we can see that as the input ‘Income Classification’ and ‘Cost of Healthy Diet’ increased, the accuracy of the model decreased. The feature that seemed to increase the accuracy of the tree model the most was the ‘Percentage Unable to Afford’ feature. However looking at the dependence curves for the multi-layer perceptron model, we can clearly see that the model was still taking time to learn towards the beginning input values, but soon was able to have exponentially increasing accuracies as the features’ data values increased. The consistency of the mult-layer-perceptron model as shown on the graphs also makes it a more preferred algorithm to utilize.


<img width="764" alt="image" src="https://user-images.githubusercontent.com/31025768/228343521-38b5f0b2-1eda-437b-9902-18bdb48136e6.png">

<img width="752" alt="image" src="https://user-images.githubusercontent.com/31025768/228343602-4d2a8bc5-31af-498b-8710-678d77f5fa99.png">

To answer our research question, we *are* able to create a machine learning model given specific numerical inputs of a certain area (income classification, cost of healthy diet, and percentage unable to afford) to predict overall malnutrition rates of that area with a high accuracy using advance ML models such as a multi layer perceptron and decision tree regressor. 
