---
{"dg-publish":true,"permalink":"/Power Bi/","created":"2025-04-08T15:19:12.715+05:30"}
---

**Business Intelligence (BI)** is the process of collecting, analyzing, and transforming raw data into meaningful insights that help businesses make informed decisions.
### Simple Definition:
> **BI = Data → Information → Decision-Making**
---
### ⚔️ **Excel vs Power Query: Key Differences**

| Feature             | **Excel**                                  | **Power Query**                                    |
| ------------------- | ------------------------------------------ | -------------------------------------------------- |
| **Main Use**        | Data analysis, reporting, and calculations | Data extraction, transformation, and loading (ETL) |
| **Interface**       | Manual (cells, formulas, pivot tables)     | No-code/low-code UI for data manipulation          |
| **Data Handling**   | Better for small datasets                  | Handles large data more efficiently                |
| **Automation**      | Limited (macros, VBA)                      | Highly automated, repeatable queries               |
| **Data Sources**    | Excel files, limited databases             | Wide variety: databases, web, APIs, Excel, etc.    |
| **Live Connection** | Manual refresh                             | Dynamic, auto-refresh possible                     |
### ✅ **When to Use Power BI vs Excel**
#### 🟡 **Use Excel When:**
- You need **quick calculations** or one-off analyses.
- You're dealing with **small to medium datasets**.
- You need to **share reports via email** or in simple formats.
- You're using **formulas, VBA**, or pivot tables.
#### 🔵 **Use Power BI When:**
- You want to build **interactive dashboards**.
- You need to work with **huge datasets** (millions of rows).
- You want to **connect to live data** from multiple sources.
- You need to **automate and refresh** reports.
- You want to share dashboards via the **Power BI service (cloud)**.
### 🎯 Example Use Cases
- **Excel**: Calculating monthly expenses, tracking grades, simple sales reports.
- **Power Query** (in Excel or Power BI): Cleaning messy CSVs, merging datasets from different systems.
- **Power BI**: Company-wide sales dashboards, real-time KPI monitoring, drill-down business reports.
    
---
# Dax functions
## 📊 **1. Aggregation Functions**

|Function|Purpose|Example|
|---|---|---|
|`SUM()`|Adds values|`SUM(Sales[Amount])`|
|`AVERAGE()`|Mean value|`AVERAGE(Orders[Quantity])`|
|`MIN()` / `MAX()`|Min/max|`MIN(Dates[Year])`|
|`COUNT()`|Count non-blank|`COUNT(Customers[Name])`|
|`COUNTA()`|Count non-empty|`COUNTA(Orders[Product])`|
|`COUNTROWS()`|Count rows in table|`COUNTROWS(Orders)`|
|`DISTINCTCOUNT()`|Count unique values|`DISTINCTCOUNT(Sales[ProductID])`|

---
## 📅 **2. Date & Time Functions**

|Function|Purpose|Example|
|---|---|---|
|`TODAY()`|Current date|`TODAY()`|
|`NOW()`|Current date & time|`NOW()`|
|`YEAR()`, `MONTH()`, `DAY()`|Extract from date|`YEAR(Sales[Date])`|
|`DATE()`|Create a date|`DATE(2023, 12, 1)`|
|`DATEDIFF()`|Difference between dates|`DATEDIFF(Orders[OrderDate], Orders[ShipDate], DAY)`|
|`EOMONTH()`|End of month|`EOMONTH(Sales[Date], 0)`|
|`WEEKNUM()`|Week number|`WEEKNUM(Sales[Date])`|

---
## 🔗 **3. Relationship & Filter Functions**

|Function|Purpose|Example|
|---|---|---|
|`RELATED()`|Get value from related table (many-to-one)|`RELATED(Customer[Name])`|
|`RELATEDTABLE()`|Get table of related rows (one-to-many)|`COUNTROWS(RELATEDTABLE(Orders))`|
|`LOOKUPVALUE()`|Fetch a value like VLOOKUP|`LOOKUPVALUE(Customer[Name], Customer[ID], Sales[CustomerID])`|
|`USERELATIONSHIP()`|Activate inactive relationship|`CALCULATE(SUM(Sales[Amount]), USERELATIONSHIP(Calendar[Date], Sales[ShipDate]))`|

---
## 🎯 **4. Filter & Context Functions**

| Function      | Purpose                                | Example                                                |
| ------------- | -------------------------------------- | ------------------------------------------------------ |
| `CALCULATE()` | Change filter context                  | `CALCULATE(SUM(Sales[Amount]), Region[Name] = "West")` |
| `FILTER()`    | Return filtered table                  | `FILTER(Sales, Sales[Amount] > 1000)`                  |
| `ALL()`       | Remove filters                         | `CALCULATE(SUM(Sales[Amount]), ALL(Sales))`            |
| `ALLEXCEPT()` | Remove all filters except some columns | `ALLEXCEPT(Sales, Sales[Region])`                      |
| `VALUES()`    | Unique column values                   | `VALUES(Products[Category])`                           |

---
## 🔠 **Text Functions in DAX**

|Function(s)|Purpose|Example|
|---|---|---|
|`CONCATENATE()`|Join two text values|`CONCATENATE(FirstName, LastName)`|
|`CONCATENATEX()`|Join text across table rows|`CONCATENATEX(Employees, Employees[FirstName], ", ")`|
|`LEFT()`|Get left part of text|`LEFT(ProductName, 1)`|
|`RIGHT()`|Get right part of text|`RIGHT(ProductCode, 3)`|
|`MID()`|Extract substring|`MID(ProductName, 3, 4)`|
|`SEARCH()`|Find text position (case-insensitive)|`SEARCH(" ", FullName, 1, -1)`|
|`FIND()`|Find text position (case-sensitive)|`FIND("Pro", ProductName, 1)`|
|`UPPER()`|Convert to uppercase|`UPPER(FirstName)`|
|`LOWER()`|Convert to lowercase|`LOWER(LastName)`|
|`TRIM()`|Remove extra spaces|`TRIM(Name)`|
|`SUBSTITUTE()`|Replace part of text|`SUBSTITUTE(Category, "Old", "New")`|
|`FORMAT()`|Convert number/date to text|`FORMAT(Date, "MMM YYYY")``FORMAT(Amount, "₹#,##0.00")`|

---
