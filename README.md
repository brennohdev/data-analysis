# Socioeconomic Indicators Analysis for Paraíba (Census, PNAD, POF)

## Project Overview

This project presents a comprehensive analysis of three major microdata surveys in Brazil, with a specific focus on the state of Paraíba. Using data from the **School Census (INEP)**, the **Continuous National Household Sample Survey (PNAD - IBGE)**, and the **Household Budget Survey (POF - IBGE)**, the goal is to apply **ETL techniques (Extract, Transform, Load)** to process real-world complex data, calculate key social and economic indicators, and present the results in a clear and visual manner.

The project serves as a practical demonstration of **data manipulation**, **statistical analysis**, and **information visualization** using **Python and its main libraries**.

---

## Project Structure

This repository contains a Jupyter Notebook organized into two main parts:

### Part 1: Python Fundamentals and Programming Logic

A series of exercises covering essential programming concepts, including conditional logic, mathematical calculations, and function definitions. These exercises serve as a foundation for the data analysis.

### Part 2: Data Analysis Challenges Using Public Sources

An end-to-end application of analysis processes on three distinct and complex datasets:

- **Challenge 1: School Infrastructure (School Census)**  
  Analysis of basic and pedagogical infrastructure in public schools in Paraíba.

- **Challenge 2: Socioeconomic Indicators (PNAD)**  
  Calculation of illiteracy rate, average income, and the Gini Index to measure income inequality.

- **Challenge 3: Household Food Expenditures (POF)**  
  Analysis of household food spending patterns in Paraíba.

---

## Methodology

Each challenge followed a structured **ETL process**, adapted to the particularities of each data source.

### Extract:

- Reading raw government microdata, including **fixed-width text files (FWF)** like `consumo_alimentar.txt` (POF) and `PNADC_..._2023.txt` (PNAD), and `.csv` files with specific delimiters and encodings from the School Census.
- Using official documentation (variable dictionaries and layouts) to define reading specifications (`colspecs`).

### Transform:

- **Filtering:** Isolating records for the target population (Paraíba state, public schools, individuals over 15 years old, etc.).
- **Cleaning:** Handling missing values (`NaN`) and correcting inconsistent data (e.g., negative ages in the School Census).
- **Harmonization:** Inverting variable logic (e.g., from `IN_AGUA_INEXISTENTE` to `IN_AGUA_EXISTENTE`) to ensure consistent analysis.
- **Enrichment:** Merging multiple data sources using `pd.merge` to add contextual information, such as linking food codes from the POF (`consumo_alimentar.txt`) with their descriptions (`Tradutor_Alimentação.xls`).

### Load:

- Loading transformed data into final analytical outputs.
- Calculating descriptive statistics (mean, median, standard deviation).
- Computing specific indicators like the **Illiteracy Rate** and **Gini Index**.
- Creating a composite index (**IQIE - School Infrastructure Quality Index**) using a weighted average for advanced analysis.
- Generating aggregated and sorted tables to identify key challenges and spending categories.

---

## Key Findings

### Education (School Census):

The analysis revealed good coverage of **basic infrastructure** (water, electricity), but significant challenges in **pedagogical resources**. A large proportion of schools lack **science and computer labs**, as well as **sports facilities**.

### Socioeconomy (PNAD):

Indicators for Paraíba show a **Gini Index of 0.55**, indicating a **high level of income inequality**. This is supported by an **illiteracy rate of 15.08%** among individuals over 15 years old and an **average income distribution** concentrated in lower income brackets, as shown in the histogram.

### Expenditures (POF):

The analysis of household food spending identified that the categories **Meats**, **Cereals**, and **Baked Goods** represent the **highest expenses** for the families in the sample.

---

## Tools Used

- **Language:** Python 3

### Libraries:

- `pandas`: for all data manipulation, cleaning, and analysis  
- `numpy`: for numerical operations and handling missing values  
- `matplotlib` & `seaborn`: for creating visualizations (bar charts and histograms)

- **Environment:** Jupyter Notebook (via PyCharm)
