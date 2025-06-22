---
{"dg-publish":true,"permalink":"/MSC DataScience/SEM 2/Time Series/Unit 3 PYQ/","tags":["msc","pyq","qb","DataScience","time-series"],"created":"2025-06-18T23:36:59.434+05:30"}
---


# Unit 3 theory

### Q1. Define forecasting. What are the main goals and applications of forecasting in business and economics?

**Forecasting:**
Forecasting is the process of predicting future events or trends based on historical data, analysis, and models.
**Goals of Forecasting:**
* Predict future demand, sales, or market trends
* Support strategic planning and decision-making
* Optimize resource allocation (like inventory, staff, and budget)
* Minimize risks and uncertainties
* Improve operational efficiency and competitiveness

**Applications in Business and Economics:**
* **Sales forecasting** to plan production and inventory
* **Financial forecasting** for budgeting and investment decisions
* **Economic forecasting** for GDP, inflation, and employment trends
* **Supply chain management** for demand planning
* **Marketing strategy** and product launches based on trend predictions

---

### Q2. Differentiate between qualitative and quantitative forecasting methods. Give two examples of each.
#### **Qualitative Forecasting Methods**

**What is it?**
These methods are based on **human judgment, opinions, and intuition**, not on historical data. They are used when **past data is not available** or when forecasting new products, trends, or situations.
**When to use?**
* When historical data is missing or unreliable
* When launching a new product or entering a new market
* When expert opinion is more useful than past patterns
**Examples:**
1. **Delphi Method** – A panel of experts is asked to give their opinions anonymously. Their responses are collected, summarized, and shared in rounds until a consensus forecast is reached.
2. **Market Research** – Surveys or interviews with customers to predict demand or trends based on what people say they will do or prefer.
#### **Quantitative Forecasting Methods**
**What is it?**
These methods use **mathematical models and historical data** to make forecasts. They rely on data patterns, trends, seasonality, and statistics.
**When to use?**
* When you have enough reliable historical data
* When patterns like trends or seasonality exist
* When you want data-driven, objective results
**Examples:**
1. **Moving Average** – Takes the average of previous values (like sales over last 3 months) to predict the next value.
2. **Exponential Smoothing** – Assigns more weight to recent data and less to older data to forecast future values more accurately.
##### Summary:

| Feature          | Qualitative Forecasting            | Quantitative Forecasting              |
| ---------------- | ---------------------------------- | ------------------------------------- |
| Based on         | Judgment, opinion                  | Historical data, math models          |
| Data requirement | Not required                       | Required                              |
| Accuracy         | Less precise                       | More precise (if data is good)        |
| Use case         | New products, uncertain conditions | Established trends, regular data      |
| Examples         | Delphi Method, Market Research     | Moving Average, Exponential Smoothing |

---
### Q3. Explain the variate component method in time series analysis. What are its key components?

##### **What is Variate Component Method?**
It is a method in time series analysis where we **break the time series data into parts** (called components) so we can **understand and analyze each part separately**.

Think of a time series (like monthly sales, temperature, website traffic, etc.) as a **mix of different patterns** — like overall growth, repeating seasons, and random changes.
This method helps us **separate** and study these patterns clearly.
##### **Why do we use it?**
* To understand **how data behaves over time**
* To know **which part is trend**, **which is seasonal**, and **what is just random noise**
* To make **better forecasts** for future values
* To identify **real business changes** without being confused by seasonal effects
##### **When do we use it?**
* When the data has **trends or patterns repeating every year or month**
* When you want to build a **forecasting model** (e.g., predicting future sales or temperature)
* When analyzing time-based data in **economics, business, finance, weather, etc.**

##### **The 4 Components (Explained in Simple Words)**
1. **Trend (T)**
   * It shows the **overall direction** — is the data going **up**, **down**, or staying the same over time?
   * Example: A company's revenue slowly increasing year by year.

2. **Seasonal (S)**
* It shows **repeating patterns** at fixed time intervals (like every month or every year).
   * Example: Ice cream sales increase every summer and drop in winter.

3. **Cyclical (C)**
	* It shows **longer-term ups and downs**, but not fixed like seasonal.
   * Example: Business cycles — economy rising and falling every few years.

4. **Irregular/Random (R or I)**
	* These are **unexpected** changes — no pattern, just noise.
   * Example: Sales drop suddenly because of a strike or a power cut.
---

> [!NOTE]
> #### **1. Additive Model**
> 
> **What it means:**
> Each component (trend, season, irregular) is **added** together.
> 
> **Formula:**
> **Y = Trend + Seasonal + Irregular**
> 
> **When to use:**
> When seasonal and irregular changes **stay the same over time**.
> 
> **Example:**
> A bakery sells 500 cakes every month. In December (due to Christmas), they always sell **+100 extra** cakes.
> * Jan: 500
> * Feb: 500
> * Dec: 500 + 100 = **600**
> The extra 100 cakes (seasonal effect) is **constant**, so this is **Additive**.
> #### **2. Multiplicative Model**
> 
> **What it means:**
> Each component is **multiplied** together.
> 
> **Formula:**
> **Y = Trend × Seasonal × Irregular**
> 
> **When to use:**
> When seasonal and irregular changes **increase or decrease with trend** (as percentages).
> 
> **Example:**
> A clothing store sees **30% more sales** in summer.
> If base sales = 1000 → summer = 1000 × 1.3 = **1300**
> If base sales grow to 2000 → summer = 2000 × 1.3 = **2600**
> Here, seasonal effect is **proportional**, so this is **Multiplicative**.
> ##### **Key Difference:**
> 
> | Model Type     | Seasonal Effect  | Example                            |
> | -------------- | ---------------- | ---------------------------------- |
> | Additive       | Fixed amount     | +100 cakes in December every year  |
> | Multiplicative | Percentage-based | 30% more clothes sold every summer |

---
### Q4. When would you choose an additive model over a multiplicative model in time series decomposition? Explain with examples.

##### **Use Additive Model when:**
* The **change** (up or down) is always the **same amount**, no matter how big or small the overall values are.
**Example:**
Every December, a shop sells **100 extra books** for Christmas — always **+100**, not more or less depending on the year.
So, use **Additive** model:
**Sales = Trend + Seasonal + Irregular**
##### **Use Multiplicative Model when:**
* The **change** is a **percentage** of the total — it **grows or shrinks** as the trend grows.
**Example:**
A shop sees a **20% increase** in summer sales every year.
If normal sales are 1000, summer sales = 1200.
If normal sales grow to 2000, summer sales = 2400.
So, use **Multiplicative** model:
**Sales = Trend × Seasonal × Irregular**
##### **In short:**
* **Additive = fixed amount change**
* **Multiplicative = percentage change**

---
### Q5. What is a stationary time series? Distinguish between strict stationarity and weak stationarity.
**Stationary Time Series (Simple Explanation):**

A **stationary time series** is one where the data’s key properties **do not change over time** — specifically:
* **Mean (average)** stays constant
* **Variance (spread of data)** stays constant
* **Covariance** (relationship between values at different times) depends only on the time gap, not the actual time
##### **Types of Stationarity:**
##### **1. Strict Stationarity:**
* The **entire distribution** (not just mean/variance) stays the same over time.
* All statistical properties are unchanged if we shift time.
**Example:** If the data pattern looks the same whether you look at day 1–10 or day 100–110, it is strictly stationary.
##### **2. Weak Stationarity (also called Covariance Stationarity):**
* Only the **mean, variance, and covariance** are constant over time.
* This is more commonly used in practice.
**Example:** A series with constant average sales and similar ups/downs over time is weakly stationary.
##### **Key Differences:**

| Feature           | Strict Stationarity           | Weak Stationarity                   |
| ----------------- | ----------------------------- | ----------------------------------- |
| Based on          | Full distribution             | Mean, variance, and covariance only |
| Strict conditions | Yes                           | Relaxed conditions                  |
| Usage in practice | Rarely checked (hard to test) | Often used in models like ARIMA     |

---
### Q6. Define autocorrelation function (ACF). How does it help in identifying the structure of a time series?
**Definition:**
The **Autocorrelation Function (ACF)** measures the correlation between a time series and its own past (lagged) values over different time intervals (lags). It tells how similar the series is to itself at different time shifts.
##### **Importance of ACF in Time Series Analysis:**

1. **Detects Serial Dependence:**
   ACF helps identify if past values influence future values — useful for forecasting.

2. **Identifies Seasonality and Cycles:**
   Regular peaks in the ACF plot (e.g., at lag 12) indicate seasonal effects (like yearly seasonality in monthly data).

3. **Tests for Stationarity:**
   If ACF dies down quickly, the series is likely stationary; if it decays slowly, the series may be non-stationary.

4. **Helps Choose Model Type:**
   ACF pattern guides the choice of model (e.g., AR, MA, ARIMA). For example, a sharp cutoff in ACF suggests an MA model.

5. **Analyzes Lag Impact:**
   Shows which lags significantly affect the current value, helping to simplify the model
##### **Example:**
If ACF shows high correlation at lag 12 repeatedly, it indicates **seasonal behavior every 12 periods**.

---
### Q7. What is a correlogram? How is it useful in time series analysis?
**Definition:**
A **correlogram** is a **graphical representation of the autocorrelation function (ACF)** of a time series. It shows how correlated the current value is with its past values (lags), plotted against the number of lags.
##### **How it is Useful in Time Series Analysis:**
1. **Detects Serial Correlation:**
   Helps identify if data points are related to previous values.

2. **Checks Stationarity:**
   If autocorrelations drop quickly (cut off), the series may be stationary. If they decay slowly, the series is likely non-stationary.

3. **Identifies Seasonality:**
   Regular repeating spikes at specific lags suggest seasonal patterns.

4. **Model Selection:**
   Helps decide the order of AR (AutoRegressive) or MA (Moving Average) components for ARIMA models.

5. **Visual Diagnostic Tool:**
   Makes it easier to understand autocorrelation behavior instead of reading values from a table.
##### **Example:**
A correlogram showing strong spikes at lag 12, 24, etc., may indicate **yearly seasonality in monthly sales data**.

---

> [!NOTE]
> simple exponential smoothing:  
> a method to forecast when data has no trend or seasonality. it gives more weight to recent values and less to older ones. used when data stays mostly stable over time.
> 
> holt’s double exponential smoothing:  
> an improved version that works when data has a trend. it smooths both the level and the trend to give better forecasts. used when values are steadily increasing or decreasing.
### Q8. Compare simple exponential smoothing and Holt’s double exponential smoothing. When is each method appropriate?
**Comparison: Simple Exponential Smoothing vs. Holt’s Double Exponential Smoothing**

| Feature               | Simple Exponential Smoothing (SES)             | Holt’s Double Exponential Smoothing            |
| --------------------- | ---------------------------------------------- | ---------------------------------------------- |
| **Trend Handling**    | Does **not** handle trend                      | Handles **linear trend**                       |
| **Components Used**   | Only **level**                                 | **Level + Trend**                              |
| **Complexity**        | Simple to apply                                | More complex (uses two smoothing constants)    |
| **Forecast Equation** | Based on weighted average of past values       | Adds a trend term to the forecast              |
| **When to Use**       | For **stationary data** (no trend/seasonality) | For **data with a trend** (but no seasonality) |

##### **When is Each Method Appropriate?**
* **Simple Exponential Smoothing (SES):**
  Use when the data has **no clear trend or seasonality** — e.g., stable monthly demand for a basic item.
* **Holt’s Double Exponential Smoothing:**
  Use when the data shows a **consistent upward or downward trend** — e.g., steadily increasing product sales over time.
##### **Example:**
* **SES:** Daily electricity usage in a factory with stable demand.
* **Holt’s:** Monthly revenue of a growing company.

---
### Q9. Discuss any two exponential smoothing methods to forecast the future data.

##### **1. simple exponential smoothing:**
this method is used when the data has no trend or seasonality. it gives more weight to recent values and less to older ones using a smoothing factor called alpha (α), which lies between 0 and 1.
the formula is:
forecast = α × current actual value + (1 − α) × previous forecast
if α is close to 1, more weight is given to the recent data.
this method is easy to apply and best suited for short-term forecasts where data is steady without much change.
**example:**
forecasting daily demand for bread in a shop where sales are usually around 100 units with small variations.
**advantages:**
* easy to compute
* works well for stable time series
* requires less data
**limitations:**
* does not work if there is trend or seasonality in data
##### **2. holt’s double exponential smoothing:**
this is an extension of simple exponential smoothing and is used when the data has a trend (either upward or downward). it uses two equations — one for the current level and one for the trend.
it uses two smoothing constants:
* alpha (α) for the level
* beta (β) for the trend
the forecast is adjusted by both the current level and the trend value. it is more accurate than simple exponential smoothing when there is a clear trend.
**example:**
forecasting monthly sales of a product that increases by 20 units every month.
**advantages:**
* captures both level and trend
* better accuracy for trending data
* suitable for short to medium-term forecasting
**limitations:**
* does not handle seasonality
* needs careful tuning of α and β values

---

# Unit 3 - Numerical
### Q1. Given a time series Y = [5, 6, 4, 7, 6, 5, 4, 6, 5, 6], compute the mean and variance. Verify if the mean and variance are constant.

To solve this, we will follow these steps:
##### Step 1: Understand the question
You are given a time series:
**Y = \[5, 6, 4, 7, 6, 5, 4, 6, 5, 6]**

We need to:
1. Find the **mean** (average)
2. Find the **variance**
3. Check if they are **constant over time**
##### Step 2: Calculate the Mean

**Mean** is the average of all the values.
**Formula:**
mean = (sum of all values) ÷ (number of values)

Now add all the values:
5 + 6 + 4 + 7 + 6 + 5 + 4 + 6 + 5 + 6 = **54**

Number of values = 10
mean = 54 ÷ 10 = **5.4**
##### Step 3: Calculate the Variance
**Variance** tells us how much the values spread out from the mean.
**Formula:**
variance = sum of (each value − mean)² ÷ number of values
First, subtract the mean (5.4) from each value and square the result:
* (5 − 5.4)² = (−0.4)² = 0.16
* (6 − 5.4)² = (0.6)² = 0.36
* (4 − 5.4)² = (−1.4)² = 1.96
* (7 − 5.4)² = (1.6)² = 2.56
* (6 − 5.4)² = 0.36
* (5 − 5.4)² = 0.16
* (4 − 5.4)² = 1.96
* (6 − 5.4)² = 0.36
* (5 − 5.4)² = 0.16
* (6 − 5.4)² = 0.36

Now add them all:
0.16 + 0.36 + 1.96 + 2.56 + 0.36 + 0.16 + 1.96 + 0.36 + 0.16 + 0.36 = **8.4**
variance = 8.4 ÷ 10 = **0.84**
##### Step 4: Check if Mean and Variance are Constant
* We found the **mean = 5.4** and **variance = 0.84**
* Since we calculated these over the full series and not over changing time windows, they are constant for the full data
If we calculate the mean and variance for different segments (e.g., first 5 values, then next 5) and they are roughly the same, it means the series is **stationary** in mean and variance.
##### Final Answer:
* **Mean = 5.4**
* **Variance = 0.84**
* Both values are constant across the full data, so the series is likely **stationary** in mean and variance.

---
### Q2. For the series Y = [5, 6, 4, 7, 6, 5, 4, 6, 5, 6], compute autocovariance and autocorrelation at lag 1.

To compute **autocovariance** and **autocorrelation at lag 1** for the series
**Y = \[5, 6, 4, 7, 6, 5, 4, 6, 5, 6]**,
we will follow these steps in **easy and clear steps**.
### Step 1: Understand what lag 1 means
Lag 1 means we compare each value with the value **just before it**.
So, we will look at pairs like:
(5,6), (6,4), (4,7), ..., (5,6)
We’ll use the following formulas:
* **Autocovariance at lag 1**:
  γ₁ = (1/n) × Σ \[(Yₜ − Ȳ) × (Yₜ₋₁ − Ȳ)]
* **Autocorrelation at lag 1**:
  ρ₁ = γ₁ / σ²
  where σ² = variance of the series
### Step 2: Compute Mean (Ȳ)
As before,
sum = 5 + 6 + 4 + 7 + 6 + 5 + 4 + 6 + 5 + 6 = 54
n = 10
mean = 54 / 10 = **5.4**
### Step 3: Create lagged pairs

We create pairs of (Yₜ₋₁, Yₜ) for t = 2 to 10:

| t  | Yₜ₋₁ | Yₜ |
| -- | ---- | -- |
| 2  | 5    | 6  |
| 3  | 6    | 4  |
| 4  | 4    | 7  |
| 5  | 7    | 6  |
| 6  | 6    | 5  |
| 7  | 5    | 4  |
| 8  | 4    | 6  |
| 9  | 6    | 5  |
| 10 | 5    | 6  |

We’ll use these to compute the sum of:
(Yₜ − Ȳ) × (Yₜ₋₁ − Ȳ)
### Step 4: Compute Each Term

mean = 5.4
Now compute (Yₜ − 5.4) × (Yₜ₋₁ − 5.4) for each pair:
1. (6−5.4)(5−5.4) = 0.6 × (−0.4) = −0.24
2. (4−5.4)(6−5.4) = (−1.4) × 0.6 = −0.84
3. (7−5.4)(4−5.4) = 1.6 × (−1.4) = −2.24
4. (6−5.4)(7−5.4) = 0.6 × 1.6 = 0.96
5. (5−5.4)(6−5.4) = (−0.4) × 0.6 = −0.24
6. (4−5.4)(5−5.4) = (−1.4) × (−0.4) = 0.56
7. (6−5.4)(4−5.4) = 0.6 × (−1.4) = −0.84
8. (5−5.4)(6−5.4) = (−0.4) × 0.6 = −0.24
9. (6−5.4)(5−5.4) = 0.6 × (−0.4) = −0.24

Now add all the above:
\= −0.24 − 0.84 − 2.24 + 0.96 − 0.24 + 0.56 − 0.84 − 0.24 − 0.24
\= **−3.32**
### Step 5: Autocovariance at Lag 1

n = 10
we used 9 pairs → divide by 9
γ₁ = (−3.32) / 9 = **−0.3689**
### Step 6: Variance (from earlier)

We already calculated:
variance (σ²) = **0.84**
### Step 7: Autocorrelation at Lag 1

ρ₁ = γ₁ / σ² = (−0.3689) / 0.84 ≈ **−0.439**

### Final Answer:

* **Autocovariance at lag 1 = −0.3689**
* **Autocorrelation at lag 1 ≈ −0.439**

> [!NOTE]
> ### what is t here and how we got t 2 to 10 
> explaining from scratch in simple terms:
> 
> you are given a time series:
> **Y = \[5, 6, 4, 7, 6, 5, 4, 6, 5, 6]**
> there are 10 values. we label them like this:
> 
> | position | value (Yₜ) |
> | -------- | ---------- |
> | t = 1    | 5          |
> | t = 2    | 6          |
> | t = 3    | 4          |
> | t = 4    | 7          |
> | t = 5    | 6          |
> | t = 6    | 5          |
> | t = 7    | 4          |
> | t = 8    | 6          |
> | t = 9    | 5          |
> | t = 10   | 6          |
> 
> here **t** just means time step or position in the series.
> ##### what does lag 1 mean?
> 
> lag 1 means we compare each value with the value **just before it**.
> so we will use pairs like:
> 
> * at t = 2: Yₜ = 6 and Yₜ₋₁ = 5
> * at t = 3: Yₜ = 4 and Yₜ₋₁ = 6
> * at t = 4: Yₜ = 7 and Yₜ₋₁ = 4
> * ... and so on
> * last one is at t = 10: Yₜ = 6 and Yₜ₋₁ = 5
> 
> we start from **t = 2** because we need **one value before** to form a pair.
> so total pairs = 9 (from t = 2 to t = 10)
> 
> that's why we say t = 2 to 10 when calculating autocovariance or autocorrelation at lag 1.

---

### Q3. Apply simple exponential smoothing with α = 0.5 to the series Y = [50, 52, 53, 54, 56]. The initial forecast is 50. Provide forecast for t = 6.
we are given:

* series Y = \[50, 52, 53, 54, 56]
* alpha (α) = 0.5
* initial forecast (F₁) = 50
we will apply **simple exponential smoothing** using the formula:
**Fₜ = α × Yₜ₋₁ + (1 − α) × Fₜ₋₁**
goal: find forecast for t = 6 (i.e., forecast next value after 56)
#### step-by-step calculations:

**F₁ = 50 (given)**

**t = 2:**
F₂ = 0.5 × 50 + 0.5 × 50 = 25 + 25 = **50**

**t = 3:**
F₃ = 0.5 × 52 + 0.5 × 50 = 26 + 25 = **51**

**t = 4:**
F₄ = 0.5 × 53 + 0.5 × 51 = 26.5 + 25.5 = **52**

**t = 5:**
F₅ = 0.5 × 54 + 0.5 × 52 = 27 + 26 = **53**

**t = 6 (forecast):**
F₆ = 0.5 × 56 + 0.5 × 53 = 28 + 26.5 = **54.5**
#### final answer:

**forecast for t = 6 is 54.5**

---
### Q4. Using Holt’s double exponential smoothing, compute the forecast for t = 4 given Y = [100, 108, 117], α = 0.6, β = 0.4.

we are given:
* time series Y = \[100, 108, 117]
* smoothing constants: α = 0.6, β = 0.4
* need to forecast for **t = 4** using **holt’s double exponential smoothing**

holt's method uses two equations:
* **level (Lₜ):** Lₜ = α × Yₜ + (1 − α) × (Lₜ₋₁ + Tₜ₋₁)
* **trend (Tₜ):** Tₜ = β × (Lₜ − Lₜ₋₁) + (1 − β) × Tₜ₋₁
* **forecast:** Fₜ₊₁ = Lₜ + Tₜ
#### step 1: initialize (t = 1)
L₁ = Y₁ = 100
T₁ = Y₂ − Y₁ = 108 − 100 = 8
#### step 2: t = 2
Y₂ = 108
L₂ = α × Y₂ + (1 − α) × (L₁ + T₁)
L₂ = 0.6 × 108 + 0.4 × (100 + 8) = 64.8 + 0.4 × 108 = 64.8 + 43.2 = **108**

T₂ = β × (L₂ − L₁) + (1 − β) × T₁
T₂ = 0.4 × (108 − 100) + 0.6 × 8 = 0.4 × 8 + 4.8 = 3.2 + 4.8 = **8**
#### step 3: t = 3
Y₃ = 117
L₃ = 0.6 × 117 + 0.4 × (108 + 8) = 70.2 + 0.4 × 116 = 70.2 + 46.4 = **116.6**
T₃ = 0.4 × (116.6 − 108) + 0.6 × 8 = 0.4 × 8.6 + 4.8 = 3.44 + 4.8 = **8.24**
#### step 4: forecast for t = 4
F₄ = L₃ + T₃ = 116.6 + 8.24 = **124.84**
**final answer: forecast for t = 4 is 124.84**

---
### Q5. Given quarterly data Y = [30, 21, 29, 36, 42, 33, 41, 48], apply additive Holt-Winters method to compute L5, T5, S5 and forecast for t = 9. Use α = 0.5, β = 0.4, γ = 0.3, s = 4.
### Holt-Winters Additive Method Solution
#### Given Data
- Y = [30, 21, 29, 36, 42, 33, 41, 48] (8 quarters of data)
- α = 0.5 (level smoothing parameter)
- β = 0.4 (trend smoothing parameter)  
- γ = 0.3 (seasonal smoothing parameter)
- s = 4 (seasonal period - quarterly data)
- Find: L₅, T₅, S₅ and forecast for t = 9

## Step 1: Initialize Parameters
### Initial Level (L₁)
For additive model, we use the average of first season:
L₁ = (Y₁ + Y₂ + Y₃ + Y₄)/4 = (30 + 21 + 29 + 36)/4 = 116/4 = 29
**Why:** The initial level represents the deseasonalized average of the first complete seasonal cycle.
### Initial Trend (T₁)
T₁ = [(Y₅ + Y₆ + Y₇ + Y₈) - (Y₁ + Y₂ + Y₃ + Y₄)]/(2s)
T₁ = [(42 + 33 + 41 + 48) - (30 + 21 + 29 + 36)]/(2×4)
T₁ = [164 - 116]/8 = 48/8 = 6

**Why:** The initial trend is calculated as the difference between the averages of two consecutive seasons, divided by 2s to get the trend per period.
### Initial Seasonal Indices (S₁, S₂, S₃, S₄)
For additive model: Sᵢ = Yᵢ - L₁
- S₁ = Y₁ - L₁ = 30 - 29 = 1
- S₂ = Y₂ - L₁ = 21 - 29 = -8  
- S₃ = Y₃ - L₁ = 29 - 29 = 0
- S₄ = Y₄ - L₁ = 36 - 29 = 7
**Why:** Initial seasonal indices represent the deviation of each period from the base level in the first season.
## Step 2: Apply Holt-Winters Equations
The three equations for additive model are:
- Level: Lₜ = α(Yₜ - Sₜ₋ₛ) + (1-α)(Lₜ₋₁ + Tₜ₋₁)
- Trend: Tₜ = β(Lₜ - Lₜ₋₁) + (1-β)Tₜ₋₁  
- Seasonal: Sₜ = γ(Yₜ - Lₜ) + (1-γ)Sₜ₋ₛ
### For t = 2:
**Level:** L₂ = α(Y₂ - S₂₋₄) + (1-α)(L₁ + T₁)
Since we don't have S₋₂, we use S₂ = -8
L₂ = 0.5(21 - (-8)) + 0.5(29 + 6) = 0.5(29) + 0.5(35) = 14.5 + 17.5 = 32
**Trend:** T₂ = β(L₂ - L₁) + (1-β)T₁ = 0.4(32 - 29) + 0.6(6) = 0.4(3) + 3.6 = 4.8
**Seasonal:** S₂ = γ(Y₂ - L₂) + (1-γ)S₂ = 0.3(21 - 32) + 0.7(-8) = 0.3(-11) + (-5.6) = -8.9
### For t = 3:
**Level:** L₃ = 0.5(29 - 0) + 0.5(32 + 4.8) = 14.5 + 18.4 = 32.9
**Trend:** T₃ = 0.4(32.9 - 32) + 0.6(4.8) = 0.36 + 2.88 = 3.24
**Seasonal:** S₃ = 0.3(29 - 32.9) + 0.7(0) = 0.3(-3.9) = -1.17
### For t = 4:
**Level:** L₄ = 0.5(36 - 7) + 0.5(32.9 + 3.24) = 14.5 + 18.07 = 32.57
**Trend:** T₄ = 0.4(32.57 - 32.9) + 0.6(3.24) = -0.132 + 1.944 = 1.812
**Seasonal:** S₄ = 0.3(36 - 32.57) + 0.7(7) = 1.029 + 4.9 = 5.929
### For t = 5:
**Level:** L₅ = 0.5(42 - 1) + 0.5(32.57 + 1.812) = 20.5 + 17.191 = 37.691
**Trend:** T₅ = 0.4(37.691 - 32.57) + 0.6(1.812) = 2.0484 + 1.0872 = 3.1356
**Seasonal:** S₅ = 0.3(42 - 37.691) + 0.7(1) = 1.2927 + 0.7 = 1.9927
### Step 3: Results for t = 5
- **L₅ = 37.691** (Level at period 5)
- **T₅ = 3.136** (Trend at period 5)  
- **S₅ = 1.993** (Seasonal index at period 5)
### Step 4: Forecast for t = 9
For additive Holt-Winters, the forecast equation is:
Ŷₜ₊ₕ = Lₜ + h×Tₜ + Sₜ₊ₜ₋ₛ
Where:
- t = 8 (last observed period)
- h = 1 (one period ahead forecast)
- We need L₈, T₈, and S₉₋₄ = S₅
First, let's continue calculations to find L₈ and T₈:
### For t = 6:
L₆ = 0.5(33 - (-8.9)) + 0.5(37.691 + 3.136) = 20.95 + 20.4135 = 41.3635
T₆ = 0.4(41.3635 - 37.691) + 0.6(3.136) = 1.469 + 1.8816 = 3.3506
### For t = 7:
L₇ = 0.5(41 - (-1.17)) + 0.5(41.3635 + 3.3506) = 21.085 + 22.357 = 43.442
T₇ = 0.4(43.442 - 41.3635) + 0.6(3.3506) = 0.8314 + 2.0104 = 2.8418
### For t = 8:
L₈ = 0.5(48 - 5.929) + 0.5(43.442 + 2.8418) = 21.0355 + 23.142 = 44.1775
T₈ = 0.4(44.1775 - 43.442) + 0.6(2.8418) = 0.294 + 1.7051 = 1.9991
### Forecast for t = 9:
Ŷ₉ = L₈ + 1×T₈ + S₅
Ŷ₉ = 44.1775 + 1.9991 + 1.993 = **48.17**
### Final Answer
- L₅ = 37.69
- T₅ = 3.14  
- S₅ = 1.99
- Forecast for t = 9: **48.17**

---

### Q6. Apply Brown’s discounted regression (double exponential smoothing) with α = 0.5 to Y = [50, 52, 53, 54]. Compute level, trend, and forecast for t = 5.

 **Problem:**
Apply **Brown’s double exponential smoothing (a.k.a. discounted regression)**
Given:
* Time series: **Y = \[50, 52, 53, 54]**
* Smoothing constant: **α = 0.5**
* Goal: Compute **Level**, **Trend**, and **Forecast** for **t = 5**

#### Step 1: What is Brown’s Double Exponential Smoothing?
This method is used when the **time series has a trend**, but **no seasonality**.
It smooths the data twice to estimate:
* The **Level** (baseline value)
* The **Trend** (upward/downward direction)
* Then uses both to **forecast future values**
We use two smoothed series:
* **S₁(t)** = single exponential smoothing
* **S₂(t)** = double exponential smoothing

#### Step 2: Formulas Used
These are the core formulas:
1. **S₁(t) = α × Yₜ + (1 − α) × S₁(t−1)**
   → smooths the raw data once
2. **S₂(t) = α × S₁(t) + (1 − α) × S₂(t−1)**
   → smooths the smoothed data (S₁) again
3. **Level (aₜ) = 2 × S₁(t) − S₂(t)**
   → estimates current value based on double smoothing
4. **Trend (bₜ) = (α / (1 − α)) × (S₁(t) − S₂(t))**
   → measures the slope of the data (rate of change)
5. **Forecast (Fₜ₊ₕ) = aₜ + bₜ × h**
   → future forecast h steps ahead

#### Step 3: Initialization (Why?)
At t = 1, we need starting values.
We start by setting:
* S₁(1) = Y₁ = **50**
* S₂(1) = Y₁ = **50**
  This is standard for Brown’s method (use first value as base).
#### Step 4: Apply the Smoothing Equations (Why?)
Now apply formulas from t = 2 to t = 4 to calculate S₁ and S₂.
#### At t = 2 (Y₂ = 52):
**S₁(2)** = 0.5 × 52 + 0.5 × 50 = **51**
**→ Why?** Smooth the actual value (52) with the previous smoothed value (50)

**S₂(2)** = 0.5 × 51 + 0.5 × 50 = **50.5**
**→ Why?** Smooth S₁(2) using S₂(1)
#### At t = 3 (Y₃ = 53):
**S₁(3)** = 0.5 × 53 + 0.5 × 51 = **52**
**S₂(3)** = 0.5 × 52 + 0.5 × 50.5 = **51.25**
#### At t = 4 (Y₄ = 54):
**S₁(4)** = 0.5 × 54 + 0.5 × 52 = **53**
**S₂(4)** = 0.5 × 53 + 0.5 × 51.25 = **52.125**

#### Step 5: Calculate Level and Trend at t = 4 (Why?)
Now that we’ve smoothed the data, we estimate:
#### **Level (a₄):**
a₄ = 2 × S₁(4) − S₂(4) = 2 × 53 − 52.125 = **53.875**
**→ Why?** This estimates the base value by adjusting for double smoothing.

#### **Trend (b₄):**
b₄ = (α / (1 − α)) × (S₁(4) − S₂(4))
\= (0.5 / 0.5) × (53 − 52.125) = 1 × 0.875 = **0.875**
**→ Why?** Measures how much the series is rising each step.
### Step 6: Forecast for t = 5 (Why?)
We use:
**F₅ = a₄ + b₄ × 1 = 53.875 + 0.875 = 54.75**
**→ Why?** We're projecting one time step into the future using the current level + one unit of the trend.
#### Final Answer:
* **Level at t = 4 = 53.875**
* **Trend at t = 4 = 0.875**
* **Forecast for t = 5 = 54.75**
---
### Q7. Given AR(1) model Yt = 0.8Yt−1 + ϵt , with Y0 = 10 and ϵt = [0.5, −0.3, 1.0, −0.2, 0.1], compute Y1 to Y5.

### AR(1) Model Step-by-Step Solution
### Given Information
- **AR(1) Model:** Yₜ = 0.8Yₜ₋₁ + εₜ
- **Initial Value:** Y₀ = 10
- **Error Terms:** εₜ = [0.5, -0.3, 1.0, -0.2, 0.1] for t = 1, 2, 3, 4, 5
- **Task:** Compute Y₁ to Y₅
### Understanding the AR(1) Model
### What is AR(1)?
**AR(1)** stands for **Autoregressive model of order 1**, which means:
- **Auto**: The variable depends on itself
- **Regressive**: It's a regression on past values
- **Order 1**: It depends on only 1 previous time period
### Model Components Explained:
- **Yₜ**: Current value we want to find
- **0.8**: Autoregressive coefficient (φ₁) - shows how much current value depends on previous value
- **Yₜ₋₁**: Previous period's value
- **εₜ**: Random error/shock term for current period
### Why This Formula Works:
The equation Yₜ = 0.8Yₜ₋₁ + εₜ tells us:
1. **80% of current value** comes from the previous value (0.8Yₜ₋₁)
2. **20% is new information** from the error term (εₜ)
3. Since 0.8 < 1, the series will gradually return to zero if no shocks occur
## Step-by-Step Calculations
### Step 1: Calculate Y₁
**Given:** Y₀ = 10, ε₁ = 0.5
**Formula:** Y₁ = 0.8Y₀ + ε₁ **Calculation:** Y₁ = 0.8 × 10 + 0.5 = 8.0 + 0.5 = **8.5**
**Why this step:** We start with the initial condition Y₀ = 10 and apply the AR(1) formula to get the first forecasted value. The 0.8 coefficient means we take 80% of the previous value, then add the random shock.
### Step 2: Calculate Y₂
**Given:** Y₁ = 8.5, ε₂ = -0.3
**Formula:** Y₂ = 0.8Y₁ + ε₂ **Calculation:** Y₂ = 0.8 × 8.5 + (-0.3) = 6.8 - 0.3 = **6.5**
**Why this step:** Now Y₁ becomes our "previous value" and we apply the same logic. The negative error term (-0.3) pushes the value down from what it would have been with just the autoregressive component.
### Step 3: Calculate Y₃
**Given:** Y₂ = 6.5, ε₃ = 1.0
**Formula:** Y₃ = 0.8Y₂ + ε₃ **Calculation:** Y₃ = 0.8 × 6.5 + 1.0 = 5.2 + 1.0 = **6.2**
**Why this step:** The positive shock (1.0) is relatively large, boosting the value significantly above what the autoregressive component alone would give us (5.2).
### Step 4: Calculate Y₄
**Given:** Y₃ = 6.2, ε₄ = -0.2
**Formula:** Y₄ = 0.8Y₃ + ε₄ **Calculation:** Y₄ = 0.8 × 6.2 + (-0.2) = 4.96 - 0.2 = **4.76**
**Why this step:** The negative shock (-0.2) pulls the value down slightly from the autoregressive component (4.96).

### Step 5: Calculate Y₅
**Given:** Y₄ = 4.76, ε₅ = 0.1
**Formula:** Y₅ = 0.8Y₄ + ε₅ **Calculation:** Y₅ = 0.8 × 4.76 + 0.1 = 3.808 + 0.1 = **3.908**
**Why this step:** The small positive shock (0.1) slightly increases the value from the autoregressive component.
#### Summary of Results

|Time (t)|Previous Value (Yₑ₋₁)|Error (εₜ)|AR Component (0.8Yₜ₋₁)|Final Value (Yₜ)|
|---|---|---|---|---|
|1|10.000|0.5|8.000|**8.500**|
|2|8.500|-0.3|6.800|**6.500**|
|3|6.500|1.0|5.200|**6.200**|
|4|6.200|-0.2|4.960|**4.760**|
|5|4.760|0.1|3.808|**3.908**|

#### Key Observations
#### Pattern Analysis:
1. **Mean Reversion**: Without error terms, the series would decay toward 0 (since 0.8 < 1)
2. **Shock Impact**: Error terms create deviations from the smooth decay pattern
3. **Persistence**: Each value still carries 80% of the previous period's influence

#### Why AR(1) is Useful:
- **Economic Modeling**: Many economic variables (GDP, inflation) show persistence
- **Financial Analysis**: Stock prices, interest rates often follow AR patterns
- **Forecasting**: Provides a simple way to model time-dependent data
- **Stationarity**: When |φ₁| < 1 (like our 0.8), the series is stationary

#### Final Answer:
- **Y₁ = 8.5**
- **Y₂ = 6.5**
- **Y₃ = 6.2**
- **Y₄ = 4.76**
- **Y₅ = 3.908**

---

