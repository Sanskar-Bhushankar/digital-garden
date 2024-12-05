---
{"dg-publish":true,"permalink":"/notes/machine-learning/pca-principal-component-analysis/","created":"2024-11-09T21:15:38.523+05:30"}
---


### Curse of Dimensionality:
- **Data sparsity**: As dimensions increase, data points become spread out and harder to analyze.
- **Increased complexity**: More dimensions make algorithms slower and data harder to visualize.

### Dimensionality Reduction Techniques:
1. **Feature Selection**: Choose important features and discard irrelevant ones.
2. **Feature Extraction**: Transform features into a lower-dimensional space that captures key patterns. **PCA** is an example of this.
## 1. Feature Selection

consider this table of house price based on rooms and no of grocery shop around

| rooms | no of grocery shops | price(lakhs) |
| ----- | ------------------- | ------------ |
| 3     | 4                   | 60           |
| 4     | 0                   | 130          |
| 5     | 6                   | 170          |
| 2     | 10                  | 90           |

![[Pasted image 20241110124942.png \| 400]]

now we can see here there is no direct relation for the rooms and grocery shop and if we were to select any column from this then we would go for room because the spread of the room data is grater than the grocery shops

## 2. Feature Extraction

Now consider the table where there is rooms and no of washrooms here both the columns are imp for the price but we want to select only one column  

| rooms | washrooms | price(lakhs) |
| ----- | --------- | ------------ |
| 3     | 1         | 60           |
| 4     | 2         | 130          |
| 5     | 2         | 170          |
| 2     | 1         | 90           |

so for feature extraction we create a subset of the data combining the both rooms and no of washrooms

| rooms | price(lakhs) |
| ----- | ------------ |
| 4     | 60           |
| 6     | 130          |
| 7     | 170          |
| 3     | 90           |

## **PCA**
**PCA (Principal Component Analysis)** simplifies complex data by reducing its dimensions while preserving the most important information
### Example: Photographer at a Football Match
Imagine a photographer at a **3D football match** trying to capture the best shot using a **2D camera**. The game has width, height, and depth, but the camera can only capture two dimensions. The photographer moves around to find the best angle that shows the most important action of the game.

In PCA, this is like finding the **best "angle"** to capture the key features of high-dimensional data (like player positions in 3D space) and reducing it to fewer dimensions (like a 2D photo) while keeping the essential information.

lets consider the room and washroom table and plot graph on it

![[Pasted image 20241110150939.png \|600]]

![[Pasted image 20241110151849.png \| 300]]

so from here we can see the spread  variance of pc1 is higher than pc2 so pc1 becomes more likely impactfull on the dataset

### Why Variance is Important in PCA:

![[Pasted image 20241110162343.png \| 400]]

> [!NOTE]
> for the above images consider the red and green dot marked if we have to find the distance between them how far they both are from each other then we can see that on x axis the difference between them is high but for the same if we capture for the y axis then the distance would be very small 
> so when making a problem statement the end goal will be to maximize the variance
> 

1. **Variance = Information**:
    - When we perform PCA, we want to keep the most important parts of the data. The variance tells us how much the data "spreads out" in different directions. More variance means more important information.
    - Think of it like a map: the directions with the most spread (variance) show us the most important landmarks in the dataset. So, we want to keep the directions with the most variance, because they help us understand the dataset better.
2. **Reducing Dimensions**:
    - PCA helps us reduce the number of features or dimensions in a dataset while keeping the most important information. To decide which features to keep, we look at the variance. The higher the variance, the more we keep that feature.
3. **Removing Noise**:
    - Low variance means that the feature doesn’t vary much, and it might just be noise (random fluctuations). So, we can safely ignore these low-variance features.

### Why Variance is Not Exactly the "Spread" of Data:

- **Spread**: When people talk about the "spread" of data, they usually mean how far the data points are from each other—like how far apart the highest and lowest points are.
- **Variance**: Variance is a **measure** of how far each data point is from the **average (mean)** of all the points. The more the points deviate from the mean, the higher the variance.
- 
So, **variance and spread are related**, but they're not the same thing:

- Variance tells us how much the data points differ from the average point (mean).
- Spread tells us the range (the difference between the largest and smallest points).

### Why Variance and Spread are Related:

- If you have a dataset with high variance, the data points are spread out far from the average (mean), and so, we would say the data is more "spread out."
- If the variance is low, the data points are close to the average, and the data is not spread out much.

### Simple Analogy:

- Imagine you have 5 students in a class, and you measure how tall they are. If all the students have almost the same height, the variance (how much the heights differ from the average height) is low. If one student is much taller or shorter than the others, the variance is high because the heights are more spread out.
- **Variance is a precise measurement of how "spread out" the heights are from the average.**

### PCA Fundamentals

#### Why Use PCA?

In high-dimensional datasets (with many features), it can be challenging to process or visualize data. Too many features can lead to redundancy and noise, making it hard to identify patterns. PCA helps by transforming the original features into a new set of fewer, uncorrelated features called **principal components**.

#### How PCA Works: Simple Steps

1. **Standardize the Data**: Ensure each feature is on the same scale (e.g., mean 0 and variance 1).
2. **Compute the Covariance Matrix**: This matrix captures the relationships (correlations) between features.
3. **Calculate Eigenvectors and Eigenvalues**: These help identify the "directions" in which data varies the most. Each eigenvector represents a principal component, and the eigenvalue shows its importance (variance explained).
4. **Sort and Select Principal Components**: Sort components by eigenvalues in descending order, then select the top components to form a reduced dataset.
5. **Transform the Data**: Project the original data onto the chosen principal components, creating a dataset with fewer dimensions but preserving the most critical variance.
