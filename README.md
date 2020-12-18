# The ALDI

You can find our data story [here](https://charlyneburki.github.io/The-ALDI/)

## Abstract
Quality of life has become a very valuable factor, as a lot of research has been dedicated on improving humans' life standards. Recently, indicators such as HDI (Human Development Index) or customized indices like the OECD “Better Life Index” have emerged to account for other facets of life rather than the previously popular income factor (measured by GDP per capita). With this project we propose a novel well-being index called "Advanced Life Development Index" (ALDI), which takes into account health, education, environment, life satisfaction, safety, food consumption and other feature in order to measure the overall quality of daily life of people in Greater London. To compute the ALDI we estimate the weights of each factor based on its relavance of quality of life and its correlation with the rest of the features. We will incorporate notably nutrition statistics and attempt to measure whether it is a good addition. 

We employ techniques as suggested in [Tools for Composite Indicators Building](https://publications.jrc.ec.europa.eu/repository/bitstream/JRC31473/EUR%2021682%20EN.pdf)

# Research Questions
 Can we create a custom-made indicator to predict objective life quality at the ward level in Greater London?
 Does adding food factors (like food entropy, fibers) make an improvement (statistically important) to the our index?
 Can we estimate the weights of ALDI based on statistical models (such as principle component analysis) created with Greater London ward data?
 Can we validate this data on subjective well-being datasets found online at both the ward and borough levels ?
 
# Proposed dataset
We incorporate various features collected in the dataset [ward atlas data] (https://data.london.gov.uk/dataset/ward-profiles-and-atlas) and aggregate them in the above factors. For instance we use the following (more detailed explanations in the p4 notebook):
* education : namely, the GCSE scores (national test scores in england), Overall un-authorized absences in school 
* health : life expectancy, diabetes, obesity.. 
* jobs / work/life balance : income, unemployment rate, education-level for working group, unemployment benefit claims, 
* Safety factors: assault incidents attended by ambulances, robbery incidents, 
* Environmental factors: Annual mean of particle matters found, homes with access to green spaces
* Community : ethical diversity (will be calculated with demographics data)

The above are all segmented into different .csv files containing data grouped by either `demographics`, `education`, `environment`, `crimes`and so forth. 

We also need the additional datasets found in the folder `\convert`:
* 2011_OA-LSOA-MSOA-LA.csv
* 2011 _OA-Ward-LA.csv
* Lower_Layer_Super_Output_Area__2011__to_Ward__2019__Lookup_in_England_and_Wales.csv 

The above are used to convert ward boundary areas dating from 2011 to 2019 boundaries. 

Additionally, our validation dataset comes from the [london government](https://data.london.gov.uk/dataset/subjective-personal-well-being-borough), in which subjective personal well being is measured at the borough level. Its name is : 
* personal-well-being-borough.csv 

Lastly, to draw the maps we need GIS boundaries, which we found from the Greater London Authority [website](https://data.london.gov.uk/dataset/statistical-gis-boundary-files-london). These are all included in the folder `statistical-gis-boundaries-london`.

Of course, we are incorporating the TESCO dataset and using those that were provided in the first replication report.  


# Methods

1. Data Pre-processing: we first need to reshape and decide which fields we are employing in each datasets. Given the large diversity of our datasets, it's a long process to evaluate whether each chosen field contains sufficient information useful for future analysis. These informations are at the ward levels.

2. Data Processing: many transformations and enrichments are done, such as :
* creating diversity ratios for certain indicators
* standardizing or normalizing the indicators
* reversing indicators (further explained in the notebook)
* removing outliers
* replacing certain missing data by the mean
* aggregating all the data for each indicator (Foods, Education, Environment, etc) at each level (ward or borough)

3. Statistical Analysis / Modeling: 
* PCA: Once the data is of sufficient quality, we run Principle Component Analysis (only on certain indicators that have many data) to determine which principle axis we should focus on.
* Weights tabulation: We run independence tests and check for correlations between our indicators. Once this is done, all the data from each indicator is aggregated together and the whole is normalized. 
* Weight Optimization: calculation followed by [Tools for Composite Indicators Building](https://publications.jrc.ec.europa.eu/repository/bitstream/JRC31473/EUR%2021682%20EN.pdf), page 56-57

4. Figure Generation and Analysis
* Creation of heatmaps to show correlations between factors
* Exploration of indicator categories to plot interesting features
* Map generations 
* Interactive Map generation

All the above then require careful analysis 

5. Validation
* Validation process by comparing the Index ALDI to subjective well-being data obtained from public London statistics. 

6. Data Story creation and Website building 
* Compiling all the data

# Proposed timeline
(This timeline was more or less followed with a lot more work done in the last week than initially planned)
* By the end of week 12 : have the full data pre-processing done, have the total combined DataFrame we will employ for this project calculated and finalised
* By the end of week-end of week 12: done with correlation analysis and interaction factors. Have begun modeling and graphs
* By the mid-week 13 : Finished preliminary modeling. A first thorough analysis of the model. Finish the figure with the geographical map data
* By end of week 13: Determine which visualisations will be retained. Determine whether further extension and analysis need to be done on the dataset. 
* By mid-week 14: Finish the textual analysis. Post everything on the blog for the data-story. If time, begin the video. 

# Organization within the team

Amaury: Data Processing, weight tabulation, Map generation, optimized heatmap generation
Charlyne: Data Pre-processing / preliminary data processing, Exploring Indicator figure generation, Datastory website generation  
Zhecho: PCA & weight optimization, preliminary heat map generation, interactive map generation

All contributed to: writing up the data story, cleaning up the notebook and supporting each other :) 

# Questions for TAs (optional)
Hopefully you enjoy reading our story ! We're quite proud of it.  

