
<!--
https://www.andywills.info/rminr/#beginners
https://learn.scds.ca/intro-r/introduction.html
https://uviclibraries.github.io/rstudio/basics-interface.html
https://stat133.berkeley.edu/spring-2024/slides/stat133-00-intro2-RStudio.pdf
https://hbctraining.github.io/main/
https://ourcodingclub.github.io/tutorials/intro-to-r/#download
https://www.css.cornell.edu/faculty/dgr2/_static/files/R_PDF/mhw.pdf
https://rstudio-education.github.io/hopr/updating.html
https://thinking-spatial.org/courses/angewandte_geodatenverarbeitung/kurs01/
https://docs.posit.co/ide/user/ide/guide/ui/ui-panes.html
https://posit.cloud/content/12373562
https://statsandr.com/blog/correlation-coefficient-and-correlation-test-in-r/
https://www.oer.psy.lmu.de/R_Tutorial/Teil2_translated.html#workflow-for-importing-datasets
https://data-flair.training/blogs/r-tutorial/
https://www.datacamp.com/tutorial/r-studio-tutorial
https://intro2r.com/data-types.html
https://researchguides.library.wisc.edu/R/basics
https://www.hec.usace.army.mil/confluence/sspdocs/ssptutorialsguides/r-based-statistics-tutorials/a-very-brief-introduction-to-the-r-programming-language/introduction-to-r
https://cmu-lib.github.io/os-workshops/reproducible-research/Introduction%20to%20R.pdf
https://statisticsglobe.com/graphics-in-r
https://sahirbhatnagar.com/EPIB607/index.html
https://sahirbhatnagar.com/EPIB607/basics.html
https://datascienceineducation.com/#purchasing-the-book
https://git.uni-due.de/somanaja/data-science-in-education/-/blob/v1.0/01-introduction.Rmd?ref_type=tags#c06
https://github.com/data-edu/data-science-in-education/blob/main/DESCRIPTION
https://bioinformatics.ccr.cancer.gov/docs/r_for_novices/Getting_Started_with_R/Lesson1/
https://mantra.ed.ac.uk/practicals/R_tutorial_ex1.html
https://www.simonqueenborough.info/R/best-practice/index.html
-->

### Step 1: Log in to Posit Cloud

To get started with R, first access Posit Cloud:

👉 [Log in to Posit Cloud](https://login.posit.cloud/login)

Use your account credentials to sign in. If you don’t have an account yet, you can create one on the same page.

Once logged in, you’ll be ready to create and run R projects directly in your browser.



# R Basics for Medical Research: Tutorial Outline


## 1. Introduction & Setup
- Explain the tutorial's purpose: "Learn R basics for medical research analysis"
- List prerequisites:
  - Posit Cloud account
  - Basic computer skills
  - No prior programming experience needed
- Provide login guide:
  1. Visit https://posit.cloud/
  2. Enter credentials
  3. Create new RStudio project



## 2. Navigating the RStudio Interface
- Describe the four main panels:
  - Console (bottom-left): Immediate command execution
  - Script Editor (top-left): Code writing and saving
  - Environment/History (top-right): Variable storage and command history
  - Files/Plots/Packages/Help (bottom-right): File management and output viewing
- Show how to:
  1. Create new script: File → New File → R Script
  2. Save script: Ctrl+S (Windows) or Cmd+S (Mac)



## 3. Running Basic R Commands
- Demonstrate simple operations:
  - Calculations: `2 + 2`
  - Text output: `print("Hello, Medical Research!")`
- Explain execution methods:
  - Console: Immediate results (press Enter)
  - Script: Run selected lines (Ctrl+Enter) or entire script (Ctrl+Shift+Enter)



## 4. Working with Variables & Data
- Show variable assignment:
  ```r
  patient_age <- 45
  patient_bmi <- 28.5
  ```
- Introduce data types:
  - Numeric: `42`, `3.14`
  - Character: `"male"`, `"diabetes"`
  - Logical: `TRUE`, `FALSE`
- Demonstrate value checking:
  ```r
  print(patient_age)
  class(patient_bmi)
  ```



## 5. Importing & Exploring Data
- Guide to upload CSV:
  1. Click "Upload" in Files panel
  2. Select medical dataset file
  3. Click "OK"
- Show data loading:
  ```r
  medical_data <- read.csv("patient_data.csv")
  ```
- Demonstrate exploration:
  ```r
  head(medical_data)    # First 6 rows
  summary(medical_data) # Statistical summary
  str(medical_data)     # Data structure
  ```



## 6. Basic Data Analysis
- Show calculations:
  ```r
  mean(medical_data$age)
  median(medical_data$blood_pressure)
  ```
- Introduce correlation:
  ```r
  cor(medical_data$age, medical_data$cholesterol)
  cor.test(medical_data$age, medical_data$cholesterol)
  ```
- Create basic plot:
  ```r
  plot(medical_data$age, medical_data$blood_pressure,
       main = "Age vs Blood Pressure",
       xlab = "Age (years)",
       ylab = "Blood Pressure (mmHg)")


## 7. Saving & Exporting Work
- Save scripts:
  - File → Save (or Ctrl+S/Cmd+S)
- Export plots:
  ```r
  png("blood_pressure_plot.png")
  plot(medical_data$age, medical_data$blood_pressure)
  dev.off()
  ```
- Clean workspace:
  ```r
  rm(list = ls())
  ```



## 8. Conclusion & Next Steps
- Recap key learnings:
  - RStudio interface navigation
  - Basic R commands and variables
  - Data import and exploration
  - Simple analysis and visualization
- Suggest next topics:
  - ggplot2 for advanced visualizations
  - dplyr for data manipulation
  - Regression analysis
- Provide resources:
  - [R for Data Science](https://r4ds.had.co.nz/)
  - [RStudio Cheat Sheets](https://www.rstudio.com/resources/cheatsheets/)
  - [Posit Cloud Documentation](https://docs.posit.co/)


