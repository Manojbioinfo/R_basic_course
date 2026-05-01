# 📥 Step 1: Download the Dataset

In this tutorial, we will use a clinical dataset from TCGA-LUAD (Lung Adenocarcinoma).

## 🔗 Dataset Source
You can download the dataset from GitHub:

https://github.com/Manojbioinfo/R_basic_course/blob/main/Data/LUAD_clean_data_all_patients.csv

👉 Click the link, then click **"Download"** or **"Raw" → Save As** to download the file.

---
## 📦 Load Required Libraries

Before working with the data, we need to load the required R packages.

```r
# Install packages (run only once if not installed)
# install.packages("tidyverse")

# Load the library
library(tidyverse)
```
---

## 📂 Load the Dataset in R

After downloading the file, place it in your working directory and load it in R:

```r
Data <- read.csv("LUAD_clean_data_all_patients.csv")
```
