## Executive Summary

   It's time to prepare the California Environmental Protection Agency's Office of Environmental Health Hazard's for a successful auditing process on industry leading companies within the state. California is the home to many successful industry leading companies that supply on a global scale. It is crucial that no area of any company is overlooked by the OEHHA and is inefficient or unorganized as to ensure no health hazards are unrecognized for the public. Our aim is to capitalize on the meticulous data gathered in the yearly Enviro-Screen report and be prepared to answer confidently the questions about pollution production and correalation within public health. When it comes to the health of our citizens there is no room for error.

   We are a team of data scientist's that specialize in exactly that and have found atleast 5 points of interest so that the OEHHA will be able to accurately label and have predictive strength to monitor adverse health effects caused by pollution in industry and beyond. First-hand, there are insightful correlations (both negative and positive) between asthma,low birth weight, cardiovascular disease, Diesel particulates, and Ozone. Secondly, I have a plan of action for how to increase citizen awareness and highlight specific areas prone to health complication factors from pollution. These two factors in conjunction will pave the way for predictive/preventitive techniques so that California remains the Golden State for future generations. 

   Through our Regression modeling techniques, the team can determine a statistically correct predictive algorithm that can Identify future and current 'hot spots' of heavy pollution and how they impact the population. With millions of industry dense areas.

   This data science team has experience and the energy to see this project through to the final stages of success. There is no better time than the present to educate and potentially prevent future detriment to the populous and enviroment. With the growing state of California on a local and global scale the clock is ticking and we have not only identified the issues but put together a comprehensive plan to visualize and execute a preventitive and insightful plan for medical and government agencies.

   Let's make it happen and leave no doubt that the beautiful beaches, mountains, and valleys stay pure and continue to bring joy not health issues to our wonderful citizens. We have the chance to change and impact future generations and policy makers accross the globe. 
   
## Activity log


4/10
- Familiarized myself with team and proceeded to look around the first viable dataset(Enviroscreen)

4/11
- Inital score with regression is quite poor, but teammates are quite good at EDA. 
- thinking about executive summary and what our "theater" goal is for this project to make it seem real

4/14
Met with team
- All focused on figuring out my Github
- taking noted from both David and Giovanna to make sure my pushes are communicated

Needing structure on: 
- understanding the zip and warehouse data connection with data.
- continue drawing inference on deatailed reports for health conditions. 
- Using my knowledge of growing up in CA to infer certain ares as being prone to higher pollution and contamination from heavy warehouse or buisness interaction. (first thought is that so many cars are Environmentally stringent with big corps(CA is so strict with regulations, imagine Texas or the midwest). Will warehouses show a big impact with pollution? im sure higher than average, but its not a coal plant in Oklahoma. 
- What health effect will be the target? asthma seems the most obvious for me.

4/16
- busy day
- I merged together the Datasets from EnviroScreen but it did not include census and tract info like how Giovana and David collected.
- understanding the impact of the census data. 
4/18
- Great processed dataset created by group with all EnviroScreens and CEAS data. This is what I will use to model effectively. 
- Lots of good learned process from the team with how to deal with missing data in this merged and processed dataset, I have a tendancy to drop and make similar which would ruin integrity. 

4/20
- I have regression models that are not great (.60 R2 roughly)
- Have tried multiple different types of models, diving into GridSearch CV heavily and trying to tackle the XGboost Regression modle.

4/23
- Wrote executive summary and additions to the READ.md for the group.


4/26
- I have completed multiple GridSearch models. 
- My XGboost Reg I think has the best score with .85-.87 R2 score so far but i need to follow up with team to make sure my target health outcome is correctly formatted. 
- confident with the GS I made we can feed in a any of the processed data and achieve a pretty good score!

4/28
- finalized all model projections. 
- finalized exectutive summary.



### append to main READ.md:
Background on the data what each of the sets are, Big picture(where it came from, how we obtained it, why it is useful). Describe how it was transformed, and what were the general results. Explaination of data dictionary. 

How we encountered percentiles and values in values. initial findings with barebones models. Findings in EDA with location, industry, traffic and connection to health problems. Why its relevant now for someone analyzing this. 

Methodology for why certain models were choosen. 


## Background

#### Cal Enviroscreen
- CalEnviroScreen is a mapping tool that helps identify California communities that are most affected by many sources of pollution, and where people are often especially vulnerable to pollution’s effects.
- CalEnviroScreen uses environmental, health, and socioeconomic information to produce scores for every census tract in the state.
- The scores are mapped so that different communities can be compared. An area with a high score is one that experiences a much higher pollution burden than areas with low scores.
- CalEnviroScreen ranks communities based on data that are available from state and federal government sources. (Source: https://oehha.ca.gov/calenviroscreen/about-calenviroscreen)

#### model types
- SVR - Support Vector Machine can also be used as a regression method, maintaining all the main features that characterize the algorithm (maximal margin). The Support Vector Regression (SVR) uses the same principles as the SVM for classification, with only a few minor differences. First of all, because output is a real number it becomes very difficult to predict the information at hand, which has infinite possibilities. In the case of regression, a margin of tolerance (epsilon) is set in approximation to the SVM which would have already requested from the problem. But besides this fact, there is also a more complicated reason, the algorithm is more complicated therefore to be taken in consideration. However, the main idea is always the same: to minimize error, individualizing the hyperplane which maximizes the margin, keeping in mind that part of the error is tolerated.(refrence: https://www.saedsayad.com/support_vector_machine_reg.htm) 
- Random forest Regressor - A random forest is a meta estimator that fits a number of classifying decision trees on various sub-samples of the dataset and uses averaging to improve the predictive accuracy and control over-fitting. (refrence: https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html)
- Elastic Net - Linear regression with combined L1 and L2 priors as regularizer. (refrence: https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.ElasticNet.html)

- XGboost regressor with brew install in jupyter lab - When using gradient boosting for regression, the weak learners are regression trees, and each regression tree maps an input data point to one of its leafs that contains a continuous score. XGBoost minimizes a regularized (L1 and L2) objective function that combines a convex loss function (based on the difference between the predicted and target outputs) and a penalty term for model complexity (in other words, the regression tree functions). (refrence: https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost-HowItWorks.html)

#### Health effects and Pollutants

- [link to data dictionary](https://oehha.ca.gov/calenviroscreen/maps-data/download-data)

## Summary of Methodology and Results

- I saw a meaningful R2 score with both my random forest and XGboost regression models. Like mentioned in the presentation they rely heavily on socioeconomic factors. 
- I used multiple regression models outined above and achieved the best score with an XGboost regressor. 
- The EDA was achived through combining all the datasets of enviroscreen while also combining the warehouse data to achieve the optimal dataset. 
- This dataset was used to achive the best models in my notebook.




| Model         | features used                                                                                                                                                                                                                                                                                                                                                                             | type                                    | evaluation metric           | Train Accuracy     | Test Accuracy      | RMSE score | MAE test score |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------|-----------------------------|--------------------|--------------------|------------|-----------|
| XGBoost       | total population, ozone, pm2.5, diesel pm, pesticides, traffic, cleanup sites, groundwater threats, haz. waste, imp. water bodies, solid waste, pollution burden, low birth weight, education, linguistic isolation, poverty, pop. char. , drinking water, tox. release, unemployment, ces_per, cardiovascular disease, housing burden, est total, est gen, est cold, est farm, est other | gradient boosting supervised regression | Accuracy, r_2 score, & RMSE | 0.9472151826696329 | 0.7639090300436409 | 14.376141  | 0.7       |
| Random Forest | total population, ozone, pm2.5, diesel pm, pesticides, traffic, cleanup sites, groundwater threats, haz. waste, imp. water bodies, solid waste, pollution burden, education, linguistic isolation, poverty, pop. char. , drinking water, tox. release, unemployment, ces_per, housing burden, est total, est gen, est cold, est farm, est other                                           | meta estimator regression               | Accuracy, r_2 score, & RMSE | 0.9631357268516347 | 0.7488496371839088 | 14.739432  | 9.70       |
|               |                                                                                                                                                                                                                                                                                                                                                                                           |                                         |                             |                    |                    |            |           |



                                                                                             |                                         |                             |                                                                                                    |



| Model         | features used                                                                                                                                                                                                                                                                                                                                                                             | type                                    | evaluation metric           | Train Accuracy     | Test Accuracy      | RMSE score | MAE test score |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------|-----------------------------|--------------------|--------------------|------------|-----------|
| XGBoost       | total population, ozone, pm2.5, diesel pm, pesticides, traffic, cleanup sites, groundwater threats, haz. waste, imp. water bodies, solid waste, pollution burden, low birth weight, education, linguistic isolation, poverty, pop. char. , drinking water, tox. release, unemployment, ces_per, cardiovascular disease, housing burden, est total, est gen, est cold, est farm, est other | gradient boosting supervised regression | R2, RMSE, & MAE | 0.9139 | 0.7853 | 13.6915  | 9.3296       |
| Random Forest | total population, ozone, pm2.5, diesel pm, pesticides, traffic, cleanup sites, groundwater threats, haz. waste, imp. water bodies, solid waste, pollution burden, education, linguistic isolation, poverty, pop. char. , drinking water, tox. release, unemployment, ces_per, housing burden, est total, est gen, est cold, est farm, est other                                           | meta estimator regression               | R2, RMSE, & MAE | 0.9634 | 0.7503 | 14.7307  | 9.9952       |
|               |                                                                                                                                                                                                                                                                                                                                                                                           |                                         |                             |                    |                    |            |           |