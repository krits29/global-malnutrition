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
