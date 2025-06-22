---
{"dg-publish":true,"permalink":"/MSC DataScience/SEM 2/Time Series/Unit 4 PYQ/","tags":["msc","pyq","qb","DataScience","time-series"],"created":"2025-06-20T01:06:12.263+05:30"}
---


### 1. Define deseasonalization. Why is it an important step in time series analysis?
Deseasonalization is the process of removing seasonal patterns or fluctuations from a time series data to reveal the underlying trend and cyclical components. It involves adjusting the data to eliminate predictable, recurring variations that occur at specific intervals such as monthly, quarterly, or annually.

The main methods of deseasonalization include seasonal decomposition where we separate additive or multiplicative seasonal components, moving averages using centered moving averages to smooth seasonal variations, seasonal indices by calculating and removing seasonal factors, and advanced statistical methods like X-12-ARIMA used by government agencies.

Deseasonalization is important in time series analysis for several key reasons. First, it reveals true underlying trends because seasonal patterns can mask the actual long-term direction of the data. This helps identify whether a series is genuinely increasing, decreasing, or stable, which is essential for understanding the fundamental behavior of the variable.

Second, it improves forecasting accuracy since seasonal patterns are predictable and can be modeled separately. Deseasonalized data is easier to forecast using trend-based methods and reduces forecast errors by isolating irregular components.

Third, it enables better comparative analysis by allowing meaningful comparison between different time periods. Month-to-month or quarter-to-quarter comparisons become more reliable as it eliminates distortions caused by seasonal effects.

Fourth, it facilitates economic analysis because economic indicators often contain strong seasonal components. Policy makers need to distinguish between seasonal variations and structural changes, and deseasonalization helps in identifying business cycles and economic turning points.

Fifth, it improves model performance since many time series models assume stationarity, but seasonal patterns violate these stationarity assumptions. Deseasonalization makes data more suitable for ARIMA and other statistical models.

Finally, it supports better decision making as businesses can better understand their performance trends, distinguish between seasonal fluctuations and actual performance issues, and make more informed strategic planning decisions.

Practical applications include retail sales analysis where Christmas shopping effects are removed, tourism data where vacation seasons are adjusted for, employment statistics where seasonal hiring patterns are eliminated, and energy consumption data where heating and cooling seasonal demand is removed.

In conclusion, deseasonalization is crucial because it transforms raw seasonal data into a cleaner form that reveals true patterns, improves analytical accuracy, and enables better forecasting and decision-making across various fields of study and industry applications.

---
### 2. Explain the principle of harmonic analysis for estimating the seasonal or cyclic component in a time series.

Harmonic analysis is a mathematical technique used to decompose a time series into its constituent periodic components using sinusoidal functions. The principle is based on the idea that any periodic pattern in time series data can be represented as a sum of sine and cosine waves with different frequencies, amplitudes, and phases.

The fundamental principle relies on Fourier's theorem, which states that any periodic function can be expressed as an infinite series of harmonic terms. In time series analysis, we assume that the seasonal or cyclic component can be written as a combination of sinusoidal functions of the form: a cos(2πft + φ) where 'a' is the amplitude, 'f' is the frequency, 't' is time, and 'φ' is the phase angle.

The harmonic analysis process involves several steps. First, we identify the dominant frequencies in the data using techniques like periodogram analysis or spectral density estimation. Then we estimate the amplitudes and phases of the significant harmonic components using methods such as least squares regression. Finally, we reconstruct the seasonal component by summing all significant harmonic terms.

The advantages of harmonic analysis include its ability to handle multiple seasonal patterns simultaneously, such as both monthly and quarterly cycles in economic data. It provides a smooth representation of seasonal patterns and can capture complex seasonal variations that simple seasonal indices might miss. The method is particularly useful when seasonal patterns are not perfectly regular or when there are multiple overlapping cycles.

Applications include analyzing economic time series with multiple seasonal patterns, studying tidal data with multiple harmonic components, examining biological rhythms with circadian and other cycles, and analyzing sales data with both weekly and seasonal patterns. The technique is especially valuable in fields like oceanography, meteorology, and economics where natural phenomena exhibit multiple periodic components.

---
### 3. Differentiate between Moving Average (MA) and Autoregressive (AR) processes. Give examples.

Moving Average and Autoregressive processes are two fundamental building blocks of time series modeling, but they operate on different principles and capture different types of temporal dependencies.

An Autoregressive process of order p, denoted AR(p), models the current value as a linear combination of its own past values plus a random error term. The general form is: Yt = φ1_Yt-1 + φ2_Yt-2 + ... + φp*Yt-p + εt. The key characteristic is that current values depend directly on previous values of the same series, creating a memory effect where past observations influence future ones.

A Moving Average process of order q, denoted MA(q), models the current value as a linear combination of current and past error terms. The general form is: Yt = εt + θ1_εt-1 + θ2_εt-2 + ... + θq*εt-q. Here, the current value depends on current and past random shocks rather than past values of the series itself.

The main differences lie in their memory properties. AR processes have infinite memory, meaning the effect of a shock persists indefinitely but decays over time. MA processes have finite memory, where shocks only affect the series for a limited number of periods. AR processes show gradual decay in their autocorrelation function, while MA processes show abrupt cutoff after q lags.

Examples of AR processes include stock prices where today's price is influenced by recent prices, GDP growth where current growth depends on past economic performance, and interest rates where current rates are influenced by recent rate levels. A simple AR(1) example would be: Yt = 0.8*Yt-1 + εt, where 80% of today's value comes from yesterday's value.

Examples of MA processes include measurement errors in scientific instruments where current error depends on recent calibration issues, inventory adjustments where current stock changes depend on recent demand shocks, and short-term market reactions where current price movements depend on recent news events. A simple MA(1) example would be: Yt = εt + 0.5*εt-1, where today's value includes both current and previous period's random effects.

In practice, many real-world time series exhibit both AR and MA characteristics, leading to ARMA models that combine both processes to capture the full complexity of temporal dependencies in the data.

---
### 4. Write short notes on the significance of Fourier series in harmonic analysis for time series.

Fourier series plays a fundamental role in harmonic analysis for time series by providing the mathematical foundation for decomposing complex periodic patterns into simpler sinusoidal components. The significance lies in its ability to transform time domain data into frequency domain representation, revealing hidden periodic structures.

The mathematical basis of Fourier series states that any periodic function with period T can be expressed as an infinite sum of sine and cosine functions with frequencies that are integer multiples of the fundamental frequency 1/T. For time series analysis, this means: f(t) = a0/2 + Σ[an_cos(2πnt/T) + bn_sin(2πnt/T)] where the coefficients an and bn represent the contribution of each harmonic component.

The key significance in time series analysis includes frequency domain analysis, where Fourier series converts time series data from time domain to frequency domain, making it easier to identify dominant cycles and periodic patterns. It enables spectral analysis by providing the foundation for power spectral density estimation, helping analysts understand which frequencies contribute most to the series variance.

Fourier series is crucial for seasonal decomposition as it allows for sophisticated seasonal pattern modeling that can capture multiple overlapping seasonal cycles simultaneously. Unlike simple seasonal indices, Fourier analysis can handle complex seasonal patterns that may not repeat exactly from period to period.

The practical applications are extensive. In economics, Fourier analysis helps identify business cycles, seasonal patterns in sales data, and cyclical components in macroeconomic indicators. In engineering, it's used for signal processing, vibration analysis, and quality control monitoring. In natural sciences, it helps analyze tidal patterns, climate cycles, and biological rhythms.

The advantages include its ability to handle non-stationary seasonal patterns, capability to model multiple seasonal frequencies simultaneously, provision of smooth seasonal estimates, and strong theoretical foundation based on well-established mathematical principles. It also allows for easy reconstruction of the original series from its harmonic components.

Modern computational tools have made Fourier analysis more accessible through Fast Fourier Transform algorithms, enabling real-time analysis of large datasets. This has expanded its application to areas like financial market analysis, where traders use harmonic analysis to identify market cycles and predict price movements.

The significance extends to providing a bridge between time series analysis and signal processing techniques, enabling cross-disciplinary applications and methodological advances that benefit both fields of study.

---
### 5. Discuss the assumptions and interpretation of the Autoregressive process of order 1 (AR(1)).

The AR(1) process is a simple time series model where today's value depends on yesterday's value plus a random error. The general form is Yt = φ*Yt-1 + εt, where φ is the autoregressive parameter and εt is the error term.

The main assumptions of AR(1) include that the error terms are independent and identically distributed with zero mean and constant variance. This means each error is random and unrelated to previous errors. The errors follow a normal distribution, which helps with statistical inference and prediction intervals.

Another key assumption is stationarity, which requires that the absolute value of φ is less than 1. When this condition is met, the series has a constant mean and variance over time, and the effect of past shocks gradually fades away. If φ equals 1, the series becomes a random walk, which is non-stationary.

The parameter φ determines the behavior of the series. When φ is positive and close to 1, the series shows strong persistence, meaning high values tend to be followed by high values. When φ is negative, the series alternates between high and low values. When φ is close to zero, the series behaves more like random noise.

The interpretation of AR(1) is straightforward. If φ equals 0.8, it means that 80% of today's value comes from yesterday's value, and 20% is new random information. This creates a memory effect where past values influence current values, but this influence decreases over time.

AR(1) processes are commonly found in economics and finance. Stock prices often follow AR(1) patterns because today's price is heavily influenced by yesterday's price. Economic indicators like GDP growth and inflation also show AR(1) behavior due to economic momentum and persistence.

The model is useful for forecasting because it captures the tendency of time series to continue their recent patterns. However, it assumes that the relationship between consecutive observations remains constant over time, which may not always hold in practice.

---
### 6. Explain how the Yule-Walker equations are used to estimate parameters in AR models.

The Yule-Walker equations provide a method to estimate parameters in autoregressive models by using the relationship between the model parameters and the autocorrelations of the time series. These equations connect the theoretical properties of AR models with the observed data patterns.

For an AR(1) model, the Yule-Walker equation is simple: ρ1 = φ, where ρ1 is the first-order autocorrelation coefficient and φ is the AR parameter. This means the AR parameter equals the correlation between consecutive observations in the series.

For higher-order AR models, the equations become more complex. For an AR(2) model with parameters φ1 and φ2, we have two equations: ρ1 = φ1 + φ2_ρ1 and ρ2 = φ1_ρ1 + φ2. These equations can be solved simultaneously to find the parameter values.

The estimation process involves several steps. First, calculate the sample autocorrelations from the observed time series data. Then, set up the Yule-Walker equations using these sample autocorrelations. Finally, solve the system of equations to obtain estimates of the AR parameters.

The method of moments approach uses the Yule-Walker equations directly. We replace the theoretical autocorrelations with sample autocorrelations and solve for the parameters. This gives us the Yule-Walker estimators, which are consistent and asymptotically normal under standard conditions.

The advantages of Yule-Walker estimation include its computational simplicity and the fact that it always produces stationary parameter estimates. The estimated parameters automatically satisfy the stationarity conditions, which is not guaranteed by other estimation methods.

However, the method has some limitations. It can be less efficient than maximum likelihood estimation, especially for small samples. It also assumes that the true model order is known, and the estimates can be sensitive to the choice of sample autocorrelations used in the equations.

The Yule-Walker equations are particularly useful for initial parameter estimation and model identification in AR processes. They provide a quick way to get reasonable parameter estimates that can serve as starting values for more sophisticated estimation procedures.

---
### 7. State the general form of a Moving Average process of order q (MA(q)) and explain its properties.

The general form of a Moving Average process of order q, denoted MA(q), is: Yt = εt + θ1_εt-1 + θ2_εt-2 + ... + θq*εt-q, where εt are independent error terms with zero mean and constant variance, and θ1, θ2, ..., θq are the moving average parameters.

This equation shows that the current value depends on the current error term and the past q error terms. Unlike autoregressive models, MA models do not depend on past values of the series itself, but only on past random shocks or innovations.

The first important property of MA(q) processes is that they have finite memory. The effect of any shock completely disappears after q periods. This means that an unusual event will influence the series for only a limited time, after which its impact vanishes completely.

MA processes are always stationary regardless of the parameter values. This is because they are linear combinations of stationary error terms, so the resulting series automatically has constant mean and variance. This property makes MA models easier to work with compared to AR models, which require parameter restrictions for stationarity.

The mean of an MA(q) process is zero if the error terms have zero mean. The variance depends on the error variance and the MA parameters. For MA(1), the variance is σ²(1 + θ1²), where σ² is the error variance.

The autocorrelation function of MA(q) has a distinctive pattern. It is non-zero for lags 1 through q, and exactly zero for all lags greater than q. This creates a sharp cutoff pattern that helps identify the order of the MA process. For example, MA(1) has non-zero autocorrelation only at lag 1.

MA processes exhibit invertibility conditions similar to stationarity in AR models. For the process to be invertible, the parameters must satisfy certain restrictions. Invertibility ensures that the MA process can be written as an infinite AR process, which is useful for forecasting and analysis.

Common examples of MA behavior include measurement errors that persist for a few periods, inventory adjustments that affect production for several quarters, and market reactions to news that last for a limited time. Weather patterns also sometimes follow MA processes where current conditions depend on recent disturbances.

The practical advantage of MA models is their ability to capture short-term dependencies and temporary shocks in time series data. They are particularly useful when the underlying process is driven by external events or interventions that have temporary but predictable effects on the series.

---
### Q8. What is meant by the cyclic component in a time series? How does it differ from the seasonal component?

The **cyclic component** in a time series refers to the long-term fluctuation or wave-like movement in data that occurs over a period longer than one year. These cycles are usually caused by economic, political, or social conditions, such as a business boom or recession. The duration of cycles is not fixed—they can last for several years and vary in intensity and length. The key feature of a cyclic pattern is that it does not follow a strict, regular time interval, but it still shows a clear upward and downward movement over time.

The **seasonal component**, on the other hand, consists of patterns that repeat at regular, fixed intervals within a year. These patterns are caused by seasonal factors like weather changes, holidays, festivals, or school terms. For example, sales of air conditioners increase during summer every year, and this pattern repeats annually.

**Key Differences:**
- **Time Interval**: Seasonal effects occur at fixed, known intervals (like monthly or quarterly), while cyclic effects occur over irregular and longer intervals (often years).
- **Cause**: Seasonal variations are due to environmental or calendar-related factors; cyclic variations are caused by economic and business cycles.
- **Regularity**: Seasonal components are regular and predictable; cyclic components are irregular and often unpredictable in timing and length.
- **Duration**: Seasonal components are short-term (within a year); cyclic components are long-term (over years).
In summary, while both involve repetitive patterns, seasonal components are consistent and predictable due to fixed time causes, whereas cyclic components are more variable and reflect broad economic changes over time.

---
### Q9. Outline the steps for applying harmonic analysis to a monthly time series.
Here are the steps for applying **harmonic analysis** to a **monthly time series**, explained simply:

1. **Collect and organize the data**
   * Use monthly data over several years.
   * Make sure the time series is complete (no missing months).

2. **Remove trend**
   * Detrend the data to isolate the seasonal/cyclic part.
   * Use differencing or fit a trend line and subtract it.
   
2. **Deseasonalize if needed**
   * If focusing only on cyclic components, seasonal patterns may be removed first.

3. **Apply Fourier series (harmonic model)**
   * Fit a Fourier series: a combination of sine and cosine functions.
   * Example:
     Yₜ = a₀ + Σ \[aₙ cos(2πnt/T) + bₙ sin(2πnt/T)]
     where T = 12 for monthly data (12 months in a year), n = 1, 2,...

5. **Estimate coefficients (a₀, aₙ, bₙ)**
   * Use least squares or other fitting methods to find the best values for these coefficients.

5. **Reconstruct the time series**
   * Combine the fitted sine and cosine terms to model the cyclic pattern in the data.

5. **Interpret results**
   * Identify dominant cycles (like yearly, semi-annual) by checking which harmonics have the largest amplitude.
   * Higher amplitude = stronger influence on the time series.

5. **Validate model**
   * Check how well the harmonic model fits the actual data using residuals and error metrics.

This method helps find and understand **cyclical** or **seasonal** behaviors hidden within time series data using mathematical wave functions.

---
### 10. Explain how lag autocorrelations help identify the order of an AR process
**Lag autocorrelations** (ACF – Autocorrelation Function) help identify the order of an **Autoregressive (AR)** process by showing how current values relate to past values.

In an **AR(p)** process (where *p* is the order), the key idea is:
* The **partial autocorrelation** cuts off after lag *p*.
* The **autocorrelations** (ACF) gradually decrease or tail off after lag 1.

**Steps:**
1. **Plot the ACF and PACF**:
   * ACF shows correlations at different lags.
   * PACF shows the correlation of Yₜ with Yₜ₋ₖ after removing effects of intermediate lags.

1. **Check PACF pattern**:
   * If PACF cuts off sharply after lag *p*, that suggests AR(p).
   * Example: If PACF is significant only at lag 1 and near zero afterward → likely AR(1).

1. **Check ACF pattern**:
   * In AR processes, ACF decreases gradually (tailing off), not cutting off suddenly.
**Conclusion:**
The **order p** of an AR process is identified by the **last significant lag** in the **PACF** plot. A sharp cutoff in PACF and a slow decline in ACF indicates an AR process.

---

# Numerical

### Q1. 1. Given lag-1 autocorrelation ρ1 = 0.6 and lag-2 autocorrelation ρ2 = 0.7, estimate the AR(1) parameter ϕ1 and AR(2) parameters ϕ1 and ϕ2.

Sure, here’s a detailed and clear explanation of what we did and **why** we did it:

We are given:

* **Lag-1 autocorrelation (ρ₁)** = 0.6
* **Lag-2 autocorrelation (ρ₂)** = 0.7

We want to estimate the parameters for:

* An **AR(1)** model: only one parameter → **ϕ₁**
* An **AR(2)** model: two parameters → **ϕ₁ and ϕ₂**

### Step 1: AR(1) model

**AR(1) equation:**
Yₜ = ϕ₁Yₜ₋₁ + εₜ

This model only uses one previous value (lag-1) to predict the current value.
In AR(1), the **only** autocorrelation used is lag-1 (ρ₁), and it is directly equal to ϕ₁.

So, we directly say:
**ϕ₁ = ρ₁ = 0.6**

**Why?**
Because for AR(1), the formula assumes the lag-1 autocorrelation is the same as the coefficient ϕ₁.

### Step 2: AR(2) model

**AR(2) equation:**
Yₜ = ϕ₁Yₜ₋₁ + ϕ₂Yₜ₋₂ + εₜ

This model uses **two past values** (lags 1 and 2) to predict the current value.
To find ϕ₁ and ϕ₂, we use **Yule-Walker equations**. These equations relate autocorrelations to AR parameters.

#### Yule-Walker equations for AR(2):

These equations are derived from the statistical properties of the time series. For AR(2), they are:

1. ρ₁ = ϕ₁ + ϕ₂ \* ρ₁
2. ρ₂ = ϕ₁ \* ρ₁ + ϕ₂

We plug in the given values:
Equation 1:
0.6 = ϕ₁ + ϕ₂ \* 0.6

Equation 2:
0.7 = ϕ₁ \* 0.6 + ϕ₂

Now we solve these two equations to find ϕ₁ and ϕ₂.

### Solving step-by-step:

From equation 1:
ϕ₁ = 0.6 - 0.6ϕ₂ → (we isolate ϕ₁)

Now plug this into equation 2:
0.7 = (0.6 - 0.6ϕ₂) \* 0.6 + ϕ₂
→ 0.7 = 0.36 - 0.36ϕ₂ + ϕ₂
→ 0.7 = 0.36 + 0.64ϕ₂
→ 0.34 = 0.64ϕ₂
→ ϕ₂ ≈ 0.531

Now go back and find ϕ₁:
ϕ₁ = 0.6 - 0.6 \* 0.531 ≈ 0.281

### Final Results:

AR(1):
ϕ₁ = 0.6

AR(2):
ϕ₁ ≈ 0.281
ϕ₂ ≈ 0.531

### Summary (what and why):

* We used **Yule-Walker equations** because they are standard formulas for estimating AR model parameters based on autocorrelations.
* For AR(1), it’s direct: parameter equals lag-1 autocorrelation.
* For AR(2), we used two equations and solved them algebraically to get both parameters.
* This helps us build AR models that best fit the observed autocorrelation in the time series.

---

### Q2. 2. Given lag-1 autocorrelation ρ1 = 0.9 and lag-2 autocorrelation ρ2 = 0.7, estimate the AR(2) parameters ϕ1 and ϕ2.

We are given:
* ρ₁ = 0.9 (lag-1 autocorrelation)
* ρ₂ = 0.7 (lag-2 autocorrelation)

We want to estimate parameters ϕ₁ and ϕ₂ of an **AR(2)** process using **Yule-Walker equations**.
### Step 1: Write Yule-Walker equations

These equations relate autocorrelations to AR(2) parameters:
1. ρ₁ = ϕ₁ + ϕ₂ \* ρ₁
2. ρ₂ = ϕ₁ \* ρ₁ + ϕ₂

Substitute given values:
1. 0.9 = ϕ₁ + ϕ₂ \* 0.9
2. 0.7 = ϕ₁ \* 0.9 + ϕ₂
### Step 2: Solve the equations

From equation 1:
ϕ₁ = 0.9 - 0.9ϕ₂  → (i)

Substitute (i) into equation 2:
0.7 = (0.9 - 0.9ϕ₂)\*0.9 + ϕ₂
0.7 = 0.81 - 0.81ϕ₂ + ϕ₂
0.7 = 0.81 + 0.19ϕ₂
0.7 - 0.81 = 0.19ϕ₂
-0.11 = 0.19ϕ₂
ϕ₂ ≈ -0.5789

Now plug into (i):
ϕ₁ = 0.9 - 0.9\*(-0.5789)
ϕ₁ = 0.9 + 0.521 ≈ 1.421
### Final Answer:
ϕ₁ ≈ 1.421
ϕ₂ ≈ -0.579

---
### Q3. The autocorrelations of a stationary process are: ρ1 = 0.5, ρ2 = 0.2. Estimate the AR(2) parameters using Yule-Walker equations

We are given:

* ρ₁ = 0.5 (lag-1 autocorrelation)
* ρ₂ = 0.2 (lag-2 autocorrelation)

We are asked to estimate **AR(2)** parameters: **ϕ₁ and ϕ₂** using **Yule-Walker equations**.
### Step 1: Why use Yule-Walker?

In an AR(2) model:

Yₜ = ϕ₁Yₜ₋₁ + ϕ₂Yₜ₋₂ + εₜ

The Yule-Walker equations are used to link autocorrelations (ρ) to AR coefficients (ϕ) for stationary processes.

They help estimate AR parameters from autocorrelation values when the actual data points are not given.
### Step 2: Write Yule-Walker equations for AR(2)

For AR(2), the standard Yule-Walker equations are:

1. ρ₁ = ϕ₁ + ϕ₂ \* ρ₁
2. ρ₂ = ϕ₁ \* ρ₁ + ϕ₂

We substitute the given values:

Equation 1:
0.5 = ϕ₁ + ϕ₂ \* 0.5  → (i)

Equation 2:
0.2 = ϕ₁ \* 0.5 + ϕ₂  → (ii)

### Step 3: Solve the equations

**From (i):**
ϕ₁ = 0.5 - 0.5ϕ₂ → (iii)

Now plug (iii) into (ii):

0.2 = (0.5 - 0.5ϕ₂)\*0.5 + ϕ₂
0.2 = 0.25 - 0.25ϕ₂ + ϕ₂
0.2 = 0.25 + 0.75ϕ₂
0.2 - 0.25 = 0.75ϕ₂
-0.05 = 0.75ϕ₂
ϕ₂ = -0.0667

Now use (iii) to get ϕ₁:

ϕ₁ = 0.5 - 0.5 \* (-0.0667)
ϕ₁ = 0.5 + 0.0333
ϕ₁ ≈ 0.5333
### Final Answer:

ϕ₁ ≈ 0.533
ϕ₂ ≈ -0.067
### Summary of what and why:

* Used **Yule-Walker equations** to estimate AR(2) parameters from autocorrelations.
* These equations relate lagged correlations (ρ₁, ρ₂) to the unknown AR coefficients (ϕ₁, ϕ₂).
* Solved a system of two linear equations by substitution to find the values.
* This helps define the AR(2) model that best fits the correlation structure of the data.

---
### Q 4. For the AR(1) process: Xt = 0.6Xt−1 + ϵt , compute the autocorrelation function up to lag 2.

We are given an **AR(1)** process:
**Xₜ = 0.6 Xₜ₋₁ + εₜ**
Where ϕ = 0.6 and εₜ is white noise (mean 0, constant variance).

We are asked to compute the **autocorrelation function (ACF)** up to **lag 2**, i.e., ρ₁ and ρ₂.

### Step 1: Use the AR(1) autocorrelation formula

For an AR(1) process, the ACF at lag k is given by:
**ρₖ = ϕᵏ**

So we simply raise ϕ (0.6) to the power of lag.

### Step 2: Calculate autocorrelations

Lag 1:
ρ₁ = ϕ¹ = 0.6

Lag 2:
ρ₂ = ϕ² = 0.6² = 0.36

### Final Answer:

ρ₁ = 0.6
ρ₂ = 0.36

These values show how strongly Xₜ is correlated with its previous values at lag 1 and 2.

---
### Q 5. Using the Yule-Walker equations, estimate the parameter of the AR(1) and AR(2) process if γ0 = 10, γ1 = 6, γ2 = 10.
We are given:

* γ₀ = 10 (variance at lag 0)
* γ₁ = 6 (autocovariance at lag 1)
* γ₂ = 10 (autocovariance at lag 2)

We are asked to estimate parameters of:

1. AR(1): estimate ϕ₁
2. AR(2): estimate ϕ₁ and ϕ₂

Using **Yule-Walker equations**
#### Why use Yule-Walker?

Yule-Walker equations relate the **autocovariance** or **autocorrelation** values of a time series to the coefficients of an **AR(p)** model.
They help estimate AR model parameters when you know γ values but not the full dataset.

### Step 1: AR(1) Estimation

For AR(1), Yule-Walker equation is:
γ₁ = ϕ₁ \* γ₀
We solve for ϕ₁:
ϕ₁ = γ₁ / γ₀ = 6 / 10 = 0.6

### Step 2: AR(2) Estimation

For AR(2), the Yule-Walker equations are:

1. γ₁ = ϕ₁ \* γ₀ + ϕ₂ \* γ₁
2. γ₂ = ϕ₁ \* γ₁ + ϕ₂ \* γ₀

Substitute given values:

Equation 1:
6 = ϕ₁ \* 10 + ϕ₂ \* 6 → (i)

Equation 2:
10 = ϕ₁ \* 6 + ϕ₂ \* 10 → (ii)
### Step 3: Solve the equations

From equation (i):
6 = 10ϕ₁ + 6ϕ₂
Divide entire equation by 2:
3 = 5ϕ₁ + 3ϕ₂ → (iii)

From equation (ii):
10 = 6ϕ₁ + 10ϕ₂ → (iv)

Now solve equations (iii) and (iv) using substitution or elimination.

Multiply (iii) by 10:
30 = 50ϕ₁ + 30ϕ₂ → (v)

Multiply (iv) by 3:
30 = 18ϕ₁ + 30ϕ₂ → (vi)

Now subtract (vi) from (v):
(50ϕ₁ - 18ϕ₁) + (30ϕ₂ - 30ϕ₂) = 30 - 30
32ϕ₁ = 0 → ϕ₁ = 0

Now put ϕ₁ = 0 into (iii):
3 = 5\*0 + 3ϕ₂ → ϕ₂ = 1
### Final Answer:

AR(1):
ϕ₁ = 0.6

AR(2):
ϕ₁ = 0
ϕ₂ = 1
### Summary of what and why:

* We used **Yule-Walker** to convert given γ (covariances) into AR parameters.
* For AR(1), it’s simple: γ₁ = ϕ₁γ₀
* For AR(2), we set up two linear equations using lag-1 and lag-2 relationships
* We solved the system to find ϕ₁ and ϕ₂
* These values define how much past values contribute to the present in the AR process.

---
### Q 6. A process is defined as Xt = ϵt + 0.5ϵt−1, where ϵt ∼ iid N(0, 1). Find the mean and variance of Xt

We are given a **Moving Average process**:

**Xₜ = εₜ + 0.5 εₜ₋₁**,
where εₜ \~ i.i.d N(0, 1) → this means each εₜ is independently and identically distributed with mean 0 and variance 1.

We need to find:

* Mean of Xₜ
* Variance of Xₜ

### Step 1: Find the **mean** of Xₜ

We know:

**Xₜ = εₜ + 0.5 εₜ₋₁**

Take expectation (mean) of both sides:
E\[Xₜ] = E\[εₜ] + 0.5 \* E\[εₜ₋₁]

Since both εₜ and εₜ₋₁ have mean 0:
E\[Xₜ] = 0 + 0.5 \* 0 = 0

**Mean of Xₜ = 0**

### Step 2: Find the **variance** of Xₜ

We use the formula:
Var(Xₜ) = Var(εₜ + 0.5 εₜ₋₁)

Since εₜ and εₜ₋₁ are **independent**, we can use:
Var(aX + bY) = a²Var(X) + b²Var(Y), if X and Y are independent

So:

Var(Xₜ) = Var(εₜ) + (0.5)² \* Var(εₜ₋₁)
\= 1 + 0.25 \* 1 = 1 + 0.25 = 1.25

**Variance of Xₜ = 1.25**
### Final Answer:
Mean of Xₜ = 0
Variance of Xₜ = 1.25

### Summary of what and why:

* Took **expectation** to get mean: both εₜ terms have zero mean
* Used **variance formula for sum of independent variables**: εₜ and εₜ₋₁ are independent, so we just added variances
* Squared the coefficient (0.5² = 0.25) because variance scales with the square of constants
* This gives the spread (variance) and central value (mean) of the MA(1) process.
