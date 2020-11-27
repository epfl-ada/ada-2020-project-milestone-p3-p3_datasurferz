# Title
# Abstract
Quality of life has become a very valuable factor, as a lot of research has been dedicated on improving humans' life standards. Recently, indicators such as HDI (Human Development Index) or customized indices like the OECD “Better Life Index” have emerged to account for other facets of life rather than the previously popular income factor (measured by GDP per capita). With this project we propose a novel well-being index called "Human Life Quality Index" (HLQI), which takes into account health, education, environment, life satisfaction, safety, food consumption and other feature in order to measure the overall quality of daily life of people in Greater London. To compute the HLQI we estimate the weights of each factor based on its relavance of quality of life and its correlation with the rest of the features. We will incorporate notably nutrition statistics and measure whether it is a good addition.   
# Research Questions
 Can we create a custom-made indicator to predict objective life quality at the ward level in Greater London?
 Does adding food factors (like food entropy, fibers) make an improvement (statistically important) to the our index?
 Can we estimate the weights of HLQI based on statistical models (such as principle component analysis) created with Greater London ward data?
# Proposed dataset
We want to incorporate various features collected in the dataset ward-atlas-data (https://data.london.gov.uk/dataset/ward-profiles-and-atlas) and aggregate them in the above factors. For instance we have these ideas to calculate them:
* education : namely, the GCSE scores (national test scores in england), Overall un-authorized absences in school 
* health : life expectancy, diabetes, obesity.. 
* jobs / work/life balance : income, unemployment rate, education-level for working group, unemployment benefit claims, 
* Safety factors: assault incidents attended by ambulances, robbery incidents, 
* Environmental factors: Annual mean of particle matters found, homes with access to green spaces
* Community : ethical diversity (will be calculated with demographics data)
We would incorporate different food features based on the Tesco dataset.
# Methods
# Proposed timeline
* By the end of week 12 : have the full data pre-processing done, have the total combined DataFrame we will employ for this project calculated and finalised
* By the end of week-end of week 12: done with correlation analysis and interaction factors. Have begun modeling and graphs
* By the mid-week 13 : Finished preliminary modeling. A first thorough analysis of the model. Finish the figure with the geographical map data
* By end of week 13: Determine which visualisations will be retained. Determine whether further extension and analysis need to be done on the dataset. 
* By mid-week 14: Finish the textual analysis. Post everything on the blog for the data-story. If time, begin the video. 

# Organization within the team
* Data processing - selecting the appropriate data features and structuring them as inputs of a statistical model
* Data analysis - using correlation techniques to analyse the data and obtain knowledge about the interaction of the factors
* Modelling - creating statistical tools that allow us to compute the weights of the factors
* Data Visualization - plotting the obtained correlation values as well as graphs that explain the results of our statistical model
* Analysis - provide a thorough anaylsis of our results and figures. Draw Conclusion from what we have done. 

We have yet to determine how we will split the tasks, but the way we usually work is that we have a beginning-of-the-week meeting to determine who is free to start advancing on the task. Then, once that person has reached a milestone, the next person takes up the work. And so forth. Here, since the imporant part to get us running is to do the data pre-processing, we will all actively contribute to this task. Once this is done, we will split up the work depending on our availabilities and interests. 

# Questions for TAs (optional)


# Stuff copied from Google doc:
1. Can we create a custom-made OECD indicator to predict objective life happiness at the ward level ? Does adding food factors (like food entropy, fibers) make an improvement (statistically important) to the OECD indicator ? Can we use machine learning techniques to find optimal weights that will result in the best OECD indicator representative of the wards ?

What is OECD ? 
Recently, indicators such as HDI (Human Development Index) or customized indicators like the OECD “Better Life Index” have emerged to account for other facets of life rather than uniquely income (measured by GDP per capita). For instance factors such as health, education, environment, life satisfaction, safety are now included to measure a “better” life.

How we proceed:
Normal OECD indicators include factors like: Housing, Income, Jobs, Community, Education, Environment, Civic Engagement, Health, Life Satisfaction, Safety, Work-Life Balance

We want to incorporate various features collected in the dataset ward-atlas-data (https://data.london.gov.uk/dataset/ward-profiles-and-atlas) and aggregate them in the above factors. For instance we have these ideas to calculate them:
education : namely, the GCSE scores (national test scores in england), Overall un-authorized absences in school 
health : life expectancy, diabetes, obesity.. 
jobs / work/life balance : income, unemployment rate, education-level for working group, unemployment benefit claims, 
Safety factors: assault incidents attended by ambulances, robbery incidents, 
Environmental factors: Annual mean of particle matters found, homes with access to green spaces
Community : ethical diversity (will be calculated with demographics data)
We would incorporate different food features based on the Tesco dataset.

Once we have these factors, we want to optimize the weights to obtain the best OECD index possible. However, we are not sure how to do that by using machine learning. We have an idea that we need to find an objective function but not exactly sure how we can do it. 

To validate our method, we would compare our OECD index to a known indicator called the HDI (Human Development Index). This is not part of the dataset we found but is easily calculated since it is the geometric mean of Life Expectancy, Expected years of schooling/mean year and median income. 

If we have time, we would want to implement a sort of “matching algorithm” as done in part 3 of homework 2 to evaluate whether incorporating an indicator of food would have an influence on our index. 

Our concerns:
Is this project of creating a life quality indicator too ambitious ? Or maybe it doesn’t use the Tesco dataset enough ? Would you have an idea or suggestions on how we could proceed to optimize our weights ? 

Otherwise, we have a similar but diluted project idea, that uses the Tesco dataset to find relevant food categories/consumption patterns correlated to health (using diabetes, obesity, life expectancy, ...). We could then use these factors to create a health index based on different food habits. Then, tune the weights of the different factors and create a map of general health over the wards of London.
