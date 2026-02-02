# Presentation Outline: Healthcare Revenue Cycle Optimization

**Project:** Predicting Financial Toxicity Risk  
**Format:** 8 slides, approximately 10-12 minutes presentation time  
**Audience:** Healthcare finance executives, revenue cycle directors, consulting partners

---

## Slide 1: Title Slide

**Visual:** Clean title with your name and tagline  
**Content:**
- Title: "Reducing Hospital Bad Debt Through Predictive Risk Scoring"
- Subtitle: "A Machine Learning Approach to Proactive Financial Assistance"
- Your Name: Riya Shet
- Date: February 2026

**Speaker Notes:**  
Good morning. Today I will walk you through a predictive analytics framework I developed to help hospitals identify patients who may struggle with medical bills before debt becomes uncollectible. This approach enables early financial counseling and assistance program enrollment, benefiting both patient financial health and hospital revenue cycles.

---

## Slide 2: The Business Problem

**Visual:** Split screen - left side shows rising medical debt statistics, right side shows hospital write-off costs  
**Content:**
- Over 100 million Americans carry medical debt
- Hospitals write off billions in bad debt annually
- Traditional systems react to non-payment rather than prevent it
- Missed opportunities for patient assistance and revenue protection

**Key Message:** "We need to shift from reactive collections to proactive intervention"

**Speaker Notes:**  
The challenge facing healthcare finance teams is that traditional revenue cycle systems only identify problems after bills go unpaid for months. By that point, patients may have already damaged their credit, and hospitals have spent resources on collection efforts that could have been avoided. What if we could identify high-risk patients at the point of care and offer help immediately?

---

## Slide 3: Our Approach

**Visual:** Flowchart showing: EHR Data → Feature Engineering → ML Model → Risk Score → Intervention  
**Content:**
- Data Source: Electronic health record clinical and demographic data
- Modeling Method: Random Forest classification with cross-validation
- Key Predictors: Comorbidity count, income, age, insurance status
- Outcome: Binary classification of high-risk vs. standard-risk patients

**Key Message:** "Leverage data already in your EHR system—no new data collection required"

**Speaker Notes:**  
Our approach uses only routinely collected information that healthcare systems already have: diagnosis codes, basic demographics, and insurance information. We do not require patients to fill out financial surveys or wait for external socioeconomic data. This makes the model practical to deploy quickly. The Random Forest algorithm handles the complexity of interactions between variables while remaining interpretable for healthcare stakeholders.

---

## Slide 4: Model Performance

**Visual:** Precision-Recall curve showing model performance vs. baseline, plus key metrics table  
**Content:**
- Average Precision: 0.206 (9.4× better than random baseline)
- Cross-Validated F1 Score: 0.235 (after hyperparameter tuning)
- Handled severe class imbalance (only 2.1% high-risk prevalence)
- Robust evaluation using stratified 5-fold cross-validation

**Key Message:** "Meaningful risk stratification from simple features alone"

**Speaker Notes:**  
While the absolute performance numbers may seem modest, they represent significant signal extraction from a very sparse feature set. In bad debt prediction, even modest improvements translate to real financial impact because of the large dollar amounts involved. The 9.4-times improvement over random chance means the model can meaningfully prioritize which patients to focus intervention resources on. With richer data in a production setting, we would expect stronger performance.

---

## Slide 5: Critical Insight - Comorbidity as the Key Driver

**Visual:** Feature importance comparison chart showing comorbidity dominating, income minimal, age negative  
**Content:**
- Comorbidity count: Only feature with genuine predictive power
- Income contribution: Minimal (likely due to data limitations)
- Age: Actually degraded model performance
- Insurance status: Negligible impact once comorbidity is considered

**Key Message:** "Clinical complexity drives financial risk—and we already track it in the EHR"

**Speaker Notes:**  
This is the most operationally important finding. Comorbidity count—how many medical conditions a patient has—was the strongest and only reliable predictor of payment risk. This makes intuitive sense: patients with multiple chronic conditions hit their deductibles repeatedly and face greater care coordination challenges. But here is the powerful part: this data is already in your EHR system. You do not need to integrate external socioeconomic databases or wait for income verification. A simple rule flagging patients with three or more active diagnoses would capture most high-risk cases.

---

## Slide 6: Business Impact and ROI Potential

**Visual:** Diagram showing intervention pathway and potential cost savings  
**Content:**
- **Intervention Point:** Flag high-risk patients during registration
- **Actions:** Financial counseling, payment plan setup, charity care screening
- **Patient Benefits:** Avoid debt, credit damage, and care delays
- **Hospital Benefits:** Reduced bad debt write-offs, improved patient satisfaction, better revenue cycle efficiency

**ROI Scenario Example:**
- Hospital writes off $2M annually in bad debt
- Model identifies 60% of would-be write-offs for early intervention
- Even 25% conversion through payment plans = $300K recovered revenue
- Plus: improved patient retention and satisfaction scores

**Key Message:** "Proactive intervention creates value for both patients and revenue cycle"

**Speaker Notes:**  
The business case for this approach is compelling because it creates aligned incentives. Patients benefit from early financial assistance before debt becomes overwhelming. Hospitals benefit from recovering revenue that would have been written off and from improved patient satisfaction scores, which increasingly tie to reimbursement. A conservative estimate: if this model helps convert even 25% of would-be write-offs into managed payment plans, a hospital with $2 million annual bad debt could recover $300,000 while improving patient experience.

---

## Slide 7: Implementation Roadmap

**Visual:** Three-phase timeline graphic  
**Content:**

**Phase 1 - Pilot (Months 1-3):**
- Configure automated risk scoring in EHR workflow
- Train financial counselors on high-risk patient protocols
- Establish baseline metrics: bad debt write-offs, patient satisfaction

**Phase 2 - Intervention (Months 4-9):**
- Launch targeted financial counseling for flagged patients
- Develop segmented payment plan offerings for complex care
- Monitor intervention effectiveness and patient outcomes

**Phase 3 - Scale and Optimize (Months 10-12):**
- Refine risk model with real payment data
- Expand to all service lines
- Integrate with charity care eligibility workflows

**Key Message:** "Practical implementation in under one year"

**Speaker Notes:**  
Implementation follows a phased approach that minimizes disruption. We start with a pilot in a single department to validate the model on real data and train staff on new workflows. Once we have proven intervention effectiveness, we scale systematically. The beauty of this approach is that it builds on existing EHR infrastructure—we are not asking you to implement an entirely new system, just add a risk score calculation and trigger point for financial counseling.

---

## Slide 8: Key Takeaways and Next Steps

**Visual:** Clean summary with three main points and call to action  
**Content:**

**What We Demonstrated:**
- Bad debt prediction is feasible using routine clinical data
- Comorbidity is the strongest driver—already captured in your EHR
- Proactive intervention benefits both patients and revenue cycle

**What Production Deployment Requires:**
- Validation on your historical claims data
- Integration with existing financial counseling workflows
- Ongoing model monitoring for fairness and accuracy

**Next Steps:**
- Pilot study in a single department or service line
- Measure baseline bad debt and intervention effectiveness
- Refine model with institution-specific payment patterns

**Call to Action:** "Let's discuss how this framework can be adapted to your revenue cycle challenges"

**Speaker Notes:**  
To summarize: we have demonstrated that meaningful bad debt risk stratification is achievable with data healthcare systems already collect. The methodology I have shown here is ready to be adapted to real institutional data. The next step would be a pilot study where we validate the model on your historical claims and measure the actual impact of early financial interventions. I would welcome the opportunity to discuss how this approach could address your specific revenue cycle challenges and patient financial assistance goals. Thank you.

---

## Appendix Slides (Optional - Use if Q&A requires detail)

**Appendix A: Technical Methodology Details**
- Feature engineering process
- Hyperparameter tuning approach
- Cross-validation strategy
- Feature importance calculation methods

**Appendix B: Data Privacy and Ethics**
- This analysis used fully synthetic data (no real patients)
- Production deployment requires HIPAA-compliant de-identification
- Fairness evaluation across demographic groups essential
- Transparent model governance and appeal processes

**Appendix C: Alternative Use Cases**
- Preventive care outreach prioritization
- Care coordination resource allocation
- Value-based contract risk adjustment
- Population health management targeting

---

## Presentation Tips

**Timing:** Aim for 10-12 minutes, leaving 3-5 minutes for questions in a 15-minute slot.

**Emphasis:** Spend the most time on Slides 5-6 (the business insight and impact). This is where you differentiate yourself as a consultant who translates technical findings into actionable recommendations.

**Audience Adaptation:**  
- For finance executives: Emphasize ROI and revenue protection (Slides 6-7)
- For clinical leaders: Emphasize patient benefit and care coordination (Slide 5)
- For consulting partners: Emphasize methodology rigor and generalizability (Slides 3-4)

**Q&A Preparation:** Anticipate questions about:
- How this compares to third-party credit scoring services
- Whether this could inadvertently discriminate against sicker patients
- Integration complexity with existing revenue cycle systems
- Scalability to multi-hospital systems

---

**File Format Recommendations:**
- Export to PDF for broadest compatibility
- Consider PowerPoint version if you want to customize for specific audiences
- Use high-resolution versions of charts from the analysis notebook

**Chart Sources:**  
All charts reference figures generated in `notebooks/ftr_analysis_complete.ipynb`. Export these at 300 DPI for presentation quality.

---

**Prepared By:** Riya Shet  
**Date:** February 2026  
**Contact:** [GitHub: @riyashet](https://github.com/riyashet)
