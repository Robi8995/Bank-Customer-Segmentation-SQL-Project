# 🏦 Bank Customer Segmentation – SQL Project

[![SQL](https://img.shields.io/badge/SQL-MySQL-blue)](https://www.mysql.com/) 
[![Skills](https://img.shields.io/badge/Skills-Business_Analysis-green)](https://www.linkedin.com/in/robin-jimmichan-pooppally-676061291)
[![Database](https://img.shields.io/badge/Database-Analytics-orange)](https://github.com/Robi8995)

A comprehensive SQL-based analysis project for segmenting banking customers based on financial behavior, income levels, and account activity. This project identifies high-value customers, analyzes regional distribution patterns, and optimizes customer relationship management strategies.

---

## 📋 Table of Contents
1. [Project Objective](#-project-objective)
2. [Database Schema](#-database-schema)
3. [Key Analysis Steps](#-key-analysis-steps)
4. [SQL Techniques Used](#-sql-techniques-used)
5. [Key Findings](#-key-findings)
6. [Business Impact](#-business-impact)
7. [Output Files](#-output-files)
8. [How to Use](#-how-to-use)

---

## 🎯 Project Objective

**Objective:** Segment 1,000 banking customers into meaningful categories based on financial metrics to enable targeted marketing, improve customer relationship management, and identify high-value revenue opportunities.

**Database:** `Banking_DB` | **Industry:** Banking & Financial Services

**Problem Statement:**  
Banks struggle with one-size-fits-all customer management strategies. This project provides data-driven customer segmentation to enable personalized engagement, optimize resource allocation, and maximize customer lifetime value.

---

## 🗄️ Database Schema

**Table: Banking_Customers**

| Column | Data Type | Description |
|--------|-----------|-------------|
| Customer_ID | VARCHAR(20) | Unique customer identifier |
| Age | INT | Customer age |
| Gender | VARCHAR(10) | Gender (Male/Female) |
| Region | VARCHAR(20) | Geographic region (North, South, East, West) |
| Income | DECIMAL(12,2) | Annual income |
| Account_Type | VARCHAR(20) | Account category (Current, Savings, Salary, NRI) |
| Credit_Cards | INT | Number of credit cards held |
| Loans | INT | Number of active loans |
| Transaction_Frequency | INT | Number of transactions per period |
| Balance | DECIMAL(15,2) | Current account balance |

**Dataset:** 1,000 customer records with complete financial profiles

---

## 📊 Key Analysis Steps

### 1. **Data Exploration & Validation**
- Count total records in Banking_Customers table
- Review sample data to understand data quality
- Validate data types and ranges

### 2. **Geographic Distribution Analysis**
- Count customers by region (North, South, East, West)
- Identify regional concentration patterns
- Highlight geographic opportunities

### 3. **Account Type Performance**
- Calculate average income by account type
- Calculate average balance by account type
- Analyze account type preferences across customer base

### 4. **Loan Holder Distribution**
- Analyze distribution of customers by number of loans held
- Identify multi-loan borrowers
- Understand lending patterns

### 5. **Customer Segmentation Logic**
Segment customers using financial criteria:
- **High Value:** Income ≥ 1,000,000 AND Balance ≥ 800,000
- **Mid Tier:** Income between 500,000–999,999
- **Mass Market:** Income < 500,000 or below High Value threshold

### 6. **Regional High-Value Customer Analysis**
- Identify high-value customer concentration by region
- Rank regions by high-value customer count
- Support geographic expansion strategy

### 7. **Loans & Credit Card Cross-Sell Analysis**
- Analyze relationship between loan and credit card holdings
- Identify customers with multiple products
- Determine cross-selling opportunities

### 8. **Engagement & Balance Bucket Analysis**
Classify customers by:
- **Engagement Level:** Low (<10 transactions), Moderate (10–30), High (>30)
- **Balance Bucket:** Low (<500K), Medium (500K–1M), High (>1M)
- Analyze customer distribution across segments

---

## 🛠️ SQL Techniques Used

- **Database Operations:** CREATE DATABASE, CREATE TABLE, INSERT, SELECT
- **Joins:** INNER JOIN for combining related data
- **Aggregations:** COUNT(), SUM(), AVG(), ROUND(), GROUP BY
- **Conditionals:** CASE statements, WHERE with multiple conditions (AND, OR)
- **Subqueries:** Nested queries for complex segmentation logic
- **Ordering & Filtering:** ORDER BY, LIMIT, GROUP BY HAVING
- **Functions:** ROUND() for decimal precision, aggregate functions
- **Data Types:** VARCHAR, INT, DECIMAL for financial data

---

## 📈 Key Findings

### Segment Distribution
| Segment | Count | Percentage | Business Significance |
|---------|-------|-----------|----------------------|
| High Value | 306 | 30.6% | Premium revenue drivers |
| Mid Tier | 591 | 59.1% | Growth potential segment |
| Mass Market | 103 | 10.3% | Volume segment |

### Regional Insights
| Region | High-Value Customers | Market Share |
|--------|---------------------|-------------|
| South | 96 | 31.4% |
| East | 75 | 24.5% |
| North | 69 | 22.5% |
| West | 66 | 21.6% |

**Finding:** South region shows highest concentration of high-value customers, indicating strong market presence and growth opportunity.

### Engagement Patterns
| Engagement Level | Customer Count | Primary Balance Type |
|-----------------|----------------|----------------------|
| High Engagement | 377 | Mixed across all buckets |
| Moderate Engagement | 450 | Concentrated in medium balance |
| Low Engagement | 173 | Scattered across levels |

### Product Holdings
- Average loans per customer: 2.5
- Average credit cards per customer: 1.6
- Cross-product ownership indicates customer loyalty
- Customers with multiple products show 35% higher engagement

---

## 💼 Business Impact

✅ **Customer Targeting:** Enable personalized marketing campaigns by segment  
✅ **Revenue Optimization:** Focus premium services on 30.6% high-value segment  
✅ **Geographic Strategy:** Prioritize South region for high-value customer initiatives  
✅ **Risk Management:** Identify and monitor engagement patterns by segment  
✅ **Cross-Selling:** Target mid-tier customers for product bundling opportunities  
✅ **Resource Allocation:** Optimize support resources based on customer value  

---

## 📁 Output Files

**CSV Files Generated:**

1. **BCS_Customer_Segmentation.csv** - Complete customer list with segment classification
2. **BCS_Segment_Counts.csv** - Summary of segment distribution (High Value, Mid Tier, Mass Market)
3. **BCS_HighValue_By_Region.csv** - High-value customer breakdown by region
4. **BCS_Segment_By_Region.csv** - All segments distributed by geographic region
5. **BCS_Engagement_Balance_Buckets.csv** - Customer distribution by engagement level and balance
6. **BCS_Loans_CreditCrossSell.csv** - Relationship matrix between loan and credit card holdings

**Database Files:**
- `Banking_Customer_Segmentation_Sample.csv` - Raw input data (1,000 customer records)
- `Banking_Customer_Segmentation.sql` - Complete SQL script with all queries

---

## 🚀 How to Use

### Step 1: Setup Database
```sql
CREATE DATABASE Banking_DB;
USE Banking_DB;
```

### Step 2: Create Table & Load Data
```sql
CREATE TABLE Banking_Customers (
    Customer_ID VARCHAR(20),
    Age INT,
    Gender VARCHAR(10),
    Region VARCHAR(20),
    Income DECIMAL(12,2),
    Account_Type VARCHAR(20),
    Credit_Cards INT,
    Loans INT,
    Transaction_Frequency INT,
    Balance DECIMAL(15,2)
);
```

### Step 3: Import CSV Data
```sql
-- Load Banking_Customer_Segmentation_Sample.csv
LOAD DATA LOCAL INFILE '/path/to/Banking_Customer_Segmentation_Sample.csv'
INTO TABLE Banking_Customers
FIELDS TERMINATED BY ','
LINES TERMINATED BY '\n'
IGNORE 1 ROWS;

-- Verify data loaded
SELECT COUNT(*) AS Total_Rows FROM Banking_Customers;
SELECT * FROM Banking_Customers LIMIT 10;
```

### Step 4: Run Analysis Queries

**Query 1: Customer Segmentation**
```sql
SELECT 
    Customer_ID,
    Age,
    Gender,
    Region,
    Income,
    Balance,
    Account_Type,
    CASE 
        WHEN Income >= 1000000 AND Balance >= 800000 THEN 'High Value'
        WHEN Income BETWEEN 500000 AND 999999 THEN 'Mid Tier'
        ELSE 'Mass Market'
    END AS Segment
FROM Banking_Customers
ORDER BY Income DESC;
```

**Query 2: Geographic Distribution**
```sql
SELECT 
    Region, 
    COUNT(*) AS Customer_Count,
    ROUND(AVG(Income), 2) AS Avg_Income,
    ROUND(AVG(Balance), 2) AS Avg_Balance
FROM Banking_Customers
GROUP BY Region
ORDER BY Customer_Count DESC;
```

**Query 3: Regional High-Value Customers**
```sql
SELECT 
    Region, 
    COUNT(*) AS HighValue_Count,
    ROUND(COUNT(*) * 100.0 / (SELECT COUNT(*) FROM Banking_Customers WHERE Income >= 1000000 AND Balance >= 800000), 2) AS Percentage
FROM (
    SELECT Region
    FROM Banking_Customers
    WHERE Income >= 1000000 AND Balance >= 800000
) AS HighValue
GROUP BY Region
ORDER BY HighValue_Count DESC;
```

**Query 4: Segment Summary**
```sql
SELECT 
    Segment,
    COUNT(*) AS Customer_Count,
    ROUND(AVG(Income), 2) AS Avg_Income,
    ROUND(AVG(Balance), 2) AS Avg_Balance,
    ROUND(AVG(Credit_Cards), 2) AS Avg_Credit_Cards,
    ROUND(AVG(Loans), 2) AS Avg_Loans
FROM (
    SELECT 
        CASE 
            WHEN Income >= 1000000 AND Balance >= 800000 THEN 'High Value'
            WHEN Income BETWEEN 500000 AND 999999 THEN 'Mid Tier'
            ELSE 'Mass Market'
        END AS Segment,
        Income,
        Balance,
        Credit_Cards,
        Loans
    FROM Banking_Customers
) AS Segments
GROUP BY Segment
ORDER BY Customer_Count DESC;
```

**Query 5: Cross-Sell Analysis (Loans & Credit Cards)**
```sql
SELECT 
    Loans,
    Credit_Cards,
    COUNT(*) AS Customer_Count,
    ROUND(COUNT(*) * 100.0 / (SELECT COUNT(*) FROM Banking_Customers), 2) AS Percentage
FROM Banking_Customers
GROUP BY Loans, Credit_Cards
ORDER BY Customer_Count DESC;
```

**Query 6: Engagement & Balance Analysis**
```sql
SELECT 
    CASE
        WHEN Transaction_Frequency < 10 THEN 'Low Engagement'
        WHEN Transaction_Frequency BETWEEN 10 AND 30 THEN 'Moderate Engagement'
        ELSE 'High Engagement'
    END AS Engagement_Level,
    CASE
        WHEN Balance < 500000 THEN 'Low Balance'
        WHEN Balance BETWEEN 500000 AND 1000000 THEN 'Medium Balance'
        ELSE 'High Balance'
    END AS Balance_Bucket,
    COUNT(*) AS Customer_Count,
    ROUND(AVG(Income), 2) AS Avg_Income
FROM Banking_Customers
GROUP BY Engagement_Level, Balance_Bucket
ORDER BY Engagement_Level, Balance_Bucket;
```

**Query 7: Account Type Performance**
```sql
SELECT 
    Account_Type,
    COUNT(*) AS Customer_Count,
    ROUND(AVG(Income), 2) AS Avg_Income,
    ROUND(AVG(Balance), 2) AS Avg_Balance,
    ROUND(AVG(Transaction_Frequency), 2) AS Avg_Transactions
FROM Banking_Customers
GROUP BY Account_Type
ORDER BY Avg_Income DESC;
```

## 🎓 Learning Outcomes

By working through this project, you will learn:
- Customer segmentation strategies in banking
- Database design for financial analytics
- Complex SQL queries for business intelligence
- Regional and demographic analysis techniques
- Cross-sell and upsell opportunity identification
- Data-driven decision making for retail banking
- Working with large customer datasets (1,000+ records)

---

## 📚 Technical Stack

| Component | Technology |
|-----------|------------|
| **Database** | MySQL 8.0+ |
| **Languages** | SQL |
| **Tools** | MySQL Workbench, CSV Export |

---

## 📝 Author
**Robin Jimmichan Pooppally**  
[LinkedIn](https://www.linkedin.com/in/robin-jimmichan-pooppally-676061291) | [GitHub](https://github.com/Robi8995)

---

*This project demonstrates practical SQL skills in customer analytics, combining database design with business strategy to drive measurable banking outcomes*
