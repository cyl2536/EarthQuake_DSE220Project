# EarthQuakePrediction_DSE220Project
https://colab.research.google.com/drive/1odYaC0JoPHjLumcd7hp68RDqyxMRupgp?usp=sharing

Data Exploration 
1.How many observations does your dataset have?
(m & n data shwoing)

4360334 rows x 30 columns

2.Describe all columns in your dataset their scales and data distributions. 

'id', 'mag', 'place', 'time', 'updated', 'tz', 'url', 'detail', 'felt',
       'cdi', 'mmi', 'alert', 'status', 'tsunami', 'sig', 'net', 'code', 'ids',
       'sources', 'types', 'nst', 'dmin', 'rms', 'gap', 'magType',
       'type_property', 'title', 'longitude', 'latitude', 'depth'

3.Describe the categorical and continuous variables in your dataset.

Categorical Variables
These represent discrete labels or identifiers and are typically non-numeric or treated as categories:
- id: Unique identifier for each earthquake event
- place: Text description of the earthquake location
- time and updated: Timestamps (can be treated as categorical for grouping or temporal analysis)
- tz: Time zone offset (can be categorical if treated as discrete regions)
- url and detail: Web links (not used for modeling, but categorical in nature)
- type (if present): Earthquake type (e.g., earthquake, quarry blast, explosion)

Continuous Variables
These are numeric and measurable, suitable for statistical analysis and modeling:
- mag: Magnitude of the earthquake (floating point)
- felt: Number of people who reported feeling the quake
- cdi: Community Internet Intensity Map value (perceived shaking)
- mmi: Modified Mercalli Intensity (ground shaking intensity)


4.How will you preprocess your data?

a.Data Cleaning
b.Feature Engineering (Predict Magnitude)
c.Categorical Encoding (One-hot encode)
d.Scaling and Normalization

Milestone 4

Final Project Report Milestone 4 DSE220

2: Evaluate your model and compare training vs. test error. (3 points)

Test MSE: 0.905

Train RMSE: 0.951, MAE: 0.719, R²: 0.479
Test RMSE: 0.951, MAE: 0.719, R²: 0.480


Feature  Coefficient
0	latitude	-0.015995

1	longitude     0.007411

2	depth     	0.005251
3	year    	-0.012075

4   	month     	0.000790



3: Answer the questions: Where does your model fit in the fitting graph? and What are the next models you are thinking of and why? (3 points)

Where Does Your Model Fit in the Fitting Graph for regression?
1. Underfitting Zone with symptoms of:
- High training error
- High testing error
- Low R² on both sets
- Reason: Model is too simple to capture the underlying patterns (e.g., using linear regression on nonlinear data)

2. Overfitting Zone with symptoms of:
- Very low training error
- High testing error
- Large gap between training and testing R²
- Reason: Model is too complex or memorizes noise in the training data

3. Good Fit (Sweet Spot) with symptoms of:
- Low training error
- Slightly higher but still low testing error
- R² values are close and reasonably high
- Reason: Model captures the signal without overfitting to noise


What Are the Next Models You’re Thinking of and Why?
1. DBSCAN (Density-Based Spatial Clustering). 
Noise/outliers well and captures clusters of arbitrary shape. DBSCAN able to reveal hidden geographic clusters and earthquake data. It often has spatial density variations.
2. Gaussian Mixture Models (GMM). 
Useful when clusters overlap and probabilistic clustering with soft assignments. Depths and Earthquake magnitudes may obey mixed distributions.
3. Hierarchical Clustering. 
Explore nested structure with developing up a dendrogram. For visualizing it depends on how essential clusters merge at different thresholds.
4. Autoencoders (for Deep Feature Extraction)
Especially for high-dimensional data learn nonlinear embeddings. Autoencoders can compress and reveal latent structure, if you expand your dataset with waveform or geospatial features.


Evaluation
Train RMSE: 0.951, MAE: 0.719, R²: 0.479
Test RMSE: 0.951, MAE: 0.719, R²: 0.480




5. Conclusion section: What is the conclusion of your 2nd model? What can be done to possibly improve it? Note: The conclusion section should be it's own independent section. i.e. Methods: will have models 1 and 2 methods, Conclusion: will have models 1 and 2 results and discussion. (3 points)

 Interpretation
Magnitude is difficult to predict from depth and location alone. Because it is difficult to observe with the subsurface, which means direct observation is extremely limited and most earthquake activity happens deep under the ground. Beside that the we have to do indirect measurements like seismic waves and GPS data with the act of subsurface events.
Earthquake intensity depends on complex geophysical factors not captured in this dataset (e.g., plate movement, fault stress). Therefore wide range of intensity values that are not solely determined by the earthquake magnitude itself. Seismic waves are amplified and  attenuated due to these factors and how they interact with structures.
Regression is useful for trend analysis, feature importance, or risk scoring, but not for precise magnitude forecasting. It would not be certain showing an exact outcome between the estimating variables.
 Final Takeaway
Use regression for exploratory modeling, not for operational prediction, which can lead to unreliable and biased results because the assumptions being violated in real world data.
Clustering for alternative insights or consider classification (e.g., magnitude categories).
For richer understanding combine with geospatial and temporal analysis to deliver better predictions.

6. Provide predictions of correct and FP and FN from your test dataset. (2 point)
1. Magnitude Is Not Easily Predictable from Depth and Location 
The features like latitude, longitude, and depth we can predict magnitude with the regression model.
 (e.g., fault stress, plate movement) that are not captured in this dataset because earthquake magnitude mainly depends on complex geophysical processes.
Especially for high-magnitude events. This leads to low R² scores and high prediction error. 
2. Temporal Features Are Weak Predictors
As features assume temporal patterns in magnitude including year, month, or day.
To support regression modeling earthquakes are not seasonal or periodic in a way that we thought.
To reduce model performance these features often add noise rather than signal.
3. Magnitude Distribution Is Highly Skewed
Most earthquakes are low magnitude (0–3), hence high-magnitude (>3) events are rare.
Underestimating severe events, this imbalance causes the model to bias toward predicting low magnitudes.
Misleading predictions and poor generalization for critical cases.


 Instructions for Final README
1.	A complete introduction
The "Earthquakes Around the World from 1900–2025" dataset provides a comprehensive global record of seismic activity, is ideal for geospatial, temporal, and predictive analysis of earthquakes. Sourced from the United States Geological Survey (USGS).
The researchers, engineers, and policymakers worldwide are using trusted source for seismic data. This dataset is derived from the USGS Earthquake Catalog,. Hosted on Kaggle, curated by BwandoWando and, compiles global earthquake data spanning from 1900 to 2025.

2.	A complete submission including all prior submissions
3.	All code uploaded in the form of jupyter notebooks that can be easily followed along to your GitHub Repository. 
4.	A written report
Why Was This Dataset Chosen?
•	Global Scope: It covers earthquakes worldwide from 1900 to 2025, making it one of the most comprehensive seismic datasets available.
•	Rich Features: Enabling both temporal and geospatial analysis which includes magnitude, depth, location, time, and event type.
•	Trusted Source: Ensuring scientific credibility and consistency. Derived from the USGS Earthquake Catalog. 
•	Versatile Applications: Suitable for regression, classification, time series forecasting, clustering and geospatial modeling.

    Why Is It Cool?
•	Earthquake locations align with tectonic boundaries, the visual patterns making it visually compelling for mapping, clustering and regression.
•	Magnitude Diversity captures the full spectrum of seismic activity from microquakes to catastrophic events.
•	This Real-World Relevance dataset connects data science to infrastructure resilience and human safety. Showing that earthquakes affect millions of people.
•	Machine Learning Playground is ideal especially for experimenting with:
•	Predictive modeling (e.g., magnitude estimation)
•	Anomaly detection (e.g., rare high-magnitude events)
•	Risk classification (e.g., severity levels)

Why Is Predictive Modeling Important?
 1. Disaster Preparedness
Predicting earthquake severity or frequency helps governments and NGOs prioritize emergency planning, allocate resources and retrofit infrastructure particularly for the building structures’ sustainability and meet the modern safety standard.
2. Urban and Structural Planning
In high-risk regions models can inform building codes, zoning laws, and insurance risk assessments.
 3. Scientific Insight
Even though we can’t predict earthquakes precisely. Modeling helps us understand patterns, test hypotheses and identify hotspots about seismic behavior.

Final Thought
This dataset is more than just numbers or data— it’s a link between data science and human safety. A good predictive model won’t prevent earthquakes, but it can save lives, reduce economic loss, and guide smarter decisions in a world where seismic risk is a constant.

Figures
Your report should include relevant figures of your choosing to help with the narration of your story, including legends (similar to a scientific paper). For reference you search machine learning and your model in google scholar for reference examples.  (3 points). You can also add figures of plots obtained after EDA.

Updates and New Work
Data Preprocessing
- Cleaned missing values, duplicates and irrelevant columns
- Extracted temporal features (hour, month, year)
- Rounded magnitudes for categorical analysis
 Exploratory Analysis
- Bar charts, pie charts and scatter plot for magnitude distribution
- Resampling for Magnitude Class
- Label formatting and overlap fixes for visual clarity


![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-18%20174148.png)

 Bar Heights
•	The tallest bar is at magnitude 1.0, with over 1.4 million earthquakes.
•	As magnitude increases, on the other hand the frequency drops sharply.
•	Earthquakes above magnitude 6.0 are rare almost none, with very low counts.

Why This Matters 

-	This helps prioritize monitoring resources like most activity is low magnitude, but high-magnitude events require more attention.
-	These are useful for insurance, risk modeling and disaster preparedness.
-	An appropriate cutoff value from clustering, classification and regression models can guide threshold selection for choosing it.


![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-18%20174202.png)

 Segments
Earthquake (97.2%): Natural tectonic earthquakes are the vast majority of events. Quarry Blast (1.5%): These are man-made explosions from construction or mining. Explosion (0.4%): Includes deliberate detonations or industrial accidents. Induced or Triggered Event (0.4%): Fracking or reservoir filling are the earthquakes caused by human activity. Collapse (0.3%): Mine collapses or sinkholes are structural failures. Other Event (0.2%): Seismic disturbances are rare or unclassified.

 Why This Matters
•	Useful for filtering data when building models or conducting geological studies.
•	Focus on natural vs. industrial risks helps emergency planners.
•	Mining, energy, and urban development are able to guide with policy decisions.

![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-18%20174124.png)

Data Points
Each blue dot represents the location of an earthquake. The dots are concentrated along tectonic plate boundaries. The Pacific Ring of Fire (Japan, Indonesia, west coast of the Americas). The Mid-Atlantic Ridge. The Himalayan region. The Mediterranean and Middle East.

Why This Matters
•	Earthquakes are not randomly distributed — they cluster along fault lines where tectonic plates interact within the earth’s outermost layer.
•	This visualization guides disaster planners and geologists:
•	Identify high-risk zones
•	Understand seismic patterns
•	Prioritize monitoring and infrastructure resilience


![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-18%20174137.png)

Data Points
Each point represents an individual earthquake event. The color of each point encodes its magnitude. Yellow: Lower magnitude earthquakes. Red: Higher magnitude earthquakes

Magnitude distribution:
•	Most earthquakes are moderate (yellow to orange).
•	Fewer but more intense events (red) are visible in subduction zones and fault lines.



 Why This Matters
•	Helps determine regions prone to high-magnitude quakes and seismic hotspots. 
•	Essential for risk assessment, disaster preparedness and urban planning.
•	Can get extension to analyze depth, frequency over time, or even tsunami potential.

![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-18%20174224.png)

 Color Encoding
Each point represents an individual earthquake event.The color of each point corresponds to its magnitude:
o	Purple: Lower magnitude
o	Yellow-Green: Higher magnitude
The color bar on the side helps interpret the magnitude scale, which ranges approximately from -7.5 to 7.5.

 Why This Matters
•	This visualization helps identify regions at risk for seismic hotspots and large earthquakes. 
•	It’s useful for:
o	Disaster preparedness
o	Urban planning
o	Geological research

•	You can extend this by overlaying time, depth or event type to uncover deeper patterns.

![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-18%20174237.png)

Key Insight: Resampling
•	The bars are almost nearly equal in height, which means the dataset has been resampled to ensure each magnitude class has the equivalent number of examples.
•	This is crucial for machine learning tasks like classification and regression, where imbalanced data can bias the model toward the majority class.

Why This Matters
•	As in the earlier frequency chart, original earthquake data are heavily skewed toward low magnitudes.
•	Resampling (e.g., undersampling common ones or oversampling rare classes) ensures:

•	It shows fair training across all magnitude levels
•	Improved model accuracy for rare but important classes like "Severe"
•	Reduced bias toward frequent but less impactful events




5.	Your final model should be included in every section of your write up. i.e. Methods, Results, Discussion
Methods
List the steps from starting 
1.	Load the dataset
2.	Describe the dataset
3.	Shows number of rows and columns
4.	Counts rows and columns
5.	Check for missing values
6.	Duplicate value count
7.	Data frame with the name of columns
8.	Statistics of the dataset
9.	Magnitude prediction
10.	Basic Scatter Plot of Locations
11.	Color by Magnitude
12.	Bar Chart: Earthquake Counts by Rounded Magnitude
13.	Pie Chart: Proportion of Earthquakes Types
14.	Earthquake Scatter Plot with Magnitude
15.	Resampling Technique
16.	Resampling Graph
17.	Test MSE
18.	Regression Table
19.	Test and train


Results 
Train RMSE: 0.951, MAE: 0.719, R²: 0.479
Test RMSE: 0.951, MAE: 0.719, R²: 0.480

1. RMSE (Root Mean Squared Error)
•	Definition: The square root of the average of the squared differences between actual and predicted values.
•	Formula:
![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-20%20190433.png)

•	Interpretation:
•	Penalizes larger errors more than smaller ones.
•	Lower RMSE means better model performance.
•	In your case: 0.951 means the typical prediction error is about 0.951 units.

 3. MAE (Mean Absolute Error)
•	Definition: The average of the absolute differences between predicted and actual values.
•	Formula:

![]()



















