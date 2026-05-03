---

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

## 🔍 3. Filter Data (Only Female Patients)

```r
female_data <- Data %>%
  filter(Gender == "Female")
```

**Interpretation:**  
This extracts only female patients from the dataset.

---

## 🔢 4. Arrange Data (Sort by Age)

```r
sorted_data <- Data %>%
  arrange(Age)
```

**Interpretation:**  
This sorts the dataset in ascending order of age.

---

## 🎯 5. Select Specific Columns

```r
selected_data <- Data %>%
  select(Age, Gender, Tumor_Stage)
```

**Interpretation:**  
This keeps only important variables for focused analysis.

---

## ➕ 6. Create New Variable (Mutate)

```r
Data <- Data %>%
  mutate(Age_Group = ifelse(Age > 60, "Older", "Younger"))
```

**Interpretation:**  
This creates a new variable grouping patients by age.

---

## 📊 7. Summary Statistics (Summarise)

```r
Data %>%
  summarise(mean_age = mean(Age, na.rm = TRUE))
```

**Interpretation:**  
This calculates the average age of patients.

---

## 📊 8. Group-wise Summary

```r
Data %>%
  group_by(Gender) %>%
  summarise(mean_age = mean(Age, na.rm = TRUE))
```

**Interpretation:**  
This calculates the average age separately for each gender group.

---

## ✅ Conclusion  
This tutorial demonstrated basic data manipulation using the dplyr package, including filtering, sorting, selecting variables, creating new variables, and summarizing data. These functions are essential for efficient data handling in R.

