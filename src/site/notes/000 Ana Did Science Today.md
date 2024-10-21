---
{"dg-publish":true,"permalink":"/000-ana-did-science-today/"}
---

## Next stages
- [ ] Go through Fiona's edits
- [ ] Get running on GIC-Green and contact Tim
- [ ] Contact collaborators in Brazil
- [ ] Contact Jacob Slusser
- [ ] Falar com [[Costa, Flávia R. C.\|Costa, Flavia]] - ask about evapotranspiration in the Amazon. If that doesn't work, talk to Sara Knox through Fiona.
 - [ ] Save data sources:
		ERA5 = https://developers.google.com/earth-engine/datasets/catalog/ECMWF_ERA5_LAND_MONTHLY_AGGR#bands
		https://www.sciencedirect.com/science/article/abs/pii/S0924271621001519#preview-section-abstract
		https://github.com/et-brasil/geeSEBAL/blob/master/Examples/Image_function_geeSEBAL.ipynb
		https://forobs.jrc.ec.europa.eu/TMF
		https://www.conservation.org/about/annual-report\
		Ruth Metzel
		https://esajournals.onlinelibrary.wiley.com/doi/10.1002/eap.2208
## Papers to read
- [ ] [Wood density](https://www.nature.com/articles/s41559-024-02564-9)
- [ ] Heinrich papers and Celso ages (understand how they forced the growth curve through zero)
- [ ] [[Feng 2024 - Global patterns and drivers of tropical aboveground carbon changes
- [ ] https://phys.org/news/2024-08-nitrogen-deposition-biodiversity-larger-scale.html]]
- [ ] Jakovac policy brief

# Oct 21 : 28 - Weekly Tasks
- [ ] Write methods
- [ ] make poster
- [ ] make presentation for committee meeting
- [ ] write committee meeting report
- [ ] register for AGU with Fiona
## 21/10, Monday - Wrapping up model
- spent the weekend double checking the results.
- [x] write summary for workshop ✅ 2024-10-21

Results normalizing all data at once:

![](https://i.imgur.com/b8s2ows.png)


# Oct 13 : 20 - Weekly Tasks

## Modelling
- [x] Email Jeff again about algorithm ✅ 2024-10-16

## Travel prep
- [x] Talk to Gabriela for mining project ✅ 2024-10-16
- [x] Email guests ✅ 2024-10-17
- [x] Assign tasks to Katie for port project ✅ 2024-10-16
- [x] Check whoever in the ministry of environment we talked to. Consider institutional support from STRI. ✅ 2024-10-15
- [x] ask jeff hall for agua salud data ✅ 2024-10-16
- [x] write down expenses to claim with Brian ✅ 2024-10-16
## Others
- [x] set up github 2FA ✅ 2024-10-16

## 17/10, Thursday - Coding and writing

A lot of the past few days has been spent writing methods and planning tasks.

![](https://i.imgur.com/DIhqNDk.png)
There are very few pixels in the Amazon that don't have pastureland as their last observed land use.

I am removing last_LU since through multicollinearity it correlated strongly with number of years under each land use type.
![](https://i.imgur.com/KC2W9cv.png)
This is after sampling. There data is not evenly distributed - can this cause issues?


# 01/10 : 13/10 - Weekly Tasks
## Modelling
- Incorporate new variables:
- [x] Slope ✅ 2024-10-13
- [x] [TMF ages](https://forobs.jrc.ec.europa.eu/TMF) ✅ 2024-10-13
- [x] [[SoilGrids\|SoilGrids]] ✅ 2024-10-13
- [x] Remove forests that burned after regrowth ✅ 2024-10-13
- [x] Investigate low impact of cwd on Amazon ✅ 2024-10-13

## Work Management
- [x] Apply to GMA ✅ 2024-09-18
- [x] Apply for conference funding: ✅ 2024-09-18

## 13/10, Sun - Weekly Review

NLL does slightly better than NLS.

Correlation heatmap for mapbiomas data:
![](https://i.imgur.com/LA91XtX.png)
Correlation heatmap for EU data:
![](https://i.imgur.com/GTRtsDo.png)



![](https://i.imgur.com/8MJ7fhR.png)




## 12/10, Sat - writing down methods


### Methods flowchart for modelling, step by step
I am realizing there are too many combinations to try all at once. the combinations grow really quickly. It is best to try one at a time, and see how they behave - register the results, and later find something ultimately better.

right now the options are:

- all different functional forms
- all different parameter inclusions
- 3 biomes
- 2 fitting methods (nll and nls)
- 4 intervals
	- for 3 intervals, hard_cut or selected ranges
- aggregated or non-aggregated data
- with and without integrating through climate history


## 08/10, Tue - Wrapping up

taking the day to write current conclusions and coming plans.
For the model:
- try STAN
- try checking the effect of the predictors in the intercept
- finish implementing other data sources
- finish commenting code/finishing R testing ground

## 07/10, Mon - Wrapping up

Sent the GMA and am wrapping up coding.
Need to send off emails to the PRISM guests.

## 03/10, Thu - Coding

I'm realizing that this dataset shows a lot of the forests as disturbed 

It does not seem to be an issue to resample to 1000m - that is just a reaggregation to 1km, and that is only used to determine the nearest asymptote, so that makes sense.
In order to determine propagule pressure, nearest surrounding cover or gaussian kernel makes more sense.


![](https://i.imgur.com/4blI7cC.png)


## 02/10, Wed - Coding

In the beginning of the day, I want to run the model with just ages considering linear, random forest, and optim, with the new data, for the Amazon only.

In the rest of the day, I organize the writing/thinking, register what has been done and found so far, and clean up the code.

compare performance of celso vs mapbiomas - choose whether to do that for 2018 or 2020

check whether mature forest edge needs to be considered in this new dataset where disturbances are pointed out

get number of years of disturbance and deforestation before regrowth

Brian's delays make sense, but another thing I want to do this week is to think of how to implement different functional forms depending on what I observe with the data. Beginning slowly.

also SLOPE and mapbiomas fire/FRP while we're at it!

EU ages:
![](https://i.imgur.com/X7M3VPC.png)
MAPBIOMAS ages:
![](https://i.imgur.com/SpeHRiO.png)
Celso ages:
![](https://i.imgur.com/KZuXdyh.png)
![](https://i.imgur.com/pRgr5vo.png)
![](https://i.imgur.com/l50rvEE.png)
EU distributions:
![](https://i.imgur.com/tDY5Ti8.png)
![](https://i.imgur.com/tSOcQov.png)




# September Conclusions

## Main results

R-squared values with linear models were quite high, reaching around 40%. Optim results were also acceptable, around the 30s, but less predictive than linear models, indicating issues with the functional form.
[](https://i.imgur.com/R58jpAt.png)
[](https://i.imgur.com/lWqcy7M.png)
[](https://i.imgur.com/7I2XwPt.png)
[](https://i.imgur.com/xvNKdZt.png)
[](https://i.imgur.com/LQvQp0q.png)

Decided to check data distributions and found that mean biomass for 1 year old forests is around 100 tons per hectare. That shows that Landsat has a hard time detecting forests that are less dense than that and those are the early years that we are missing from the analysis.

![](https://i.imgur.com/6gnuCXv.png)
![](https://i.imgur.com/cLeBiBp.png)


![](https://i.imgur.com/h6Ry1Hu.png)

Interestingly, I noticed that the intercept/asymptote also changes with each predictor given. They have more of an effect on the overall shift of the growth curve than the rate itself:

![](https://i.imgur.com/d6OIXJ4.png)
![](https://i.imgur.com/4Pcc6cv.png)
![](https://i.imgur.com/Mv3VlK8.png)

It is noticeable that the intercept is not the beginning of the growth curve, but the middle onward. This can be fit through a lag term, in which case:$$ AGB = A \cdot \left( 1 - e^{-k(t + \text{lag})} \right)^{\tau} $$ Where A = biomass of the nearest mature forest, t = age, $$ k = c_{1} \cdot \text{par}_{1} + c_{2} \cdot \text{par}_{2} + \dots + c_{n} \cdot \text{par}_{n} $$ and $$ \text{lag} \sim \mathcal{N}(\mu_{\text{lag}}, \sigma_{\text{lag}}) $$
In this functional form, normalizing age should not matter, but I will compare both just in case.

However, this may also be written where $A = c_{1} \cdot \text{par}_{1} + c_{2} \cdot \text{par}_{2} + \dots + c_{n} \cdot \text{par}_{n}$ (including nearest mature forest) and k is a fit parameter. This would assume the growth rate is independent of the other parameters, and only asymptote depends on it.

Alternatively,
	$$A = c_{1} \cdot \text{par}_{1} + c_{2} \cdot \text{par}_{2} + \dots + c_{n} \cdot \text{par}_{n}$$
and
$$ k = c'_{1} \cdot \text{par}_{1} + c'_{2} \cdot \text{par}_{2} + \dots + c'_{n} \cdot \text{par}_{n} $$
Fitting the same parameters as affecting growth rate and asymptote simultaneously, with different coefficients.

The rate seems to only change with age. Biomass of the nearest mature forests also depends with all those predictors, meaning that they will affect the asymptote indirectly when A = nearest_mature_biomass.

I would have assumed that there is some effect of all other predictors on nearest forest biomass, but thought the effect seen by num_fires_before_regrowth would be completely independent to nearest mature forest. However, even though there is no significant correlation shown in the multicollinearity test:

![](https://i.imgur.com/c9CtpVP.png)

Other predictors do relate to nearest_mature_forest, probably since they indicate some level of disturbance or other indirect effect of human activity, or that human activity tends to happen in less dense environments.

This leads me to believe that nearest_mature_biomass may be enough to describe the asymptote, but it may be worth confirming.

### Comparing average biomass
Comparing the average biomass of the nearest mature forest to the average biomass of the oldest secondary forests, it shows that the nearest mature biomass seems like an acceptable asymptote.

![](https://i.imgur.com/baMXp8r.png)


![](https://i.imgur.com/msv5Ink.png)

### Future tests
- Predict biomass of mature forests based on environmental predictors is a separate test that can also be done to find out whether that would make a better asymptote. Potentially a xgboost submodel would be helpful here.
- the relationships between the predictors may not be linear - this can be investigated through:
	- partial dependence plots
	- residual plots


Julie Major mentioned:\
- Panama has more soil variability - that could lead to different predictive power of soil variables in Brazil vs Panama.
- cabeças de gado por hectare e pasto manejado ou pasto nativo.



## 30/09, Mon - Writing and coding
- Ask Fiona about applying to PGSS Travel Awards
Correlation for age_mapbiomas and age_eu is 0.41 in the atlantic rainforest and 0.66 in the amazon
R squared is 2x better in the atlantic forest (2.5 - 5%) and about same in the amazon (3.7 - 6%)

So I think the next steps are to accept the high intercept, contact jeff cardille about the algorithm, and think of modelling without land use but with fire for Brazil and Panama. Incorporate the delay term Brian mentioned and see how that does, and then consider other predictors as intercepts by looking at the data and thinking carefully about it.

This is also the time to stop and look at all the screenshots and write a small report to update Fiona.

## 27/09, Fri - Writing and planning

Main tasks:
- Organize tasks per chapter
- Read Isabella's FRQNT
- Write PRISM blurb and send it out
- Write on chapter 1 - get Fiona's edits


## 23/09, Mon - Meeting with Julie Major

tempo de manejo - tempo sob banana por exemplo é bem diferente do tempo para 

latosolo do brasil não retém nada - potássio, cálcio, tudo muda.
porcentagem de materia organica.

o panamá tem mais variabilidade nos tipos de solo e são solos mais férteis. o panamá tem solos muito recentes e curtos, o solo brasileiro é profundo e antigo. os cátios são 

muito oxido de ferro e aluminio, solos mais ácidos na amazonia.

o solo panamenho tem mais variabilidade de solos.

ph,
areia, mineralogia, dados de solo. textura. 

cabeças de gado por hectare e pasto manejado ou pasto nativo.


## 17/09, Tue - modelling, task planning and writing

I have made good progress in modelling. Now I should write down the formulas and think of how the paper is going to go given what I have right now.



Initial (Non-tuned) Results:
Cross-validation R2: 0.117 (±0.019)
Unseen data R2: 0.138

Random Forest Results:
Cross-validation R2: 0.332 (±0.018)
Unseen data R2: 0.318

Feature Importance:
                  feature  importance      std
                      cwd    0.366600 0.023969
           nearest_mature    0.156924 0.007927
                      age    0.121189 0.010427
                sur_cover    0.117791 0.010898
              lulc_sum_15    0.031879 0.004525
              lulc_sum_21    0.030922 0.004459
              lulc_sum_41    0.008952 0.001913
num_fires_before_regrowth    0.006607 0.001667
              lulc_sum_39    0.004586 0.001644


Linear Regression Results:
Cross-validation R2: 0.190 (±0.036)
Unseen data R2: 0.209

Feature Importance:
                  feature  importance      std
                      cwd    0.151801 0.010817
                      age    0.062219 0.006214
                sur_cover    0.038454 0.006047
           nearest_mature    0.017647 0.002808
              lulc_sum_41    0.005496 0.001666
              lulc_sum_15    0.004324 0.001378
              lulc_sum_39    0.003063 0.001314
num_fires_before_regrowth    0.002785 0.001420
              lulc_sum_21    0.000463 0.000195

XGBoost Results:
Cross-validation R2: 0.309 (±0.025)
Unseen data R2: 0.307

Feature Importance:
                  feature  importance      std
                      cwd    0.308156 0.021909
           nearest_mature    0.145135 0.009349
                      age    0.132427 0.006648
                sur_cover    0.098023 0.008758
              lulc_sum_15    0.032115 0.006971
              lulc_sum_21    0.016699 0.005783
              lulc_sum_41    0.012113 0.002658
              lulc_sum_39    0.008167 0.001967
num_fires_before_regrowth    0.002006 0.001960



## 14/09, Sat - Task planning and finishing retreat plans
Consider joining beeminder to motivate you to have morning work sessions and to work out in the morning.
Organize the tasks better. Consider coding progress and rewrite coding goals.

## 13/09, Fri - Task planning
Since writing was done earlier in the week, today we code.

Spent also some time doing housework and thinking of the model conceptually. Hardcore coding will be done again on Sunday.

lulc_sum_40 is too few points right now

Realizing that there may have been something wrong with the way the later dataframes were exported, with my method of trying to avoid spatial autocorrelation. I am going to confirm and run again the scripts, clean everything from beginning to end.

Concerns for now - going through with the code. Going to write the methods down to discuss with Brian.

## 12/09, Thu - Coding

Meetings went well. Nothing else is urgent so I can code.

It looks like due to data leakage, the normalization should be done within each testing/training group. Since I found that out when rewriting the code in Python, I am leaving the original code for a bit and will focus on writing the Python section.

I am starting with only one set of parameters and will build on that as the code is shown to be robust.

Email Brian to speak to Catalina about speaking to Andres and CIAM.
no monday morning, friday morning.
Undergrads to get data. Report back what they CAN't find - who are they talking to, and where are they getting it.



## 11/09, Wed - Multicollinearity and PCA for soil and ecoregion
After testing for multicollinearity and running for the main optimizers, I am also trying out [theseus](https://sites.google.com/view/theseus-ai/), Hossein's recommendation.



                               GVIF Df GVIF^(1/(2*Df))
indig                      1.047234  1        1.023344
lulc_sum_15                2.685540  1        1.638762
lulc_sum_21                3.002503  1        1.732773
lulc_sum_39                1.144176  1        1.069662
lulc_sum_40                1.047488  1        1.023469
lulc_sum_41                1.291870  1        1.136605
lulc_sum_46                1.050510  1        1.024944
lulc_sum_9                 1.876912  1        1.370005
num_fires_after_regrowth   2.076377  1        1.440964
num_fires_before_regrowth  4.512407  1        2.124243
sur_cover                  1.219305  1        1.104221
ts_fire_after_regrowth     2.070698  1        1.438992
ts_fire_before_regrowth    4.431991  1        2.105230
ecoreg                    50.929251  4        1.634447
soil                      29.095926  7        1.272212
cwd                       11.069060  1        3.327020
mean_prec                  4.796260  1        2.190036
mean_si                    7.784058  1        2.789993
age                        3.372658  1        1.836480
nearest_mature             1.523663  1        1.234368

I am removing num_fires_after_regrowth (I believe it may be related to age and num_fires_before_regrowth)

also checking the effect of cwd, mean_prec, mean_si

With cwd, mean_prec, mean_si in a PCA:
![](https://i.imgur.com/6K4KoCX.png)



![](https://i.imgur.com/TCWOLpE.png)
![](https://i.imgur.com/ly5nP8M.png)

Since I don't know the effects of introducing new continuous variables from the PCA into optim, I am going on removing ecoregion and soil and seeing how it behaves with the bare minimum.

                    indig               lulc_sum_15               lulc_sum_21 
                 1.030280                  2.622587                  2.914899 
              lulc_sum_39               lulc_sum_40               lulc_sum_41 
                 1.118340                  1.047743                  1.254247 
              lulc_sum_46               lulc_sum_48                lulc_sum_9 
                 1.037590                  1.016834                  1.819965 
num_fires_before_regrowth                    protec                 sur_cover 
                 4.343726                  1.066350                  1.148549 
  ts_fire_before_regrowth                       cwd                   mean_si 
                 4.282326                  4.387833                  3.939459 
                      age            nearest_mature 
                 3.268504                  1.397458 
             
9 and 21 are correlated land use types.

Checked for multicollinearity, included mature_forest, and the issue is the same.

Now trying fitting with python. Leave the code messy - clean it later.
pars_fit <- c("age", "nearest_mature", "lulc_sum_21", "lulc_sum_15", "lulc_sum_39", "lulc_sum_40", "lulc_sum_41", "num_fires_before_regrowth", "protec", "sur_cover","cwd", "nearest_mature")


## 10/09, Tue - Writing
- Writing
- Committee Meeting
- GMA application
I would like to organize my tasks, but I will leave that for the weekend. Today I finish writing and applications so I can move on to the code.

TAship still needs to be decided.

Considering focusmate sessions early in the morning?

After writing, I decided to start with multicollinearity.

## 09/09, Mon - Writing
I am realizing that today I don't have time to plan all my tasks again. I am letting them sit here until tomorrow while I finish today
- writing Panama summary
- writing article key sentences
- testing for multicollinearity

Change of plans - will code tomorrow. today we finish first iteration of writing and GMA application.

- [x] Call Analida and Gabriela ✅ 2024-09-17
- [x] Schedule committee meeting ✅ 2024-09-10

## 07/09, Sat - Wrapping up everything

Today I am taking stuff out of my mind so I can focus on coding and writing. Working on bureaucracies in general and planning.

## 06/09, Fri - Writing

Planning week and other logistic work should be done tomorrow.

Today I am finishing the Panama writing and will work more on chapter 1 writing.
- actually, it takes a lot of formatting to work on the workshop planning. I'll do that tomorrow with my desk. For now I focus on writing my storyline for chapter 1.


## 05/09, Thu - PRISM and modelling

- Asymptote is affecting the growth rate. What happens if I include it in the rate as well?
I closed off my participation at the port stuff for today, and reached out to some people about the mining project. I will close off the planning for Panama trip, as well as my participation in the workshop, between today and tomorrow.

Conclusions so far:
- gap between optim and LM is largest in atlantic forest than amazon
- R squared values are largest for 5 years and lowest for all

So for initial testing and comparison across optim, lm and rf, I will choose **atlantic forest, all, all_continuous_mean_clim or all_mean clim.**

### TAship no Panamá
10 de fevereiro - 2 de março (Ariel Espino e Nicolas Kosoy)
Carnaval, outro curso (3 semanas livres) - ver o custo do voo
24 março - 13 abril (Ariel Espino e Nicolas Kosoy)

Dormitório Bela Vista - Avenida Balboa. Cama King Size e banheiro
- escritório

Plano de manejo de bacia de Santa Fe
Agua Dulce (outro mar) Foz do Rio Santa Fé

Próxima semana - contatar Nicolas Kosoy

## 04/09, Wed - Coding chapter 1
I have decided to do the larger weekly management on Friday and saturday. For today, I will focus on coding.
I am comparing the effect of random forest with optim. I will run random forest with each predictor, one by one, to see how it behaves, and do the same with optim.
So now that R is done and working fine, I am going to focus on the python code:

### Task list - to do with ONLY ONE dataframe and ONLY ONE combination
- [x] Check for multicolinearity / check data ✅ 2024-09-17
- [x] Compare Scipy Nelder-Mead with Optim ✅ 2024-09-17
- [x] Hyperparameter tuning (sciopt bayesian optimization) ✅ 2024-09-17
- [x] Check results with MSE instead of r squared. ✅ 2024-09-17
- [x] Check the response curve with random forest as predictors are added. ✅ 2024-09-17
- [x] Xboost ✅ 2024-09-17
- [x] Create holdout set to test everything. ✅ 2024-09-17
- [x] To check for overfitting, use learning curves - see how performance improves with sample size. ✅ 2024-09-17

For now, as long as we are only comparing methods, stick with 10-year, Amazon.

Note: can build confidence values by running the model multiple times for each pixel and seeing how the results differ. That's probably how they did SD for CCI Biomass?


## 03/09, Tue - Random forest and wrapping up Optim

response curve - investigate with random forest by adding one by one. Use the results of random forest to compare with optim
MCMC with stan
hyperparameter tuning
MSE instead of r squared may be a better metric.

How well does the atlantic forest predict the amazon?
For MCMC, running more than 1000 for chain length is often unnecessary.

tommy laguardia - what carmen mentioned, the place where they have aerial photography to help land use classification.

multicollinearity
### Writing/storytelling thinking
- consider different land use change scenarios - how do land use projection scenarios look like, and how can we answer things.
- active vs passive reforestation - cost of regrowth
- "where should you put your money for maximum carbon bucks?"

- [x] Schedule committee meeting - talk to Catherine about land use classification ✅ 2024-09-10
## 30/08, Fri - WEEKLY REVIEW

### Coding
I have realized that the mismatch between the lm and optim outputs were largely due to:
- correlations between variables - mature_forest_years was very related to ages, and number of fires before anthro with number of fires before regrowth, and so on
- and there were columns that were empty, for the rarer ecoregion types and soil types.
I have fixed that by removing types that are too rare. Removing rare ecoregions and soil types makes such that amaz, both and atla have slightly different nrow values, but I do not think that is a problem. Think about that a bit more next week.
Another concern now is spatial autocorrelation. I could select only one point per 1km area - confirming that with GEE.

### Goals - Other
- [x] [[000 Chapter 2 - Predicting Regrowth in Panama\|000 Chapter 2 - Predicting Regrowth in Panama]] Write short summary of project for workshop ✅ 2024-09-09
- [x] Contact Gabriela and see if she knows anyone that would be interested in the project ✅ 2024-09-06
- [x] Finish retreat prep ✅ 2024-09-09

### Goals - Coding
- [x] Look over climatic variables with Fiona ✅ 2024-09-04
- [x] Look over pantanal/cerrado with Fiona ✅ 2024-09-04
- [ ] Incorporate Jeff's ages from his model
- [ ] Add slope
- [x] Check random forest outcomes with python ✅ 2024-09-03
- [x] Incorporate hyperparameter tuning ✅ 2024-09-17


## 16/08, Fri - Meeting Jeff Hall with Brian

### Important notes
- depending on the age class N fixers fix at different rates. Makes sense - connects to other papers I've read.
- The dry forest has new data that has never been analysed in the way that we can do it.
- Most forests are regrowing on pastureland - rice isnt grown everywhere, and neither is sugar cane, some areas have more presence of one land use type than others.
- would be cool to start with just fire and move on.

### People mentioned
- botanist in his lab - understands lianas and biodiversity in secondary forests. Could be useful in conceptualizing chapter 2.
- Professor in Singapore could be met over zoom - not sure of their specialty?
- Greg Asner - 2012 data. he may have information on land use classification?
	- may have other lidar flights over agua salud done this past year and other regions for other regions - would have biomass for other years.
- Helena muller-landau would have that with drones.
- Etienne university of toronto used remote sensing 
- Casey cushman - jpl, tenessee oak ridge, helped lead the radar study from JPL
- Joanne palantier was catherine potvin's postdoc. she did land use classification for land slides. [[Regrowth on Landslides\|Regrowth on Landslides]]
- Raul Martinez - remote sensing people in panama canal authority. gerente of environmental division. they may have at least within the watershed.
- Milton Solano also - write him an email and ask. manage databases.

### Final product 
- regeneration potential for Panama - marrying with the probability of deforestation map
	- how forests regenerate from landslides?
	- hills and bedrock - this could be an interesting predictor too.
- conceptualizing chapter 3 - lianas, nitrogen fixers. Catherine also has botanists, and others in forest geo.

https://ensminger.csb.utoronto.ca/2022/08/31/our-drone-data-reaches-new-heights/


## 12/08, Mon - Coding and meeting Jeff Cardille

- Check with Gabriela if she is or knows someone who would be interested in leading the mining group at the workshop
Climatic variables should only matter when age is implicit. Careful - included variables that should not have been included together. It would have been helpful to think of the model conceptually first before writing the code.

## 09/08, Fri - Planning the week/organizing things
### Work task planning
- write chapter 1 - take a full day to advance on the whole thing as well as possible.
- write project for chapter 2 and plan workshop
	- fire for Panama, run it with as many categories as we can. Check the differences between running the model with more or less categories.
- read documentation on MAPBIOMAS

## 28/07, Mon - Submit abstract
Realized why nearest mature forest biomass calculations are not running for the whole country.

<!--⚠️Imgur upload failed, check dev console-->
![Ana Did Science Today.png](/img/user/Files/Ana%20Did%20Science%20Today.png)

The extents are not the same. Fixing that on GEE.


Fitting the Gaussian kernel on R is not working:

```r
# 500 m res
mature_biomass <- rast("./data/mature_biomass_1k.tif")

w <- focalMat(mature_biomass, 200, type = "Gauss")

Error: cannot allocate vector of size 265.9 Gb
```

Next steps:
- implement biome/ecoreg switch
- implement error catch for GAM

Check for spatial autocorrelation

## 23/07, Tue - Run nearest neighbor in R

For paralellization - rule of thumb, it's good to check how much memory does it take on one core before choosing how many cores to assign the task to.

Apply for conference funding:
AGU
GIC
QLS
GREAT
QCBS

One issue with running the nearest neighbor with terra as rasters is that the distances were calculated in meters, and that requires different UTM zones to find nearest neighbors.

For now I continue calculating with matrices and later will check how to do all this in gee.

## 19/07, Fri - Writing

I have fixed the issues with code and finished the first iteration of the abstract. I spent some time preparing the thesis file on overleaf. Would be a nice thing to do over the weekend.

## 17/07, Wed - Finishing abstract
[B008 - Advances in Understanding and Constraining Uncertainties in the Terrestrial Carbon Cycle](https://agu.confex.com/agu/agu24/prelim.cgi/Session/224548) 

[B009 - Advances in Understanding and Predicting Forest Demography and Carbon in a Changing World](https://agu.confex.com/agu/agu24/prelim.cgi/Session/229276) 

[B010 - Advances in Understanding Land System Change](https://agu.confex.com/agu/agu24/prelim.cgi/Session/226148) 

[B073 - Novel Paradigms, Processes, and Emergent Behavior in Terrestrial Ecosystem Modeling](https://agu.confex.com/agu/agu24/prelim.cgi/Session/228979)

[B106 - The Global Carbon Cycle and Its Feedbacks with Anthropogenic Change](https://agu.confex.com/agu/agu24/prelim.cgi/Session/225532)

[B109 - The Use of Remote Sensing to Evaluate Ecosystem Restoration Approaches](https://agu.confex.com/agu/agu24/prelim.cgi/Session/228714)

[B112 - Tropical Forests Under a Changing Environment](https://agu.confex.com/agu/agu24/prelim.cgi/Session/224009)



## 11/07, Thu - Abstract and mature forest

18 of november to december 7th - Brian in Panama

I believe it is taking a while because the mature forest values are just too far away.

I will:
- export and use QGIS nearest neighbor to compare methods
- aggregate and run nearest neighbor on that

Must be patient - just let it run and work on the abstract.

- Was not necessary - I believe it was just a matter of scaling. The algorithm was running on the mature forest biomass resampled to 30m, which is completely unnecessary. I am running it again now with the original 100m resolution.

## 8/07, Mon - PRISM and mature forest

Getting mature forest biomass with relation to edge pixels.

Anna Spalding - or someone else in agriculture?
Martin Solano
Jeff Hall

Other data layers:
Jorge also has access to data from the department of agriculture of Panama with 1000 sampled points across Panama of soil nutrients - probably collected around agricultural systems.

GMA application for Panama

PRISM workshop section

Committee Meeting - Late October/early November


## 5/07, Fri - Edge effects and mature forests

Ask Jeff Cardille about spatial autocorrelation and his regrowth algorithm.
Check NLL
Check NA mature forest values
Pattern of mature biomass distance from border

### GAMs
Land use alone explains 12% of the variation. Splitting the data between training and testing reduced from 12.3 to 12%, so not very much.
![](https://i.imgur.com/hQdBKUl.png)


With linear model it's 10%
![](https://i.imgur.com/FcsjDhF.png)
The weird thing is the relationship between the land use metrics and the biomass of the surrounding mature forests:

![](https://i.imgur.com/yBL2ZRR.png)


### Optim
"data_5" - 5 years of land use, up to 30 years of age
"data_10" - 10 years of land use, up to 25 years of age
"data_15" - 15 years of land use, up to 20 years of age
"data_all" - no truncating history at all
all_cat <- "age", "num_fires_before_regrowth", "sur_cover", "fallow", "indig", "protec", "cwd" (cwd as cumulative water deficit)

### Mean biomass per ecoregion (nearest neighbor)
[1] "----------------------------------------------------"
[1] "data_5"
[1] "age"
[1] "R-squared: 0.264071556596866"
[1] "----------------------------------------------------"
[1] "data_5"
[1] "fires"
[1] "R-squared: 0.248694144368822"
[1] "----------------------------------------------------"
[1] "data_5"
[1] "age_fires"
[1] "R-squared: 0.265930958630639"
[1] "----------------------------------------------------"
[1] "data_5"
[1] "all_cat"
[1] "R-squared: 0.278682213112635"
[1] "----------------------------------------------------"
[1] "data_10"
[1] "age"
[1] "R-squared: 0.258415309528758"
[1] "----------------------------------------------------"
[1] "data_10"
[1] "fires"
[1] "R-squared: 0.242982017571527"
[1] "----------------------------------------------------"
[1] "data_10"
[1] "age_fires"
[1] "R-squared: 0.260463638075757"
[1] "----------------------------------------------------"
[1] "data_10"
[1] "all_cat"
[1] "R-squared: 0.271190433107168"
[1] "----------------------------------------------------"
[1] "data_15"
[1] "age"
[1] "R-squared: 0.250085077244723"
[1] "----------------------------------------------------"
[1] "data_15"
[1] "fires"
[1] "R-squared: 0.235855528106731"
[1] "----------------------------------------------------"
[1] "data_15"
[1] "age_fires"
[1] "R-squared: 0.252758992463627"
[1] "----------------------------------------------------"
[1] "data_15"
[1] "all_cat"
[1] "R-squared: 0.262614774813513"
[1] "----------------------------------------------------"
[1] "data_all"
[1] "age"
[1] "R-squared: 0.295260398927223"
[1] "----------------------------------------------------"
[1] "data_all"
[1] "fires"
[1] "R-squared: 0.265105767970166"
[1] "----------------------------------------------------"
[1] "data_all"
[1] "age_fires"
[1] "R-squared: 0.295990672664542"
[1] "----------------------------------------------------"
[1] "data_all"
[1] "all_cat"
[1] "R-squared: 0.304023715509109"

### Nearest neighbor biomass
[1] "----------------------------------------------------"
[1] "data_5"
[1] "age"
[1] "R-squared: 0.529855316899076"
[1] "----------------------------------------------------"
[1] "data_5"
[1] "fires"
[1] "R-squared: 0.525386920253416"
[1] "----------------------------------------------------"
[1] "data_5"
[1] "age_fires"
[1] "R-squared: 0.529977141644358"
[1] "----------------------------------------------------"
[1] "data_5"
[1] "all_cat"
[1] "R-squared: 0.53176720620989"
[1] "----------------------------------------------------"
[1] "data_10"
[1] "age"
[1] "R-squared: 0.502645183882817"
[1] "----------------------------------------------------"
[1] "data_10"
[1] "fires"
[1] "R-squared: 0.497680012673496"
[1] "----------------------------------------------------"
[1] "data_10"
[1] "age_fires"
[1] "R-squared: 0.502727440994759"
[1] "----------------------------------------------------"
[1] "data_10"
[1] "all_cat"
[1] "R-squared: 0.50305613964344"
[1] "----------------------------------------------------"
[1] "data_15"
[1] "age"
[1] "R-squared: 0.480715013826312"
[1] "----------------------------------------------------"
[1] "data_15"
[1] "fires"
[1] "R-squared: 0.474094172199312"
[1] "----------------------------------------------------"
[1] "data_15"
[1] "age_fires"
[1] "R-squared: 0.48088425770059"
[1] "----------------------------------------------------"
[1] "data_15"
[1] "all_cat"
[1] "R-squared: 0.481472423068221"
[1] "----------------------------------------------------"
[1] "data_all"
[1] "age"
[1] "R-squared: 0.514053925182426"
[1] "----------------------------------------------------"
[1] "data_all"
[1] "fires"
[1] "R-squared: 0.498690433074939"
[1] "----------------------------------------------------"
[1] "data_all"
[1] "age_fires"
[1] "R-squared: 0.515138794764705"
[1] "----------------------------------------------------"
[1] "data_all"
[1] "all_cat"
[1] "R-squared: 0.515824922512492"

### Fit asymptote - nearest neighbor mature biomass (raw)
[1] "----------------------------------------------------"
[1] "data_5" - 5 years of land use, up to 30 years of age
[1] "R-squared (fixed asymptote, fit growth rate): 0.47746951448223"
[1] "R-squared (fit asymptote, rate fit from age): 0.0134674823412842"
[1] "----------------------------------------------------"
[1] "data_10" - 10 years of land use, up to 25 years of age
[1] "R-squared (fixed asymptote, fit growth rate): 0.449495463965637"
[1] "R-squared (fit asymptote, rate fit from age): 0.00822052653618196"
[1] "----------------------------------------------------"
[1] "data_15" - 15 years of land use, up to 20 years of age
[1] "R-squared (fixed asymptote, fit growth rate): 0.422808759884437"
[1] "R-squared (fit asymptote, rate fit from age): 0.00711848868360519"
[1] "----------------------------------------------------"
[1] "data_all" - no truncating history at all
[1] "R-squared (fixed asymptote, fit growth rate): 0.444887876578953"
[1] "R-squared (fit asymptote, rate fit from age): 0.021890829768269"

### Fit asymptote - nearest neighbor mature biomass (mature_biomass > secondary forest agbd, within 1sd of mean ecoregion)
[1] "----------------------------------------------------"
[1] "data_5"
[1] "R-squared (fixed asymptote, fit growth rate): 0.445982932798548"
[1] "R-squared (fit asymptote, rate fit from age): 0.00178027477928929"
[1] "----------------------------------------------------"
[1] "data_10"
[1] "R-squared (fixed asymptote, fit growth rate): 0.409508387902555"
[1] "R-squared (fit asymptote, rate fit from age): 0.000341293852312481"
[1] "----------------------------------------------------"
[1] "data_15"
[1] "R-squared (fixed asymptote, fit growth rate): 0.374228168554021"
[1] "R-squared (fit asymptote, rate fit from age): 0.00242396898040558"
[1] "----------------------------------------------------"
[1] "data_all"
[1] "R-squared (fixed asymptote, fit growth rate): 0.434140919238666"
[1] "R-squared (fit asymptote, rate fit from age): 0.012970205717891"





Compared classification to [EC](https://developers.google.com/earth-engine/datasets/catalog/JRC_GFC2020_V1) and ESA Worldcover, and MAPBIOMAS 33 year classification is the most conservative (includes more consistent forests - understandable as it's using many years of history to classify, rather than doing it at yearly increments).


![](https://i.imgur.com/HebQ9nb.png)



I am realizing the biomass for edge mature forest pixels can be unreliably low because, well, it's an edge - it is the average of the biomass values in cleared areas and non-cleared ones.
![](https://i.imgur.com/IJOUX5O.png)
 
 ![](https://i.imgur.com/3X8Gfix.png)
 On darker colors, we see lower biomass values, and we can see how they are not as trustworthy.

I applied a similar filter as I did on the secondary forests on the mature forests that are being used as reference for the nearest-forest-asymptote calculation.

I was wondering if the trend would change whether I restricted ages and land use histories to include only older forests, or younger forests, that have been through long periods of pastureland. That did not change the R squared much. When I incorporated only younger forests, the

Remember that AGBD was the average in 1 hectare cells. I believe a lot of this is driven by cells that are classified as the same AGBD but are far away.

We need to consider only secondary forests that are not immediate neighbors, say less than 200m from a mature forest.

![](https://i.imgur.com/J7fLV84.png)


A limitation of the nearest neighbor algorithm, even after removing edges, is that there may be big patches of mature forest that are not considered if there is a smaller patch closer by:

![](https://i.imgur.com/v70kOd7.png)



![](https://i.imgur.com/Xvn8bZX.png)
![](https://i.imgur.com/QCqLasU.png)
![](https://i.imgur.com/LC1zay8.png)
![](https://i.imgur.com/RxJJoI6.png)


## 1/07 - Predict mature forest by environmental factors
![[Ana Did Science Today-2.pdf]]



## 11/06, Wed - Kriging and interpolation

Would be interesting to start writing the methods this weekend.

restricted maximum likelihood for GAMs instead of cross-validation

Erik Johnson - STRI soil labs
Log-log transformation changes the relationship from additive to multiplicative for GAMS.


## 10/06, Mon - Finishing writing

It has been difficult to push through writing something that I do not understand well and do not feel particularly excited about.
Maybe I just need to accept it will be less than ideal and just finish it and submit. I can always try again later if I want to get the fellowship for another part of my research.



## 4/06, Tue - Coding and writing

for fitting mature forest biomass - could use GAMs, or fit monotonic or unimodal curves, use something 


[academic_award_process_guidelines_2022.pdf (si.edu)](https://stri.si.edu/sites/default/files/academic_award_process_guidelines_2022.pdf)

1250 USD/month

- drone flights on agua salud
- land use classification comparison
- apply for 2 months

- Abstract is often the most important part.
- Make clear that this is a part of the broader picture and the goal of this chapter.
- Broader timeline and highlight the time you will spend in Panama.
- Highlight what has already been done for Brazil and build off on it for Panama.
- make explicit what will be done while I am at STRI.

Add a table for remote sensing products
like log-linear or a standard model?
GAM - reduce knots to 3


Philips et al 2

002 - increase in lianas in Amazonia

nearest few neighbors mature forest from secondary forests.

https://www.naturalearthdata.com/

## 31/05, Fri - GEE

Christian Seiler, at Queens - works with Earth System Models and Genetic Algorithms.

https://cseiler.gitlab.io/research.html

## 27/05

Got github copilot with the free trial - must remember to update it asap.

https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-git-large-file-storage

## 25/05 - 26/05, Sat - Sun - Stan considering distributions

There were many git issues. they were all solved with the config file:
```bash
[remote "origin"]
	url = https://[[personal access token]]@github.com/AnaZonia/moon_notes.git
	fetch = +refs/heads/*:refs/remotes/origin/*
```


Sigma should be thought of as percentage of true value that is expected to vary.

Dealing with censored data:
// either set parameters with a parameter with a lower bound of 
// or add a value with a distribution ranging from zero to the maximum year of colonization

> fit.gamma$aic
[1] 21223956
> fit.weibull$aic
[1] 21165728
> fit.normal$aic
[1] 21603847

## 22/05/2024, Wed - 
Every Tuesday, it's time to think over the week's tasks and prioritize.

Emails have been sent and there's been some good advance on the logistic side of things, but very little coding done as of yet.

## 21/05/2024, Weekly Goals
### Articles to read this week
- Forest restoration in practice across Latin America
- Flores 2024
- Global Forest Frag Ma 2023
- Zuquim 2023

### Emails to send
- Obsidian help group
- Andrew and Renata
- Jeff Hall
- Jeff Cardille

### Code to write
- Export rainfall
- Organize modelling in R
- Finish modelling in Python

Next week, I need to spend some time to think about PANGEA and the Alliance.
### Goals for next week
- Read over [[PANGEA - PAN tropical investigation of bioGeochemistry and Ecological Adaptation\|PANGEA]] Ecosystem Structure, Function, and Diversity Working Group conclusions and make my points. Would be interesting to do this with Katie.
- Send [[000 Chapter 1 - Predicting Regrowth in the Amazon\|000 Chapter 1 - Predicting Regrowth in the Amazon]] summary to collaborators. Does not need to be anything too elaborate I don't think, just show where the code is right now.

## 21/05/2024, Tue - Supervisor meeting

- Run it with a flat prior
	- I already have, but that did not run with the parameters we have.
- Simulated annealing

Distinguishing between mature forests (all forest since 1985) and fallow would be useful.

Biomass data for 2010 - could that help, by adding more data - running it for secondary forests in 2010?

## 20/05/2024, Sunday
- sample and export data again to make sure it's the exact same.

![](https://i.imgur.com/H18r1f2.png)

Now I have time since fire before observation (2020), but I wonder if time before regrowth would be best (basically time before observation - age?)

Also, how long before regrowth was the fallow?

## 16/05/2024, Thursday

Email Jeff Cardille
- python script and dataframe
- proposal for research
- AVOCADO - improvement on it?
- Reaching out to MAPBIOMAS people for collaboration. Here is my summary on it.

foreach with lab supercomputer 
use so that each core could use a partition of the data
if it's gigs worth of data, ask for Brian's help on partitioning it
Each core is saving things - make sure that one core per computer is compiled first, then stop, then run everything else afterwards.

if running stan across multiple cores, I need to compile it first. it'll try and run and compile 
in R portion of stan code, dont run 30 instances, run only first. and run the dumbest version of it first so that it compiles.

## 13/05/2024, Chapter 1
- QGIS earth engine can be useful for publication-grade images

detecting changes - detect deforestation and regrowth
- seasonal changes
- classifying with seasonal patterns of each land use class
- uses bayesian stats to use previous classifications to inform future classifications

- what were you thinking of doing with Brian for this?

short wave infrared is a good detector of change in humid areas - so he chose NBR

SAR can't see some things we care about - so we inhibit the detection of things.

NISAR - L band allows for looking into cuts.
the BULC algorithm allows to identify changes - deforestation, degradation, and regrowth.

The restriction is cloudy pixels.

Check if different crop types have different phenologies. At least the most popular for Panama

It shows degradation - "intermittently weird" pixels. Can show selective logging! This could not be detected with a classifier.
- How does that differ from AVOCADO?

dynamic world has a lot of daily noise

- Creative ways of searching - hyperparameter tuner. Give a .py script with the model with an optimizer task and outputs.
- Send this to the collaborator.

## 10/05/2024, Chapter 1
- check when new protected areas were established.
## 09/05/2024, Chapter 1

[Mapa global de la altura de los árboles con resolución de 1 metro - MappingGIS](https://mappinggis.com/2024/05/mapa-global-de-la-altura-de-los-arboles-con-resolucion-de-1-metro/)

Worked a lot on the GEE script today - got to exporting the images in a much better way including restricted ranges of land use history.

Am having a hard time exporting to GEE since tasks don't seem to be running properly.

## 08/05/2024, Chapter 1
Mas hoje eu preciso focar em terminar de vez os códigos de processamento e análise de dados.

Restricting to forested areas in 1985 does not avoid the possibility that these forests are "fallow", meaning they were already disturbed before 1985.
The only alternative I can envision is maybe what was done by Jeff Hall's postdoc, in which she defined forest age stratification with landsat. I am unsure whether this would be doable for 1985.

### Goals for next week
- Read over [[PANGEA - PAN tropical investigation of bioGeochemistry and Ecological Adaptation\|PANGEA]] Ecosystem Structure, Function, and Diversity Working Group conclusions and make my points. Would be interesting to do this with Katie.
- Send [[000 Chapter 1 - Predicting Regrowth in the Amazon\|000 Chapter 1 - Predicting Regrowth in the Amazon]] summary to collaborators. Does not need to be anything too elaborate I don't think, just show where the code is right now.

## 07/05/2024, Tue - Chapter 1

- Build a correlation matrix with R
- Check for multicollinearity. Correlation structures may not be found easily if they don't follow a linear trend.
- Check variance inflation factors.

**Sensitivity analysis** - checking how the fit will change with either 5, 10, or 15 years of history.

**Checking for different effects of age and number of fires** - remove or add each individual term one by one to see its effect.

**Preventing local minima** - use as starting point the fit of the last round - can only improve from the previous finding.

## 06/05/2024, Mon - Chapter 1

I'm realizing that there is no need to export all data all over again if I am restricting the "ages" vector - I can just export ages again, and rename it accordingly, and mask the unified image once it's time to export. Also, I can just export the unified image once and it'll be good - the other predictors can be added gradually.

Also could be interesting to verify what is the minimum age that is helpful to the model - should I add one year old forests? what about two, or three year olds?

There is good reason to believe there has been change in fire regime before and after 1985 - that's exactly democratization years.

[[3 Floresta Aleatória/Variáveis Censuradas e Truncadas\|Variáveis Censuradas e Truncadas]] - há maneiras de lidar com variáveis censuradas, que é o caso do histórico de uso de terra.

**Accessibility** - Missing data can be another parameter - another unknown value.

- Start from the smallest scale that makes sense with stan (constant parameters) just to get the syntax working
- Simulate data and run it with stan afterwards.

[brms: An R Package for Bayesian Multilevel Models using Stan (r-project.org)](https://cran.r-project.org/web/packages/brms/vignettes/brms_overview.pdf)

[Estimating Non-Linear Models with brms (r-project.org)](https://cran.r-project.org/web/packages/brms/vignettes/brms_nonlinear.html)
[Andrew MacDonald - Simple nonlinear growth (aammd.github.io)](https://aammd.github.io/posts/2022-11-21-growth-curve-known-age/)

[Andrew MacDonald - Discrete-time population growth in Stan (aammd.github.io)](https://aammd.github.io/posts/2023-11-15-ives03-ts/)


## 05/05/2024, Sun - Chapter 1

Since tomorrow I am meeting Andrew, today I need to take a quick refresher on bayesian to be able to keep a conversation going with him.

Exporting the image with the 30x30 resolution works before sampling for the points needed. Also, having it as image is best since masking and other operations can be done easily and quickly.

I'm realizing there is a lot I want to do regarding the project planning (reading the papers and all) but for now I should really just finish the code and the README.

## 01/05/2024, Tue - Chapter 1
After the weekly meeting:
- Andrew's idea to use Bayesian to infer what happened to old growth forests has happened to new growth would infer that the trends we observe for young forests are the same for old growth. We do not, however, know if burn rates were the same before 1985 as they were after.
- Therefore, the best way forward is to constrain history ranges. That could be 5 years up to 15 years of age, and see when the benefits start to diminish.

So, the goal for this week is to:
1. Finish writing the summary of options and send out the code, as well as the methods, to collaborators. Ask for advice, potentially to schedule meetings, to ask about the functional form and the optimizers.
2. Study bayesian so I can ask Andrew on monday about optimizers and how they work. Ask direct questions to him about the methods in general.
3. Finish implementing the hyperparameter tuner with Hossein
4. Mask only forests that were mature in 1985 and that were up to 15 years old. Test run for different configurations.

### Journal Club
- Ask Fiona about wall art
- [[2 Research/Crouzeilles 2017 - Ecological restoration success is higher for natural regeneration than for active restoration in tropical forests\|Crouzeilles 2017 - Ecological restoration success is higher for natural regeneration than for active restoration in tropical forests]]

## 29/04/2024, Mon - Chapter 1
After meeting with Brian, the priorities seem to be to finish organizing the code and writing the summary of the project to send out.

sensoring - you haven't observed everything, but you can make inferrences from what you have not observed.

- Final goal is to compare the predictions with other results, plotting predicted versus observed.

## 24/04/2024, Wed - Chapter 1

Considering options to export feature collection to google earth engine.

Having issues because of the projection of the climate data. Trying to reproject.

When tried to stratifiedSample 1000 points per ecoregion first and then use reduceRegions:

LU_sum_sampled = LU_sum.reduceRegions(stratified, ee.Reducer.first(), scale = 30, crs = proj.crs())

That ran out of memory - too many pixels at too high a resolution. Ideally, stratifiedsample will be done directly on the image with all bands added.

Since that's generating "Error: Projection error: Unable to transform features into projection", that means the large resolution images must be reprojected first.

Adding biomass and mature forest biomass.

The code works well when it's sampled with categorical variables first, but export breaks when I try to sample with the higher resolution given (landsat). That's fine for now, but I'm going to double check what the consequences are.

### Journal club - Carbon offsets in Panama

Incentives for forest conservation and regrowth - a document we can do with Cristina, talk to Guido, and hopefully get it published in Panama.
- Should we do an infographic?

[[2 Research/Shinbrot 2022 - Natural and financial impacts of payments for forest carbon offset - A 14 year-long case study in an indigenous community in Panama\|Shinbrot 2022 - Natural and financial impacts of payments for forest carbon offset - A 14 year-long case study in an indigenous community in Panama]]

[SoilGrids1km — Global Soil Information Based on Automated Mapping | PLOS ONE](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0105992)

## 23/04/2024 - Department Day
### Obsidian workshop
- What is Obsidian
- Advantages of Obsidian
	- Internal Links
	- Excalidraw
	- Canvas
	- Github
	- Digital Garden
	- Graph view
- What is Zotero
- How to link things?
	- Better Bibtex
	- Zotero for Obsidian
	- Pandoc
	- Templater
[[Obsidian\|Obsidian]]

## 22/04/2024 - Chapter 1

- Hamiltonian Monte Carlo could be helpful to fit my model without getting stuck on local minima and having to do small adjustments with a weird functional form - I guess?
	- Asking Andrew about this would be awesome!
- Fiona is interested in what we have going for the Panama forest incentives document. It could be a good idea to work on it to make it publishable and useful and add it to the portfolio.

Sampling points - direct sampling isn't working to increase the projection of the higher resolution data (which I could just resample like I did for biomass, but maybe that's still unnecessary)

## 20/04/2024, Sat - Chapter 1

Stratified points won't export for the whole country at once. - I wonder if feature collections take more time, or is it the sampling process that takes too much computational power?

sampleRegions will sample over NAs so you end up with less points than what was wanted. so stratifiedSample really is the best way to do this. I think stratifiedSample wasn't working because it was being run with ecoregions as a feature collection, which was then projected to image - importing ecoregions as image made everything much faster.

Exports are going well. Now trying to export CSV for the whole country.

Now the question is that there are few points with non-pasture history. I will try to sample specifically those to run the analysis with them.

Also, I am adding last observed land use type and mature biomass which hadn't been exported properly before as images to the cloud.

fallow has a different resolution - recalculate it.
## 19/04/2024, Fri - Chapter 1

Some time this morning was spent cleaning, and then a bit more once arriving in lab so I chose how to track my time.

I like the simplicity of having google calendar open and editing it throughout the day, and having a look at my tasks as the day goes.

Looking at the code, a lot is already done. I managed to focus quite well for the first hour, and am still going. I'm thinking of how to keep track of things that I'd like to work on in the future while still prioritizing the task at hand.

I think google tasks may not be the best way to plan work tasks, although it does help keep me on track with what I have to do.

Chapter 1
- Get model running. For this, I need to have the CSV files exported and merged properly. The first one is now exporting and I just need to wait for that to finish and see how that goes.
In the meantime, it would be nice to look into:
- How the secondary forests look in comparison with a background - that can be done by clipping to an area of interest
- Mature forest biomass and fragmentation
- Organizing the code

Realized the masking needs to happen before the sampling and exporting.

Today, I got some work done, but it was still hard to get started. I think I'm still settling into the new way of things being.

The best way to get this to work well is to have interesting/useful podcasts going so I'm less easily distracted or tempted by running off-track.
## 18/04/2024 - Planning upcoming coding
Github hasn't been updated in a while. I remember I had some issues exporting the data from google earth engine, because I thought I needed to export tables right away.
I finally ended up exporting images to google earth engine, and found that to be way easier, faster, and more replicable. For a second I exported tiles of layers, but I now find that exporting individual layers is best (they all need to be in Landsat projection anyways).
I already know how to get the table from the data:
- create feature collection of 10000 randomly selected pixels for each region
- extract data for each one of them separately as a CSV
- merge all feature selections and run model there.
README needs to be fixed.
So the goal is to do all this tomorrow and write summary next week to send to collaborators.

Another thing I was working on was removing isolated pixels that could be misclassified - keeping only pixels with at least some amount of neighbors.

### Meeting
**Evapotranspiration/Climatic variables**
- Adding historical ET - Asking Catherine could be a good idea. Also, schedule a meeting with Fiona the following week to talk about the climatic variables and the soil map.

**Chapter 2**
- Jorge also has access to data from the department of agriculture of Panama with 1000 sampled points across Panama of soil nutrients - probably collected around agricultural systems. That could also be interesting for us to use for the nutrient map of Panama.

**Tree plantations**
If we're expanding to Cerrado and Atlantica, there are more tree plantations to consider.
- How does MAPBIOMAS classify tree plantations?
- Do we need other maps of tree plantations?

**Weekly Goals**
- Finish the CSV files
- Run the model with the integration of climatic variables
- Compare medians with total values. Consider last land use type, as well as all other variables.

**Next goals**
- Finish README and make code nice and reproducible for the collaborators to read next week
- Look in detail into MAPBIOMAS classification quality and which land use types does it do worse in. Also a nice preparation for when we reach out to other people working in land use classification. (Elizabeth, Jorge, Jeff Hall and Kendra)

## 16/04/2024

### Meeting with Jorge
Jorge is making a map of nitrogen addition in Panama by interviewing farmers. This should make a map of nitrogen usage by district, watershed, and land usage. Would be an interesting way to check if there are significant differences in ways that farmers fertilize the same crops depending on the part of the country they're in.

Jorge also needs history of mangrove change for a few parts of the country, especially this one:

![](https://i.imgur.com/zfWYkm8.jpeg)

So there's good room for collaboration as we work on things that are useful to each other. Keep Jorge posted on the progress of chapter 2!

## 12/04/2024
- [Oliver Coomes](https://www.mcgill.ca/geography/people-0/coomes) does interesting research in the geography department.
 
## 09/04/2024

### Meeting with Brian
- Interesting parts of Chapter 2
	- The effects of nutrient addition with Jorge

[[PANGEA - PAN tropical investigation of bioGeochemistry and Ecological Adaptation\|PANGEA - PAN tropical investigation of bioGeochemistry and Ecological Adaptation]]

## 25/03/2024 : 07/04/2024 - Organizing and writing

Talked to Olivia Milloway about [[Science Journalism\|Science Journalism]].

**AAAS mass media fellowship** - place people in US institutions for summer media internships. Must be an American citizen, but a lot of the alumni would be cool inspiration.

### Encuentro con Jimena Pitty
After I spoke to her at the [[000 Ana Did Science Today#Science communication\|NEO course]], it becomes more clear that I can work with science communication if I want. Along with Jeff Hall, she is preparing an Agua Salud exhibit at Culebra for children. Also, she is working with a Brazilian PhD student that has a background in biotechnology and is transitioning to education.
Thinking of the essays I'd like to be writing, she mentioned how it would be interesting to look into:
- how to communicate with farmers
- writing simple, eye-catching text like the STRI magazine does

### Soil data
#### Meeting [[Agudo, Dayana\|Agudo, Dayana]] and [[Nottingham, Andrew\|Nottingham, Andrew]]

- pH is an indicator of a healthy soil microbial community
- microbial biomass related with total soil carbon
- stoichiometric ratios in microbial biomass could be interesting to look into, and that data seems to be available for ForestGEO.
- Total soil carbon content relates to high nutrients

Recommended contacting [[Dent, Daisy\|Dent, Daisy]] and [[Dalling, Jim\|Dalling, Jim]] for soil maps.

#### Meeting with [[Hall, Jefferson S.\|Hall, Jefferson S.]]
- In general, geology-based soil maps are preferred.
- Attention to soil map classification systems. USDA system is different from FAO, and there are 
- Agua Salud is quite phosphorus poor - lower middle of the Amazon basin.
- rainfall often overlaps with fertility in soils
- We can compare 2012 to 2020 carbon to estimate deforestation and regrowth 
- nitrogen fixer identity matters. lai ha rao ecology letters paper
- Agua Salud has good allometric equations for dry forests.
#### Useful contacts
- [Kendra Walker at UCSB](https://emlab.ucsb.edu/index.php/about/our-team/kendra-walker) has done a 30x30 land use change map for Panama.
- [[Teixeira-Anderson, Kristina\|Teixeira-Anderson, Kristina]] works with GeoTrees
- [[Davies, Stuart\|Davies, Stuart]] can give ForestGEO data, which would be very useful (everyone said that!)
- Kasey cushman - airborne and satellite data with agua salud data
- [‪Katherine Sinacore‬](https://scholar.google.com/citations?user=6fq4FOEAAAAJ&hl=en) is a previous postdoc

#### Reading
- Ben Turner/Condit paper - [Pervasive phosphorus limitation of tree species but not communities in tropical forests | Nature](https://www.nature.com/articles/nature25789)
- 2023 article on patches that are more likely to persist as secondary forest [Landscape context importance for predicting forest transition success in central Panama | Landscape Ecology (springer.com)](https://link.springer.com/article/10.1007/s10980-023-01694-y)
- [[Tropical carbon sink accelerated by symbiotic dinitrogen fixation\|Tropical carbon sink accelerated by symbiotic dinitrogen fixation]] - Levy-Varon
- [Feedback loops drive ecological succession: towards a unified conceptual framework](https://onlinelibrary.wiley.com/doi/full/10.1111/brv.13051)

I did a lot of mapping for the TAship as well - that took a few days.

### Marine lab - Sean Connely
He mentioned what I am interested in is Systematic Conservation Planning - using quantitative methods to inform policy. More applicable research than pure science.
- Hugh Possingham
- Mic McCarthy
- Paul Armsworth
- NimBios Institute - University of Tennessee

## 08/03/2024 - INPA

### Noemia Kazue Ishikawa
- trabalha com cogumelos e povos indígenas amazônicos.
Dr. Fidalgo e Dr. Prance são pioneiros na micologia, e Dr Prance na etnobotânica na Amazonia.
Izonete - Litter Decomposition and Ectomycorrhizae in Amazonia

A identificação desse fungo ajudou a promover a comercialização de cestaria indígena. O Marasmius sp. também é usado por aves para fazer ninhos (o fungo chama black horsehair em inglês).

Novo projeto
Diálogos científicos multiculturais sobre a sociobiodiversidade na Amazônia com potencial bioeconômico. 

**Buscar depois:**
- O livro dos cogumelos yanomami ganhou um premio Jabuti!
- TEDx Amazonia
- Ruby Vargas - Livro Cogumelos da Amazônia
- Marasmius yanomami - espécie nova de cogumelos

### Resultado das conversas com [[Costa, Flávia R. C.\|Costa, Flávia R. C.]] e [[Guimarães, Aretha\|Guimarães, Aretha]]

> Floresta amazônica tem fonte de fósforo de outras fontes - "não se pode dizer que há limitação de fósforo na Amazônia."

- Existem modelos de biodiversidade botânica pra Amazônia - Numeros de espécies e composição de espécies, baseado em dados de campo.
- duração e frequencia das estações secas é importante.

#### Relevant reading
- [[2 Research/Figueiredo 2018 - Beyond climate control on species range - The importance of soil data to predict distribution of Amazonian plant species\|Figueiredo 2018 - Beyond climate control on species range - The importance of soil data to predict distribution of Amazonian plant species]] - Soil grids e mapa da [[Zuquim, Gabriela\|Zuquim, Gabriela]] com base em samambaias para panamazonia.
- [[2 Research/Zuquim 2023 - Introducing a map of soil base cation concentration, an ecologically relevant GIS-layer for Amazonian forests\|Zuquim 2023 - Introducing a map of soil base cation concentration, an ecologically relevant GIS-layer for Amazonian forests]]
- [[2 Research/Flores 2014 - Fire disturbance in Amazonian blackwater floodplain forests\|Flores 2014 - Fire disturbance in Amazonian blackwater floodplain forests]]

#### Relevant people
- [[McMahon, Sean\|McMahon, Sean]] - do STRI, trabalha com a Flavia.
- [[Quesada, Carlos\|Quesada, Carlos]] - coordinates AmazonFACE.
- Adriana Esquivel Muelbert
- Andy Walker Oak Ridge
- Mamirauá - boas bolsas pra quem quer morar em Tefé
- PPBio
- [[Tuomisto, Hanna\|Tuomisto, Hanna]] (fez um modelo de distribuição de espécies pra Amazonia)
- [[Magnusson, William E.\|Magnusson, William E.]]
- [[Barlow, Jos\|Barlow, Jos]] (vem e fica em Belém e na Inglaterra)
- ForestPlots
- Oliver Philips - trabalha com a Erika
- Felipe França
- Hans ter Steege (author of Hyperdominance in amazonian tree flora)

## 26/02/2024 - 03/03/2024 - Trabalho de casa

**Modelagem de desmatamento** é uma área interessante também. Vi a palestra do [Carlos Souza Jr. ](https://geog.umd.edu/event/invited-guest-talk-31-carlos-souza-jr-preventing-deforestation-brazilian-amazon-geospatial) e tem artigos interessantes que eu já adicionei ao Zotero pra ler. [Imazon Case Study](https://centers.fuqua.duke.edu/yyyyyyyy/wp-content/uploads/sites/7/2020/11/FINAL-Scaling-Pathways-Imazon-Case-Study-5.11.17.pdf) em Paragominas também fala de estratégias com municipalidades pra evitar o desmatamento.

[[Debate da SBPC - O Futuro da Amazônia\|Debate da SBPC - O Futuro da Amazônia]]

- Planet - emailed Ruilan to ask for access.
- Copa airlines flight change is possible and free.
- Many emails have been sent and answered! Planned almost all relevant meetings for Manaus and Panama.

### Questões para Hugo
- Enquanto me preparo para voltar ao Brasil, o que eu preciso ter em mente pra ser uma boa cientista aqui.
- As colaborações no exterior - no momento eu considero um pos doutorado no Instituto Smithsonian, o que seria uma oportunidade interessante de talvez estabelecer parcerias com o Brasil.

Acho que não vale a pena eu investir no momento em aprender persa. Já sei todas as línguas que eu queria saber, a única que eu ainda preciso mesmo aprender é libras. Até nheengatu não vale a pena aprender agora, já que não sei se realmente vou poder usar lá pra frente, e quais as línguas das pessoas que eu vou encontrar. Francês também, já sei o suficiente; saber mais pra que?

Agora eu quero aprender história, arte, política, economia. E investir no meu corpo - exercícios físicos, dança, flexibilidade. Ler bons livros, comer bem, e dançar, e já tá bom demais. O resto, é a ecologia, o meu trabalho. Acho que é só isso que eu vou mesmo estudar daqui pra frente.

## 23/03/2024, Fri : 25/03/2024 - Return to work

==Finished my part on projects 3 and 4.== Decided to wait to contact the activist, Gabriela, before publishing - turns out neither person writing it is a journalist or has the time to dedicate to a full piece on Panamanian ports, so it is responsible to be careful with what info we put out to the public. It is best if after that, if we do want to publish it, to focus on the environmental impacts part, and leave the political-economical parts (including much of what was talked about with Andrés) to be developed later, after consulting economists and reaching out to other sources. Also, this is a long term issue. Ports have been expanded since Neopanamax and will continue to be until 2040 as far as we can see, so it's a long battle to be fought.


![](https://i.imgur.com/gLgPQSi.jpeg)
![](https://i.imgur.com/rNbpCjg.jpeg)

[[Prensa Neotropical - Puertos de Panamá.pdf]]

[[Ana Did Science Today.pdf|A história do pai da Cristina]], jornalista da Costa Rica cobrindo a invasão do Panamá.

## 2/2/2024, Fri : 3/2/2024, Sat - Pixvae

- Also curious about tides (much higher in the Pacific than in the Atlantic). Are they the same at each longitude at the same time?

### The Pacific

The reef is definitely healthier than the Caribbean one. Many sharks, turtles, dolphins, schooling fish and staghorn sea stars. The coral was layering on top of each other in a super interesting way, really looking like a forest canopy. <mark>I'm curious about shark movement and fishing pressures.</mark> Has there been a recovery in shark populations? I wonder how modelling can help point out helpful protected areas.

### The talks

**Diana** works on the effect of heating and salinity changes on the dominant coral species in the gulf of Panama and the bay of Chiriquí, where we are.
Gotta communicate with her about meeting Sean and sharing bayesian material.

*Upwelling and winds* - Because of the differences in Panamanian geography, the two bays have different temperatures and salinity levels due to rainfall. Corals are stressed with lower salinity (result of heavier rains) and higher temperatures, and their photosynthesis rates are lower.

I wonder if modelling the future of corals like this we can inform policy like Jon did with Hong Kong.

**Jonathan Cybulski** studies food webs.
O uso de isotopos em ecossistemas terrestres é mais complicado - I wonder why?
Fitoplancton fazem [[Photosynthesis\|Photosynthesis]] C3 - would be cool to study nutrient fluxes in marine systems. How does it work without fungi? Jon mentioned marine systems have better documented nutrient data, and there's also a lot of large scale climatic and physical data, which would be awesome.

Bayesian statistics can also be useful for a situation of many predictors - here he is using only all fixed priors at 1, but then uses MCMC to predict proportion of contribution of each prey item to an animal's diet.

***Really cool application*** - prove that birds are eating biofilm to prove that an area is worth preserving.

Human-environment-climate interactions over thousands of years.

> Nitrogen is the baseline of all food webs.

Things become more enriched with nitrogen as they go up in trophic level (pee out light nitrogen and keep heavy isotopes)

The planetary boundaries paper shows that the global nitrogen cycle has been changed for decades because of human waste and agriculture.

Corals can assimilate almost any form of nutrients because of their symbiotic algae. This makes them resilient to live in nutrient poor waters (they can eat and get stuff from PS)

Hong Kong has a lot of cool corals, but also a very high concentration of people, so a lot of nutrient input.

It is possible to look at the history of coral reefs by taking a segment of the coral matrix, that can grow on top of each other for meters. This is a cool history of an ecosystem and climate!

He could identify nitrogen from different sources (the polluted river as well as the ocean). The results showed that there is less flow from the river because there has been a decrease in rainfall over 7000 years.

Massive coral cores grow like tree rings!

To tell the history of an ecosystem, it's necessary to know how corals grow. The differences between the nitrogen levels of different species can be corrected for through modelling given what each species eats.

He is doing very interesting applicable large scale ecology in coral reefs, looking at community composition and its change through time. He got to speak to the government about water quality, and the information is now used to restore reefs quite successfully! Since the stressor has been alleviated (it was only water quality)

Climate change is a global issue, but in local level there are other stressors that can also help like fishing and pollution. That can also help protect the corals for the climate change issues that are coming.

Well that's bad news for the shifting baseline case of climate change - the stressor won't really go away in that case.

**Diet** - Most of the fish from Panama comes from the Pacific. - *What was the historical human diet?*
Before this, gotta understand how did the climate baseline change over time.

Each point is about 50-150 years because that's how long a coral lives??

This is really cool - there are a lot of long term climatic changes over the last 7000 years which is interesting to keep in mind when looking at climate change!

Also looked at archaeological changes - comparisons between trophic levels can be made through different aminoacids which show the baseline of Nitrogen or show the trophic level.


## 30/01/2024, Wed - Mountain

Eu não me sinto muito confortável nas montanhas, mas fui assim mesmo. Foram conversas interessantes com Mulget, o etíope que correu desde a Patagônia até aqui. Ele me mencionou que o café arabica vem das regiões montanhosas da Etiópia e o café robusta vem das áreas mais planas do Kenya.

A vegetação do topo da montanha era interessantíssima, bem diferente do que se vê nas regiões mais baixas.

Não sei se tenho vontade de repetir a experiência. Foi interessante, mas não foi tão bom a ponto de querer fazer de novo o sacrifício de subir. Eu tinha a sensação de que eu não sabia o que eu tava fazendo, e eu acabei saindo cheia de mordida de bicho, que aparentemente não é um problema na Costa Rica, mas é um problema no Panamá. Não sei onde mais isso existe.

## 29/01/2024, Tue - Project Day

### Project possibilities
- bird friendly coffee/smart reforestation (carbon)/fruit agroforestry (local diet diversification)
	- things that farmers can optimize for, pros and cons of each
	- do better farming for nature and for people
	- future vs present outcomes
	- "why not" - if something is better and cheaper
	- highlight the issues - what can be more expensive
- this can be interesting for both government approaches and general communication

Been wondering whether to go talk to Alexis again. It would be interesting because of his connection to both places, but at this point time is so restricted I should try to reduce expectations for each specific project and really focus on learning what is important for me in the long run. It would be cool to sit and talk to him again, but there's a ton more things going on, and I gotta prioritize. También no sé qué fiable es por lo que dijo de Café Duran que no fue comprado por Colombia.

### Empresa Panameña de Alimentos - Sustentabilidad

Más grande corporación de alimentos en Panamá. Dueña de Café Durán. 80% of the market, and buy 50% of coffee of the country.

Hubo queda de producción nacional. Él dijo algo sobre la producción no ser suficiente a la demanda nacional?

Trabajan con el Banco Interamericano de Desarollo & FAO. Dijo de nuevo que hay un problema político, y las comunidades indígenas se pueden desarollar mejor si hay asistencia tecnica y material. Trabajan con la organización casa esperanza para prevenir el trabajo infantil, que niños de 14 años ya tienen que empezar a trabajar en comunidades indígenas.

**Proyecto Escuela de Cultivo de Café** - Mejorar acceso a mercados, prácticas sostenibles. Hay alianza del ministerio de desarrollo, la ONU y la EPA a hacer este trabajo de recuperación de producción pos-covid.
- Educación
- Equipamiento
- Acopo (storage)
Se genera conocimiento con los grupos de productores (aprender haciendo - aprentissaje participativa) y se difunde este conocimiento hasta otros productores de café. Se también usan videos a capacitar jóvenes.

El BDA (banco de desarrollo) ayuda con acceso a crédito.

Ya hay un documento de buenas prácticas agrícolas!

**Proyecto Granja Tulú Arriba Auto Sostenible** - Nutrición! Facilitan plantones y herramientas.
[Comarcas fortalecen prácticas de producción de café](https://www.panamaamerica.com.pa/sociedad/comarcas-fortalecen-practicas-de-produccion-de-cafe-1215921)
También hay necesidad de enseñanza financiera y de manejo de grandes fincas.

**Organización de productores cafeteros** - Hay menos cooperativas que en Colombia. La hay tiene más que ver con la exportación. También hay un problema muy serio con hierarquia y imposición sobre los productores cafeteros locales, y con intermediarios que sacan mucho lucro.

Plantar en tierra ya cansada y la necesidad de pousio (descanso inicial). Como passar por esse investimento inicial com comunidades mais pobres?

Arábica es un café suave, tiene balances diferentes. Robusta es un café más fuerte. En Panamá, la gente prefiere una mezcla tradicional. Colombianos y europeos prefieren arabica, Brasil es lo más grande productor de robusta del mundo.

La FAO does an inicial capital injection, and even after the first harvest, there is still not profit to make it back, so there needs to be a lot of inicial investment.

Se llevan a productores de café a una finca modelo también a aprender los benefícios a la biodiversidad.

> What Café Duran is doing with robusta could be useful reference for what can be done in Brazil with robusta agroforestry!

En Ipetí hay también malas prácticas - la gente quita la rama entera del árbol y después saca el café, en vez de sacar la frutita directo del árbol.

The question is whether or not this project is applicable at a large scale, and 

### Butterfly thermoregulation

Reflectance in butterfly wings is an adaptation for thermoregulation.

Tropical species were expected to be more vulnerable to temperature change than temperate species, but they were observed to be actually better at thermoregulation. The species are larger in size and this could explain this result, rather than some physiological factor. I wonder whether this would change if the model took size in consideration.

Butterfly wings are selected by predators and sexual selection, but also could be for temperature. For this, the temperature of dead vs live butterflies was measured (interesting method!) and also was expected that similar morphologies would explain thermoregulation better than similar phylogenetics. She sampled mimetic pairs across different clades of Heliconia. Turns out colors do affect temperature, but physiology and behavior do as well.

## 28/01/2024, Mon - Mont Totumas

**Shade cover** - percentage of branch cover. Since the apps to estimate cover are not always available for farmers on the phone, people are trained to work on eye estimates. It is super error-prone! It's unfortunate that there's these limitations, I bet there is a way to build an app that would calculate this more efficiently and would work on the farmers' phones.
75+60+55+20+10+20+40+40+45+55 = 42% shade
- People are unfamiliar with quantitative methods... also, there may not be a need to improve the precision of this method and there's bigger battles to be fought here, so maybe it's just a matter of prioritization that improving shade measurements is just not a concern.

**Tree diversity** - 25m transect, identify as many trees as you can and count individual species observed. Repeated up to 4 times to cover a full hectare to check for the fulfillment of the native species criteria.

**Tree height** - Using a pencil and a person of known height standing next to the tree, walk back until the pencil is about the same size as the person, and then see how many times the height of the person will cover the tree height.
9 Analidas = 14.4 m
7 Analidas = 11.2 m
12.8m average

We are also observing:
- ground cover
- epiphytes
- riparian buffers of at least 5m, hopefully 20m
- living fences
- insects

### Cloud Forest

**Bajareke** is how you call the mist in the mountain forest. Eu nunca tinha sentido isso nas florestas de Nova Friburgo, mas as florestas de lá também são consideradas florestas montanhosas (acima de mil metros mais ou menos). A altura daqui é 1900m, e o pico mais alto da Serra chega a 2300m, e Nova Friburgo a 1100 m. Apesar disso, outras sensações me lembram da Serra do Mar - a temperatura, a floresta densa.
- The forest here has a lot of berries - many amoras and tasty mountain guava!

**Biomass turnover** - Mature forest biomass here cycles every 250 years or so, meaning there is a mosaic of different succession stages. This is awesome for passive reforestation as you find seeds of all sorts of trees at all times. <mark> I wonder how this turnover happens differently in different ecosystems - why do temperate forests have longer-lived trees? How does that work in Amazon lowlands, and Southeast Asia? </mark>

### The Reserve and Regrowth
- The farm is set in the largest protected upland area in Central America. There is [[Páramo\|Páramo]] in the region, a very unique ecosystem. The farm was bought and passive regrowth began in 2008. Fallow lasted around 6 years, so the soil could recover from cattle farming. The initial intention was to just have a bird sanctuary and eco lodge, and later the idea came to have a coffee system.
- Plots are small and grown in between full forest. There are 160 hectares in total. In 2008, 50 hectares were pasture. Now 20 are pasture (for horses and a scenic trail), 10 are coffee, and 20 are actively reforesting.
- **Succession** - Naturally established trees were selected for ideal spacing and best shade species (deciduous are not preferred). Inga is an early successional tree that is good for shade, so it was selected and left behind. However, as a fast-grower with less resilience, it is more prone to pests which can decimate a monoculture. <mark>Do these species provide the needed habitat for native wildlife?</mark>
- Some plots received more diversity than others as it naturally regrew. Size and near mature forest cover seemed similar, so it is unclear why that happened.
- One grove was more managed than others - banana and Inga trees were planted for quick shade. Also since Inga trees are short-lived, young Inga are planted near old Inga so as they die, they can be replaced.
- <mark>Naturally established individuals are more resilient than actively planted ones</mark> - forest strains could be healthier somehow?
- This coffee farm is regrown on previous pasture, ranging from 10-4 years old. The 10 year old plot has surprisingly large trees - much larger than Ipetí. <mark> I wonder if with Planet data, I can build something interesting to study agroforestry success in mountain areas using high resolution data since 2016. Does Planet also have more bands than Landsat, to facilitate classification?</mark>
- There was a gradual phasing out of cattle that took 12 years from the moment of regrowth, since in the beginning there needed to maintain income from beef farming.
- Natural regrowth here was also possible because of many frugivores from bats and birds in the neighbor mature forests.
- Over time, Jeff expects that naturally there will be more late-successional species in the plot.
- **Riparian buffer** - There is no regulation in Panama for riparian zones. The distance of coffee to the river is established by slope (gets really steep near the river at times), changes in river course (flooding zones), and humidity levels that may be too high and cause mold.
	- Avoiding planting in naturally moldy areas, rather than apply fungicide, is an aspect of organic farming.

### Agroforestry practices
- Dead vegetation is left in the soil for organic matter to fertilize the coffee
- Many insects everywhere, good food for birds!
- No understory shorter than the coffee to prevent mold
- There needs to be a perfect balance between sun and shade - around 40% shade is ideal.
- Coffee is profitable, but it takes a while to transition as the soil needs to recover and then the trees must grow and fruit. Because of the cold, in the mountains coffee takes longer to fruit (6 years in comparison with 3 in Ipetí) and each year the fruit takes longer to ripen (9 months vs 6 months in lowlands). However, the slower growth makes the bean denser, which is higher quality.
- Shaded coffee plants are visibly healthier, with darker leaves.
- Different management styles can occur in the same farm, due to the needs of different coffee types, experiments on coffee productivity, stage of recovery of the land, or land use legacy (depending on the previous use of the land before being used as coffee).
- The agroforests here look much larger and healthier than the ones in Ipetí at the same age.
- Coffee farmers can get about 50 cents more per pound for certified bird-friendly coffee and an advantage for having the same buyers every year.
- **Consumers** in North America, however, tend to favor organic coffee to sustainable (Annual Report)
- **Brazil** - Coffee in Brazil is mostly machine farmed, while here in the mountains it's harder to get machinery. Also, in Ipetí and Periatí, much of the soil was damaged by machine-farmed rice.
	- Jeff has travelled to Brazil and visited two coffee farms - Un Café in São Paulo (by a Japanese family) and Grau in Cuiabá.
	- Coffee here is arabica, but in the Amazon it's robusta (lower quality). Jeff mentioned it would be hard for high quality coffee farming to be doable in the Amazon due to the hot lowland sort of forest, and it seems like local species would grow better. <mark> I wonder if cacao is a better fit for the Amazon.</mark>
	- Melissa is more pessimistic about working in Brazil. She said it is hard to get people interested in growing sustainable coffee as the farms are mechanized. Maybe there needs to be culture change?
- **Peru** - Melissa mentioned there is a law that says whatever land is forested in a person's property, will be given to the government. It's an active incentive for people to deforest so they can keep their land! <mark>I wonder how private forests are managed in different parts of Latin America.</mark>
- **Batipa Reserve** in David is a lowland teak plantation. Landowners prefer to keep the understory cleared so their workers have easy snake-free access, but studies have been done to show that having native trees in the understory is actually helpful. Interesting to think of planting <mark> non-native timber trees as well as native trees for selective logging.</mark>

### Environmental factors
**Microclimate** is a way bigger deal than I originally thought. In the mountains, they are reliant on the positions of the mountains and how that affects the mist that comes in the dry season, and also the breeze that is essential to prevent mold.
- Because of this, it's hard to tease out the effects of climate change. Lower areas can have more issues with humidity (which matches what [[000 Ana Did Science Today#Alexis\|Alexis]] said!) since here the clouds hold back a lot of the heavy rain. He has noticed more extreme weather events. I am concerned that it may be hard to explain differences in microclimate in the mountains, and that could make it hard to model regrowth in such a climatically patchy region. Another reason why <mark> my model probably won't work in the mountains...</mark>

**Loess** soil -  <mark>I would like to get to know more about soil types in here and in Ipetí </mark>

### Social context
This place was built by workers from the neighbouring regions. The people settled in the past for subsistence farming and were given uso capião/direito de posse/homestead by the government that allows them to use the land, but not sell or mortgage it. There is also a Ngobe reserve nearby, and indigenous peoples used to also work on these farms for the campesinos.
The natural reserve established nearby took off the right of people to homestead, so only the largest two out of all of them are left today and still do beef and subsistence farming.

People here don't eat a lot of fruits - I heard a lot of that is because of *American diet influence*, as people learned to eat more fried foods and meat. <mark>I wonder if a comparison with Colombian and Costa Rican diet would show a lesser consumption of fresh fruits by Panamanians, and how much that changes across class.</mark>

Over time, children of these families wanted more to work in other things. Jeff also says that it is important *to allow people to not rely on the forest to make a living,* and that for that there needs to be roads and schools built around isolated homestead communities. I see an appeal to that, but I also see a difference between for example wanting to build roads near isolated indigenous communities that are still subsisting sustainably and healthily.

### Wildlife
 **Pumas, jaguars and tapirs** are present.
 - There are more jaguar observations now - could be because of better placement of cameras, but also could be because there are less hunters now and there are more prey mammals now.
 - female jaguars need to keep their cubs in the same place for up to 8 months, and bring them food. In the mother's territory there are overlapping males, so a male cub will leave the mother at one year old to avoid conflict. A female cub will stay with the mother for two years to get more hunting training.
 
**People's reputation improves if they work more sustainably** - It was also noticeable how the reforestation workers in Ipetí spoke about their work with pride, and in general poachers also gain status if they shift activities to ecotourism. <mark>Would be interesting to explore pros and cons of ecotourism as a solution.</mark>

### Consumers and power
Consumers are mostly in the US, Canada, and Japan. Much of it is sold in gift shops at zoos and aquariums.
Not as much is sold in Latin America. Then, it makes sense why the funding would be done for North American birds. It is unfair how the purchasing power of consumers is determinant of where conservation efforts are sent. However, looking at the annual report, it seems like there are also efforts being made in other parts of the world and there is more efforts into 

**Criteria for bird-friendly coffee**
![](https://i.imgur.com/dUm3mfu.jpg)

- Organic
- Zero deforestation (10 years)
- Biodiversity conservation
And either:
- Agroforestry
	- Average 40% shade cover
	- 10 species for hectare, over 60% native
	- No bird hunting allowed
OR
- Forest conservation (pilot - more common in cocoa)
	- Forest area is equal than or larger to the bird friendly crop area
	- No more than 2km away from production area
	- Reserve management (prevent logging and hunting)

**Best practices**
- Planning for canopy layers
- Not removing fallen branches or epiphytes
- *Traceability* - keeping certified products from mixing with non-certified on the production path from farm to consumer.




## 27/01/2024, Sun - Ciencia Social en Volcán

![](https://lh7-us.googleusercontent.com/NQ5hUOuPLA1VhqMlf1hfaaopCwmBXSo_fe4f5h_xSI64yRLfnAIof61cpc2wjF4tD4s9Ke_bPd_o-cmFxZjkjVsvFEIWMl_f8xTYRrd-VXY62Oiw0gWrwwHj609Ayby12Lkr7xKs7HIkMkR2gRlXuc-ofw=s2048)
### Roberto y su familia

- Roberto trabaja en turismo y rescatismo en el volcán Barú. Turistas vienen para los miradores del volcán y se quedan 8-15 días subiendo el volcán.
- **Buena vida en Volcan** - la gente no quiere salir de aquí por lo caro que son las cosas en la ciudad grande. Hay familias que viven por generaciones aquí y los niños se quedan - diferente de Ipetí...
- Hay almejas de río (conchas). Water here is extremely high quality, so much that it's won prizes for it and there's awesome local beer!
- Dice que hay poca reciclaje y hay humo tóxico de quema de basura a veces.
- Su familia tiene cultivos de lechuga, maíz, cebollas, y plátanos. Usan abono natural, insecticida o fungicida cuando necesario.
- Hay muchas hidrelétricas en la región, pero la luz se va todos los días. La energia se vende a Costa Rica, que solo produce energia renovable suficiente a 90% de sus necesidades.
- **Control de natalidad y salud** - dijo que está muy bien en la región. También los perros - en Ipetí eran débiles y enfermos, pero aquí están saludables y hay pocos callejeros. Pero todavía se queja de la salud pública. Como dijo Daniel, es cierto que medicaciones cuestan bien caro, pero yo me quedo confundida con eso. Cuando me fui al hospital fui muy bien recibida, y la gente en Tortí parecia satisfecha con el cuidado, pero puede ser solo un momento específico

### Alexis
Cafetero, trabaja con Durán. Tiene su cultivo pequeño en su casa.
- Hay muchas **variedades de café**:  Caturra, caracolillo, mormon, magarojipi. Caracolí es robusta, más acido, y los otros son variedades de arabica, más suave. Las montañas son mejores a cultivar arabica, bajo sombra.
	- Dijo que Café Duran fue comprado por Colombia (pero no parece verdad). Hay confederaciones de café (Café Balboa) que también trabajan con la gente. El café de diferentes partes de Panamá (Colón, Coclecito, Volcán/Boquete, Veraguas)
	- Durán tiene finca propia pero también compra directo con la gente.
- **Cultivo** - The water is a blessing and a curse. The main concern is the mold (Mycena citricolor) that grows on coffee when humidity is too high. With climate change, there is more rain, so there is also more need for fungicide.
	- La broca del café (besouro Hypothenemus hampei) está siendo derrotado con una cepa mutante en qué el gusano le come a otros gusanos.
	- Excremento de gallina es un buen fertilizante
	- Es dificil quitar de todo la ganadería, pero se la puede diminuir. Así como el uso del pesticida - si no le quita de todo, se le puede diminuir.
- **Diferencias entre Ipetí y Volcán** - Aquí la gente tiene mejor calidad de vida. El problema es que los incentivos no llegan a la gente allá - unos agarran mucho y no llega a los demás. Hay gente preparada, pero hay necesidad de *entrenamiento*.
	- Allá también los santeños/colonos dañaran al bosque del otro lado de la carretera, que también dificulta mucho la vida de la gente.
	- La calidad de suelo varía, pero aquí hay ceniza volcánica.

### Frank
- Trabaja en la cafetería. Los turistas son de la Ciudad de Panamá, de EEUU o Europa, a ver el volcán o hacer ecoturismo/agroturismo. Muchos se jubilan aquí.
- **El río Chiriquí Viejo** era chevere para bañarse y pescar. Las hidroeléctricas dañaron eso, hace 5-10 años. Ellas cortaron la dirección de movimiento de los pezes que no lograron más subir el río a reproducirse. Las concesionarias fueran vendidas a compañías de afuera. La gente protestó, pero no lograran impedir las construcciones.
- Hay monopólio de partidos políticos, entonces es difícil que todo cambie (qui pro quo).
- Las calles principales son limpias, pero hay problemas en otras partes de la ciudad. La basura va a un vertedero, dónde  la quema.
- Los invernaderos están más lejos, donde se cultivan las flores y tomates, a protegerlos del frío y de insectos. En su dirección, hay Cerro Punta, donde se cultivan fresas, cerezas y vegetales.
- **Self-subsistance** - the community produces everything it needs, and some more of it comes from the neighboring community of Cerro Punta.
- **Reforestación es excusa para la extracción minera** - hay compañías que se logran tierra con la intención declarada de reforestar, pero hacen minería. La montaña es muy rica, incluso en oro, entonces se quitan la tierra a la gente más humilde.
- Hubo una guerra con Costa Rica por el território de la región (hay un monumento a eso en el límite con Costa Rica). También huvo disputa de Costa Rica con Nicaragua que se resolvió con diplomacia.

### Sandy y Teresa
- **Parque de los Caídos** - los mártires pelearon contra los militares que empezaron un golpe de estado a empezar la dictadura de Noriega aquí. Noeriega mató a los padres que defendían a la gente, como el padre que empezó la cooperativa de la región del projecto [[Panamá - comunidades de Piedra y Piura\|ENVR 451]].
- **Hay apoyo a EEUU a pesar de la matanza** - Tereza tenía una gratitud por el fin de la dictadura. Aquí puede ser que la gente tenga más gratitud a los EEUU por la violencia de la dictadura que empezó aquí - los militares quitaban tierra de la gente, y torturaban. pero Sandy dijo "the Americans will go wherever there is money"
- **Trompeta de Ángel (floripondio)** - Sandy trabajó con Ubaldina la curandera. Es una planta medicinal que se usa como expectorante, bronchidilator para asma, y relajante pero también tiene propiedades alucinógenas. Teresa, muy religiosa, le tiene miedo a la planta,  La polinizan murciélagos y abejas.

### El día pátrio
Nos fuimos a ver el defile del día pátrio. Fue interesantísimo ver el patriotismo de la gente aquí, y cómo eso no existe de la misma forma en Brasil. Creo que eso puede ayudar mucho a nosotros si nos quedamos más patrióticos como los Panameños, y la buena amistad con los vecinos ya que huvo una parte del defile que eran Costaricenses.

### Observaciones generales
No sé si la gente estaría así de abiertas en un grupo de hombres como en un grupo de mujeres. **Las personas tienen la tendencia de tener más confianza en mujeres** en general, y la manera que nos habló la señora - "encontré tres niñas estudiantes!" - me dejó la duda si hubiéramos sido invitadas a la casa de la maestra católica si fuéramos hombres.

**El radialista en la panadería** - el dueño de la Panadería California es un señor que trabaja con rádio, y parece conocer mucho de la historia del pueblo. Quisiera ir hablarle y preguntar de los deditos de miel, pero no logramos tiempo.

Presencia de iglesias evangélicas y católicas, pero **no encontramos iglesia central**. 

Hay **paja canalera** cerca de la carretera - a ver si es un problema a la agricultura local

**Desigualdad social** - las casas de turismo tienen arquitectura europea y son muy fancy, pero las de las personas en general son más humildes. La gente cerca de la carretera todavía parece vivir bien, pero puede ser que no sea bien así más lejos de la carretera.

La vestimenta tradicional Ngobe se llama Nágua.

The old indigenous art from here looks Mayan. Parece que por la explosión del volcán hace mil años, puede ser que eso ha desplazado las poblaciones originarias de aquí.
    
### Melissa Mazurkewicz - Bird-friendly coffee
American, but 12 years in Panama City.
Works in the resilience center with Ana Spalding and Diana.

"If you take care of the birds, you take care of most of the big environmental problems in the world"

3 billion birds have disappeared since the 70s in North America, 2.5 billion of which are migratory.

> **Lack of monitoring in developing countries.** It's really sad to see the data desert in South America. The fact that the map shows higher diversity of bird species in Canada than in Brazil says a lot.

**The main threat to birds is habitat loss** - as it is for most everyone else too I guess. Also, the insect decline is a big issue for birds.

The habitat in farms is very important to migratory birds, also as Panama is a path for them in between the continents.

With more sun, coffee grows faster, but it needs more nutrient input from the farmer. In agroforestry system, coffee will grow slower but rely on less fertilization since the trees provide that. <mark>Are they more likely to use nitrogen fixer trees for this?</mark>
75% of coffee in latam is in open areas, but agroforestry has 4x the bird diversity.

I am concerned about how focused on North America this is.

> A twelve-year study in Costa Rica’s human-dominated agricultural countryside found that 62% of bird populations declined over the study period, with most of these declines occurring in more specialised, sedentary and/or insectivorous species.

Organic, shade cover, tree diversity (10 species per hectare... what are these species?), zero deforestation.

Would be interesting to see what Jeff Hall has to say about this. Is the diversity of trees/forest composition chosen in a way that it supports endemic bird species?

- How does that address both endemic and migrating species?
	One PhD student is working on this, and the species are chosen based on what is available around, but it does not seem like supporting tropical species is a priority here.

50% of predation of coffee broca in Jamaica is migratory birds.

This seems like the sad old thing of supporting the tropics because it matters to North America. I doubt this would be happening if it wasn't for the NA bird decline, and it does not look like endemic tropical species are mentioned at all.

There is a fungus that is parasitic and eats the broca.

Bird-friendly cocoa is also happening.

The agroforestry system won't provide the same biodiversity as full forests, but it does provide better services than a traditional agricultural system.

- Is certification providing enough incentive for producers to join the program?
- What do we do for producers that can't fulfil all the requirements to still be able to be sustainable? Often it's hard for people to get certified because they can't be organic, but they can be trying very hard to conserve forests otherwise.

They are researching with farms in Peru and Colombia as well. Nespresso farms - Nestlé's presence is definitely a reason to be alert, as it is funding the research.
- these farms are being widely studied - insects, fruits, flowers, trees.

Birds are separated in functional groups (generalists, open area specialists, forest specialists)

Incorporating native species can also be hard as seeds are not always easily sourced.

In shade forests, some trees can be harvested. Selective logging less than 40% is not considered deforestation.

[SELVA – Investigación para la Conservación en el Neotropico](https://www.selva.org.co/) 
Susan Cook-Patton also works with carbon and coffee farms.

Outreach work is also done to communicate with farmers and the government.

- What kind of pesticides are used?
- Why are birds the umbrella species chosen here?

Ruth Bennett
Katherine Arauz-Ponce

### Pessoal
É frustrante como os benefícios à América Latina são meio que secundários aos benefícios à América do Norte. As universidades panamenhas têm dificuldades e os estudantes vão estudar fora e não existe parceria de universidades panamenhas com o Smithsonian, mas os estudantes de McGill têm uma parceria antiga com o Smithsonian e enviam estudantes aqui há muitos anos, e só agora temos estudantes latinoamericanos no curso, embora esses são as pessoas mais comprometidas com o desenvolvimento dos trópicos. Os benefícios aos pássaros endêmicos não são nem mencionados, e a queda de população de pássaros endêmicos não é nem mencionada. As vantagens às espécies nativas parecem ser um benefício colateral aos benefícios às espécies-foco, que existem nos EUA. Ainda assim, as coisas têm sido bem piores no passado, e agora é meio necessário aceitar que não vai haver justiça perfeita tão cedo, e tentar lidar com o que a gente tem pra hoje, e tentar melhorar.

## 26/01/2024, Fri - Scicomm and Coiba

### Science communication
**Talking to Science Deniers** - Speaking to Jimena, science communicator focused on children, fue muy interesante como aprendizaje de como estabelecer confianza en la ciencia. Ella dijo que es importante hacer preguntas en vez de confrontar a la gente con fatos. Parece tener mucho que ver con el método socrático, pero todavía me parece increíblemente difícil.
- Hay que practicar, y la práctica es difícil, pero necesaria. Also, each person is unique, so what works with one may not work with another.
- The older generation also never learned to discern fake news as they did not grow up with this information overload.

> Things you think and feel by yourself are more likely to stick.

**Kids** - Teaching the scientific method to adults is not the solution, but it can work with children. Also, kids often help change the minds of their family members, which can work better than us trying very hard.

**Q?urioso** - Hay un [laboratório educacional](https://stri.si.edu/es/educacion-y-divulgacion/qrioso) cerca de dónde hay las exibiciones de los animales. I found it sper interesting how they made an environment that looks and feels like a laboratory, but is interesting and exciting for kids of all ages to explore. Something like this, as well as conversations with actual scientists of similar backgrounds and potentially visits to real laboratories, could be an interesting way to help encourage interest in science.

I've felt concerned in the past about how to approach science outreach in Latin America, given the difficulties of life as a scientist. Still, we can share what we know and let kids make their own choice. We can only be responsible for our own experience.

### Travelling to the Pacific
John is a geochemist working on historical ecologist focusing on the past 10k years of Panamá. He studies human interaction with coral reefs and works with archaeologists.
- The Panama istmus closed off 3 MYA
- The Caribbean has the same temperature year round
- Corals can receive indirect impact from humans through fishing, pollution, sedimentation.
- As Carrie said, faster growing corals are less resilient, just like trees.

### Catalina - Coiba

The protected areas of Coiba are connected to multiple other large protected areas, including Galapagos. It is a system of islands. 

Hard corals photosynthesize, so they need to be in shallow water. Soft coral can be everywhere because they mostly filter the water for prey.

29-30 degrees is the threshold for coral bleaching.

She has worked with fishermen in Coiba, doing surveys on nets and fish size before and after regulation. Could be useful information for the project.

## 25/01/2024, Thu - Project day

I am seeing my career following a Brian-like path - a modelling lab that intersects a lot with social methods, minimal but present field work (mostly through collaborations with field scientists), and applications across a broad variation of ecosystems. 

## 24/01/2024, Wed - Fish and Fungi

Muitas conversas sobre a descoberta de espécies novas.
### Carlos Arias - Electric Fish
With an electrode, we detect fish in the river and catch them with a net. The idea is to compare these populations with the Bocas del Toro population, to help identify a new species.

There is variation across the tone of the electric signal across fish, and it's a way to discern populations.
- the populations in Gamboa, Darién, and Bocas are very different, and were isolated about 10 million years ago, with major geological changes with the rise of the istmus and the formation of the Andes and the Amazon basin.
- There are multiple criteria to determine what is a new species, and these thresholds of genetic difference vary among biologists. Some people are "splitters" and others are "lumpers" in how they do taxonomy. Crossing studies to tell whether populations can successfully interbreed is the most foolproof method (everything else is just trying to test for potential of successful reproduction)

### Luis - Fungi

Heterotrophs with a chitin cell walls, that excrete digestive enzymes and then absorb the digested material. The body is called *hyphae*, and many hyphae make a *mycelium*.
- **Ascomycota** - bag-shaped fruiting bodies
- **Basidiomycota** - larger structures

**Mycologists** study fungi, slime molds and stramenophiles. It's super interesting how some of these living beings are a very weird in between plant-animal-fungus-protist-????
- **Marine fungi** - what are they?? <mark> how does the nitrogen cycle in land compare with the cycle in the sea?</mark>
- **Hyperparasites** - fungi that eat other fungi!
- **Entomopatógenos** - parasite insects and spiders!

There is a huge potential to study fungal taxonomy. A very small percentage of them is known, and the species can be identified through sequencing eDNA to look for the fungal "fingerprint" locus and then matching it to existing databases.

It was exciting to hear about awesome research going on in Brazil, and to think of Brazil as a leader in Latin American science that can help establish that network.

Coffee and cacao can have 200 species of fungi in one leaf. <mark>I'm still super interested in endophyte fungi and would love to learn more about fungi-plant symbiotic relationships.</mark> Seems like some of this fungi deter insects.

**Biodiversity loss** - It's sad to realize how many fungus species we are also losing with deforestation, and how little of them we know. Eating them helps know them - people that historically consume mushrooms understand them best.
	[[Agroforestry\|Non-Timber Forest Product (NTFP)]] - Os cogumelos yanomami também crescem no Panamá, e são cultivados e consumidos. Eles crescem depois que a capoeira é abandonada depois da queima e cultivo da mandioca.

## 23/01/2024, Tue - Arduino and Tupper talk

Arduino is coming together easier, and I appreciate having a concrete way to see the outcome of a script, rather than just doing data analysis.

### Geology
The Amazon and the Andes are about 10 million years old. Like Amazonian wildlife colonized the tropics, temperate north american wildlife colonized South America temperate zones. The Andes were a path!

I'm remembering the book I read as a kid that denied climate change, saying molten ice won't raise the sea level.

The sea level today is only one among many in history, which was usually higher or lower.

Deglaciations happen slowly since the high albedo of white snow reflects heat.

Oceanic plates are thin, so they go under when they collide with continental. The caribbean plate, however, is thick, and the collision with the Pacific makes the volcanoes of Central America.

### Tupper talk

May be interesting to study drought resistant individuals for reforestation.

Met Yu-yun Chen, studying flowering and forest growth with ForestGeo in Southeast Asia (Malaysia? Originally from Taiwan, like the speaker). Was working with Helena Muller-Landau.

- trees with more branches and basal area recover faster from disturbance  
- seed traps showed few seeds for abundant species. One big reason is seed predation on the canopy. The seed traps exclude predators well.  
- Taiwan is an interesting place to study isolated communities in mountains  
- 17 years of seedling census, 20 years of plot age  
- general linear mixed model  
Compared survival and growth  
- a high recruitment year had positive effect on survival  
- demographic process model - survival, growth, and growth transition from seedling to sapling  
- 47 years for 2m sapling? That's super slow  
- damage to living trees as cost for the carbon budget  
- 42% of biomass loss in the Forestgeo plots is due to damage to living trees (mainly in disturbed areas like Taiwan with the typhoons)  
- high rainfall increases growth even in wet forests in Taiwan because of typhoon. Maybe loss of leaf area could allow light in and allow growth.  
- frequency of disturbance is not as important as intensity of disturbance.  
  


## 22/01/2024, Mon - Projects

### Essay 3 - Positionality

La Latina puede salir de Latinoamérica, pelo Latinoamérica jamás sale de la Latina. Even after having left my country to go study abroad, tudo que eu tenho visto é moldado pela minha perspectiva brasileira. Nascida na Zona Norte do Rio de Janeiro, filha única de mãe solteira (e jornalista!), desde cedo fui impactada pela injustiça que afeta a natureza e os seres humanos. Minha paixão e curiosidade por tudo que é vivo me levaram a desejar uma vida dedicada à ciência. O valor que a minha família dá à educação, bem como o grande esforço de professores engajados, me abriram portas pra que meu desejo pudesse se materializar.

I left Brazil with the desire to acquire skills and experiences that would not only enrich my life, but make me a better scientist in service of Brazilian nature, bringing the knowledge from abroad and teaching the next generation. It has broken my heart to see the inequality that exists not only across the very steep, unclimbable without proper equipment, social cliff in my hometown, but also at a global scale. For a while, I have struggled with homesickness, and feelings of exclusion created an aversion to much of what originates in WEIRD (Western, Educated, Industrial, Rich and Democratic - or the Wealthy Ensuring Inequality by Raiding the Developing?) societies. Maybe I have given white nationalists a bit of a reason to be afraid of "reverse racism", as I am much faster to trust people from the global south than europeans and north americans, and have multiple times openly expected the worst from them.  Eu lembro da sensação de tristeza por não ter olhos azuis, de olhar os estrangeiros como pessoas mais interessantes do mundo, e da frustração por não ter tido as facilidades que meus colegas estrangeiros tiveram. Sendo uma mulher branca brasileira, de classe baixa, eu sempre tive expectativas muito altas pra mim, e essa sensação só piorou com o choque cultural e a xenofobia que eu encontrei na América do Norte. I've found my chronic feeling of inferiority is also due to internalized racism. I feel I need to be specially extraordinary to feel like I am as good as my white counterparts that went to good schools. This disparity is much lesser with other latin american people, so I tend to feel more comfortable with them.

Thankfully, having met such WEIRD people that have treated me and my culture with respect has helped me overcome that bias over the years, and it's much less of a toxic voice in my head as it used to be. Ahora, yo realmente creo que como latinos, necesitamos allies en países ricos para que nuestra lucha tenga frutos - solos, es más difícil vencer enemigos fuertes y poderosos.

Déjà au Québec, j'ai étudié la biologie et les, mathématiques, et j'ai reçu une éducation d'elite qui a bien sûr changé ma manière de voir la nature, et même ma ville et mes compatriotes. C'est difficile d'encore vivre dans une société aussi differente de la mienne, mais je comprends la necesité de rester au Canadá et d'étudier dans une institution comme McGill, surtout en un moment politique compliqué au Brésil avec la takeover de l'extrême-droite.

Viviendo fuera de Brasil, también aprendi mucho sobre la cultura de otros países latinos, que ya me encantaban por la lengua y la música. Sigo con un gran deseo de diminuir la distancia entre los lusófonos y los hispanohablantes, ya que tenemos mucho en común en nuestras luchas. El sueño bolivariano, de una perspectiva más pan-latina incluyendo a los hermanos lusófonos, está muy fuerte conmigo; hay un deseo fuerte que con una unión científica y cultural pueda ayudarnos a mantenernos fuertes en nuestra lucha unificada.

El sentimiento de exílio, el amor por la naturaleza y las ciências, y mi personalidad más me motivan. Yo vivo por la ciencia, vivo por mi trabajo, y por supuesto esto me puede cambiar la manera que investigo, con desventajas y ventajas. Así como las similaridades de las lenguas hacen que sea más difícil aprenderlas a la perfección, las similaridades de las realidades puede ocultar las diferencias más pequeñas. Pero también, las similaridades ayudan a empezar a comprender la lengua - estudiando poco, entiendo más español que otro extranjero, y también entiendo más de la cultura panameña por sus similaridades con la mía.

#### Translation

 Even after having left my country to go study abroad, everything I have seen is shaped by my Brazilian perspective. Born in the North Zone of Rio de Janeiro, the only child of a single mother (and a journalist!), from an early age I was impacted by the injustice that affects nature and human beings. My passion and curiosity for all things living led me to desire a life dedicated to science. The value my family places on education, as well as the great efforts of committed teachers, opened doors for me so that my desire could materialize.

I left Brazil with the desire to acquire skills and experiences that would not only enrich my life, but make me a better scientist in service of Brazilian nature, bringing the knowledge from abroad and teaching the next generation. It has broken my heart to see the inequality that exists not only across the very steep, unclimbable without proper equipment, social cliff in my hometown, but also at a global scale. For a while, I have struggled with homesickness, and feelings of exclusion created an aversion to much of what originates in WEIRD (Western, Educated, Industrial, Rich and Democratic - or the Wealthy Ensuring Inequality by Raiding the Developing?) societies. Maybe I have given white nationalists a bit of a reason to be afraid of "reverse racism", as I am much faster to trust people from the global south than europeans and north americans, and have multiple times openly expected the worst from them.  Eu lembro da sensação de tristeza por não ter olhos azuis, de olhar os estrangeiros como pessoas mais interessantes do mundo, e da frustração por não ter tido as facilidades que meus colegas estrangeiros tiveram. Sendo uma mulher branca brasileira, de classe baixa, eu sempre tive expectativas muito altas pra mim, e essa sensação só piorou com o choque cultural e a xenofobia que eu encontrei na América do Norte. I've found my chronic feeling of inferiority is also due to internalized racism. I feel I need to be specially extraordinary to feel like I am as good as my white counterparts that went to good schools. This disparity is much lesser with other latin american people, so I tend to feel more comfortable with them.

Thankfully, having met such WEIRD people that have treated me and my culture with respect has helped me overcome that bias over the years, and it's much less of a toxic voice in my head as it used to be. Ahora, yo realmente creo que como latinos, necesitamos allies en países ricos para que nuestra lucha tenga frutos - solos, es más difícil vencer enemigos fuertes y poderosos.

Already in Quebec, I studied biology and mathematics, and received an elite education that of course changed my way of seeing nature, and even my city and my fellow countrymen. It's still hard to live in a society so different from my own, but I understand the need to stay in Canada and study at an institution like McGill, especially at a complicated political moment in Brazil with the takeover of the extreme right.

Viviendo fuera de Brasil, también aprendi mucho sobre la cultura de otros países latinos, que ya me encantaban por la lengua y la música. Sigo con un gran deseo de diminuir la distancia entre los lusófonos y los hispanohablantes, ya que tenemos mucho en común en nuestras luchas. El sueño bolivariano, de una perspectiva más pan-latina incluyendo a los hermanos lusófonos, está muy fuerte conmigo; hay un deseo fuerte que con una unión científica y cultural pueda ayudarnos a mantenernos fuertes en nuestra lucha unificada.

El sentimiento de exílio, el amor por la naturaleza y las ciências, y mi personalidad más me motivan. Yo vivo por la ciencia, vivo por mi trabajo, y por supuesto esto me puede cambiar la manera que investigo, con desventajas y ventajas. Así como las similaridades de las lenguas hacen que sea más difícil aprenderlas a la perfección, las similaridades de las realidades puede ocultar las diferencias más pequeñas. Pero también, las similaridades ayudan a empezar a comprender la lengua - estudiando poco, entiendo más español que otro extranjero, y también entiendo más de la cultura panameña por sus similaridades con la mía.

## 20/01/2024, Sat : 21/01/2024, Sun - Piriatí & Ipetí

### Essay 2

*What surprised you about the visit? Did anything challenge your beliefs?*
- I did not expect the people to be so focused on carbon as a major mode of subsistence. I think this can be concerning, as there is still the urgent need to regenerate the landscape in a way that it shelters biodiversity, and the need to provide better nourishment and financial stability for the people.

*Did the experiences of visiting reforestation plots, meeting project participants, and/or getting a small taste of how much work is involved in planting trees expand your perspective on this project? On reforestation and carbon offsets more broadly? If so, how? And if not, why do you think that might be the case?*
	I did not expect the forest plots to be that intensely managed, and the difficulties of active regeneration in such depleted soils. It made clear why active regrowth is so expensive, and it does not seem to me like something that should be the first line of action as far as reforestation goes.

*In what ways did your ideas, opinions, values, and/or aspects of your personal history act as a lens or filter through which you experienced the trip?*
	I am concerned about education and health coming from a well-educated and healthy background. I understand that the need to diversify a diet may not look as urgent to people that culturally are accustomed to an american-style diet, and that the possibility of higher education may not be as accessible to people that historically have relied on their land for a living. There is a delicate balance between the cultural aspect and needs of subsistence agriculture, but also the opportunity and need to diversify sources of income and support independence of the community in a changing world.

En los dois países, todo depende de estruturas muy más grandes que nosotros. Hay mucha emphasis en lo que la gente puede y quiere hacer, pero al fin, las decisiones del gobierno local y de los países desarollados son cruciales a lo que se hace con cada cocobolo en Ipetí, o en Amazonas. We can hope and try very hard, and do our best to make sure the nature is protected and people are provided for, but in the end it all will come down to who is in power and what do they do with that power.

A president required the Emberá to leave their original land because a dam would be built and flood the place. Out of the options given, they preferred to settle in Ipeti and Periatí. There was conflict with campesinos that were already in this area. Now, their ancestral land has not been flooded and is not inhabited by the Guna.

I really think it would be very doable to execute a project with high rez Planet data on active reforestation plots going back to 2016.

### Agroforestry
There were some fruit trees like plantains, guayábana, y mandarina, as well as fiber palm that is used for artisanía. However, there was more emphasis on carbon and coffee as the source of livelihoods of people. There was still cattle pasture, and for the people a cow is insurance - at any moment it can be sold and they have some safety. Also, the difficulty of transport (not everyone has a car, and that's far away!) makes it hard for people to be financially independent and commercialize in their own terms.

### Carbon Offsets
- Faltan técnicos que vayan a la tierra a ayudar a planear el proyecto.
- The river helps, but the soil fertility is the main limiting factor. As they arrived on land that had been very used by cattle and mechanized rice, it was quite poor in nutrients. Up to 20 years fallow was needed to fully recover the land.
- The separated monocultures will most likely become timber. <mark>I wonder how these active reforestation projects are carried out in other parts of Latin America and the Tropics.</mark>
- In the end, this seems like a long-term investment for the peoples which is a better use of land than cattle farming, but it is not quite sheltering biodiversity. However, it has been unclear to them, and they seem to speak of it as a forest regeneration project.
- The longevity of the project relies on many external factors, such as incentives to keep mature forests standing. Also, <mark>incentives for the kids to study so that they don't need to be desperate about making money to send their kids to school.</mark> This will also rely on local institutions and partnerships with schools and other capacitation opportunities for the Emberá.
- Cata brings up very well that this is a very different effort from what happened in Agua Salud, which is more of a restoration project with the end goal of forest regeneration. Catherine Potvin and Jeff Hall have worked together on planning the plots. Katie reminded well that Jeff Hall said "monocultures grow better", which is also why this was deliberately done this way for a carbon uptake perspective. Lady said herself that "what matters to Catherine is the carbon uptake".

I'm amazed at how quickly the forests can grow, and it makes me think of regrowth modelling projects in the short term and <mark>a comparison of active vs passive reforestation plots.</mark>

### Dependency on external policies

I pointed out to them the inevitable slow in carbon uptake, and what would happen then once the sequestration rates slow down.
They mentioned:
- **Hipoteca**: they can mortgage not the lands, as they're indigenous, but the trees, as they gain inherent value.
- **Financial incentives to maintain standing trees**:  There can be pay from the local government, as well as foreign governments (the same northern European countries were mentioned)
In the end, to maintain this forest will also depend on them **no longer relying so much on extractivist activities to make a basic living and maintain their relationship with the forest as a cultural one**, which goes through **education and youth empowerment**. There has been some talk about the lack of quality of Panamanian universities, and this strengthening of institutions is crucial for this to happen. I am an outcome of science outreach initiatives and science Olympiads, as well as good teachers in small universities, and I realize that my current privileged position as a scientist for my country has relied on politics, so that is also the case for these kids that often do want to grow to be scientists and lawyers. The few that managed to do so (like the Emberá lawyer that was mentioned, or Lady, a biologist herself) can make a difference. Unfortunately, all this relies on something much greater than our sphere, as it always does. **Maybe it is also the role of STRI and McGill to open doors for education for indigenous peoples, as has happened with Lady,** who started this by taking a field study course with Cat Potvin.

### Culture
I am concerned about how much of that performance was more staged and touristy than a spontaneous thing. When asking a girl about where she was from, she mentioned she travels back and forth as "all her family works with tourism". So, how different would all this have been if Catherine Potvin was Catarina Pontes, and <mark>how is it going to change as Lady takes over the leadership of the carbon offset project? </mark> Lady mentioned she is more focused on the social aspect and Catherine has done more of the "brain work", so I wonder how that will change with her leadership.

The kids also felt abandoned - "when are you coming back?"
They did not understand who we were and what we were doing there, and that could have affected them emotionally.
The kids did not know what the songs meant. There was disconnect with their own identity.

The dogs were in bad shape. The people looked short, but reasonably healthy.

There is also internalized racism within people from latin american origin on their own latinhood and the more indigenous parts of their own peoples.
 
### Salud
El centro de salud es muy bien puesto y bien cuidado. La gente allá parecia satisfecha, y los trabajadores son buenos.

## 19/01/2024, Fri - pre-Ipetí

Social science data takes longer to collect, so what we are doing is more of a superficial exercise on it.

A **field diary** is similar to what I had been doing so far, but with a bit more space to reflect over your position in relation to your research, biases, and feelings.

> Human geography is a branch of anthropology or etnography.

**People are allowed to lie.** Prioritize people's agency, as after all they owe you nothing. That is another reason why it takes time and experience to learn how to properly conduct this research.

It is hard to know how people perceive you, but it is an interesting thought exercise to reflect on the aspects of you that can affect the way you perceive and react to things or the way that you are perceived. 

**Reproducibility** -> Depends on the goal of the research goal. Some papers will be exploratory. When the results are expected to be used in a standardized way, there is a standardization of questionnaires and research methods, and as much care as possible is spent on making sure these questions are perceived similarly by the study participants. **Member-checking** is a practice to double-check preliminary results with key knowledge holders in the community. Robustness is also assured by an iterative process of data analysis.

> There is no way to have completely unbiased social science - or even natural science.

### Emberá

Originated from the Brazilian Amazon, immigrated up thousands of years ago. Their culture is more similar to Amazonian peoples than the Guna, for example.

**Tierra colectiva (collective tenure)** -> not at the level of comarca, but recognizes the rights of indigenous peoples that live there.

The Emberá settle near rivers. In Ipetí there are other indigenous, and there are other Emberá in other lands. They have been relocated there after a hydroelectric dam.

**Land tenure** -> regulation of land ownership, access, and use. Land in Ipetí is owned by everyone, but is managed by a specific household. This way, people can't sell the land to an outsider - you can only sell to another Emberá. Land was established in 1975 but the title was only recognized in 2014.

![](https://i.imgur.com/0J0a7c5.png)

There is a gradual transition away from subsistance agriculture.

It is interesting to compare Piriatí and Ipetí and what we are told in both villages, as they are both Emberá but with different landscapes - [[2 Research/Sharma 2016 - A comparison of influences on the landscape of two social-ecological systems\|Sharma 2016 - A comparison of influences on the landscape of two social-ecological systems]]

As it usually is, the Ipetí land is a visible green area among a very modified landscape. *What an awesome place to ask about change in diets with forest change!*

The offset project came from a desire to conserve the forests for a cultural reason.

### Ipetí reflection assignment

#### How do I feel about the upcoming trip?
I feel curious. I have never visited an indigenous community or an agroforestry system, and it's going to be interesting to visit both this weekend. I am excited about the chance to sit and chat with interesting people, but intimidated by the whole setting of visiting and being perceived as a researcher. I like having long conversations with people, but I've never had one in which people have expectations about the interaction. This adds a whole extra layer of pressure that I've never experienced so I'm unsure how it's going to go, and how it'll feel.
#### How do I feel about carbon offsets? 
In an ideal world, in which they were accurately priced and correctly implemented, it'd be a great idea. However, I believe the price of carbon is too low to truly disincentivize pollution, and with things like the payment for the mere maintenance of mature forests or trees that are planted but never reach maturity, or the planting of dense wood monocultures, ends up either not being a true solution to the climate crisis, or a disservice to conservation in another way. I understand Jeff's argument that "if the problem isn't solved in 30 years, we're screwed" but I don't really think the effort is helping much today, if at all. Carbon taxes, on the other hand, seem better implemented and to truly disincentivize pollution.
#### Are there ideas, opinions, values, and/or personal experiences that might influence the way I experience this trip? 
Physically, I am probably to be perceived by people as a white north american woman. My tattoos may stand out, and the snake is not a well-liked animal in general, so I wonder whether the one on my arm will be an issue. Also, I may be getting sick so I may wear a mask, which could also deter people from speaking to me and make conversations more difficult.
I am anti-religious, which can cause discomfort with evangelical missionaries and churches that often are around indigenous groups.
Being Brazilian may be an advantage, as it is a generally well-liked country due to its football and carnaval fame. Also, I am extroverted and generally have an easy time approaching and connecting with people of different backgrounds.
As a biologist and conservation enthusiast, I also have historically have a hard time dealing with situations in which people harm wildlife.
#### How might they bias my experience, and what can I do to mitigate that?
I can try and avoid having conversations around religion. Also, I need to remind myself that it is okay to keep a distance and not necessarily make the most out of everything since there is a whole lifetime ahead to have this kind of interaction and it is okay to miss out on some things to make sure everything goes well.

## 18/01/2024, Thu - Social Sciences Talks

Our TA Ariana is an architect!

### Cultural exchange
**Baile Congo en Colón.** We saw some people on the way to Colón that were dressed in costumes, on speed bumps, dancing and asking for money. It is a pre-carnaval celebration (and also at another time of the year). It's super interesting that it was a dance done out of spite against the Spaniards - they wear patched clothes to show how they would get only the leftovers from the elite, and the dance displays a conflict between white and black people. They paint their faces black and wear crowns to mock the status that the white men would put themselves on. Also, some people dress up as devils to represent the spaniards (a fight of good vs evil).
**The típico baile of Panama** is a nice chill dance similar to forró. Típico from Costa Rica looks like carimbó mixed with gaúcho clothing, it's quite interesting. It's nice how latinos truly dance their traditional dances and enjoy them.

<mark>I am thinking of writing a summary of the history and significance of Brazilian carnaval to present its beauty to foreigners, and make a cross-comparison with other regions of Latin America.</mark>

Also, it's interesting how much of the biodiversity and nature in Brazil inspires national pride and national art. I was reading a tweet on how ufanist nationalism is a part of far-right ideology, but <mark>I would like to write about not a blind "patriotism", but a true love and appreciation for your nation's culture and art and nature </mark>, and THAT'S what is valuable about Brazil, and our Latin siblings. Tom Jobim and all the music about nature is great example of this. Take away our biodiversity, our carnaval, our art, and the flag will mean nothing. Also, the culture and the nature unites us with the rest of Latin America, while a blind nationalism only enforces meaningless borders.

[Self-Determination: A Perspective from Abya Yala](https://www.e-ir.info/2014/05/20/self-determination-a-perspective-from-abya-yala/#google_vignette)

<mark>I am curious as to how the Guna people of Panama influenced indigenous movements across Latin America.</mark>
#### Helicopter science and Smithsonian in Panama

A major downside of English as a scientific language is that regardless of the fact that it is an "easy" and already widespread language, it does give an inherent major advantage to anglophones, which already have way too many advantages to begin with.
- Whole can of worms. <mark>What should be the neutral international science language?</mark>

Another added pressure to global south researchers is the added pressure that we have to share with our own communities and give back what we got. Global North researchers get to think of themselves and their career, while we do carry a significant extra load of being aware of the global inequality that exists and how hard it is to navigate it. Also, we have a harder time standing up for ourselves, showing our abilities, which is easier for Global North researchers.

Only 3 years ago all documents started being available in both English and Spanish at STRI!

One major advancement is the appointment of Dr. Oris Sanjur as director of STRI, the first Panamanian and first woman on the position. Also, over time, more partnerships with Panamanian research institutes are happening, although due to the recent tensions with the US there is still resistance from local scientists. Over time, the relationship with local institutes becomes more horizontal.

> If the immediate social benefit outweighs ecological benefits, the activity will go on.

Remembering yesterday's conversation with MC where she mentioned the different attitudes of indigenous peoples regarding the forest - weighing benefits and costs.

### Microbiota and epiphytes - Lilisbeth Rodriguez-Castro 

*Zamia pseudoparasitica* - the only strictly epiphytic gymnosperm!

**Phyllosphere** - all that plants cover and surrounds them.
The **microbiota** depends on many factors, including position in the forest strata and climate.
They have ecological function (disease control, defenses, nutrient acquisition, stress tolerance) and can benefit their hosts (besides pathogenic microbes).

**Diasotrophic bacteria** -> they fix nitrogen. proteobacteria and cyanobacteria can both do it. <mark>There is a question whether nitrogen fixation that happens outside the roots can also benefit plants.</mark>

*What is the bacterial community composition on the leaves of this epiphyte in Panamanian protected areas?*
- One of the places chosen to answer this question was Santa Fe! Also Palo Seco and El Cope. The biggest population of this plant is in a mining region and they could not go there to sample it.

Data collection was done on wet and dry seasons. They collected information on temperature, humidity, and lighting on each sample.

A study was done comparing the microbiota in the neo and paleotropics, and there were similarities.

### Panama Canal Zone - Marixa Lasso
An anthropologist and historian raised in Panama. MC is a big fan of her.

[[Cuartos\|Cuartos]]
Related to the podcast recommended by MC, Radio Ambulante, on La Zona of the Americans in Panama. The disdain of Americans in regards to Panamanians and the degree of the segregation was palpable in the interview with the american kid raised in La Zona.

The Zona was densely inhabited before the railway and canal was built, and people were made to relocate. It is not well known how people felt about the initial announcement of the canal construction. However, the relocation was not necessary - many villages were only minorly flooded, or not flooded at all. **The removal of people at few months' notice was a deliberate effort to remove Panamanian presence from the canal area.**

It is hard to find registry of what these cities looked like before they were abandoned, as the photos represented what the government wanted - big trains, big canal gates.

**Public health became an excuse for racism** -> under the excuse of "indigenous peoples bring diseases", they were made to leave from the areas where the white people wanted to inhabit. Makes sense from the disdain in the talk of the american guy that said that "before the US that was all a swamp with nothing but mosquitoes and indigenous people"

At the time there was a lot of influence of other countries too, mainly the French. But after the early 20th century, it became a smaller, "perfect" version of an american village in the middle of the jungle.

After the canal construction, there was the municipality period, in which there were both american and panamanian mayors. However, they tried to defend the rights of the people against the interests of the canal company, and then were removed so the company had complete control over the canal.

**Gorgas** was a doctor responsible for combating yellow fever in the canal region. There was a big debate on whether the region should be inhabited or not, and he strongly defended that people should inhabit the area and thought it was unlikely that Americans would settle.

**The myth of the native hut** -> the idea that technology and the tropics don't mix. gold miners came spreading once again the belief that natives were dirty and lazy. The huts, however, were connected and integrated with the railway.

Another myth is the idea that the tropics were not good places for democracy, but some pioneer republics were founded in the Americas. Panama abolished slavery in 1851, before the US. Americans were racist towards black Panamanians (shocker)

There is also an idea of the tropics as a place without history, that just absorbs and repeats what happens outside. It is important to fight against this misconception and remember that republic was expanded in the americas much before in many european states.

*Roosevelt once was asked about the Panama Canal. His answer was a simple "we just took it".*

It is important for small nations to exercise their influence and sovereignty.

**Countryside schools are not necessarily bad schools** -> Connects nicely to what was being discussed today, with the Brazilian Northeast being simultaneously the poorest and best educated region. Culture, teacher quality, all of that makes a huge difference.

**Contrast between the two sides of the fence** -> There is only perfection if another side of the fence is in misery. In the Southeast in Brazil, there is a large mass of extreme poverty and a few ultrawealthy, which is not as much the case in the better educated northeast.
The pattern of pushing natives into impoverished ghettos repeats throughout history.

### Citizen Participation - Gabriela Rogers

She has felt mostly frustrated and powerless because while trying to fight for issues such as garbage maintenance and water supply, local politicians can have people "tricked" by fancy words, abandoning the local communities and seeing people as ignorant.

**Fight against extractivism** -> the fight has been going for a while (around 90s), but over the past couple of years it has been made national and more powerful. The protests have been against mining in general but also the contract of "Proyecto Cobre Panamá".
A company transferred an inconstitutional concession to mine to a Canadian company around 2007. The government intended to renegotiate the contract with the same company, with the intention of trying to make it look better, but the contract never went to public bidding (licitação) so the contract easily remained inconstitutional. In 2023, the contract was being renegotiated again, and the companies were not extracting minerals yet, but only starting to set up infrastructure.
Most people in Panama didn't even know there was mining going on here!
In the beginning, only people who joined the movement were environmentalists and people in the neighbor communities near the mining companies.
It was a big powerful company, so for this to work out, they'd need to get the whole country to uprise.
She made instagram posts in the beginning against the company, and as soon as the posts would go live, the links would disappear, as the companies were managing to denounce and take away from the internet anything that was attacking them.
They thought together that *the way to get the message to Panamanian people was to draw parallels with the Canal Zone apartheid and American domination.* Once the contract was approved, everyone in Panama joined and took the streets.
They were in the online groups "Sal de Las Redes" to try to get people to protest in real life, beyond the networks. They wanted to organize protests in front of major government buildings but it was impossible due to police repression, so they started with protesting in the streets, and millions of people joined, calling for mining and other social issues. Not everyone in the street was an environmentalist, as some people were protesting for other issues in Panama.
They had full time jobs and were exhausted by daily planning and promoting protests, and the fear of exposing themselves on national TV, as there was pressure from interviewers for them to end up saying that they did not want to say.
They tried to put them against other groups that were also organizing protests and get them to say something to calm down the protests. They picked words to absolutely not say to avoid misunderstandings, and still journalists with bad intentions could publish the news in a way that made things look more desirable to the companies.
They were paranoid and scared.
In Panama, mining is constitutional, so they needed a moratorium (a delay in execution of mining activities) in order to prove that this mining activity is inconstitutional. This divided the social groups, as some wanted to go on to press for complete ending of the contract, and some wanted to wait for the supreme court to rule the inconstitutionality of the contract.
It was sad to see the division of the groups. In reality, the leaderships disagreed and would fight, and the only thing they had in common was that they did not want the contract, so it was not a perfectly harmonious union as it may have looked like on TV.
This contract had been an issue for so long, and environmentalists were shocked to see how quickly did the issue get resolved as the contract got repelled.
Politicians were shocked as well - many were baffled that they managed to be so successful and tried to investigate to see if there was someone very powerful behind the movements, and found nothing.
One member of the parliament said they would vote for whatever they wanted, and for her feeling powerful was shocking, as an activist she never thought she could have true influence and be heard.
It is hard to have so many important things to push through while also dealing with stress, exhaustion, and fear.
The group was very tense, and fights between them did happen. People died, and one of the activists that she knew lost his eye while covering the protests (taking pictures, writing). She was sad but so enraged that she thought, now there is no backing out, and we can't lose this.

Reacting with violence is an act of resistance, and expected, if you are being treated with violence. However, in their case, it was not strategic, and what really made sense was to put people in the streets and make them feel safe in the protests. Still, no matter how peacefully you protest, you will always get repression.
The smallest the town, the harshest the repression - in Panama repression was lesser than what happened in Veraguas, where people got attacked with tear gas for peacefully protesting. In smaller towns, protest leaders were more afraid 

**Do you see Panama as an outlier in Latin America in political engagement and social awareness of the population? What can other Latin countries, given our diversity and common struggles, learn from the Panamanian experience?**
Panama is an outlier as we saw results, but there was really no guarantee. Chileans also collectively rose, and still haven't got the constitution that they wanted. Also, not even in Panama they know if the company will go away. We could have done the exact same thing and not gotten the same successful result. One crucial factor is that Panama has elections coming next May. They knew the politicians wanted to be well seen and they used that - they printed politicians' faces and put them everywhere, to make the issue against the politicians personally, instead of just the government in general, so they felt like they had to bend to the people's will. Also, there was a call to *nationalism and sovereignty*, which fired people up.
In comparison with Colombia - protests can last too long and then people get tired and abandon them. It was complicated to control the narrative, and that's why they stopped giving interviews to the media, as there was no control of the narrative. Also, the attempt to divide the people (put some groups as bad and others as good) was risky, as well as trying to avoid putting only one leader that could be brought down easily, and make sure that this issue was happening around the whole country. If this had happened, the protests would've definitely had lost energy.
Wealthy people sent infiltrated youth to the protests with a covered face to fight.

**Who are these people and what makes you and the others activists? What causes certain people to lead movements, and how can we make that work in other places?**
She worked for years in the biomuseum, and that made her realize that the value of Panama is not in the mining, it's in its biodiversity. In Panama, sometimes there's trash around, there's no water, and no other activities, so some of the few things that people can enjoy is nature - parks, waterfalls. So it's the only thing that people feel that is their own and they feel like they should be proud of it. Also, education and information has a lot to do with it.
Before the contract was deemed inconstitutional, she went to the COP in Dubai, funded by NGO Climate Reality Project (started by Al Gore) to send youth leader to these places to try to make goals more ambitious. She got to represent Panama as a negotiator. She was worried the Panamanian government would not have let her go, as they could take her badge away. Thankfully, they didn't know she was going. It was a completely different environment from the activism battleground.
There were power dynamics that did not allow her to really speak what she wanted to - the whole dynamic was controlled by the US, China and the Arab countries. Latin American countries had little space to be heard.
Progress is very slow. We need more unity in Latam.

**Far-right - are you concerned about the rise of hyper nationalism in Panama?**
Not concerned about far right rise in Panama. She feels that the nationalism right is something pontual, more specific, that is needed in certain moment to engage the people, but should not engrain to strengthen the far right in the long term. There are right wing parties, but they are not a big threat to the country. If nationalism was a big problem in Panama, the protests would have exploded earlier.

<mark>Maybe the way to encourage latin american unity and activism is in having nationalism be attached to nature and culture of our countries, as we share so much of it.</mark>

### Resilience and Sustainability - Ana Spalding & Dayana Agudo Atencio

Dayana is a chemist. Ana Spalding did economics, master's in marine policy (where she took a marine ecology course), and did a phd at UC Santa Cruz in environmental policy (a true interdisciplinary program - mixing social and natural chapters). She was a prof at Oregon State doing public policy. It is hard to fit somewhere when you're interested in both natural and social sciences. There's many people interested, but few paths to do that.

[Karen Holl - Restoration Ecology](https://envs.ucsc.edu/faculty/index.php?uid=kholl)

There is more emphasis on human-environment relationships right now due to multiple factors. Climate change has definitely made this a hotter topic, but other things like social media may have made that more evident too. However, advances in this area have been made up to 25 years ago.

- What are the drivers of change?
- What are the strategies of adaptation?
- What are the desired resilient outcomes?

There is a resilience postdoc fellowship!

The Smithsonian Science Education Center is involved.

**Resilience definitions** -> There is a questioning of the need to return to a previous state - this may be impossible, so we're looking for alternate stable states.

**Cannot oversimplify the drivers of change** -> "humans are evil and overpopulation is the issue!" Some people don't have agency and can't choose, so it's not all people. Not everyone in this world can live the way I live.

- She is looking for a social-ecological vision for research in the tropical eastern Pacific.

> "Instead of big science questions, I am driven by solutions" - Ana

The knowledge you search for is driven by **your question** - from then, you look for who you need to work with. *You don't need to know the social sciences themselves, but you need to know about them so you know who you need to contact.* This rings true as right now I feel like I have a ton of questions that I don't really know how to ask them. Also, I didn't even know about the existence of human geography before this trip, so there's a lot I need to learn still, and I don't know what I don't know, so that's a bit overwhelming.

> If you have that drive, design your project around a real world question. - Ana

**Policy windows?** -> Where in policy is there a gap for the science to enter? What decisions are being made in which your science would make a difference?

**How to tradeoff the need of time to do science and the urgency to get solutions** -> policy is passed without scientific backing frequency. It is necessary to have meetings with decision makers to understand what materials do they need to get information passed.

**What is a policymaker?** -> A person that makes decisions in an organization (government or multilateral organization like the mercosul or the UN) that are binding, in some degree, to its members.

A big issue in sharing data is to make sure it is in a cleaned format to be shared, and in a relevant platform.

In order to improve communication, be **intentional**: who are you trying to communicate with, and why? Be clear to yourself on where you are and where you want to go. Also, remembering to **listen** is important.



## 17/01/2024, Wed - Project Day


### Overview of ongoing questions

- Does biodiversity loss affect stability similarly in coral reefs as it does in tropical forests?
- How are the Amazon reefs affected by deforestation?
- How does the Amazon and Atlantic forests affect fisheries in the Brazilian coast?


### New interests

**Human Geography** -> A whole research field examining the relationships between people and their environment. Addresses exactly my intended expansion from ecology. Working more on this would also allow me the opportunity to explore my desire to work on communication (not only journalists get to talk to people for their jobs!).
 
> "Ecologia sem luta de classes é jardinagem" - Chico Mendes

**Coral Reef Ecology** -> The overlap between community ecology and species coexistence in coral reefs and forests is super interesting, which would be a cool avenue to explore my interest in marine biology. Also, the effects of deforestation on marine ecosystems through river flow is interesting, as well as aquaculture and fishing. Maybe I don't need to be restricted to terrestrial ecology.

I am rethinking my role as a scientist. I planned on being a modeller working on young forests, but I may see myself more as a landscape ecologist working on human-environment interactions, degradation and restoration, in the tropics, across ecosystems, using both quantitative and qualitative methods, primarily as a quantitative ecologist collaborating with social scientists, and dabbing into social science (primarily environmental policy and human geography) as much as I can.

### Project Ideas

#### Fellowship Proposal
Good opportunity to investigate the old interest of Javier Sanchez-Galán and myself into the relationship between forest degradation and human nutrition. Depending on the cost, could investigate how does human nutrition quality change depending on whether a community is surrounded by healthy old growth, disturbed old growth, new growth, or fully modified landscapes.

#### Ipeti Report
I am curious about how much the Emberá people still rely on the forest for their livelihoods. How does forest degradation or protection affect them?

MC mentioned how there are conflicting views - they realize that cattle farming will damage their ability to grow medicinal herbs, but they need the cattle to subsist today, and have little option. In the end, the short-term benefits outweigh the long-term benefits.

**Tragedy of the commons** -> the idea that once a good becomes common, it is more prone to exploitation because short-term individual benefits outweigh long-term collective benefits. [Has been contested by Elinor Ostrom.](https://www.aei.org/articles/elinor-ostrom-and-the-solution-to-the-tragedy-of-the-commons/), the same person who came up with the [[Ostrom Framework\|Ostrom Framework]].

#### Course Final Project

- comparacion dentre relacion de comunidades agroforestales y comunidades aquaculturales, o ganaderia y pescado. como la gente vive de la tierra y el bosque y la gente que vive del mar, las diferencias y similaridades
- que come la gente en areas de degradacion diferente. como cambio de uso de tierra cambia la diversidad alimentaria y salud de dieta
- comunicación y educación y su impacto en relación a cuestiones que envuelvan livelihoods - la gente mata al jaguar por ignorancia y necesidad

MC mentioned I should talk to representatives of the communities rather than the people themselves, to get a broad sample of many communities and different perspectives with less conversations and interviews. This can be community leaders, scientists, company heads.

##### People with overlapping interests:

**Dineilys**
- ganado y agua y uso de tierra
- educacion y corales
	- coral bleaching y el niño
	- edad aproximada de los corales ya estabelecidos
- diferencias de comunidades en copa de arbol y understory (murcielagos)
- como el reconocimiento de los murcielagos que están polinizando la parte de arriba y que se sabe de su historia natural.
- relacion del nutriente del suelo y los arboles

**Cristina**
- migrantes y danos ambientales
- credito de carbono y livelihoods

**Analida**
- climate change y climate action

**Katie**
- opinión de la gente en relación a la naturaleza

## 16/01/2024 - Agua Salud

### Hydrology
It was interesting that he began talking about forest sponge effect rather than carbon uptake, biodiversity, and other ecosystem services.

The Panama Canal is an obvious reason - there has been concern over planting trees that soak up water during rainy season and release it during dry to keep levels of the gatun lake.
After the 2016 expansion, there has been more shutdowns because more water is needed and there are issues with pastureland around. He did some calculations that showed that if the whole basin had been cleared and made pasture, the gatun lake dam would have broken during the rainy season, which would have been a disaster for the canal.

<mark>I wonder why he said forests are not as efficient a solution for water management, and that they should be conserved for wood value and biodiversity instead.</mark>

Forests in Panama have different influences on rainfall as Amazon does, evidently because of the size of the isthmus (a short drive of less than two hours and you go ocean to ocean!). The water that is transpired in the forest rains in the Pacific most often.

70% of trees planted in Panama are teak. It has good commercial value.

Storm chasers go measure the flow of water on storms and how that's different depending on the ecosystem.

### Forest Ecology
- African tropical forests are more dominated by a single species.
- It is harder to do research in Africa than here. Jeff has worked in central Africa for 20 years and has felt a large gap between tool availability there and here.
- Political instability is an issue to establish long term plots in tropical areas.
- My model does not incorporate the time between abandonment and regrowth, truly. Only the time when the satellite can identify regrowth, and anything before that is still considered pasture. Looking at this distinction in Agua Salud could be interesting, and using it to validate my model at least for pasture sites.

There is also a concern with regards to whether there should be a fixed payment per hectare for carbon offsets or a yearly increment payment. The former is currently preferred due to reduced costs in maintenance (nobody needs to go there to keep measuring the trees), but as new and better biomass products come out, there will be free ways to monitor carbon accumulation. This, however, is another concern as forests will be most valuable at around 15 years old and continuously lower in value as they reach 30 years old, which would lead to turnover in plots. If young trees are cut and left to die, all the carbon goes back to the atmosphere anyways, and the whole effort is wasted.

### Major takeaways

It seems like there is good room for collaboration here. Agua Salud has a similar plot in the tropical dry forest on the other side of the country, and he is doing interesting long term studies with economic viability, as well as the effect of the understory, and passive vs active reforestation, from a pure as well as applied science perspective.

Jeff brought up how wars and conflict are a consequence of environmental collapse. Scientists studying Rwandan resource management predicted the genocide based on when the situation would become critical. With the upcoming climate crisis, things are likely to become worse.

## 15/01/2024, Mon - Huerta reef snorkeling

We worked on coral identification, benthic relief, and  used interesting methods to randomize sampling.

Coral ID was done by dropping a 1m long bar with 5 markings on it. The bar was to be dropped randomly in a zig zag pattern around the reef. Corals touched by the bar to be IDd.

Benthic relief was measured with a chain of known length that was dropped on the reef, and then beginning to end was measured. Enough to get a rough measure of terrain roughness (ha ha)

Also, to measure cover, we put a square on the reef to see the percent cover of different types (algae, CCA, dead coral, living coral, sponges). Overall ineffective, but made much better by the use of AI!

They use [TagLab: A CNN based image segmentation tool oriented to marine data analysis](https://github.com/cnr-isti-vclab/TagLab/tree/main). My immediate reaction was that there MUST be a Python package for this because there is no way I am learning to use GUI for a specific tool unnecessarily. However, a lot of the data cleaning is done manually (segmentation done by the algorithm needs to be fixed), not unlike collecting training data for land use classification. At some point, there is always some sort of manual data collection happening; nothing can be 100% automatized!

### Coral Reefs

<mark> I am curious about the Amazon delta reef system </mark>, and how it is affected by the forest. Also, the freshwater barrier opens a possibility for an interesting study on a marine barrier, and the sister species Sotalia guianensis and fluvialis and how they evolved across a salinity gradient.
### Coral reproduction

**Coral spawning is timed abased on light spectra cues given by the full moon and the sunset.** Once the full moon is up, and the setting sun is at the expected angle for each specific species, they spawn within 15 minutes of each other. Studies have been done to shade coral during spawning time, showing they needed the correct lighting cues.
Main method of reproductive isolation is timing. When timing overlaps, they develop other methods to inviabilize fertilization.
Some coral species produce sperm and eggs at the same time. Other species will have each colony release only eggs or only sperm.
Corals can be **spawners** or **brooders**. Spawners need to time perfectly the release of eggs and sperm so there can be fertilization in the water, while brooders release already fertilized larvae.

#### Settlement
Corals settle in CCA (crustose coralline algae), calcareous red algae that are essential for reef cementation.

Two individual larvae of the same cohort, after they settle at the same time in very close spots, can fuse and become a chimera. About 5% are chimeras.

Conspecific negative density-dependence: Do corals also tend to settle far away from their parent, like trees?
- Few ongoing studies! Unsure if corals tend to avoid their own species rather than other species (heterospecific negative density-dependence).
- On healthy reefs, monospecific stands are rare.

<mark>How do strategies differ between shallow and deep water corals?</mark>

<mark>How does remote sensing of coral reefs work, from space and from water-surface drones?</mark>

Corals seem understudied! I guess I was wrong to assume that the field is oversaturated.

### Personal reflections

Doing science in Latin America is reminding me of the possibilities I've missed out on by being in North America. I am truly grateful for the opportunities I've had, and I recognize my open doors are the result of lots of hard work by myself and many others and even more luck, but at the same time it is painful that to be this privileged, I had to leave Brazil, and that people like me became biologists in a place where the profession is undervalued, with a president who destroys all that has to do with conservation and science.

## 14/01/2024, Sun - Seaweed Farming

Note: the sky here is absolutely beautiful, and these nighttime seascapes would make stunning astrophotography.

### Construction

The mayor mentioned how beaches are protected and houses cannot be built within less than 20 or 30 m from the sea. However, we are sleeping in a house a few steps away from the sea. I have a feeling we have been very excited about something illegal.

### Education

-   On connecting with Daniel on Thu 11/01/2024, we talked about education and its role in forest conservation, as well as livelihoods. This seems to be part of every successful conservation project, like the TAMAR in Brazil - where turtle fishermen were given jobs in ecotourism and taught the importance of turtles to the ecosystem to the tourists instead of killing them - and the jaguar conservation project in Panama, where camera traps were installed in campesinos' properties so they could see the jaguars in their land and relate to them. I would be curious to gather stories from other successful ecological awareness projects and what they have in common across ecosystems.

Also, <mark>I am curious about the difference between the attitudes of fishermen across both oceans on sea turtle and shark fishing</mark>, and what that means for the populations of these two animals.

### Gloria Batista: Seaweed aquaculture and indigenous peoples

![](https://i.imgur.com/yNvrIu9.jpg){width="30%"}

Very exciting to see an older generation latin american female scientist being a leader in her field.

Mapping in her era was extremely difficult. Daviken and her both believe that using paper maps can be beneficial (and in her case, drawing the maps yourself) for understanding of geography. <mark>Mapping seagrass and different types of coral reefs is harder to do on satellite than manually.</mark>

![](https://i.imgur.com/loJloRU.jpg){width="50%"}

Gloria and her husband are the first people to plant marine algae in Central America. He worked on an oil refinery, and at that time there was a large oil spill. The worker of the refinery met the marine biologist Gloria to try to protect the environment and they've been married for 25 years. They wanted to recover what was damaged from the spill.

She started developing a macroalgae project. Now they sell marine algae to Europe. The company has existed for as long as they've been together.

\[\[Ecosystemology\]\] is a book she introduced to us.

At some point, the library they built was destroyed by the American soldiers during the Panamanian invasion.

There is a division of labour in seaweed farming - women prepare the seeds, men plant them into the ocean. They can be planted with low water, but with sea level rise it can become too deep for the algae and generates tall waves.

In Colón, people sell dry algae to be consumed as drinks. They produce algae with indigenous peoples. The government has invited them to do projects with carbon sequestration but they don't work with it yet. They are not sure if this is a truly useful solution or if it is an attempt of governments to greenwash.

#### Guna people usage of algae for food and medicine

[Las algas brindan nuevas oportunidades a los pescadores indígenas en Panamá \| Historias de la FAO \| Organización de las Naciones Unidas para la Alimentación y la Agricultura](https://www.fao.org/fao-stories/article/es/c/1538466/)

She noticed that Guna people were working with macroalgae. It is healthy for stomach, as people were ill from hunger and constantly changing diets. She published much about the indigenous and caribbean afroantillanos usage of algae. The local inaduledi (pajé) would help classify the algae. They were used for healing as well as chants and dances. The inaduledi communicates with auxiliares that treat the ill, diagnose, practice infirmary, and attend epidemics.

There has been good documentation of how these people use land plants, but this was a new project that incorporated algae.

**How is the market for these algae, and do the same people also work with sustainable agriculture and/or agroforestry?** - The Guna people mainly live in islands so they are very reliant on the sea. They have been moved to the land due to sea level rise. Historically they lived on land, but the Spaniards expelled many of them to the sea. However, there are still some on land and some in Colombia.

Panama is the first country (at least in Latin America an the Caribbean) that have started a program to move communities due to climate change

I'm remembering a really cool [study](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3835452/#:~:text=The%20Kuna%20Indians%20who%20reside,least%20on%20their%20death%20certificates.) I read with regards to the Guna people and heart disease, back in the 1990s. The study showed that the Guna originally had no heart disease issues, and as they moved to the city they started developing heart disease issues.

Algae can be an interesting food supplement - the guna of san blas (guna yala), that consume algae, are taller and more robust than the guna of bayano. The difference can be attributed to diet or physical conditions.

New skin for burns can be made from algae.


## 13/01/2024, Sat - Sea cucumber aquaculture

We visited an aquaculture facility near Colón. The company, PanaSea, collects sea cucumbers from the seagrass during their egg-laying season, which is 4 days before every full or new moon. I appreciate the idea of a project that works on commercialization of a natural product, while also working on the restoration of ecosystems through mangrove seedlings and reintroduction of sea cucumbers into the depleted seagrass.

It was interesting to learn how mangrove seedlings can choose where to settle by controlling their buoyancy. One more point on corals and plants and plankton having more choice than we'd give them credit for.

It was really disappointing to see the presentation by a French masters' student that had no results and spoke as if he did, with terribly insignificant plots. It was, however, an interesting opportunity to converse with Jarrod on keeping expectations high and toxicity low in academia by providing feedback when it's warranted while never assuming malintent.

### Snorkeling

The beach has the most coral skeleton that I've ever seen. It's incredibly shallow with few waves. Seabirds are either small andorinhas or large pelicans, no seagulls or albatrosses to be seen. I'm sure there's medium sized birds somewhere.

Seagrass bed was beautiful, with interesting round algae (Penicill) and colourful fish living within it. Coral reef seemed surprisingly degraded.
Absence of:
- starfish
- large crustaceans
- sharks
- turtles
- jellyfish
Little presence of:
- small crustaceans
- schools of fish
Plenty of:
- fire coral
- non-schooling like damselfish and butterflyfish
- dead patches
- bleached coral
Notable presence:
- large barracuda (at least 1m)
- large blowfish

The reef reminded me a lot of Arraial do Cabo, but with no coral-sol to be seen, and very warm shallow waters. Arraial, however, has larger reef fish and more sea turtles, and is in an upwelling zone. 
### Conversation with Carrie 
#### Random thoughts
- corals are animals, so they are not equal to trees in the sense that the larvae do have some matter of choice of where to settle. There are some interesting similarities between coral reefs and forest ecosystems.
- <mark>theoretical modelling of metaecosystem dispersal would be also nicely applied to coral reefs. Unlike large land predators, large marine predators can disperse more easily without the impedement of roads and farms.</mark>
- segmentation modelling can also be done to identify coral species in coral reefs.

#### Coral morphology

![](https://i.imgur.com/cRBFN55.jpg)

![](https://i.imgur.com/3I00QOb.jpg)

-   The corals grow in different shapes depending on the environment, like plasticity in trees. A coral can also change its phenotype depending on its lifetime.
-   Corals can hybridize into chimeras.
-   Distinguishing species can be hard. Molecular evidence and reproductive studies are conducted for the answer.
-   One "mouth" is one individual! So what looks like an individual "coral" is a colony of many little mouths bundled together, each one belonging to an individual. They are characterized based on:
    -   colony shape
    -   the sharing of walls (shared, separate, absent)
    -   Septa, costae, septo-costae \#### Bleaching and invasive corals \##### bleaching
-   They get rid of their zooxanthellae as oxygen reactive species become too much of a problem. The tissue gets discolored. It can recover if this is not long. \##### has a bleached region ever been successfully restored?
-   not yet :(((( there are efforts, a largest one done in Florida, but no reef recovered yet

![](https://i.imgur.com/7ADp4gi.png)

Percentage of living coral cover of what are coral communities.

-   corals have different life strategies - stress-tolerant slow growing, stress-intolerant fast growers, and unstable life strategies. Photogrametry is also used here to measure tree cover.
-   Disease also affects coral communities, as well as storms, temperature rise and pH. Diseases are more of a common issue in the caribbean, as it suffers from lots of direct sewage pollution and agriculture runoff (deforestation kills corals too! through sedimentation).
-   Many oil spills are also an issue around Panama.

#### Symbiosis

-   the endosymbiosis of zooxanthellae and corals provides them with food but also restricts their range based on the range of the symbiont. They can shift their ranges and shift back depending on the conditions. Also, there needs to be the ideal conditions for coral to grow. One of which is low nutrients, because where there are algae they suffer from competition with algae.
-   There's a large range of environments you can find
-   coral and symbiotic relationship with algae - do most of them do it?
    -   the vast majority of corals in the photic zone has zooxanthellae. many in more darkness do not.
-   some corals do have pigments.

## 12/01/2014, Fri - Crane day

The crane is 50m long, 60m tall. There was a lot of illumination on the top of the canopy, and the ground looked very dark when seen from the top, although the trails look well lit when you're walking through them - gives a good perspective on the light gradient and competition. <mark>I wonder what is the increase gain in information with an increase in resolution in SAR and LiDAR-measured plots,</mark> and when does the increase in resolution reach a moment that it is just too much. Say, 2cm is useless information! Where in between 100m and 2cm is optimal biomass resolution? I'd guess somewhere around 30-60m, as a large tree crown seems to easily be 15m wide.

Top-down or bottom-up dominance - evolutionary ecologists need information from community ecologists to understand what currently goes on (where are herbivores more diverse, and how does that vary in relation with producer diversity?) to then extrapolate into the past. <mark>I wonder what theoretical models have been done about this.</mark>

Bryophyte biodiversity with Mikol - it was a bit annoying to feel like I was being treated like a high schooler in the beginning, but once he understood I already knew basic plant taxonomy it was AWESOME. Got to see liverwort and red algae in a pond full of tadpoles. Held frog eggs on my hand, they look like foam but from up close are tiny tiny eggs.

Katie asked Mikol about the most threatened forest in Panama, and he said it is the dry forest as people don't recognize it as a real forest. I have a feeling this is a local phenomenon, as wet forests in South America, Africa and SE Asia are definitely very threatened. Which forests are more threatened, dry or wet? - the Cerrado deforestation has risen by 40% while Amazon deforestation has decreased by 50% over the past year - I WAS WRONG! Dry tropical forests are more threatened! To check whether that is a result of disturbance or deforestation. - [Tropical Dry Forests The Most Endangered Major Tropical Ecosystem - Biodiversity - NCBI Bookshelf](https://www.ncbi.nlm.nih.gov/books/NBK219281/#:~:text=The%20rain%20forest%20is%20not,dry%20forests%20hold%20this%20honor.)

### Panamanian history

Panamanian have pride in their fighting spirit.

**Watermelon slice incident** - one american "bought" a watermelon slice from a panamanian but did not want to pay. a huge fight started and 16 people died.

**Jan 9th is Panama Martyr Day** - around 1964 40-60 students died bringing the Panamanian flag to be hasteada in the Panama Canal area, after the US disrespected an agreement to put both flags in the area. This made the government of Panama more determined to get the canal area back from the US. The flag was taken and ripped in half. It was reconstructed and is now in a museum. There is a monument to them under the name of the red cross volunteer that was one of the leaders of the monument.

**1979** was the Carter treaty where they gave the land back to Panama. Was signed by General Turizo, who actually had consideration for the people's well being. Panama progressed after independence from the US.

**Dec 18 1989** - US military wanted to kill a panamanian general and bombed and destroyed the whole Canal zone. This was due to a part of the CIA wanting to allow drug dealing to reach the US in their efforts to emprison and enslave poor people as prison workers for crack cocaine consumption.

The president that signed the treaty with the US for independence from Colombia did not know English well, so there is a chance he did not understand he was giving away a critical part of his country. Americans lived as kings in Panamanian soil while the locals starved. With the killing of Panamanians in the 80s, people still resent the US.

**Dec 30th 1999** - US finally leaves the Canal Zone.


## 11/01/2024, Thu - Daviken/Daniel

Daviken spoke about decolonizing science - mentioned the book that Holly had mentioned before as well, \[\[Decolonizing Methodology\]\] by \[\[Linda Thuhui Smith\]\]. We mentioned the dialogue that must happen between indigenous communities and scientists, which has historically been a dismissal of the indigenous as scientists occupy their land as if it's empty (violating territorial sovereignty). The conversation was geared much towards the relationship between the researcher and the people at the targeted communities. I feel like there is space for more discussions on the role of scientists as active agents - activists - on the issues that these communities face.

Daniel was speaking as a leader of an NGO that works with social-environmental issues in Panama, ranging from gender issues to indigenous territorial sovereignty. He is a biologist, so also a scientist, but he is very involved with social work now, which is interesting. Over dinner he spoke as if he was almost less a biologist because of it? It's a sentiment I can understand, but it's interesting to see the gradients that exist between the social and biological sciences and how they overlap in different ways, and how a biologist can be so successfully involved with communities while still addressing conservation. He mentioned how some of the malnutrition that happens in Ngobe Bugle region is due to them being displaced from their ancestral land by the spaniards and having to find refuge in poorer areas which are naturally not forested. So, land sovereignty is also an issue of food security - I assume the peoples who are able to maintain their ancestral lands (which tend to be richer) and keep it undisturbed have less nourishment issues. Also connects to the Yanomami that starved after the garimpeiros arrived. Also, we talked how introduction of processed foods and refined sugars is an issue everywhere and brings addiction (like alcohol) and diabetes.

Also, we talked about respecting people's right to choose what happens through their land, campesinos and indigenous alike. We mentioned how protecting the nature is a matter of social equality. Panama is incredibly socially unequal, with an income index skewed high due to the large social gaps. This also makes medications so incredibly expensive here that people bring medications from neighboring countries and even from the US. Whenever there is poverty, nature is the first to suffer. Also reminds of the conversation with Gabriel, on the campesinos that killed the harpia and the jaguar for killing chickens. People don't have the same respect for the environment when they don't understand its value and they have food insecurity. Their work with education is likely as important as their work with agroforestry. They are also involved with Jeff Hall's reforestation project. Also, there was a lot of talk of the mining activities of gold and copper and how many of them have thankfully been closed. They were right in the middle of the mesoamerican corridor, which is also a very awesome thing, an agreement across Central american countries to assure a wildlife corridor.

I would like to incorporate a mix of both Daviken's and Daniel's talks today. Still approach my work from a researcher's lens, with the people I'm working with as aware consenting parts of the project, and also as a part of the community myself, within Brazil and LatAm, to think of how I can help support people in my region. My project proposal will definitely be more on this end of the thing.



## 08/01/2024, Mon : 10/01/2024, Wed - BCI Overhaul

Some species:
- Hura crepitans
- Ficus aurea
- Jacaranda copaia
- Dipteryx oleifera/panamensis

Low wood density ficus aster can reduce tree width when it's dry because it loses water!

**Photogrammetry** -> measuring trees (and also coral!) using photographs. Can be done with terrestrial or aerial photos.

**Tree Core** -> basically one large screw that allows you to remove one pencil-sized cylinder from the whole radius of the tree to examine its rings without cutting it down.

It is super easy to get lost in the forest.

It is interesting to observe the closeness of frugivores and how they are not very alarmed by humans. Quati follow monkeys as they go through the forest eating fruit. Both quati and monkey prefer an area of the forest that is dominated by one species of tree that is currently fruiting and a N fixer so prob full of protein (dipteryx).

Many of the flowers are purple or pink, likely to attract hummingbirds. Bats like strong-smelling flowers. Fewer yellow flowers - <mark>what does flower color say about the pollinator community?</mark>

### Bill Weislo

**Why be social?**
- Increase in productivity (biomass, not biodiversity)
- Survivorship

**Disadvantages**
- Cheaters
- + disease
- + competition

> Simpson says behavior leads to evolution. Meyer says evolution also leads to behavior change.

**Bee facts**
- Most are solitary
- Basically just vegetarian wasps
- One family can show multiple different lifestyles
- A bee can be a queen, a worker, or solitary
- Males are haploid, females are diploid, so a female can choose to have female offspring or not
- Social females invest in females, solitary females invest in males
- Dominant bees can control the amount and protein content of food given to the subordinate
- True sociality is only found in hymneroptera - social spiders aren't as interesting.

> Models can help point out the right direction but may not be realistic in and on themselves in studying the origin and characteristics of sociality. - Bill

> Ants and bees are not automata. Animals have more thought that we give them credit for. - Bill


### 50 hectare plot

Every tree above 10cm DBH in the plot is measured. It was strange to walk around with extreme concern to not damage anything. There are many measurements taken (census, mortality, DBH, aerial monitoring) which happen at different intervals, some yearly and some at 5 year intervals.

It was interesting to not only see the plot that I've read so much about, but see an eddy covariance tower, and dentrometers in real life.

## 07/01/2024 - From Arduino to BCI

- Costa Rican regeneration success is largely due to payments for ecosystem services established since the 80s.

It was cool to work with Arduino for the first time, and have some of that feeling of curious play that the pressure of academia has beat out of me. I do have a lot that I want to learn, and a bunch of opportunities that would require me a whole year off to just study if I wanted to do everything, and I am incredibly curious, but way too overwhelmed to really just take my time, slow down, and play as I learn new things without the pressure of having a specific goal to be achieved.

I'm realizing I would've enjoyed circuits and physics labs much better if they had been taught like this, and I'd be excited to try to customize things at home using an arduino.


## Monthly Report
### Research
- got NLL working properly - finished the whole process of data, from initial cleaning to running the model.
- learned about QGIS
- got back into outreach
- got into obsidian
- applied to FRQNT
### Self
It's been a good month, without many drawbacks. Overall have felt much progress and improvement.

For the coming month, would like to finish the whole chapter 1 methods, from data to model, reorganize all my notes, and get a workout routine started and going.


