# AI Ethics Assignment: Written Responses

## Part 1: Theoretical Understanding (30%)

### 1. Short Answer Questions

#### Q1: Define algorithmic bias and provide two examples of how it manifests in AI systems.

**Definition:**  
Algorithmic bias refers to systematic errors in an AI system's output that result in unfair, prejudiced, or inequitable outcomes for specific groups of people. These biases often originate from skewed, incomplete, or historically prejudiced training data, but can also arise from flawed model design or misalignment between the model’s intended use and real-world deployment.

**Examples:**

- **Facial Recognition:** Early facial recognition systems trained primarily on light-skinned male faces exhibited significantly higher error rates for women and individuals with darker skin tones, leading to real-world cases of misidentification and wrongful accusations.

- **Loan Approval Systems:** AI models trained on historical lending data that reflected past discriminatory practices (e.g., denying loans to applicants from certain zip codes or minority groups) learned and perpetuated these patterns, continuing to reject qualified applicants based on biased proxies.

---

#### Q2: Explain the difference between transparency and explainability in AI. Why are both important?

**Difference:**

- **Transparency** refers to the openness of an AI system’s design, development, and deployment—answering questions like: *What data was used? What model architecture was chosen? Who built it? What assumptions were made?*

- **Explainability** (or interpretability) refers to the ability to understand *why* a specific decision was made—e.g., *What features led the model to deny a loan?* It focuses on making the internal logic of complex models understandable to humans.

**Importance:**  
Both are essential for **trust, accountability, and fairness**.

- **Transparency** enables external audits, regulatory compliance, and early detection of systemic risks like data bias.
- **Explainability** empowers individuals to challenge, appeal, or understand automated decisions that affect them directly—critical for due process and ethical recourse.

---

#### Q3: How does GDPR impact AI development in the EU?

GDPR imposes strict requirements on AI systems that process personal data:

- **Data Minimization:** AI systems must collect and process only the personal data strictly necessary for their purpose—challenging for data-intensive models.
- **Lawful Basis for Processing:** Explicit, informed, and revocable user consent is required before processing personal data.
- **Right to Explanation (Article 22):** Individuals have the right not to be subject to decisions based solely on automated processing. While legally nuanced, this strongly encourages the use of interpretable models and meaningful explanations for high-stakes decisions.
- **Data Protection by Design:** Privacy and data protection must be integrated into the AI system from the outset—not added as an afterthought.

---

### 2. Ethical Principles Matching

| Principle         | Description |
|------------------|-------------|
| **A) Justice**           | Fair distribution of AI benefits and risks. |
| **B) Non-maleficence**   | Ensuring AI does not harm individuals or society. |
| **C) Autonomy**          | Respecting users’ right to control their data and decisions. |
| **D) Sustainability**    | Designing AI to be environmentally friendly. |

---

## Part 2: Case Study Analysis (40%)

### Case 1: Biased Hiring Tool

#### 1. Identify the source of bias:
The bias stemmed from **historical hiring data** that reflected a male-dominated tech industry. The AI learned to associate male-associated terms (e.g., “women’s chess club captain”) or attendance at all-women’s colleges as negative signals, directly encoding past human discrimination into its decision logic.

#### 2. Propose three fixes:

1. **Data Remediation (Pre-processing):**  
   - Rebalance training data by oversampling successful female candidates.  
   - Remove gender-proxied features (e.g., club names, college names) to prevent the model from learning spurious correlations.

2. **Model Constraint (In-processing):**  
   - Integrate fairness constraints during training (e.g., optimize for both accuracy and equal opportunity) to ensure similar true positive rates across genders.

3. **Human-in-the-Loop (Post-processing):**  
   - Use AI to generate a **diverse shortlist** (e.g., balanced by gender), with final hiring decisions made by human recruiters trained in unconscious bias mitigation.

#### 3. Suggest metrics to evaluate fairness:

- **Disparate Impact Ratio (DIR):**  
  `Selection Rate (Women) / Selection Rate (Men)` → Target ≥ 0.8 (80% rule).
  
- **Equal Opportunity Difference:**  
  Difference in **true positive rates** between groups → Target ≈ 0.
  
- **Statistical Parity Difference:**  
  `Selection Rate (Women) – Selection Rate (Men)` → Target ≈ 0.

---

### Case 2: Facial Recognition in Policing

#### 1. Discuss ethical risks:

- **Wrongful Arrests:** High false positive rates for minorities can lead to innocent people being detained or charged.
- **Pervasive Surveillance:** Constant monitoring chills freedom of assembly and expression (e.g., avoiding protests).
- **Reinforcement of Systemic Bias:** False matches in over-policed neighborhoods fuel a feedback loop of increased surveillance and discrimination.
- **Privacy Violations:** Biometric data is collected without consent, violating bodily and informational privacy.

#### 2. Recommend policies for responsible deployment:

- **Ban in High-Stakes Scenarios:** Prohibit use for real-time suspect identification (e.g., live bodycams) until accuracy is near-perfect across all demographics.
- **Mandatory Human-in-the-Loop:** Treat AI matches as **investigative leads only**, requiring independent human verification before any legal action.
- **Public Transparency & Audits:**  
  - Publish error rates by race, gender, and age.  
  - Require independent third-party audits.
- **Clear Legal Framework:**  
  - Require judicial warrants for deployment.  
  - Limit data retention.  
  - Guarantee legal recourse for misidentified individuals.

---

## Part 4: Ethical Reflection (5%)

> *Note: This is a personal reflection. Adapt the example to your own project.*

**Project Idea:**  
A mobile app that uses computer vision to scan food and provide nutritional info and healthy recipe suggestions.

**Ethical Adherence Plan:**

- **Justice & Accessibility:**  
  Avoid a “health gap” by training the model on globally diverse foods—including non-Western dishes, irregular produce, and cultural cuisines. Ensure accessibility features (e.g., screen reader support).

- **Non-maleficence:**  
  Never guess. If model confidence < 95%, respond: “I’m not sure what this is.” Use only verified nutrition databases (e.g., USDA) and include clear disclaimers for users with medical conditions.

- **Autonomy & Privacy:**  
  Process images **on-device** whenever possible. If cloud processing is needed, anonymize data and obtain **explicit opt-in consent** with a transparent privacy policy.

---

## Bonus Task: 1-Page Guideline for Ethical AI in Healthcare

### **A Framework for Trustworthy AI in Patient Care**

#### 1. Guiding Principle: Patient Well-being and Autonomy  
AI must **augment—not replace—clinical judgment**, with the primary goal of improving patient safety, outcomes, and autonomy.

#### 2. Patient Consent and Transparency  
- **Informed Consent:** Patients must be clearly told when AI is used in their care—in plain language.  
- **Right to Opt-Out:** Where feasible, patients may choose non-AI-assisted care without penalty.  
- **Data Use Disclosure:** Explain how (anonymized) data will train future models and obtain explicit consent.

#### 3. Bias Mitigation and Equity  
- **Mandatory Bias Audits:** Test performance across race, sex, age, and other clinically relevant groups.  
- **No Deployment if Biased:** Systems with clinically significant performance gaps (e.g., skin cancer detection failing on dark skin) must not be used.  
- **Document Limitations:** If training data lacks diversity, flag this to clinicians at the point of care.

#### 4. Transparency and Explainability for Clinicians  
- **Clinician-in-the-Loop Required:** AI supports decisions—it never makes autonomous medical judgments.  
- **Explainable Outputs:** Provide clear, actionable reasons for AI recommendations (e.g., “High sepsis risk due to elevated lactate + low BP”).  
- **Accountability:** Legal and professional responsibility remains with the **clinician and institution**, not the AI.

---
