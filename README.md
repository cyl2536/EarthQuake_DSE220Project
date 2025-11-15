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

a.Load the dataset 
b.Describe the dataset
c.Counts of rows and columns
d.Check for missing values
e.Duplicate value count
f.Print the columns of the Dataframe to verify the exact column name 
g.Statistics of the dataset
h.Magnitude prediction
i.Basic Scatter Plot of Locations
j.Color by Magnitude
k.Bar Chart: Earthquake Counts by Rounded Magnitude
l.Pie Chart: Proportion of Earthquake Types
m.Earthquake Scatter Plot with Magnitude
n.Resampling Techniques

