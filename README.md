# Home_values-clustering-visuals
A house flipping company would like to identify underpriced homes by comparing asking prices to predicted sale prices. They would like to segment homes into groups to analyze what kinds of homes there are. They would also like a model that predicts the selling price of a home. 

# Task

A house flipping company would like to identify underpriced homes by comparing asking prices to predicted sale prices.   They would like to segment homes into groups to analyze what kinds of homes there are. They would also like a model that predicts the selling price of a home.

The company has provided publicly available data from the King County Assessor's office to use for clustering and prediction.

# determining clusters via kmeans

## Inertia

![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/c708dce8-d286-4124-acde-6307c062448e)

## Sihloutte

![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/6c9ad710-8046-4266-a003-4682892845c3)

## Visualize clusters

![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/9bf8a902-0481-4bdc-b60a-388ba1050206)
![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/300c4544-2164-4896-95d3-f455710a2791)

## Cluster Demographics

- Cluster0
  - large basements with daylight view
  - mostly brick/stone builds
  - large basaement garages
- Cluster1
  - most half floor sqft (loftstyle home)
  - smaller garagesor basement
  - lowest sqft livingsace
- Cluster2
  - large decks
  - largest top floor (stilthouses or townhomes)
  - larger  enclosed porches
- Cluster3
  - most multifloor floorplans
  - smaller basements
  - more baths
  - Highest listing prices

- overall summary
  - cluster0
    -  presents as  hillside homes with larger basement/garages that still have daylight views and made mostly of brick/stone
  - cluster1
    - more on the scale of a starter home with smaller floorplans, lower price and lack of multistory floorplans
  - cluster2
    - homes with larger outdoor living spaces such as townhomes with roof access
  - cluster3
    - larger homes with more sqft  and multiple floors, on average higher bed/
  bath count

 based on that rubric the following differences can be intrerpreted :

![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/bcd7a5d8-51e6-4fe6-bd5f-07816a5bb0d1)

- according to the spread of price, cluster 2 falls in line with the  prediction of it being a less expensive starter home, clusters 0 and 2 can be interpreted as  mid range/ more extablished homes and cluster 3 is the larger more high end homes.

  ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/99597ec3-2e3e-4ca1-8ade-c20b1ba40763)

- according to the  amount of bedrooms generally observed in each cluster type it can be  interpreted that the cluster1 can be  an (average) amount of rooms for a starter home, cluster 0 is more rooms for a more established and larger home, cluster2 having less rooms which falls in line with it being a townhome type house, and finally cluster3 having the most amount of rooms  being on the larger side of the spectrum.

# Deep Learning models

- SalePrice is the target variable so the metric to interpret will be regression
  - Sequential model 1
    - ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/695f8649-2944-473f-9a66-085f519d5597)
   
    - ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/2d88f0d3-57f4-44c5-8e45-82d5310231f9)
    - ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/38f5ee49-1d5d-4bc0-b0d9-55f7164f6fdd)
   
    - ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/3b36981a-03d6-4015-8a40-2b349da856bb)
   
    - Summary: model one  is showing signs of underfitting  and is too simple, to combat this  model 2 will increase complexity and increasethe training epochs
 
  - Sequential model 2 (Tripled neurons in hidden layers to add complexity and combat underfitting of first model.)
    - ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/61c1cd77-6807-487a-88d0-510393a6986c)
   
    - ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/5d684c64-4026-49fb-98e7-f63197a06f8b)
    - ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/e2eb95ef-26a3-469e-a1dd-2ae380b6cb66)
   
    - ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/3cfb01bb-23f1-4f08-8fd1-cdede5de3f6d)
   
    - Summary:
    - the train and test have leveled out from the previous model  and model is no longer underfit, but model is now displaying Overfit qualities perfroming worse on test  data than on training data.
    - models seem to level out aorund 100 epochs, next model will decrease complexity abit and add regularization via  early stop  and dropout params since we can see visually where the model begins to stray from accuracy.
   
  - Sequential model 3( decrease complexity, add earlystopping, add dropout)
    - ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/1543aed2-eec8-4a3a-8a46-ad87679ed91f)
   
    - ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/4c451cb3-643a-4950-8679-89128e05bc53)
    - ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/738a42fc-aa34-44df-80c3-5e62e7926d81)
   
    - ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/da93131d-85ec-428d-a7b7-2abf08cda630)
   
    - Summary:
      - model learning curve has leveled out.
      -  high variance has been managed.
      - model accuracy R2 scove has increased.

      - Overview of regession evaluations.
        ![image](https://github.com/clovestad/Home_values-clustering-visuals/assets/103072823/67c0129f-907b-4cb7-9312-4d14b110469d)
## model selection
the selected model will be model 3.
model 3 has been fine tuned to address the high variance than model1 and model 2 have and the model accuracy is far better as well.

[interactive dashboard](https://public.tableau.com/app/profile/colin.lovestad/viz/Seattle_Housing_16980307174840/Dashboard1?publish=yes)






















