
# CS 598 DLH Final Project

**Name:** Fabio Vera

**Team:** 133

**Project:** 11

**Github link:** https://github.com/fverac/cs589dlh

**Video link:** https://www.youtube.com/watch?v=ymaahdX9844

**Reproducing:** "Predicting 30-days mortality for MIMIC-III patients with sepsis-3: a machine learning approach using XGboost."

# Project setup / Installation

The two prerequisites needed to be able to run the notebook are to:
1. Obtain MIMIC-III data, and
2. Set up your environment.


### MIMIC-III

Data is all from MIMIC III v1.4, which "is a large, freely-available database comprising deidentified health-related data associated with over forty thousand patients who stayed in critical care units of the Beth Israel Deaconess Medical Center between 2001 and 2012. The database includes information such as demographics, vital sign measurements made at the bedside (~1 data point per hour), laboratory test results, procedures, medications, caregiver notes, imaging reports, and mortality (including post-hospital discharge)."

Data can be obtained from this link after completing the required training.
https://physionet.org/content/mimiciii/1.4/

Precomputed features like first-day vital signs and many more were obtained from Google BigQuery, which in addition to storing 
More information as well as underlying code for creating these precomputed/derived tables can be found here: 
https://github.com/MIT-LCP/mimic-code/tree/main/mimic-iii/concepts

Additionally, here are some resources for accessing MIMIC through BigQuery:
https://mimic.mit.edu/docs/gettingstarted/cloud/bigquery/

Tables needed:
1. Raw MIMIC-III tables
    1. D_ICD_DIAGNOSES
    2. DIAGNOSES_ICD
2. Precomputed MIMIC concepts
    1. icustay_detail
    2. labs_first_day
    3. heightweight
    4. vitals_first_day
    5. gcs_first_day
    6. elixhauser_ahrq_v37
    7. ventilation_first_day
    8. rrt_first_day
    9. urine_output_first_day
    10. sapsii
    11. sofa
    12. qsofa

The notebook expects the raw uncompressed MIMIC-III csv's to reside in the ```mimic-iii-clinical-database-1.4``` directory, and similarly expects the precomputed mimic concepts files to live in the ```mimic_concepts``` directory. 


### Setting up the environment 

For convenience, an environment.yml file is provided for reproducibility, for use with Conda. To create the project environment one can use the following command

```
conda env create -f environment.yml
conda activate dlh_final_proj
```

In the event that Conda is not possible to use, key environment details are below:
```
python 3.9.12
sklearn 1.0.2
pandas 1.4.2
numpy 1.21.5
xgboost 2.0.3
```
