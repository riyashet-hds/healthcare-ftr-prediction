# Case Study: Reducing Hospital Bad Debt Through Predictive Risk Scoring

**Client Context:** Healthcare Revenue Cycle Management  
**Project Type:** Predictive Analytics for Financial Risk Stratification  
**Methodology:** Machine Learning Classification with Feature Importance Analysis  
**Impact:** 9.4× improvement in identifying high-risk patients for early intervention

---

## Business Challenge

American hospitals write off billions in bad debt annually while millions of patients struggle with medical bills they cannot afford. Traditional revenue cycle systems react to non-payment after it occurs, missing opportunities to provide financial assistance before debt becomes uncollectible. The challenge was to develop a proactive risk scoring system that identifies patients likely to face payment difficulties, enabling early financial counseling and assistance program enrollment.

The analysis needed to use only routinely available data from electronic health records and claims systems, avoiding external data dependencies that would slow deployment. Most critically, the model needed to be interpretable and explainable for healthcare finance stakeholders who require transparency in any automated decision support system.

---

## Analytical Approach

I developed a supervised machine learning framework using Random Forest classification on synthetic electronic health record data from 1,701 patients. The analysis focused on four key predictors identified in financial toxicity literature: clinical complexity (comorbidity count), socioeconomic status (income), demographic factors (age), and insurance coverage status.

The modeling pipeline addressed several technical challenges inherent in bad-debt prediction. First, severe class imbalance required balanced class weights and stratified cross-validation, since only 2.1% of the patient cohort met high-risk criteria. Second, I used Precision-Recall metrics rather than standard accuracy measures, following best practices for imbalanced classification where the positive class is rare. Third, I implemented dual feature importance analysis using both Mean Decrease in Impurity and permutation importance to identify truly predictive features versus spurious correlations.

The model was trained and validated using five-fold cross-validation to ensure robust performance estimates despite the limited number of positive cases. Hyperparameter tuning was conducted systematically, improving model F1 score by 61% relative to the baseline configuration.

---

## Key Findings

The optimized model achieved a cross-validated Average Precision score of 0.206, representing a 9.4-fold improvement over the random baseline of 0.022. While this appears modest in absolute terms, it demonstrates meaningful risk stratification from simple clinical and demographic features alone. Real-world deployment with richer data would likely achieve stronger performance.

The most striking finding came from the feature importance analysis. Comorbidity count was the only predictor with genuine predictive power, while income contributed minimally and age actually degraded model performance when included. This contradicts the initial hypothesis that socioeconomic factors would dominate, but it aligns with clinical reality: patients with multiple chronic conditions face higher out-of-pocket costs through repeated deductible hits and greater care coordination challenges.

This insight is operationally powerful because comorbidity data is already captured in EHR systems at the point of care, requiring no external data integration or patient questionnaires. A simple rule flagging patients with three or more active diagnoses for financial counseling would capture the majority of high-risk cases.

---

## Business Impact and Recommendations

The analysis demonstrates a practical pathway for healthcare systems to implement risk-based financial assistance targeting. Rather than waiting for billing statements to go unpaid, hospitals can proactively identify high-risk patients during registration and offer payment planning, charity care screening, or financial navigation services before debt accumulates.

I recommend three implementation priorities for healthcare finance teams. First, configure automated risk scoring in the EHR workflow, flagging high-comorbidity patients for financial counselor review. Second, pilot a targeted intervention program measuring impact on both bad debt write-offs and patient satisfaction scores. Third, develop segmented payment plan offerings that recognize medically complex patients may need longer timelines and lower monthly payments than standard plans offer.

For revenue cycle consultants positioning predictive analytics solutions, this analysis demonstrates that meaningful risk stratification is achievable with modest feature sets already available in most healthcare systems. The key is not data volume but careful feature engineering and model interpretation. Consultants should emphasize patient-centric outcomes alongside revenue protection, framing financial assistance as a retention and equity strategy rather than pure collections optimization.

The model developed here was trained on synthetic data and would require validation on real claims data before production deployment. However, the methodology provides a template that can be adapted to any healthcare system with access to diagnosis codes and basic demographic data.

---

## Methodology Note

This analysis used fully synthetic patient data generated by Synthea, an open-source healthcare data simulator. All results demonstrate methodological feasibility using realistic data structures without exposing any real patient information. The modeling approach and business framework are designed to be deployable on actual de-identified EHR data in HIPAA-compliant healthcare settings.

**Technical Stack:** Python (pandas, scikit-learn), Random Forest classification, cross-validated evaluation, permutation feature importance  
**Repository:** [github.com/riyashet-hds/healthcare-ftr-prediction](https://github.com/riyashet-hds/healthcare-ftr-prediction)

---

**Riya Shet** | Quantitative Consultant | Health Economics & Predictive Modeling  
Available for healthcare analytics and revenue cycle optimization projects
