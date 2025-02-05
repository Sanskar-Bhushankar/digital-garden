---
{"dg-publish":true,"permalink":"/Notes/Machine Learning/One hot encoding/","created":"2024-11-10T16:49:50.284+05:30"}
---


### What is One-Hot Encoding?

One-Hot Encoding is a technique used to convert categorical data (like labels or categories) into a numerical format that machine learning algorithms can understand. Here's how it works:

- If you have a categorical column with multiple possible values (e.g., "Urban", "Suburban", "Rural"), One-Hot Encoding creates a new binary column (0 or 1) for each unique category.
- For each row, if the category matches the one represented by the column, it gets a 1; otherwise, it gets a 0.

For example:

- **Original Column**: Location_Category with values ["Urban", "Suburban", "Rural"]
- **One-Hot Encoded Columns**:
    - Urban → [1, 0, 0]
    - Suburban → [0, 1, 0]
    - Rural → [0, 0, 1]

### One-Hot Encoding for the "Location_Category" Column:

Let's apply one-hot encoding to the "Location_Category" column in your provided data:

**Original Data**:

| Number_of_Riders | Number_of_Drivers | Location_Category | Customer_Loyalty_Status | Number_of_Past_Rides | Average_Ratings | Time_of_Booking | Vehicle_Type | Expected_Ride_Duration | Historical_Cost_of_Ride |
| ---------------- | ----------------- | ----------------- | ----------------------- | -------------------- | --------------- | --------------- | ------------ | ---------------------- | ----------------------- |
| 90               | 45                | Urban             | Silver                  | 13                   | 4.47            | Night           | Premium      | 90                     | 284.26                  |
| 58               | 39                | Suburban          | Silver                  | 72                   | 4.06            | Evening         | Economy      | 43                     | 173.87                  |
| 42               | 31                | Rural             | Silver                  | 0                    | 3.99            | Afternoon       | Premium      | 76                     | 329.80                  |
| 89               | 28                | Rural             | Regular                 | 67                   | 4.31            | Afternoon       | Premium      | 134                    | 470.20                  |
| 78               | 22                | Rural             | Regular                 | 74                   | 3.77            | Afternoon       | Economy      | 149                    | 579.68                  |

**One-Hot Encoded Data**:

| Number_of_Riders | Number_of_Drivers | Urban | Suburban | Rural | Customer_Loyalty_Status | Number_of_Past_Rides | Average_Ratings | Time_of_Booking | Vehicle_Type | Expected_Ride_Duration | Historical_Cost_of_Ride |
| ---------------- | ----------------- | ----- | -------- | ----- | ----------------------- | -------------------- | --------------- | --------------- | ------------ | ---------------------- | ----------------------- |
| 90               | 45                | 1     | 0        | 0     | Silver                  | 13                   | 4.47            | Night           | Premium      | 90                     | 284.26                  |
| 58               | 39                | 0     | 1        | 0     | Silver                  | 72                   | 4.06            | Evening         | Economy      | 43                     | 173.87                  |
| 42               | 31                | 0     | 0        | 1     | Silver                  | 0                    | 3.99            | Afternoon       | Premium      | 76                     | 329.80                  |
| 89               | 28                | 0     | 0        | 1     | Regular                 | 67                   | 4.31            | Afternoon       | Premium      | 134                    | 470.20                  |
| 78               | 22                | 0     | 0        | 1     | Regular                 | 74                   | 3.77            | Afternoon       | Economy      | 149                    | 579.68                  |

### Explanation:

- For the "Location_Category" column, we created three new binary columns: **Urban**, **Suburban**, and **Rural**.
- In each row, the respective column for the location category gets a **1**, and the others get a **0**.

For example:

- The first row is in the **Urban** category, so it gets a **1** in the "Urban" column and **0s** in the "Suburban" and "Rural" columns.
- The second row is in the **Suburban** category, so it gets a **1** in the "Suburban" column and **0s** in the others.
