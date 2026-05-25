# ADRD_LLM_ResearchProject
Data &amp; Coding Repository for ADRD LLM research Project

# **NHATS Round 14 Dataset Documentation**

## **Overview of NHATS**

The **National Health and Aging Trends Study (NHATS)** is a nationally representative longitudinal study designed to investigate aging, disability, health, and late-life functioning among older adults in the United States. NHATS is sponsored by the National Institute on Aging (NIA) and conducted by the Johns Hopkins Bloomberg School of Public Health in collaboration with Westat.

NHATS was established to better understand:

- How aging affects physical and cognitive functioning
- Disability trends among older adults
- The social and environmental factors influencing aging
- Healthcare utilization and caregiving needs
- Changes in independence and quality of life over time

The study primarily focuses on Medicare beneficiaries aged **65 years and older** in the United States.

### **Key Characteristics of NHATS**

|**Feature**|**Description**|
|---|---|
|Study Type|Longitudinal panel study|
|Target Population|Medicare beneficiaries aged 65+|
|Sponsor|National Institute on Aging (NIA)|
|Data Collection Frequency|Annual interviews|
|First Round|2011|
|Current Round Used|Round 14 (2024/2025 release)|
|Approximate Sample Size|~35,000+ sampled individuals across all rounds|
|Interview Types|In-person, proxy interviews, facility questionnaires|
|Main Topics|Health, disability, cognition, mobility, mental health, caregiving, living arrangements, healthcare utilization|

NHATS data are organized into **rounds**, where each round corresponds to one wave of annual data collection. Participants are followed longitudinally over time, allowing researchers to study aging trajectories and health transitions.

The NHATS dataset contains multiple interconnected files, including:

- Sample Person (SP) files
- Other Person (OP) files
- Tracker files
- Facility questionnaires
- Accelerometry data
- Tablet activity data
- Income imputation files

Additional official documentation can be found on the NHATS website and user guides.
## **NHATS Round 14 Data Structure**

For this project, we use the **NHATS Round 14 Public Use Final Release** dataset.

According to the official Round 14 README documentation, the Round 14 STATA release contains **16 files** in total, including both data files and codebook frequency files.  

### **Main Data Files in Round 14**

|**File Name**|**Description**|**Observations**|**Variables**|
|---|---|---|---|
|`NHATS_Round_14_SP_File.dta`|Sample Person (SP) + Facility Questionnaire data|7,655|1,454|
|`NHATS_Round_14_OP_File.dta`|Other Person (OP) data|61,904|1,016|
|`NHATS_Round_14_Tracker_File.dta`|Tracking information for all sampled individuals|35,257|2,077|
|`NHATS_Round_14_Tab_Act_File.dta`|Tablet activities data|7,655|145|
|`NHATS_Round_14_Accel_Summ_File.dta`|Accelerometry summary data|480|76|
|`NHATS_Round_14_Accel_Det_File.dta`|Accelerometry detailed data|3,369|1,444|
|`NHATS_Round_14_Accel_Track_File.dta`|Accelerometry tracking information|7,655|11|
|`NHATS_R14_Int_Inc_Imp_File.dta`|Interval income imputation data|7,655|23|

Source: NHATS Round 14 README documentation.  

---

### **Frequency / Codebook Files**

NHATS also provides frequency PDF files for each dataset. These files contain:

- Variable names
- Variable labels
- Frequency distributions
- Value labels
- Means and summary statistics for continuous variables

Examples include:

- `NHATS_Round_14_SP_Frequencies.pdf`
- `NHATS_Round_14_OP_Frequencies.pdf`
- `NHATS_Round_14_Tracker_Frequencies.pdf`

These frequency/codebook files are extremely useful for:

- Understanding variable meanings
- Identifying coding schemes
- Data preprocessing
- Feature engineering
- Missing value interpretation

---

## **Dataset Used in This Project**

### **File Used**

```text
NHATS_R14_Final_Release_STATA/NHATS_Round_14_SP_File.dta
```

This project primarily uses the **Sample Person (SP) File**, which is the core respondent-level dataset in NHATS Round 14.

### **What Information Does the SP File Contain?**

The SP file contains detailed information about each sampled older adult participant, including:

- Demographics
- Physical health
- Chronic diseases
- Functional limitations
- Cognitive health
- Mental health
- Sleep quality
- Falls and mobility
- Healthcare utilization
- Surgeries and medical procedures
- Residential and living arrangements
- Proxy interview information

The file contains:

- **7,655 observations (participants)**
- **1,454 variables**

as documented in the official README file.  

The accompanying frequency/codebook PDF (`NHATS_Round_14_SP_Frequencies.pdf`) provides detailed descriptions and distributions for all variables.  

---

# **Selected Variables Used in This Project**

The following variables were selected from the SP dataset for analysis and modeling purposes.

---

# **1. Demographic Variables**

|**Variable**|**Description**|
|---|---|
|`r14d2intvrage`|Age group at interview|
|`r13dgender`|Gender|
|`rl13dracehisp`|Race and Hispanic ethnicity|
|`hh14dmarstat`|Marital status|
|`hh14livwthspo`|Lives with spouse or partner|

### **Purpose**

These variables describe participants’ demographic and social background characteristics, which are important predictors of aging outcomes, disease risk, and healthcare utilization.

---

# **2. General Health Status**

|**Variable**|**Description**|
|---|---|
|`hc14health`|Self-reported overall health|

### **Purpose**

This variable measures participants’ overall perceived health condition and is widely used as a general indicator of health status in aging research.

# **3. Chronic Disease History**

|**Variable**|**Description**|
|---|---|
|`hc14disescn1`|History of heart attack (ever)|
|`hc14disescn2`|Has heart disease (ever)|
|`hc14disescn3`|Has high blood pressure (ever)|
|`hc14disescn4`|Has arthritis (ever)|
|`hc14disescn5`|Has osteoporosis (ever)|
|`hc14disescn6`|Has diabetes (ever)|
|`hc14disescn7`|Has lung disease (ever)|
|`hc14disescn8`|History of stroke (ever)|
|`hc14cancerty1`|History of skin cancer|

### **Purpose**

These variables capture major chronic medical conditions commonly associated with aging, disability, mortality, and quality of life.

---

# **4. Fracture and Injury History**

|**Variable**|**Description**|
|---|---|
|`hc14brokebon1`|History of hip fracture|
|`hc14brokebon2`|History of other bone fracture|

### **Purpose**

Fracture-related variables are important indicators of frailty, osteoporosis risk, mobility decline, and fall-related injuries in older adults.

---

# **5. Cognitive and Memory Health**

|**Variable**|**Description**|
|---|---|
|`cg14ratememry`|Self-rated memory|
|`cg14ofmemprob`|Frequency of memory problems interfering with activities|
|`cg14memcom1yr`|Memory compared to one year ago|

### **Purpose**

These variables evaluate participants’ perceived cognitive functioning and memory changes, which are important for studying cognitive aging and dementia risk.

---

# **6. Surgical and Medical Procedures**

|**Variable**|**Description**|
|---|---|
|`hc14knesrgyr`|Knee surgery in past 12 months|
|`hc14hipsrgyr`|Hip surgery in past 12 months|
|`hc14catrsrgyr`|Cataract surgery in past 12 months|
|`hc14backsrgyr`|Back or spine surgery in past 12 months|
|`hc14hartsrgyr`|Heart surgery in past 12 months|

### **Purpose**

These variables reflect recent major medical interventions and healthcare utilization among older adults.

---

# **7. Falls and Mobility Concerns**

|**Variable**|**Description**|
|---|---|
|`hc14fllsinmth`|Fallen in the last month|
|`hc14worryfall`|Worried about falling|
|`hc14worrylimt`|Activities limited due to fear of falling|
|`hc14faleninyr`|Fallen in the last 12 months|
|`hc14multifall`|Fallen more than once in the last 12 months|

### **Purpose**

Falls are a major cause of disability and hospitalization in older adults. These variables help assess fall risk, mobility limitations, and fear-related activity restriction.

---

# **8. Mental Health and Emotional Well-being**

|**Variable**|**Description**|
|---|---|
|`hc14depresan1`|Little interest or pleasure in doing things|
|`hc14depresan2`|Feeling down, depressed, or hopeless|
|`hc14depresan3`|Feeling nervous, anxious, or on edge|
|`hc14depresan4`|Unable to stop or control worrying|

### **Purpose**

These variables measure depressive and anxiety-related symptoms and are commonly used to evaluate mental health among aging populations.

---

# **9. Sleep Health**

|**Variable**|**Description**|
|---|---|
|`hc14aslep30mn`|Takes more than 30 minutes to fall asleep|
|`hc14trbfalbck`|Trouble falling back asleep after waking|
|`hc14sleepmed`|Frequency of using medication to help sleep|

### **Purpose**

Sleep quality is strongly associated with cognitive function, mental health, physical health, and overall well-being in older adults.

---

# **10. COVID-19 Related Variable**

|**Variable**|**Description**|
|---|---|
|`cv14covid`|Had COVID-19 in the last year|

### **Purpose**

This variable captures recent COVID-19 infection history, allowing researchers to investigate the impact of COVID-19 on aging-related health outcomes.

---

# **Notes on Variable Coding**

NHATS variables often use special codes for missing or inapplicable responses, including:

|**Code**|**Meaning**|
|---|---|
|`-1`|Inapplicable|
|`-8`|Don’t Know|
|`-9`|Missing|
|`-7`|Refused|

Researchers should properly handle these values during preprocessing and statistical analysis.

---

# **References**

- NHATS Official Website: https://www.nhats.org/
- NHATS Round 14 User Guide
- NHATS Round 14 Public Use Data Documentation
- NHATS Round 14 SP Frequency Codebook  
- NHATS Round 14 README Documentation