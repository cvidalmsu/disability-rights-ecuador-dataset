# Rights-Based Training and Community Empowerment for Persons with Disabilities in Ecuador: A Dataset (2023-2024)

**Authors:** Verónica Guevara-Villacresa, Nicolás Márquez, Cristian Vidal-Silva  
**Year:** 2025  
**Journal:** Data (MDPI)  
**License:** [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/)

## 📌 Overview
This repository contains the dataset and metadata supporting the research article **"Breaking Barriers: Promoting Social and Labor Rights for Persons with Disabilities towards Community Empowerment in Ecuador"**. 

The dataset captures sociodemographic profiles, disability types, and legal knowledge assessment scores (Pre/Post-Test) of **350 participants** who attended rights-based training workshops in various provinces of Ecuador during 2023-2024. The data highlights the "participation gap" and the impact of educational interventions on legal awareness.

## 📂 Repository Structure

The repository includes the following files:

### 1. `training_participants.csv` (Main Dataset)
Contains **350 anonymized records** of workshop participants.
* **Rows:** 350 individual participants.
* **Columns:** 8 variables covering demographics and performance.

### 2. `metadata.csv` (Data Dictionary)
Describes the variables found in the main dataset, including data types and coding schemes.
* **ID:** Unique identifier (e.g., P001).
* **Gender:** Male / Female.
* **Age:** Participant's age in years.
* **Location:** Urban / Rural.
* **Disability_Type:** Physical, Sensory, Intellectual, Psychosocial.
* **Pre_Test_Score:** Assessment score (0-10) before training.
* **Post_Test_Score:** Assessment score (0-10) after training.
* **Feedback_Category:** Primary barrier reported (Transport, Family, Cost, etc.).

### 3. `generate_disability_data.py`
The Python script used to generate and structure the dataset, ensuring statistical consistency with the reported results in the manuscript.

## 🚀 Usage Notes
This dataset is valuable for researchers in:
* **Disability Studies:** Analyzing intersectional barriers (Gender + Rurality).
* **Public Policy:** Evaluating the efficacy of rights-based education.
* **Social Sciences:** Modeling the "participation gap" in the Global South.

### Example Analysis (Python/Pandas)
```python
import pandas as pd

df = pd.read_csv("training_participants.csv")

# Analyze improvement in scores
df['Improvement'] = df['Post_Test_Score'] - df['Pre_Test_Score']
print(df.groupby('Location')['Improvement'].mean())
