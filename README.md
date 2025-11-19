# MIST4610 Group Project 2

## Team Name: 
15058_Group3

## Team Members:
1. Aidan Combs [@acombs122](https://github.com/acombs122)
2. Joey Maitran [@Jbm39435 ](https://github.com/Jbm39435)
3. Praneet Venigalla [@pxv24](https://github.com/pxv24)
4. Cameron White [@cfw10166](https://github.com/cfw10166)
5. Mariam Zaman [@mad1amz](https://github.com/mad1amz)

## Dataset Description: 
For our project, we chose the Food Access Research Atlas, which we obtained from the US Data Gov website (https://catalog.data.gov/dataset). This specific version of the Food Access Research Atlas was dated from 2019, and contained 72531 rows and 121 columns depicting each census tract in the United States, and maps certain indicators of food access to these tracts. The data includes a host of variables, 147 to be exact, touching on various demographic points, like race, vehicle ownership, age, and community characteristics like median family income, whether or not a tract was urban, and poverty rate. A lot of the variables were also interactions between two or more of these variables, like “lakids10,” which depicted the number of children that were deemed low access by being 10 or more miles away from the nearest supermarket. Generally, there was also another variable that compared this number to the overall tract population, which in the case of the “lakids10” variable, was aptly named “lakids10share.” Some variables were also binary values, like “LA1and10,” which depicted whether or not a specific tract was considered low access at 1 mile for urban areas and 10 miles for rural areas. These variables generally acted as “flags” for the data, meaning that these variables were supposed to indicate whether or not the tract would be classified a certain way. The dataset tested access at a variety of different levels, as some variables tested for low access at a ½ mile distance instead of 1 mile in urban areas, and at a 20 mile distance instead of a 10 mile distance for rural areas. It is also worth noting that many of these rows had a lot of NULL values, as some of these variables didn’t apply to that specific census tract. This was something that, as described later, we needed to address in order to get the most accurate and useful insights from this dataset. Due to the vast amount of data that this dataset collected, there are various types of data that are represented, including strings (state, county), integers, and decimals (essentially everything else). Overall, this dataset gave us a lot of insight into the state of food access in the United States, which provided us with a wide foundation to structure our analysis on.

## Question 1: What percentage of low access areas are also low income? 
This question examines the intersection of food access and economic disadvantage. In our dataset, “low access” refers to census tracts where a significant portion of the population lives far from supermarkets or large grocery stores. “Low income” means tracts where the tract's poverty rate is 20% or greater. Understanding the overlap between low-income communities and low food access is important because it highlights food deserts which are areas where residents may struggle both economically and geographically to obtain food. 

These visualizations depict an interesting association between low income and low access areas. A common misconception that some hold is that low access areas simply exist in areas where there is less material wealth. This visualization indicates that this relationship isn’t so cut and dry; as the first graph depicts, certain regions, like the western and northeastern United States, depict low-income and low-access occurring a little bit more independently. These areas have many dots indicating a low ratio between low income areas to low access areas, which means many low access areas exist that may not be considered low income. Intuitively, this makes sense. The increased cost of living in these spaces means that more people may make more money, but despite this, food deserts still exist in those spaces. This means that being low income and having low access to sufficient nutritious food aren’t 100% correlated. However, there are also many areas that have, especially in the southeast and midwest, ratios that are close to 1.0. This means that a lot of areas in those regions are both low access and low income, indicating that these two ideas are more heavily correlated in these regions. 

This contrast is important, as it suggests that food deserts, or areas that are both low access and low income, occur for different reasons in different areas of the country. Therefore, blanket federal legislation may be unable to address this issue, and may require regional-based solutions and additional analysis/investigation to solve the issue. 

<img width="1031" height="644" alt="image" src="https://github.com/user-attachments/assets/137555e1-9810-44cc-ad54-286c9d66f7aa" />

From the map, we can infer that a notable percentage of low-access census tracts are not also low-income. Large sections of the South and Midwest show ratios close to 0, (being blue) so there is a higher proportion of low acces that are not low income. While some regions, like the West, show low-income and low-access correlation. 

<img width="1036" height="586" alt="image" src="https://github.com/user-attachments/assets/2ee28710-8c9a-4100-9772-fac4d2ffb6d9" />

The tree map further depicts the ideas touched on in graph 1, as it demonstrates the ratios of low income areas to low access areas by state. Most of the states with a low ratio are in the aforementioned regions of the northeastern or western United States, further demonstrating the earlier point of being low income and having low access aren’t 100% correlated. However, this graph points out one notable exception: Iowa. There may be some unique conditions specific to Iowa that causes this, which may be something to explore further. We can conclude that while the ratio of low-income to low-access areas varies by state, the majority of states display moderate to high overlap (light to dark blue). This indicates that a significant portion of low-access areas across the country are also low-income. Only a small number of states show low overlap, suggesting that nationally, poverty is a major contributing factor to food access issues. 


## Question 2: Is there a correlation between the amount of SNAP benefits and low-income and low-access areas?
This question examines how SNAP benefits relate to the likelihood that a census tract is both low-income and low-access. This question helps us understand why certain communities are more likely to experience both low income and limited food access. Understanding these relationships can highlight the factors contributing to food deserts. This makes the question important for reasons like identifying vulnerable communities, knowing where to build food resources, showing the disproportionate impact on marginalized groups, etc. 

<img width="1035" height="801" alt="image" src="https://github.com/user-attachments/assets/52c2141b-9709-4bab-8904-e50f80b81f8b" />

Our polynomial regression analysis of SNAP-participating households in low-access areas shows a remarkably strong relationship with the number of low-income/low-access tracts at the county level. With an R-squared value of 0.9088 and a p-value below 0.0001, the model explains over 90% of the variation, indicating that SNAP housing is one of the most powerful predictors in our dataset. The nonlinear trend demonstrates that as SNAP housing increases, LILA tracts grow at an accelerating rate, suggesting that structural poverty compounds food access challenges. Counties with high SNAP participation tend to experience disproportionately more food-desert conditions, reinforcing the conclusion that economic need is a primary driver of low-income, low-access classifications.

<img width="1046" height="633" alt="image" src="https://github.com/user-attachments/assets/9aa67533-7c93-4d91-b22d-3d8748dd495e" />

By normalizing SNAP-participating households in low-access areas by total housing units, we removed the bias caused by differences in county population. Even after this adjustment, the relationship between SNAP participation and LILA tracts remained extremely strong, with an R-squared of 0.9086 and a p-value under 0.0001. Number of housing units has little effect on number of LILA tracts within a county. This demonstrates that the correlation between number of SNAP households and number of LILA tracts in a county is not skewed by overall population. 

## Data Manipulation
We didn’t modify, remove from, or add to our dataset in any way, even by way of reformatting or standardization. It is also worth noting that, to the best of our knowledge, this data doesn’t have any redundant, inaccurate, or low-quality data as well. Due to the scale and highly specific nature of the dataset, it is next to impossible for us to validate the accuracy of the data. However, due to the reputable source that compiled this dataset, we can assume that the data is largely accurate. 

# Tableau Packaged Workbook
The packaged workbook containing the visualizations is attached to this repository.

