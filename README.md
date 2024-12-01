# ML-Concepts

## MCAR, MAR, MNAR
## Scenario: A Study on Patient Health and Medication Adherence

Imagine a clinical study where researchers are tracking medication adherence (whether patients take their prescribed medication as directed) and various other health-related metrics like blood pressure, cholesterol levels, and age.

**Observed Variables**:  
- Age  
- Blood Pressure  
- Cholesterol Levels

**Unobserved Variable**:  
- Medication Adherence (whether or not a patient took their medication regularly, which is being self-reported by patients)

## Types of Missing Data

### MCAR (Missing Completely at Random)
Missingness occurs due to a random reason.  
Example: 
- Technical glitches
- Forgetting to fill out the form

### MAR (Missing at Random)
Missingness occurs due to a systematic reason related to observed data.  
Example: 
- Older patients do not give the survey because they are not comfortable with online forms.
- Patients with lower education do not give the survey because they are unaware of technology.

### MNAR (Missing Not at Random)
Missingness occurs due to reasons related to unobserved data, and the missing data cannot be explained by observed data.  
Example:
- People who did not follow their medication regimen feel guilty or embarrassed, and therefore choose not to report it.


` Missing Data : Data that is not available or has not been recorded for some reason.`

` Observed Data: Data that has been collected and is available for analysis.`

## Explanation in Detail

### MCAR Example (Missing Completely at Random)

In the MCAR scenario, the missingness of the medication adherence data is not related to any characteristic of the patients, either observed or unobserved. In other words, the patients who didn’t report their medication adherence could have done so for purely random reasons (e.g., a technical issue, forgetting to fill out the survey, or being distracted at the time they were asked to provide the data).

**Real-Life MCAR Scenario:**

- Imagine that patients are asked to self-report their medication adherence through an online portal every month.
- Some patients forget to fill out the survey. Others may face technical issues (e.g., the website crashes, or they can't access the portal due to internet connectivity issues).
- In some cases, a few patients skip the survey by accident because they are busy with work, family, or other commitments.

The key point here is that the patients who miss reporting their adherence are not doing so because of their medication adherence itself (whether they are adhering or not). The missingness of the data is completely random and is not dependent on whether they are adherent or not, or on any other factors such as age, gender, income, or health conditions.

**Why It’s MCAR:**

- The missingness is completely random — it's not related to any observed variables (like age, gender, blood pressure, or cholesterol levels), and it is not related to the unobserved data (whether or not the patient is adhering to their medication).
  
For instance:
- If a patient forgets to fill out the survey, that’s a random event, unrelated to the patient's health condition, age, or any other factor in the study.
- Similarly, if another patient experiences technical difficulties while submitting their medication adherence data, that too is unrelated to their adherence behavior.

**In Practice:**

In this case, since the missingness of the data is random, it is safe to assume that the missing values won’t introduce bias into the analysis, because the data is not systematically missing for any specific group of patients.

**How to Handle MCAR:**

When the missing data is MCAR, it’s often straightforward to handle:

- **Deletion**: You can simply drop the rows with missing data (this is called listwise deletion). Since the missingness is random, the remaining data will still be representative of the overall population.
- **Imputation**: You can impute the missing data using basic methods like mean imputation, median imputation, or multiple imputation without introducing much bias, because the missingness is random and not related to any observed or unobserved variables.

---

### MAR Example (Missing at Random):

In this case, **Missing at Random** means the probability of missing medication adherence data is related to other observed variables but not related to the missing medication adherence values themselves.

**Scenario:**

- Age and Education Level are observed variables that we can track for each patient.
- The probability that a patient does not report their medication adherence may be higher in older patients or those with lower education levels. Older patients may be less comfortable using the online system for reporting, or those with less education might have difficulty understanding the survey questions.
- However, the missingness of the Medication Adherence data is not related to how well the patient is actually adhering to their medication. In other words, patients who miss reporting their medication adherence are not more or less likely to be non-adherent in terms of their actual medication-taking behavior.

**Why It’s MAR:**

- The missingness is related to observed factors (like age and education level), but it is not dependent on the unobserved value (i.e., whether or not the patient actually adhered to the medication).

**Handling MAR:**

- In this case, you could use techniques like **Multiple Imputation** to fill in the missing values for medication adherence, as the missingness is related to observable variables, and you can model it using these variables.

---

### MNAR Example (Missing Not at Random):

In this case, **Missing Not at Random** means that the probability of missing medication adherence data depends on the missing values themselves (i.e., patients are more likely to miss reporting their medication adherence because they have lower adherence).

**Scenario:**

- Self-reporting of medication adherence is prone to biases, especially when the adherence is low. Patients who are not adhering to their medication regularly may feel guilty or embarrassed about it and therefore choose not to report their adherence.
- The missingness is not random, but rather it is specifically related to the unobserved value — in this case, the level of medication adherence. If a patient is not taking their medication as prescribed, they may not report it.

**Why It’s MNAR:**

- The missingness is directly tied to the unobserved value: if the patient is non-adherent to their medication, they are more likely to omit or skip reporting that information.
- In this case, the missing data isn’t just random or dependent on other observable characteristics (like age or education). It's specifically tied to the missing data itself (whether or not the patient took their medication).

**Handling MNAR:**

- Handling MNAR data is more challenging. Standard imputation methods (like multiple imputation or using observed variables) may not be sufficient, as the missingness mechanism itself depends on the unobserved values.
- You might need sensitivity analysis, selection models, or pattern-mixture models to handle the missing data, and you would need to make assumptions about how non-adherence might influence missingness.
---  
