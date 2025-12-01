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
   Noise/outliers well and captures clusters of arbitrary shape. DBSCAN able to reveal hidden geographic       clusters and earthquake data. It often has spatial density variations.

2. Gaussian Mixture Models (GMM). 
   Useful when clusters overlap and probabilistic clustering with soft assignments. Depths and Earthquake      magnitudes may obey mixed distributions.

3. Hierarchical Clustering. 
   Explore nested structure with developing up a dendrogram. For visualizing it depends on how essential       clusters merge at different thresholds.

4. Autoencoders (for Deep Feature Extraction)
   Especially for high-dimensional data learn nonlinear embeddings. Autoencoders can compress and reveal       latent structure, if you expand your dataset with waveform or geospatial features.


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
   (e.g., fault stress, plate movement) that are not captured in this dataset because earthquake magnitude     mainly depends on complex geophysical processes.
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
       The "Earthquakes Around the World from 1900–2025" dataset provides a comprehensive global record of         seismic activity, is ideal for geospatial, temporal, and predictive analysis of earthquakes. Sourced        from the United States Geological Survey (USGS).
       The researchers, engineers, and policymakers worldwide are using trusted source for seismic data.           This dataset is derived from the USGS Earthquake Catalog,. Hosted on Kaggle, curated by BwandoWando         and, compiles global earthquake data spanning from 1900 to 2025.

2.	A complete submission including all prior submissions

3.	All code uploaded in the form of jupyter notebooks that can be easily followed along to your GitHub         Repository. 

4.	A written report
Why Was This Dataset Chosen?
•	Global Scope: It covers earthquakes worldwide from 1900 to 2025, making it one of the most                  comprehensive seismic datasets available.
•	Rich Features: Enabling both temporal and geospatial analysis which includes magnitude, depth,              location, time, and event type.
•	Trusted Source: Ensuring scientific credibility and consistency. Derived from the USGS Earthquake           Catalog. 
•	Versatile Applications: Suitable for regression, classification, time series forecasting, clustering        and geospatial modeling.

    Why Is It Cool?
•	Earthquake locations align with tectonic boundaries, the visual patterns making it visually                 compelling for mapping, clustering and regression.
•	Magnitude Diversity captures the full spectrum of seismic activity from microquakes to catastrophic         events.
•	This Real-World Relevance dataset connects data science to infrastructure resilience and human              safety. Showing that earthquakes affect millions of people.
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
-	This helps prioritize monitoring resources like most activity is low magnitude, but high-magnitude          events require more attention.
-	These are useful for insurance, risk modeling and disaster preparedness.
-	An appropriate cutoff value from clustering, classification and regression models can guide                 threshold selection for choosing it.


![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-18%20174202.png)

 Segments
Earthquake (97.2%): Natural tectonic earthquakes are the vast majority of events. Quarry Blast (1.5%): These are man-made explosions from construction or mining. Explosion (0.4%): Includes deliberate detonations or industrial accidents. Induced or Triggered Event (0.4%): Fracking or reservoir filling are the earthquakes caused by human activity. Collapse (0.3%): Mine collapses or sinkholes are structural failures. Other Event (0.2%): Seismic disturbances are rare or unclassified.

 Why This Matters
•	Useful for filtering data when building models or conducting geological studies.
•	Focus on natural vs. industrial risks helps emergency planners.
•	Mining, energy, and urban development are able to guide with policy decisions.

![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-18%20174124.png)

Data Points:
Each blue dot represents the location of an earthquake. The dots are concentrated along tectonic plate boundaries. The Pacific Ring of Fire (Japan, Indonesia, west coast of the Americas). The Mid-Atlantic Ridge. The Himalayan region. The Mediterranean and Middle East.

Why This Matters
•	Earthquakes are not randomly distributed — they cluster along fault lines where tectonic plates             interact within the earth’s outermost layer.
•	This visualization guides disaster planners and geologists:
•	Identify high-risk zones
•	Understand seismic patterns
•	Prioritize monitoring and infrastructure resilience


![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-18%20174137.png)

Data Points:
Each point represents an individual earthquake event. The color of each point encodes its magnitude. Yellow: Lower magnitude earthquakes. Red: Higher magnitude earthquakes.

Magnitude distribution:
•	Most earthquakes are moderate (yellow to orange).
•	Fewer but more intense events (red) are visible in subduction zones and fault lines.



 Why This Matters
•	Helps determine regions prone to high-magnitude quakes and seismic hotspots. 
•	Essential for risk assessment, disaster preparedness and urban planning.
•	Can get extension to analyze depth, frequency over time, or even tsunami potential.

![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-18%20174224.png)

 Color Encoding
Each point represents an individual earthquake event. The color of each point corresponds to its magnitude:
o	Purple: Lower magnitude
o	Yellow-Green: Higher magnitude
       The color bar on the side helps interpret the magnitude scale, which ranges approximately from -7.5         to 7.5.

 Why This Matters
•	This visualization helps identify regions at risk for seismic hotspots and large earthquakes. 
•	It’s useful for:
o	Disaster preparedness
o	Urban planning
o	Geological research

•	You can extend this by overlaying time, depth or event type to uncover deeper patterns.

![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-18%20174237.png)

Key Insight: Resampling
•	The bars are almost nearly equal in height, which means the dataset has been resampled to ensure            each magnitude class has the equivalent number of examples.
•	This is crucial for machine learning tasks like classification and regression, where imbalanced data        can bias the model toward the majority class.

Why This Matters
•	As in the earlier frequency chart, original earthquake data are heavily skewed toward low magnitudes.
•	Resampling (e.g., undersampling common ones or oversampling rare classes) ensures:

•	It shows fair training across all magnitude levels
•	Improved model accuracy for rare but important classes like "Severe"
•	Reduced bias toward frequent but less impactful events




5.	Your final model should be included in every section of your write up. i.e. Methods, Results,        Discussion
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
•	Definition: The square root of the average of the squared differences between actual and predicted          values.
•	Formula:
![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-20%20190433.png)

•	Interpretation:
•	Penalizes larger errors more than smaller ones.
•	Lower RMSE means better model performance.
•	In your case: 0.951 means the typical prediction error is about 0.951 units.

2. MAE (Mean Absolute Error)
•	Definition: The average of the absolute differences between predicted and actual values.
•	Formula:

![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-20%20190421.png)

•	Interpretation:
•	Treats all errors equally (no squaring).
•	More robust to outliers than RMSE.
•	In your case: 0.719 means the average prediction is off by 0.719 units

3. R² (R-squared or Coefficient of Determination)
•	Definition: Measures the proportion of variance in the target variable that is explained by the model.
•	Formula:

![](https://github.com/cyl2536/EarthQuake_DSE220Project/blob/main/Screenshot%202025-11-20%20190357.png)

•	Interpretation:
•	Ranges from 0 to 1 (sometimes negative if the model is worse than a horizontal line).
•	0.479 means your model explains 47.9% of the variance in the data 





Discussion
This is where you will discuss the why, and your interpretation and your thought process from beginning to end

Why did I choose the model?

I chose the regression model because we need to measure the magnitude. What do those results means from the Train and Test output? Give some comments on the results with pros and cons.

What the Metrics Mean:
RMSE (Root Mean Squared Error) ≈ 0.951
o	Measures the average size of prediction errors, penalizing large errors more strongly (because of           squaring).
o	Here, on both train and test sets, the error magnitude is about 0.95 units.

MAE (Mean Absolute Error) ≈ 0.719
o	Measures the average absolute difference between predicted and actual values.
o	Less sensitive to outliers compared to RMSE.
o	On average, predictions are off by about 0.72 units

R² (Coefficient of Determination) ≈ 0.48
•	Explains the numbers of variance in the target variable is captured by the model.
•	In earthquake outcomes a value of ~0.48 means the model explains about 48% of the variability.
•	It shows the model is learning something beyond random guessing, this is considered not very high.

Train vs Test Comparison
•	Train and Test metrics are nearly identical (RMSE, MAE, R²).
       This suggests:
•	The model is not overfitting (the performance generalizes well).
•	The overall predictive power is moderate — it captures ~half of the variance (leaving room for              improvement).

In summary 
The earthquake model makes predictions with about 0.7–0.95 units of the average error. This explains ~48% of the variability, and generalizes consistently across train and test sets. (This means it’s stable but not highly accurate yet)

  	Comments:
•	The model is stable (train ≈ test), which is encouraging.
•	However, the predictive power is limited — explaining only half the variance suggests either the            features don’t capture enough signal, or the model type is too simple for the complexity of                 earthquake data. 

The next steps could include:
•	Featuring engineering (e.g., geological variables, temporal features) to transform variables from           data to make them more suitable for the model and at the same time improve machine learning and             model performance. These factors helps boost the model’s predictive accuracy.
•	Try nonlinear models for a more complex pattern (Random Forests, Gradient Boosting, Neural Nets).           When a linear model is inadequate this is very useful.
•	Check for noise or limitations in the dataset itself (missing data, bias, quality and size issues). 

What this tells us:
•	The train and test metrics are almost identical with consistency. That’s a good sign — the model is         generalizing well and not overfitting. We can avoid not overfitting with training with more data,           reducing the number of features through selection of features and simplifying the model.
•	On average, predictions are off by about 0.7–0.95 units of Error magnitude. That’s a moderate error         depending on the scale of your target variable, mainly magnitude followed by timing/ location,              casualties and damages.
•	The variance of R² around 0.48 means the model explains ~48% of the variability in earthquake               outcomes. It’s capturing some meaningful patterns, but there’s still a lot of variances left                unexplained like impact on seismic hazard, between-event variance and ground motion variability. 




Pros:
•	Train and test metrics are Generalization strong and nearly identical (RMSE ≈ 0.951, MAE ≈ 0.719, R²        ≈ 0.48). It performs consistently on unseen data, meaning to say the model is not overfitting.

•	Both sets show the same average error magnitude with Stable error level, which suggests the                 preprocessing and model choice are robust.
•	MAE and RMSE Interpretability are easy to understand in terms of “average error size,” and R² gives         a clear measure of explained variance like depth difference and ground motion surprised.

Cons:
•	Moderate accuracy: R² ≈ 0.48 means the model explains less than half of the variance in earthquake          outcomes. 
•	Error magnitude may be high: Depending on the scale of your target variable, an average error of            ~0.7–0.95 units might be significant.
•	Potential underfitting: The fact that train and test scores are equally low suggests the model isn’t        capturing enough complexity in the data (It’s too simple or the features don’t contain enough               predictive signal).

Summary:
•	Pro: The model generalizes well and is stable across training/testing.
•	Con: It doesn’t capture enough variance, so predictive power is limited.


This will mimic the sections you have created in your methods section as well as new sections you feel you need to create. 

Methods Section

1. Data Preprocessing
•	Missing Values: Remove or input missing entries in depth, magnitude, and type.
•	Feature Engineering:
o	Extracted year, month, day from timestamps
o	Encoded type as categorical
o	Normalized depth and location features for modeling
•	Resampling: Balanced magnitude classes to address skewed distribution

2. Exploratory Data Analysis (EDA)
-Bar Chart
-Pie Chart
-Scatter Plots
-Resampling
-Regression

•	Mapped earthquake locations to identify tectonic clusters with Spatial Distribution
•	Plotted Magnitude Frequency histogram to show dominance of low-magnitude events
•	Pie chart Event Type revealed 97% of events are natural earthquakes

3. Modeling Approaches
A. Regression
•	Predicting magnitude from location and depth are the main goals
•	Used Linear Regression Model
•	Limited predictive power due to missing geophysical context, with moderate R² (~0.4–0.6) Outcome;
•	To categorize earthquakes into magnitude classes (e.g., Low, Moderate, Severe) are the Goals.

4. Evaluation Metrics
•	Regression with RMSE, MAE, R²
•	We can Visualize Residual plots, confusion matrices, prediction vs. actual scatter plots

Interpretation & Thought Process
•	This dataset is globally relevant, scientifically credible, and rich in features for both temporal          and spatial modeling.
•	Depth and location are the Initial hypothesis to predict magnitude — but regression revealed                limitations.


Broader Impact
•	NGOs and governments help Disaster Preparedness identify vulnerable zones (e.g., areas near tectonic        plate boundaries with seismic activity )
•	Informs infrastructure resilience and building codes about Urban Planning:
•	Supports research into seismic patterns and tectonic behavior with Scientific Insight.
•	A rich, real-world dataset for teaching machine learning and geospatial modeling through Education.

You can also discuss how believable your results are at each step

 1. Data Cleaning & Preprocessing
What I Did:
•	Removed missing or invalid values (e.g., magnitude, NaNs in depth)
•	Converted timestamps to datetime and extracted year, month, day
•	Encoded categorical variables like type
•	Normalized numerical features (e.g., depth, longitude, latitude)


Believability:
High — These are standard, transparent preprocessing steps. However, we must acknowledge:

•	Older records (pre-1960s) due to limited instrumentation it might be imprecise or incomplete.
•	Magnitude and depth values may have inconsistencies across variables like time and regions.

 2. Exploratory Data Analysis (EDA)
What I Did:
•	Plotted magnitude distributions (revealed heavy skew toward low magnitudes)
•	Mapped global earthquake locations (aligned with tectonic boundaries)
•	Visualized event types (97% are natural earthquakes)

Believability:
Very High —These are geophysically well-established with the patterns observed (e.g., along the Pacific Ring of Fire). With known seismic behavior the skewed magnitude distribution is consistent.
 3. Regression Modeling (Predicting Magnitude)
What I Did:
•	Trained models like Linear Regression 
•	Used features like latitude, longitude, depth, year, month

Believability:
Low to Moderate — The underlying assumption is flawed while the models may show some correlation (R² ~ 0.3–0.6):
•	Solely from surface-level features, earthquake magnitude is not reliably predictable.
•	Missing key variables: fault stress, tectonic strain, subsurface geology.
As Conclusion Regression results are not scientifically predictive but mathematically valid.

5. Evaluation & Interpretation
 What I Did:
•	Used RMSE, MAE, R² for regression
•	Used accuracy, precision
•	Visualized residuals and confusion matrices

Believability:
High — Metrics are standard and interpretable. However:
•	Overfitting risk if not validated properly (e.g., using time-based splits)
•	False confidence can lead to incorrect assumption if model performance is not contextualized with           domain knowledge. This includes geological processes that causes tectonic plate movement and the            resulting seismic phenomena (waves, magnitude and epicenter).

You can discuss any short comings

Key Shortcomings of the Dataset

1. Magnitude Skew and Imbalance
•	Issue: The dataset is heavily skewed toward low-magnitude earthquakes (e.g., 0–3).

•	Impact: This imbalance can bias models toward predicting underperformance on small events and rare          but critical high-magnitude earthquakes.
•	Mitigation requires resampling to reduce severity.

2. Missing Geophysical Context
•	Issue: For the dataset lacks crucial features like tectonic plate interactions, fault line                  proximity, or stress accumulation.
•	The Impact limits the ability to build physically meaningful predictive models for occurrence or            magnitude.  
•	Mitigation: Supplement with unsupervised methods or external geophysical datasets for pattern               discovery.

3. Temporal and Spatial Reporting Bias
•	Issue: Due to limited instrumentation, older records (pre-1960s) and for remote regions may have            underreported or imprecise data.
•	Impact: In time series or geospatial analysis introduces gaps and noise.
•	Mitigation: Apply confidence weighting or temporal filters based on reporting density.

4. Ambiguity in Event Types
•	Issue: While most events are labeled as "earthquake," others like "quarry blast" or "explosion" may         be misclassified or inconsistently recorded.
•	Impact: Interpretation of seismic patterns and also affects classification accuracy.
•	Mitigation: Clean and validate event types or exclude ambiguous categories.

5. Depth Measurement Inconsistencies
•	Issue: Depth values can be missing, rounded, or estimated differently across regions and time.
•	Impact: Reduces reliability of depth-based modeling or clustering.
•	Mitigation: Use depth only in exploratory analysis or input missing values cautiously.

Final Thought

This dataset is a powerful starting point for seismic analysis, but with its limitations remind us that earthquake modeling is not just a data science problem — it’s a geophysical one. To extract meaningful insights thoughtful preprocessing, domain knowledge, and cautious interpretation are essential.

Accounts for these limitations would you like help integrating external geophysical data or designing a robust pipeline?

Disadvantages of the model

1. Temporal Bias and Incompleteness
•	Older records (pre-1960s) due to limited seismic instrumentation are most likely imprecise or               incomplete.
•	With introducing a temporal imbalance, recent decades have more frequent and accurate recordings.
•	This can bias models toward reducing generalizability and recent patterns across time.

2. Geographic Sampling Bias
•	Denser in regions with better monitoring infrastructure (e.g., U.S., Japan) from the earthquake             report.
•	Clustering or spatial models may skew by Underreporting in less-developed or remote regions.

3. Magnitude Thresholding
•	Many datasets exclude earthquakes below a certain magnitude (e.g., <4.0)
•	This creates a truncated distribution that results from restricting the domain of other probability         distribution, which can distort regression models predicting frequency or magnitude .
 
 4. Missing or Inconsistent Features
•	Missing or inconsistently might from the formatted Fields like location, depth, or event type.
•	The number of usable samples and data cleaning challenges like handling large datasets, removing            duplicates and managing missing data can be reduced.

 5. No Ground Truth for Impact
•	For impact prediction the dataset lacks labels for casualties, damage, or economic loss, limiting           supervised learning.
•	For richer modeling you’d need to merge with external datasets.
 
 6. Noisy or Redundant Features
•	Latitude/longitude may be redundant with some features (e.g., location names).
•	Requiring careful preprocessing, others may be categorical but poorly encoded.































