## Assignment 3 ##


11/13/20


Word Count: 1,524


[*Link to Equations and Visuals*](https://docs.google.com/document/d/1gUhnYs2u4NbFHLRorHqXBI1M6kzIOXclJdd2VcQb08c/edit?usp=sharing)


#### Introduction ####


My research question is: Does climate change and decreasing crop yields have an effect on educational attainment in Sub Saharan Africa? This is an evaluative inquiry as I am seeking to discover or explain a relationship between two factors-- climate change and educational attainment. Previously, I created a relationship based on childhood nutrition as a uniting entity, conducting an evaluative inquiry between three factors, as no method directly measures the impact of climate change and education. My current central research explores the causal relationship between climate change and nutrition then the causal relationship between nutrition and educational attainment. In order to excise the mediating factor, two sub research questions would be: do areas with decreasing crop yields as a result of the changing climate have lower literacy rates than comparable areas with relatively stable crop yields? And similarly, do areas with decreasing crop yields as a result of the changing climate have less economic activity than comparable areas with relatively stable crop yields? There is a clear connection between literacy rates and education and there is evidence that those who are less educated contribute less to the economy than individuals who achieved a higher level of education. Consequently, both of these measurements could quantifiably reveal levels of educational attainment. These metrics could be combined with a measurement of crop yields and a geographical comparison could determine whether areas with lower crop yields due to more acute impacts of climate change have lower rates of educational attainment. I have discovered a concrete geospatial method using climatic data to calculate crop yield and a possible geospatial method to calculate economic activity. I did not find a method for calculating literacy rates. However, it could be possible to use a similar data collection method as used for countrywide literacy rate, but on a smaller scale to provide data for sects of a region.


#### Climate and Crop Yields Model ####


The first geospatial analysis models maize production and various future climate scenarios to find the percent change in maize yields from between 2010 and 2090. The researchers determined these estimated values by connecting spatial patterns of increasing aridity and yield losses. The measurement of aridity acts as the climate factor, as arity is expected to increase as climate change progresses. The scientists used a crop model called AquaCrop-OS from the Food and Agriculture Organization of the United Nations to calculate yields and compiled 122 climate projections to utilize a wide variety of environmental data. The AquaCrop-OS model includes a formula **(equation 1)** with four coefficients that act as independent variables for the hypothetical climate scenarios. These coefficients include temperature stress (Ksb), crop water productivity (WP*), transpiration (Trd) on the day (d), and evapotranspiration (ET0d) and can be used to calculate the total above-ground dry biomass (B) over the entire growing season. The biomass value can then be multiplied by the harvest index (HI), a measurement of the fraction of above-ground biomass that results in a yield, to arrive at the desired value-- total annual crop yield (Y) **(equation 2)**.

The AquaCrop-OS index was run on a map of Africa on a 2o x 2o grid. The yield for each square was calculated with the predicted climate data from the 122 climate models for four different time periods: 2010, 2030, 2050, and 2090. The median crop yield for each grid cell was compiled on a map of Africa, making it possible to compare predicted yield losses across the continent. By considering the squares that encompassed the area of Sub Saharan Africa (for the various “era” projections), it was possible to determine an estimate for the median yield loss in Sub Saharan Africa in the next 70 years. **Figure 1** shows the median percent yield change for five different ensembles of climate scenarios. Looking at the maps, one can appreciate the devastating impacts some communities will feel in the future as crop yields are projected to decrease by more than 50%. Also, there will be a wide range of effects across the region, as some areas will see an increase in crop yield, particularly in the east (it is predicted this area will see an increase in rain). Importantly, the equation used and geospatial analysis is not structured to be exclusively used for predictions, one can input past or present climate data. Therefore, the crop yields in the area can be better compared with other, real-time data collection like economic activity.


#### Road Density and GDPD Model ####


The second geospatial method I researched could be applied as a proxy to measure educational attainment. Researchers investigated the spatial variation of road networks in Fujian province in China and whether there was a correlation between road density and socioeconomic factors. First, they digitized hard copy maps of road networks in the providence. Then, they collected the socioeconomic data, Gross Domestic Product Density (GDPD) and population density (PD), from county offices and district censuses from 2000 and from 2012. In order to place the variables on a pixel scale, the data was interpolated on maps as polygon vectors at 30-m resolution. The initial equation the researchers ran was an Ordinary Least Squares (OLS) calculation **(equation 3)**. However, because OLS can only accurately describe the relationship in an area if it is homogeneous and stationary, the researchers believe the results from the OLS will be biased, as the study area is nonstationary. The equation calculates (y1) the Kernel Density Estimate (KDE), which describes the spatial pattern of road density change along and perpendicular to a road. x1 is the variable determined to affect road distribution, B0 is a constraint, B1 is the estimated coefficient, and ei is the stochastic error term.


The researchers next ran a Geographically Weighted Regression (GWR) which accounts for the heterogeneity of an area **(equation 4)**. The regression coefficient was different for each sample location in the area and the GWR was run at 5 resolutions: 1x1, 2x2, 3x3, 4x4, and 5x5. All variables represent the same as in **equation 3**, with the addition of (ui, vi) which are the longitudes and latitudes of centroids. Information was collected from surrounding grids and each location possessed its own parameter. Both the OLS model and the GWR model were estimated using SAM v3.1, a software package of spatial analytical tools. Gaussian functions were employed to assign a spatial weight matrix to the data and applied a cross-validation process set to optimal bandwidth to minimize Akaike Information Criterion (AIC). Both function to decrease variation and assess the accuracy of the OLS and GWR models. In addition, the researchers ran a Moaran’s Ig statistical test on the data, finding all of their data regarding the clustering of road density was statistically significant at the 5% level. **Figure 2** shows the calculated road density in the province. Finally, the socio-economic data was incorporated into the GWR equation at the 5x5 sample resolution. It was found to be appropriate to do so based on a Diff-Criterion test to determine there was significant spatial variation in GDPD and PD. Parameter estimates for both variables were used to explain the spatial variation between road networks and socioeconomic variables. Generally, a link was found between road density and GDPD-- the higher the road density, the higher the GDPD. The prevailing theory to explain this relationship is that economic growth increases the need for transportation as goods and people flow to and from an area, necessitating the construction of more roads.


#### Conclusion ####


The above point is important because a similar analysis could be applied to Sub Saharan Africa and it would be reasonable to assume that the areas with higher road density had a higher level of economic activity. Connections have been found between low rates of education attainment and lost earnings, so regions with low road density and low GDPD could be associated with poor educational attainment. Granted, the connection found in China could vary in Sub Saharan Africa, but it is worth adapting the method to the region and testing effectiveness, as it would be an invaluable addition to answering my question as well as others. The method investigating climate change is more applicable, but it has previously been used as a predictive tool. Given the environmental analysis would be compared to the present state of road density, the climate change model would have to be adapted somewhat to be appropriately used for presently collected climate data. With both geospatial methods combined, one could determine which places in Sub Saharan Africa have lower agricultural yields due to climatic variation and which have low road density and resultingly less economic activity. A geographical comparison could reveal whether both phenomena occur in the same areas. If so, there would be a preliminary correlation between climate change and education. Although, it must be considered that both topics are complex and possess many confounding factors, discounting the possibility of a definitive answer. A method to measure literacy levels would add credence to any conclusion, but there is little evidence of such in the literature. I believe it would be possible to collect literacy rates on a relatively fine scale through a survey type method of data collection in order to supplement the other data.




**References**


Dale, A., Fant, C., Strzepek, K., Lickley, M., & Solomon, S. (2017). Climate model uncertainty in impact assessments for agriculture: A multi-ensemble case study on maize in sub-Saharan Africa. *Earth’s Future*, 5(3), 337–353. Advancing Earth and Space Science. https://doi.org/10.1002/2017ef000539



Hu, X., Wu, C., Wang, J., & Qiu, R. (2018). Identification of spatial variation in road network and its driving patterns: Economy and population. *Regional Science and Urban Economics*, 71, 37–45. Science Direct. https://doi.org/10.1016/j.regsciurbeco.2018.04.014
‌





