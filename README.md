# Predicting Loan Approval using Classification Models

## Objective

The goal of this project is to construct a machine learning model that predicts Loan Approval. We'll explore five different classificaton models: 

<div class="unordered">
<ul>
    <li>K-Nearest Neighbor (KNN)</li>
    <li>Support Vector Machine (SVM)</li>
    <li>Decision Tree</li>
    <li>Random Forest</li>
    <li>XGBClassifier</li>
<ul>
</div>

</br>
Each model will be carefully evaluated using cross-validation and performance metrics such as F1 score. After identifying the best base model, we'll fine-tune its parameters to improve its accuracy too. Finally, we'll compare the tuned model with the base one to choose the best option for predicting loan approval accurately and reliably.

## Dataset Information

This project utilizes a raw dataset sourced from kaggle.com titled *"Loan Approval Dataset"* uploaded by Rohit Sharma. The dataset comprises information on various attributes of loan applicants, including demographic details, financial status, employment history, and ownership status. The dataset includes both numerical and categorical features, making it suitable for diverse analytical approaches. For access to the dataset source, you can click [here!](https://www.kaggle.com/datasets/rohit265/loan-approval-dataset)

## Dataset Description Table

<center>

| Column Name       | Description                                                                                                         |
|-------------------|---------------------------------------------------------------------------------------------------------------------|
| ID                | Unique identifier for each loan applicant.                                                                          |
| Income            | The income level of the applicant.                                                                                  |
| Age               | Age of the applicant.                                                                                               |
| Experience        | Years of professional experience.                                                                                   |
| Married/Single    | Marital status of the applicant.                                                                                    |
| House_Ownership   | Indicates whether the applicant owns or rents a house.                                                              |
| Car_Ownership     | Indicates whether the applicant owns or rents a house.                                                              |
| Profession        | Occupation or profession of the applicant.                                                                          |
| City              | City of residence of the applicant.                                                                                 |
| State             | State of residence of the applicant.                                                                                |
| Current_Job_Yrs   | Duration of employment in the current job.                                                                          |
| Current_House_Yrs | Duration of residence in the current house.                                                                         |
| Risk_Flag         | Binary indicator of loan risk, where 1 represent a flagged risky applicant and 10 represents a non-risky applicant. |

</center>

---

# Sample Dataset

---

## Raw Dataset

<center>

|Id |Income |Age|Experience|Married/Single|House_Ownership|Car_Ownership|Profession         |CITY               |STATE         |CURRENT_JOB_YRS|CURRENT_HOUSE_YRS|Risk_Flag|
|---|-------|---|----------|--------------|---------------|-------------|-------------------|-------------------|--------------|---------------|-----------------|---------|
|1  |1303834|23 |3         |single        |rented         |no           |Mechanical_engineer|Rewa               |Madhya_Pradesh|3              |13               |0        |
|2  |7574516|40 |10        |single        |rented         |no           |Software_Developer |Parbhani           |Maharashtra   |9              |13               |0        |
|3  |3991815|66 |4         |married       |rented         |no           |Technical_writer   |Alappuzha          |Kerala        |4              |10               |0        |
|4  |6256451|41 |2         |single        |rented         |yes          |Software_Developer |Bhubaneswar        |Odisha        |2              |12               |1        |
|5  |5768871|47 |11        |single        |rented         |no           |Civil_servant      |Tiruchirappalli[10]|Tamil_Nadu    |3              |14               |1        |

</center>

## Final Dataset for Modeling

<center>

|Married/Single|House_Ownership|Car_Ownership|CITY|Age|Experience|CURRENT_JOB_YRS|CURRENT_HOUSE_YRS|Risk_feature|
|--------------|---------------|-------------|----|---|----------|---------------|-----------------|------------|
|1             |2              |1            |45  |60 |10        |5              |11               |0           |
|1             |2              |0            |280 |66 |18        |12             |10               |0           |
|1             |2              |0            |187 |59 |14        |14             |14               |0           |
|1             |2              |0            |303 |32 |3         |3              |11               |0           |
|1             |2              |0            |162 |21 |18        |8              |12               |0           |

</center>


# Model Performance


## Five Model Performance Comparison

<center>

| Metric                       | KNN    | SVC    | Decision Tree | **Random Forest** | XGBoost |
|------------------------------|--------|--------|---------------|-------------------|---------|
| **Train Score**              | 0.801  | 0.571  | 0.929         | **0.921**         | 0.805   |
| **Test Score**               | 0.7632 | 0.502  | 0.82          | **0.835**         | 0.748   |
| **Precision Train**          | 0.802  | 0.561  | 0.898         | **0.893**         | 0.794   |
| **Precision Test**           | 0.314  | 0.146  | 0.405         | **0.412**         | 0.298   |
| **Recall Train**             | 0.799  | 0.648  | 0.967         | **0.963**         | 0.825   |
| **Recall Test**              | 0.787  | 0.631  | 0.858         | **0.839**         | 0.779   |
| **F1 Score Train**           | 0.800  | 0.601  | 0.931         | **0.927**         | 0.809   |
| **F1 Score Test**            | 0.450  | 0.237  | 0.551         | **0.553**         | 0.432   |
| **Cross Validation F1 Mean** | 0.763  | 0.594  | 0.835         | **0.830**         | 0.763   |

</center>

## Random Forest vs Tuned Random Forest Performance

<center>

| Model Name             | Random Forest | Tuned Random Forest |
|------------------------|---------------|---------------------|
| **Train Score**        | **0.921**     | 0.571               |
| **Test Score**         | **0.835**     | 0.502               |
| **Precision Train**    | **0.893**     | 0.561               |
| **Precision Test**     | **0.412**     | 0.146               |
| **Recall Train**       | **0.963**     | 0.648               |
| **Recall Test**        | **0.839**     | 0.631               |
| **F1 Score Train**     | **0.927**     | 0.601               |
| **F1 Score Test**      | **0.553**     | 0.237               |
| **CV F1 Mean**         | **0.830**     | 0.594               |


</center>
