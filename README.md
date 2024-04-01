# Clustering-Penguin-Species
Use unsupervised learning skills to reduce dimensionality and identify clusters in the antarctic penguin dataset

![Penguin Species](https://imgur.com/orZWHly.png)
source: @allison_horst 
Read Further at: https://github.com/allisonhorst/penguins

**The dataset consists of 5 columns.**

- `culmen_length_mm`: culmen length (mm)
- `culmen_depth_mm`: culmen depth (mm)
- `flipper_length_mm`: flipper length (mm)
- `body_mass_g`: body mass (g)
- `sex`: penguin sex


**Sample rows from the dataset:**

<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>culmen_length_mm</th>
      <th>culmen_depth_mm</th>
      <th>flipper_length_mm</th>
      <th>body_mass_g</th>
      <th>sex</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>39.1</td>
      <td>18.7</td>
      <td>181.0</td>
      <td>3750.0</td>
      <td>MALE</td>
    </tr>
    <tr>
      <th>1</th>
      <td>39.5</td>
      <td>17.4</td>
      <td>186.0</td>
      <td>3800.0</td>
      <td>FEMALE</td>
    </tr>
    <tr>
      <th>2</th>
      <td>40.3</td>
      <td>18.0</td>
      <td>195.0</td>
      <td>3250.0</td>
      <td>FEMALE</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>36.7</td>
      <td>19.3</td>
      <td>193.0</td>
      <td>3450.0</td>
      <td>FEMALE</td>
    </tr>
  </tbody>
</table>
</div>


While the dataset lacks labeled instances, it presents an opportunity to apply unsupervised learning techniques to cluster the instances and identify potential groups or classes within the dataset. It is given that there are three species of penguins native to the region: *`Adelie`*, *`Chinstrap`*, and *`Gentoo`*, so the task is to leverage my data science skills and apply unsupervised clustering algorithms to help identify the underlying groups or clusters present in the dataset!


## Project Approach

### 1. Loading and examining the dataset

- create a pandas DataFrame and examine `"data/penguins.csv"` for data types and missing values. 
- store the DataFrame in `penguins_df` variable.

### 2. Dealing with null values and outliers

- using the information you gained in the previous step, identify outliers and null values and remove them.

### 3. Perform preprocessing steps on the dataset to create dummy variables

- create dummy variables for the available categorical feature in the dataset, then drop the original column.

### 4. Perform preprocessing steps on the dataset - scaling

- utilize an available preprocessing function to standardize the features in the dataset and prepare it for the unsupervised learning algorithms. 
- create a preprocessed DataFrame for the PCA process.

### 5. Perform PCA

- perform `PCA()`, without specifying the number of components, to determine the explained variance ratio versus the number of principal components. 
- detect the number of components that have more than 10% explained variance ratio.
- finally, create a variable named `n_components` to store the optimal number of components determined by the analysis, and run the PCA while setting `n_components`.

### 6. Detect the optimal number of clusters for k-means clustering

- perform Elbow analysis to determine the optimal number of clusters for this dataset. 
- store the optimal number of clusters in the `n_clusters` variable.

### 7. Run the k-means clustering algorithm

- using the optimal number of clusters obtained from the previous step, run the k-means clustering algorithm once more on the preprocessed data.

### 8. Create a final statistical DataFrame for each cluster

- create a final characteristic DataFrame for each cluster using the groupby method and mean function only on numeric columns.


