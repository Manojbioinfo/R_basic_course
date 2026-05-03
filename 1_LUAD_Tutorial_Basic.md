---
# 🫁 LUAD (Lung Adenocarcinoma) Data Analysis in R

---

## 📌 1. Introduction  
Lung Adenocarcinoma (LUAD) is one of the most common types of lung cancer and a leading cause of cancer-related mortality worldwide. Analyzing clinical and demographic patient data helps identify disease patterns, risk factors, and supports better treatment strategies.

In this tutorial, we will work with a LUAD dataset containing variables such as age, gender, smoking status, tumor stage, and race. The goal is to perform data loading, cleaning, exploration, and basic statistical analysis using R.

---

## 📥 2. Download the Dataset  

The dataset used in this tutorial is publicly available.

🔗 **Dataset Source:**  
https://github.com/Manojbioinfo/R_basic_course/blob/main/Data/LUAD_clean_data_all_patients.csv  

👉 Click the link → select **"Raw"** → right-click → **Save As** to download the file.  

Place the file in your R working directory before proceeding.

---

## 📌 3. Workspace Preparation  

```r
# Clear workspace
rm(list = ls())
```

**Interpretation:**  
This ensures a clean working environment and avoids conflicts with previously stored variables.

---

## 📦 4. Load Required Libraries  

```r
# Install (run once only)
# install.packages("tidyverse")

# Load library
library(tidyverse)
```


Below message is **automatically printed by R when you load tidyverse**. 


```
── Attaching core tidyverse packages ───────────────── tidyverse 2.0.0 ──
✔ dplyr     1.2.1     ✔ readr     2.2.0
✔ forcats   1.0.1     ✔ stringr   1.6.0
✔ ggplot2   4.0.2     ✔ tibble    3.3.1
✔ lubridate 1.9.5     ✔ tidyr     1.3.2
✔ purrr     1.2.1     

── Conflicts ───────────────────────── tidyverse_conflicts() ──
✖ dplyr::filter() masks stats::filter()
✖ dplyr::lag()    masks stats::lag()
ℹ Use the conflicted package to force all conflicts to become errors
```


**Interpretation:**  
The tidyverse package provides tools for data manipulation, analysis, and visualization.

This output confirms that the tidyverse package and its core components have been successfully loaded.  

The “conflicts” message indicates that some functions (such as `filter()` and `lag()`) from dplyr override functions with the same name from base R (stats package). This is normal and does not cause errors in most analyses.


---

## 📂 5. Load the Dataset  

```r
# Load dataset
Data <- read.csv("LUAD_clean_data_all_patients.csv")
```




```r
# Inspect data
head(Data)
str(Data)
summary(Data)
```

```
> head(Data)
            ID Age Gender     Race Vital_Status Pathologic_stage Cigarettes_per_day Age_Group
1 TCGA-55-A48X  63 Female European        Alive        Stage IIA          1.9726027     Young
2 TCGA-NJ-A55R  67   Male European        Alive         Stage IA          0.2739726       Old
3 TCGA-53-A4EZ  63   Male European        Alive        Stage IIA          2.1917808     Young
4 TCGA-44-6777  85 Female European         Dead         Stage IB          3.5068493       Old
5 TCGA-44-6777  85 Female European         Dead         Stage IB          3.5068493       Old
6 TCGA-55-6982  79 Female European         Dead        Stage IIB          0.0000000       Old
```





Nice — now you can present this much more professionally in your report like this ✅

---

:::writing block
## 🔍 Inspecting the Dataset Structure

```r
# Inspect structure of the dataset
str(Data)
```

**Output:**  
```
'data.frame': 579 obs. of  8 variables:
 $ ID                 : chr  "TCGA-55-A48X" "TCGA-NJ-A55R" ...
 $ Age                : int  63 67 63 85 ...
 $ Gender             : chr  "Female" "Male" ...
 $ Race               : chr  "European" "European" ...
 $ Vital_Status       : chr  "Alive" "Alive" ...
 $ Pathologic_stage   : chr  "Stage IIA" "Stage IA" ...
 $ Cigarettes_per_day : num  1.973 0.274 2.192 ...
 $ Age_Group          : chr  "Young" "Old" ...
```

**Interpretation:**  
The dataset contains **579 observations and 8 variables**.  

- **Numerical variables:** Age, Cigarettes_per_day  
- **Categorical variables:** Gender, Race, Vital_Status, Pathologic_stage, Age_Group  
- **Identifier variable:** ID  

Most categorical variables are currently stored as character type and should be converted to factors for proper analysis. The dataset appears clean and suitable for further statistical analysis.

---

```r
# Inspect data
summary(Data)
```

```

```



**Interpretation:**  
These functions help understand the dataset structure, variable types, and summary statistics.

---

## 🧹 6. Data Cleaning  

```r
# Check missing values
colSums(is.na(Data))
```

```r
# Remove missing values
Data <- na.omit(Data)
```

```r
# Convert categorical variables to factors
Data$Gender <- as.factor(Data$Gender)
Data$Tumor_Stage <- as.factor(Data$Tumor_Stage)
Data$Smoking_Status <- as.factor(Data$Smoking_Status)
Data$Race <- as.factor(Data$Race)
```

```r
# Verify structure
str(Data)
```

**Interpretation:**  
Cleaning ensures the dataset is accurate and ready for analysis. Missing values are removed to avoid bias.  

Categorical variables (Gender, Tumor Stage, Smoking Status, Race) represent groups and are converted into factors so that R handles them correctly.  

Numerical variables such as Age represent measurable quantities and remain numeric.

---

## 📊 7. Descriptive Statistics  

```r
# Mean age
mean(Data$Age)
```

```r
# Median age
median(Data$Age)
```

```r
# Frequency tables
table(Data$Gender)
table(Data$Tumor_Stage)
```

**Interpretation:**  
Descriptive statistics summarize the main characteristics of the dataset and help understand distributions.

---

## 📈 8. Data Visualization  

```r
# Histogram
hist(Data$Age,
     col = "lightblue",
     main = "Age Distribution",
     xlab = "Age")
```

```r
# Bar plots
barplot(table(Data$Gender),
        col = "pink",
        main = "Gender Distribution")

barplot(table(Data$Tumor_Stage),
        col = "lightgreen",
        main = "Tumor Stage Distribution")
```

**Interpretation:**  
Visualizations provide an intuitive understanding of data patterns and distributions.

---

## 📉 9. Relationship Analysis  

```r
# Scatter plot
plot(Data$Age, Data$Smoking,
     xlab = "Age",
     ylab = "Cigarettes per Day",
     main = "Age vs Smoking")
```

```r
# Regression line
abline(lm(Smoking ~ Age, data = Data), col = "red")
```

**Interpretation:**  
This explores the relationship between age and smoking behavior, helping identify trends.

---

## 📊 10. Correlation Analysis  

```r
cor(Data$Age, Data$Smoking, use = "complete.obs")
```

**Interpretation:**  
Correlation measures the strength and direction of association between two numerical variables.  

Values range from -1 to +1:  
- Close to +1 → strong positive relationship  
- Close to -1 → strong negative relationship  
- Close to 0 → no relationship  

---

## 📦 11. Boxplots  

```r
# Age by Tumor Stage
boxplot(Age ~ Tumor_Stage, data = Data,
        col = "orange",
        main = "Age by Tumor Stage")
```

```r
# Age by Race
boxplot(Age ~ Race, data = Data,
        col = "purple",
        main = "Age by Race")
```

**Interpretation:**  
Boxplots compare distributions across groups and help detect variability and outliers.

---

## 💾 12. Saving Output  

```r
jpeg("luad_plot.jpg", width = 2000, height = 1500, res = 300)

plot(Data$Age, Data$Smoking)
abline(lm(Smoking ~ Age, data = Data), col = "red")

dev.off()
```

**Interpretation:**  
This allows saving visual outputs for reports and presentations.

---

## 🔧 13. Reproducibility  

```r
sessionInfo()
```

**Interpretation:**  
Records R environment details to ensure the analysis can be reproduced.

---

## ✅ 14. Conclusion  
This tutorial demonstrated a complete workflow for analyzing LUAD clinical data in R. The process included data downloading, cleaning, descriptive analysis, visualization, and basic statistical methods.

The results provide insights into patient characteristics and relationships between variables such as age and smoking. This structured approach ensures accurate, reproducible, and meaningful analysis of healthcare datasets.

