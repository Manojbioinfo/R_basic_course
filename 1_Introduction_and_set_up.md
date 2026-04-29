---
title: "R Basics for Medical Research"
author: "Your Name"
date: "`r Sys.Date()`"
bibliography: Ref.bib
output:
  html_document:
    toc: true
    toc_float: true
---

# Introduction

This tutorial introduces R programming basics specifically tailored for medical research. We'll cover essential concepts using Posit Cloud and RStudio, following best practices from established R education resources [@Sanchez2024_RIntro].

## Learning Objectives
By the end of this tutorial, you will be able to:
- Navigate the Posit Cloud interface
- Understand basic R syntax
- Perform simple data analysis
- Create basic visualizations

# Step 1: Log in to Posit Cloud

To get started with R, first access Posit Cloud:

👉 [Log in to Posit Cloud](https://login.posit.cloud/login)

1. Enter your account credentials
2. If you don't have an account:
   - Click "Sign Up"
   - Complete the registration form
   - Verify your email address
3. After logging in, click "New Project" → "New RStudio Project"

Once logged in, you'll be ready to create and run R projects directly in your browser.

# Setup

## R {#r-section}

R is a powerful programming language for statistical computing and graphics [@Sanchez2024_RIntro]. Key features include:

- Open-source and free to use
- Extensive package ecosystem (over 18,000 packages)
- Strong community support
- Excellent data visualization capabilities

## RStudio {#rstudio-section}

RStudio is an integrated development environment (IDE) that makes working with R easier [@Sanchez2024_RIntro]. The interface includes:

1. **Source Editor**: For writing and editing scripts
2. **Console**: For executing commands and viewing output
3. **Environment/History**: For viewing variables and command history
4. **Files/Plots/Packages/Help**: For managing files, viewing plots, and accessing documentation

## First Steps in RStudio

```r
# Check R version
R.version.string

# Create your first variable
patient_count <- 100

# View the variable
patient_count
