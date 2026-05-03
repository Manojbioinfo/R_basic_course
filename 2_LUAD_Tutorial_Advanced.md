
# 🫁 LUAD Data Manipulation using dplyr (Basic Tutorial)

---

## 📌 1. Load Library

```r
library(dplyr)
```

---

## 📂 2. Load Dataset

```r
Data <- read.csv("LUAD_clean_data_all_patients.csv")
```

---

## 🔍 3. Explore Dataset

```r
head(Data)
```

```

```


**Interpretation:**  
Displays the first few rows of the dataset to understand variable layout and sample values.  
Helps confirm correct data loading and detect any obvious issues.

---

```r
str(Data)
```

**Interpretation:**  
Shows the structure of the dataset, including variable types and number of observations.  
Reveals that categorical variables are stored as character and may require conversion to factors.

---

## 🔍 4. Filter Data (Only Female Patients)

```r
female_data <- Data %>%
  filter(Gender == "Female")
```

**Interpretation:**  
This extracts only female patients from the dataset for subgroup analysis.

---

## 🔍 5. Explore Female Dataset

```r
head(female_data)
```

**Interpretation:**  
Displays the first few rows of the female-only dataset to verify successful filtering.

---

```r
str(female_data)
```

**Interpretation:**  
Shows the structure of the filtered dataset and allows comparison with the full dataset.  
This helps identify differences in sample size and confirms that variables remain consistent.

---

## 🔢 6. Arrange Data (Sort by Age)

```r
sorted_data <- Data %>%
  arrange(Age)
```

**Interpretation:**  
Sorts the dataset in ascending order of age, making it easier to identify youngest and oldest patients.

---

## 🎯 7. Select Specific Columns

```r
selected_data <- Data %>%
  select(Age, Gender, Pathologic_stage)
```

**Interpretation:**  
Keeps only relevant variables for focused analysis and reduces dataset complexity.

---

## ➕ 8. Create New Variable (Mutate)

```r
Data <- Data %>%
  mutate(Age_Group = ifelse(Age > 60, "Older", "Younger"))
```

**Interpretation:**  
Creates a new categorical variable that groups patients based on age.

---

## 📊 9. Summary Statistics

```r
Data %>%
  summarise(mean_age = mean(Age, na.rm = TRUE))
```

**Interpretation:**  
Calculates the overall average age of patients in the dataset.

---

## 📊 10. Group-wise Summary

```r
Data %>%
  group_by(Gender) %>%
  summarise(mean_age = mean(Age, na.rm = TRUE))
```

**Interpretation:**  
Calculates the mean age separately for male and female patients, enabling comparison between groups.

---

## ✅ Conclusion  

This tutorial demonstrated basic data manipulation using the **dplyr** package, including filtering, sorting, selecting variables, creating new variables, and summarizing data.  
Additionally, comparing the full dataset with the female subset helps in understanding subgroup-specific patterns, which is important in healthcare data analysis.
