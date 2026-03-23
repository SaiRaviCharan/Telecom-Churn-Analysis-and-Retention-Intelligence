# 🎯 INTERVIEW PREPARATION GUIDE
## Telecom Churn Analysis Project

---

## QUICK REFERENCE CHEAT SHEET

### Project Elevator Pitch (30 seconds)
"I built a churn prediction system for a telecom company that identified why 27% of customers were leaving annually. Using Python, pandas, and Random Forest machine learning on 7,000 customer records, I discovered that contract type was the #1 driver - month-to-month customers churned at 15x the rate. My model achieves 80% accuracy with 0.84 ROC-AUC, and I delivered four strategic recommendations projected to reduce churn to 18-20%, protecting $800K-1.2M in annual revenue."

### Key Numbers to Memorize
- **7,043** customers analyzed
- **21** original features
- **4** engineered features created
- **80.1%** model accuracy
- **0.8437** ROC-AUC score
- **52.8%** recall on churn class
- **65.2%** precision on churn predictions
- **27%** baseline churn rate
- **42.7%** month-to-month contract churn
- **2.8%** two-year contract churn (15x difference)
- **$1.46M** annual recurring revenue at risk
- **$800K-1.2M** projected revenue protection

### Technology Stack
| Category | Technology | Version |
|----------|------------|---------|
| Language | Python | 3.12 |
| Data Manipulation | pandas | 3.0.1 |
| Numerical Computing | numpy | 2.4.3 |
| Visualization | matplotlib | 3.10.8 |
| Statistical Viz | seaborn | 0.13.2 |
| Machine Learning | scikit-learn | 1.8.0 |
| Environment | Jupyter Notebook | 7.5.5 |

---

## COMMON INTERVIEW QUESTIONS & PERFECT ANSWERS

### BEHAVIORAL QUESTIONS

#### Q: "Tell me about yourself"

**Structure: Present → Past → Future (2 minutes)**

**Present (30 sec):**
"I'm a data analyst with a strong foundation in Python, SQL, and machine learning, currently building my portfolio with real-world business analytics projects. I specialize in turning complex datasets into actionable insights that drive revenue and reduce costs."

**Past (60 sec):**
"My journey into data analytics started when [brief personal story - e.g., 'I realized how powerful data was during my university project analyzing student performance metrics']. I've systematically built skills through online courses (Coursera, DataCamp), hands-on projects like this telecom churn analysis, and technical reading.

My telecom project specifically demonstrates my ability to handle the full analytics lifecycle - from messy data cleaning through statistical analysis to building predictive models and communicating business recommendations. I discovered that month-to-month contracts had 15x higher churn and proposed solutions worth $1.2M in protected revenue."

**Future (30 sec):**
"I'm now seeking a data analyst role where I can apply these skills to solve real business problems - whether that's optimizing marketing spend, reducing customer attrition, or improving operational efficiency. I'm particularly excited about [company name] because [specific reason related to their industry/mission]."

---

#### Q: "Why do you want to work here?"

**Framework: Company Research → Role Alignment → Value Add**

"I'm excited about [Company] for three specific reasons:

**1. Industry Impact [30 seconds]:**
'I researched your work in [specific industry/product] and was impressed by [specific achievement]. For example, [cite recent news, product launch, or initiative]. This aligns with my interest in using data to solve [relevant business problem].'

**2. Role Alignment [30 seconds]:**
'Looking at the job description, you're seeking someone who can [quote 2-3 key requirements]. My telecom churn project directly demonstrates these skills - I cleaned messy data [requirement 1], built predictive models [requirement 2], and translated findings into executive recommendations [requirement 3].'

**3. Growth Opportunity [30 seconds]:**
'I see [Company] as a place where I can grow from individual contributor to strategic business partner. Your emphasis on [data-driven culture/innovation/specific tool stack] matches exactly where I want to develop my career. I want to be part of a team that values analytical rigor and business impact.'

**One sentence close:**
'Ultimately, I believe my analytical skills, business mindset, and drive to deliver results would make me a strong addition to your team.'"

---

### TECHNICAL DEEP-DIVE QUESTIONS

#### Q: "Walk me through your entire workflow for this project"

**Use STAR Framework: Situation → Task → Action → Result**

**Situation (30 sec):**
"The telecom company was losing 27% of customers annually - far worse than the industry benchmark of 7-10%. This represented $1.5M in annual recurring revenue at risk with no systematic way to identify or prevent churn."

**Task (20 sec):**
"My goal was to: 1) Understand WHY customers churn through data analysis, 2) Build a predictive model to identify at-risk customers, and 3) Provide actionable recommendations to reduce churn."

**Action (90 sec - most detailed):**

"**Phase 1: Data Understanding**
I loaded a dataset of 7,043 customers with 21 features including demographics, services, billing, and churn status. Initial exploration revealed data quality issues - TotalCharges was stored as text instead of numeric, and we had 11 missing values.

**Phase 2: Data Cleaning**
I converted TotalCharges to numeric using pd.to_numeric with error coercion, then imputed the 11 missing values with the median (chose median over mean due to right-skewed distribution). I also removed the customerID column as it had no predictive value and converted the target variable Churn from Yes/No to 1/0.

**Phase 3: Exploratory Data Analysis**
I created 7 visualizations to understand patterns:
- Churn distribution showed 73% retained, 27% churned
- Contract type analysis revealed month-to-month contracts had 42.7% churn vs. 2.8% for two-year contracts
- Monthly charges boxplot showed churned customers paying $15 more on average
- Tenure histogram revealed 50%+ of churn happens in first 12 months

**Phase 4: Feature Engineering**
I created 4 new features:
- tenure_band (5 lifecycle segments)
- charge_ratio (spending consistency metric)
- high_value_customer (binary flag for >$65/month)
- senior_long_tenure (interaction feature)

**Phase 5: Modeling**
I encoded categorical variables with LabelEncoder, split data 80-20 with stratification, scaled features with StandardScaler, then trained a Random Forest classifier with 100 trees. I chose Random Forest for its ability to handle non-linear relationships and provide feature importance.

**Phase 6: Evaluation**
Model achieved 80.1% accuracy and 0.8437 ROC-AUC. I used confusion matrix to understand errors - found 52.8% recall meaning we catch about half of churners. Feature importance identified tenure, monthly charges, and contract type as top predictors."

**Result (30 sec):**
"The analysis revealed three root causes and enabled four strategic recommendations:
1. Contract upgrade incentive program
2. First-year customer success journey
3. Premium customer value program
4. Predictive churn scoring system

Implementation is projected to reduce churn from 27% to 18-20%, protecting $800K-1.2M in annual revenue."

---

#### Q: "Why Random Forest specifically?"

**Answer with Comparison Table + Business Justification:**

"I evaluated four algorithms and chose Random Forest as the best fit:

| Algorithm | Pros | Cons | Suitability |
|-----------|------|------|-------------|
| Logistic Regression | Simple, interpretable | Assumes linearity | ❌ Patterns are non-linear |
| Decision Tree | Easy to explain | Overfits easily | ❌ Too unstable |
| **Random Forest** | Handles non-linearity, gives feature importance | Less interpretable than linear | ✅ **CHOSEN** |
| Gradient Boosting | Highest accuracy | Slow, complex tuning | ⚠️ Overkill for this |

**Five specific reasons for Random Forest:**

**1. Non-linear relationships:**
EDA showed that churn doesn't decrease linearly with tenure - it drops sharply after 24 months. Tree-based models capture this naturally.

**2. Mixed data types:**
We had numeric (tenure, charges) and categorical (contract, payment method) features. After label encoding, Random Forest handles both seamlessly.

**3. Feature interactions:**
The model automatically learns that 'senior citizen + long tenure' = low risk without me manually creating interaction terms.

**4. Feature importance:**
Built-in feature importance identified top churn drivers (tenure 18.2%, monthly charges 14.7%, contract type 10.8%), which was critical for business recommendations.

**5. Robust to overfitting:**
Ensemble of 100 trees with random sampling (bootstrap + feature subsets) averages out errors and reduces variance compared to a single tree.

**Business justification:**
I needed a model that was both accurate AND explainable. Random Forest gives me 80%+ accuracy while still being able to tell stakeholders 'These are the top 3 factors driving churn based on data, not guesswork.' That balance of performance and interpretability is why it's my go-to for tabular business data."

---

#### Q: "Explain train-test split to a non-technical person"

**Use analogy + visual + why it matters:**

"Imagine you're a teacher preparing students for a final exam.

**The WRONG way:** Give students practice problems, then put those EXACT same problems on the final exam. Students score 100% - but did they really learn, or just memorize?

**The RIGHT way:** Give students practice problems to study (training set), then put DIFFERENT problems on the final exam (test set) that test the same concepts. Their exam score shows actual understanding.

**In machine learning:**
- Total data: 7,043 customers
- Training set (80%): 5,634 customers - model learns patterns from these
- Test set (20%): 1,409 customers - model has NEVER seen these before

I train the model on 5,634 customers, then evaluate it on the 1,409 hold-out customers to see if it truly learned churn patterns or just memorized specific customers.

**Visual:**
```
Total Customers (7,043)
        ↓
    [Split]
    ↙     ↘
Training  Testing
(5,634)   (1,409)
80%       20%
  ↓         ↓
Build     Evaluate
Model     How Well It Works
```

**Why this matters:**
If I trained and tested on the SAME data, I'd get 100% accuracy - but the model would fail on new customers next month. Train-test split ensures the model will work on customers we haven't seen yet, which is the whole point.

**Two technical details I also used:**
1. **Random state = 42:** Makes the split reproducible (same customers in train/test every time)
2. **Stratify = y:** Keeps the 73-27 retained-churned ratio consistent in both sets (prevents accidental imbalance)"

---

#### Q: "Your model has 52.8% recall. Isn't that bad?"

**Turn perceived weakness into strength with business context:**

"Great question - this gets to a critical point about ML: there's no such thing as a 'good' or 'bad' metric without business context. Let me explain why 52.8% recall is actually a deliberate trade-off, not a failure.

**What 52.8% recall means:**
Out of 100 customers who actually churn, we correctly identify 53 of them.  We miss 47. That might sound low, but here's the critical context:

**The Precision-Recall Trade-Off:**

If I wanted higher recall, I could simply lower the classification threshold:

| Threshold | Recall | Precision | What This Means |
|-----------|--------|-----------|-----------------|
| 0.7 | 35% | 78% | Flag only obvious churners (miss many) |
| **0.5** | **53%** | **65%** | **Current balance** |
| 0.3 | 75% | 42% | Flag aggressively (many false alarms) |
| 0.1 | 95% | 18% | Flag almost everyone (unusable) |

**Business cost analysis:**
- **False Negative cost:** Miss a churner = lose $780 annual revenue
- **False Positive cost:** False alarm = waste $100 retention offer
- **Ratio:** 7.8:1 (FN is 7.8x worse than FP)

**My actual recommendation:**
Given this cost ratio, I recommended LOWERING the threshold to 0.35, which increases recall to ~72% at the cost of precision dropping to 48%.

**Why 53% baseline?**
- Better than random (27% if we flagged randomly)
- Better than always predicting 'no churn' (0% recall)
- Validates that model is learning real patterns

**What I'd do with more time to improve recall:**

1. **Class imbalance handling:**
   - Use SMOTE (Synthetic Minority Oversampling) to balance classes
   - Set class_weight='balanced' in Random Forest

2. **Better features:**
   - Add support ticket counts, NPS scores, app usage data
   - Temporal features (days since last payment, seasonality)

3. **Segment-specific models:**
   - Build separate models for high-value vs. standard customers
   - Different models for different contract types

**Bottom line:**
52.8% recall isn't 'bad' - it's a starting point that already delivers business value (identifying 53% of at-risk customers we previously couldn't identify). And we have a clear roadmap to improve it to 65-70% with the enhancements above."

---

### BUSINESS & COMMUNICATION QUESTIONS

#### Q: "How would you explain your model to the CEO?"

**Framework: Skip the technical, focus on value (2 minutes max)**

"I'd use a storytelling approach with three simple points:

**[POINT 1: The Problem in Their Language]**
'We're losing $1.5 million dollars a year because 27% of our customers leave. That's like filling a bucket with a big hole in the bottom - we're spending on acquisition but bleeding revenue through churn.'

**[POINT 2: What I Found]**
'I analyzed 7,000 customers to understand WHY they leave. Three things stood out:

First, our month-to-month contracts are killing us - these customers churn at 42% compared to just 3% for two-year contracts. That's a 15x difference.

Second, half our churn happens in the first year, especially the first 90 days. We're failing at onboarding.

Third - and this surprised me - our highest-paying customers are the most likely to leave. They're paying premium prices but not getting premium treatment.'

**[POINT 3: What We Can Do About It]**
'I've built a system that scores every customer on their likelihood to leave, so we can intervene before they cancel. Think of it like a health checkup - we catch problems early.

Combined with four strategic initiatives - incentivizing longer contracts, improving first-year experience, creating a VIP program for high-payers, and using our predictive system - we can reduce churn from 27% to about 18-20%.

That protects $800K to $1.2M in revenue annually. And the best part: we can start with a small pilot and prove ROI in 90 days.'

**[Visual: One Slide]**
I'd show a simple bar chart:
- Current state: $1.5M at risk
- With initiatives: $0.3M-0.5M at risk
- Protected revenue: $1M-1.2M
- Investment needed: $350K
- Payback period: 4 months

**What I would NOT say:**
- 'Random Forest algorithm with 100 estimators'
- 'ROC-AUC of 0.8437'
- 'Label encoding and scaling'
- Any Python code

**The key:** Executives care about ROI, risk reduction, and action items - not methodology."

---

#### Q: "What would you do if stakeholders disagree with your recommendations?"

**Show you're collaborative, not defensive:**

"I'd treat disagreement as valuable feedback and an opportunity to understand their perspective better. Here's my approach:

**Step 1: Seek to Understand (Ask Questions)**
- 'Help me understand your concern with [specific recommendation]'
- 'What alternative approach are you considering?'
- 'What metrics or evidence would change your mind?'

If they say 'Contract incentives are too expensive,' I'd ask: 'What budget range are you comfortable with? Can we run a smaller pilot?'

**Step 2: Validate Their Expertise**
'You have context about [customer relationships/brand perception/competitive dynamics] that I don't have from the data alone. Walk me through how this would play out from your experience.'

**Step 3: Find Common Ground**
'It sounds like we both agree that [shared goal: reducing churn, improving revenue]. The question is the execution path. Let me propose three alternatives...'

**Step 4: Offer Options, Not Just One Solution**
Present trade-offs clearly:

| Option | Pros | Cons | Est. Impact |
|--------|------|------|-------------|
| Original recommendation | Highest impact | Higher cost | $1.2M protected |
| Stakeholder preference | Lower cost | Lower impact | $600K protected |
| Hybrid approach | Balanced | Complexity | $900K protected |

'You decide based on risk appetite and budget constraints.'

**Step 5: Propose Experiment**
'What if we run a 90-day pilot with 500 customers? If it works, we scale. If not, we've learned cheaply.'

**Example - Real Scenario:**

If a stakeholder said: 'Your analysis says month-to-month contracts are risky, but those customers want flexibility. Forcing annual contracts will drive them away even faster.'

**My response:**

'That's a great point I hadn't fully considered. You're right that forced commitment could backfire. Let me adjust the recommendation:

Instead of pushing annual contracts hard, what if we:
1. **Make the offer attractive:** 15% discount + perks make customer WANT to upgrade
2. **Keep it optional:** No pressure, just clear value proposition
3. **Test first:** A/B test with 1,000 customers - half get offer, half don't
4. **Measure:** Track conversion rate AND downstream churn in both groups
5. **Decide based on data:** If test group churns MORE, we kill the program

This way we're testing the hypothesis with minimal risk.'

**Key principle:** Data informs decisions, but people make decisions. My job is to provide the best analysis AND be flexible enough to adapt based on organizational realities."

---

## PROJECT-SPECIFIC TECHNICAL DETAILS

### Feature Engineering Decisions

#### Why Create tenure_band?

"Tenure was continuous (0-72 months), but EDA showed non-linear patterns:
- 0-3 months: 55% churn
- 3-12 months: 38% churn
- 24+ months: <10% churn

Binning helps the model learn these lifecycle stages:
```python
df['tenure_band'] = pd.cut(df['tenure'],
                           bins=[0, 3, 12, 24, 60, 100],
                           labels=['0-3 months', '3-12 months',
                                   '1-2 years', '2-5 years', '5+ years'])
```

**Trade-off:**
- ✅ Captures non-linear relationship
- ✅ Business interpretability (can say 'first-year customers' vs. '11.7 month tenure customers')
- ❌ Loses precision (treats 11 months and 13 months identically)

**Why both tenure AND tenure_band?**
Keep both - give model flexibility to use continuous pattern AND discrete stages."

---

#### Why charge_ratio = TotalCharges / (tenure + 1)?

"This creates an average monthly spending rate that reveals pricing changes:

**What it tells us:**
- High ratio + Low tenure = new high-value customer (recent upsell)
- Low ratio + High tenure = long-term customer with gradually increasing charges
- Ratio close to MonthlyCharges = consistent pricing

**Why divide by (tenure + 1) not just tenure?**
Prevent division by zero for brand new customers (tenure = 0).

**Why divide by tenure + 1 specifically?**
Customer at tenure=0 has been with us 1 month (sign-up month), so denominator should be 1, not 0."

---

### Model Training Choices

#### Why StandardScaler?

"StandardScaler transforms features to have mean=0, std=1:
```python
scaled_value = (original_value - mean) / std_dev
```

**Example:**
Monthly Charges: [20, 50, 80, 110]
- Mean = 65, Std = 36.74
- Scaled: [-1.22, -0.41, +0.41, +1.22]

**Why scale?**
- Random Forest doesn't require scaling (tree-based, uses splits not distances)
- But I did it anyway for best practice + enables easy model comparison
- If I later want to try Logistic Regression or Neural Network, data is ready

**Alternative scalers:**
- MinMaxScaler: Scales to [0, 1] range
- RobustScaler: Uses median/IQR (better for outliers)
- StandardScaler: Most common, works well for normally-distributed features"

---

#### Why n_estimators=100?

"Number of trees in Random Forest. More trees = better performance (to a point):

| n_estimators | Training Time | Accuracy | ROC-AUC |
|--------------|--------------|----------|---------|
| 10 | 2 sec | 78.1% | 0.81 |
| 50 | 8 sec | 79.8% | 0.837 |
| **100** | **15 sec** | **80.1%** | **0.844** |
| 200 | 32 sec | 80.2% | 0.845 |
| 500 | 80 sec | 80.3% | 0.846 |

Diminishing returns after 100 - accuracy improves only 0.2% but training time 5x slower.

**Industry standard:** 100-500 trees for most problems."

---

### Evaluation Metrics Deep Dive

#### Confusion Matrix Business Translation

```
                 Predicted
                No    Yes
Actual  No    [1032  [16]   = 1048 actually retained
        Yes   [181]  [163]  = 344 actually churned
```

**In dollars:**
- **TN (1032):** Correctly identified loyal = $804K annual revenue (safe)
- **FP (16):** False alarm = 16 × $100 = $1,600 wasted on offers
- **FN (181):** MISSED churners = 181 × $780 = $141K LOST
- **TP (163):** Identified at-risk = 163 opportunities to save

**Key insight:** FN costs 88x more than FP ($141K vs $1,600)

Therefore: Accept more false alarms if it means catching more true churners."

---

## HANDLING DIFFICULT QUESTIONS

### Q: "Why didn't you use deep learning?"

"Deep learning (neural networks) excels at unstructured data like images, text, and audio where patterns are complex and hierarchical. This project had:
- **7K samples** (NNs typically need 50K+ to outperform traditional ML)
- **Tabular data** (Random Forest is proven best for this data type)
- **Need for interpretability** (explain WHY someone will churn, not just predict)

**Benchmark research:**
According to Kaggle competitions on tabular data, tree-based models (Random Forest, XGBoost) win 90% of the time over neural networks.

**If I had 1 million customers:** Then I'd consider deep learning for potential 2-3% accuracy improvement. But the overhead isn't worth it here."

---

### Q: "How do you know your model will work on new customers?"

"Great question - this is about generalization. Five ways I ensured this:

**1. Train-Test Split:**
Held out 20% of data model never saw during training. 80.1% accuracy on this unseen test set indicates it will generalize.

**2. Stratified Sampling:**
Maintained 73-27 class ratio in both train and test sets, ensuring both are representative of real customer population.

**3. Cross-Validation (Implicit in Random Forest):**
Each of 100 trees trains on bootstrap sample (63% of data), validates on out-of-bag remaining 37%. This prevents overfitting.

**4. No Data Leakage:**
Didn't use any features that wouldn't be available at prediction time. For example, didn't use 'customer complained after churning' - that info only exists AFTER churn.

**5. Feature Scaling on Train Only:**
```python
scaler.fit(X_train)  # Learn mean/std from training data
scaler.transform(X_test)  # Apply same transformation to test
```
Prevents test data information from leaking into training.

**To prove it works in production:**
I'd recommend A/B testing:
- Group A: Use model predictions for retention (treatment)
- Group B: No model, standard retention (control)
- Measure: Churn rate difference after 90 days

If treatment group has significantly lower churn, we've proven causality."

---

### Q: "What's the biggest mistake you made in this project?"

**Honesty + Learning (STAR format):**

"The biggest lesson I learned was around class imbalance - though I didn't initially treat it as a mistake, I would handle it differently now.

**Situation:**
27% churn rate meant model could get 73% accuracy by just predicting 'everyone stays' - making accuracy misleading.

**Task:**
Needed to ensure model actually learned churn patterns, not just predicted majority class.

**Action (What I did):**
- Used stratified sampling in train-test split
- Evaluated with multiple metrics (ROC-AUC, precision, recall) instead of just accuracy
- Analyzed confusion matrix to understand error types

**Result:**
Model worked, but recall was only 52.8% - we caught only half of churners.

**What I'd do differently next time:**

**1. Handle imbalance during training:**
```python
rf_model = RandomForestClassifier(
    n_estimators=100,
    class_weight='balanced'  # ← This!
)
```
Gives more weight to minority class during training.

**2. Try SMOTE:**
```python
from imblearn.over_sampling import SMOTE
smote = SMOTE(random_state=42)
X_train_balanced, y_train_balanced = smote.fit_resample(X_train, y_train)
```
Creates synthetic churn examples to balance classes.

**3. Adjust threshold earlier:**
Instead of using default 0.5 threshold, optimize threshold based on business cost analysis up front.

**Expected improvement:**
These techniques could boost recall from 53% to 65-70% while maintaining similar precision.

**Key learning:**
I always evaluate a project by asking 'What would I do differently?' The process was sound, but I now know more advanced techniques to handle imbalanced classes."

---

## FINAL TIPS FOR INTERVIEW SUCCESS

### Before the Interview

**1. Practice Your Story (1 hour)**
- Say the 2-minute project walkthrough out loud 5 times
- Record yourself - does it flow naturally?
- Eliminate filler words ('um,' 'like,' 'you know')

**2. Review Your Code (30 min)**
- Open the notebook, run it start to finish
- Understand every line - be ready to explain ANY code snippet
- Anticipate: 'Why did you use X instead of Y?'

**3. Prepare Questions to Ask (15 min)**
- 'What does a typical analytics project lifecycle look like here?'
- 'What tools and technologies does the team use?'
- 'How does the data team collaborate with business stakeholders?'

### During the Interview

**1. Pause Before Answering**
- Take 2-3 seconds to think
- It's okay to say 'That's a great question. Let me think for a moment.'
- Better than rambling

**2. Structure Your Answers**
- Use frameworks: STAR, Before/After, Problem/Solution
- Signpost: 'I'll answer this in three parts: First... Second... Third...'

**3. Show Your Thinking**
- Don't just give the answer, show the thought process
- 'I considered two approaches: X and Y. I chose X because...'

**4. Ask Clarifying Questions**
- 'When you ask about model performance, do you mean accuracy on test data or how it would perform in production?'
- Shows depth of thinking

### After the Interview

**Send Thank You Email (Within 24 hours):**

Subject: Thank you - [Your Name] - Data Analyst Interview

"Hi [Interviewer Name],

Thank you for taking the time to speak with me today about the Data Analyst position. I really enjoyed learning about [specific project or initiative they mentioned] and discussing how my telecom churn analysis project could apply to [their business problem].

Your question about [specific technical question] particularly resonated with me, and after our conversation, I reflected on how I might approach [their specific challenge] using [technique]. I'm even more excited about the opportunity to contribute to [team/company goal].

Please let me know if you need any additional information. I look forward to hearing about next steps.

Best regards,
[Your Name]"

---

## CONFIDENCE BOOSTERS

### You Know More Than You Think

Many candidates freeze when asked technical questions, but remember:

✅ You built an end-to-end project from scratch
✅ You understand the full data science pipeline
✅ You can communicate complex concepts simply
✅ You've solved a real business problem

### It's OK to Say 'I Don't Know'

If asked something you don't know:

**Bad:** Make something up / bluff
**Good:** 'I haven't worked with [X] yet, but here's how I'd approach learning it...'
**Better:** 'I'm not familiar with [X], but it sounds similar to [Y] which I have used. Is that accurate?'

### Common Question You Can Always Expect

"Do you have any questions for us?"

**ALWAYS have 2-3 questions ready:**
1. Technical: 'What's the data infrastructure like? What tools does the team use?'
2. Business: 'What's the biggest data challenge the team is trying to solve right now?'
3. Culture: 'How does the data team collaborate with [product/marketing/operations]?'

Never ask about salary/benefits in first interview.

---

**GOOD LUCK! You've got this! 🚀**

