---
{"dg-publish":true,"permalink":"/notes/machine-learning/standard-scaling/","created":"2024-11-10T16:53:14.253+05:30"}
---



**Standard scaling** (also known as **Z-score normalization**) is a technique to transform features into a common scale without distorting the differences in the ranges of values. It is used to make sure that each feature in a dataset contributes equally to the model, especially in cases where features have different units or scales (e.g., one feature ranges from 0 to 1, and another ranges from 1,000 to 10,000).

Standard scaling transforms each feature so that:
- The **mean** of the feature becomes **0**.
- The **standard deviation** becomes **1**.

Formula:
$$
Z = \frac{X - \mu}{\sigma}
$$
Where:
- \(X\) is the original value.
- \(\mu\) is the mean of the feature.
- \(\sigma\) is the standard deviation of the feature.
- \(Z\) is the scaled value.

### Why Use Standard Scaling?
Standard scaling is important when:
1. Features have different units (e.g., age in years and income in dollars).
2. Features have different ranges or variances.

It ensures that no single feature dominates the model simply because it has a larger range or different units.

---

### Example for **Average Ratings** Column

The **Average Ratings** column is not a continuous variable like income or age; instead, it is a **categorical numeric variable** with discrete values typically ranging from 1 to 5 (like ratings). Standard scaling for such columns is less commonly applied, but we can still demonstrate it with an example.

Let's assume the **Average Ratings** column has values like:

| Average_Ratings |
| ---------------- |
| 4.47             |
| 4.06             |
| 3.99             |
| 4.31             |
| 3.77             |

#### Step-by-Step Standard Scaling:
1. **Calculate the mean** (\(\mu\)) and **standard deviation** (\(\sigma\)) of the Average Ratings column.

   $$ 
   \mu = \frac{4.47 + 4.06 + 3.99 + 4.31 + 3.77}{5} = 4.12 
   $$

   $$ 
   \sigma = \sqrt{\frac{(4.47 - 4.12)^2 + (4.06 - 4.12)^2 + (3.99 - 4.12)^2 + (4.31 - 4.12)^2 + (3.77 - 4.12)^2}{5}} \approx 0.26 
   $$

2. **Apply the scaling formula** for each value:

   $$ 
   Z = \frac{X - \mu}{\sigma} 
   $$

   For each row in the Average Ratings column, we subtract the mean (\(4.12\)) and divide by the standard deviation (\(0.26\)):

   - For 4.47:
     $$ 
     Z = \frac{4.47 - 4.12}{0.26} = 1.35 
     $$
   - For 4.06:
     $$ 
     Z = \frac{4.06 - 4.12}{0.26} = -0.23 
     $$
   - For 3.99:
     $$ 
     Z = \frac{3.99 - 4.12}{0.26} = -0.50 
     $$
   - For 4.31:
     $$ 
     Z = \frac{4.31 - 4.12}{0.26} = 0.73 
     $$
   - For 3.77:
     $$ 
     Z = \frac{3.77 - 4.12}{0.26} = -1.35 
     $$

#### Standardized Data (Scaled Values):

| Average_Ratings | Scaled Average_Ratings |
| --------------- | ---------------------- |
| 4.47            | 1.35                   |
| 4.06            | -0.23                  |
| 3.99            | -0.50                  |
| 4.31            | 0.73                   |
| 3.77            | -1.35                  |

---

### Important Note:
For categorical numeric variables like ratings (1-5 scale), **standard scaling** is generally less useful, because the values themselves don't follow a continuous distribution that can be meaningfully normalized in the same way as continuous features (like income). In such cases, **normalization** or **min-max scaling** may be a more suitable approach, or you may even leave the ratings as they are, depending on the context and the model you're building.

--- 

