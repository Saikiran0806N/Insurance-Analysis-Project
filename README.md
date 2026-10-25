# Insurance Analysis Power BI Project — Business Case Study
Insurance Analysis dashboard for Thaswika Insurance Pvt. Ltd. can be presented as a business intelligence project focused on understanding insurance premiums, claims, coverage, policy status and customer demographics.


### 1. Business problem statement

Insurance Portfolio & Claims Performance Analysis
Insurance companies need visibility into premium collections, claim amounts, coverage commitments and policy status to understand portfolio performance and identify areas that require further investigation.

The objective of this project is to analyze insurance policy and customer data using Power BI to evaluate premium and claims distributions, compare policy types, examine claim statuses, understand policy lifecycle status and assess differences across customer age groups and gender.

The analysis aims to provide stakeholders with a consolidated view of insurance portfolio performance, helping them investigate potential claims exposure, review policy mix and identify opportunities to improve operational monitoring and business decision-making.

Key business questions
- Financial performance: How much premium has been collected, and how does it compare with the claim amounts recorded?
- Policy portfolio: Which policy types contribute the most premium and coverage?
- Claims management: How are claims distributed across different claim statuses?
- Policy lifecycle: What proportion of policies are active, expired or in other statuses?
- Customer demographics: How do claim amounts and policy distributions vary across age groups and gender?
- Risk monitoring: Which policy segments may need further investigation based on claim amounts relative to premiums and coverage?
Note that this dashboard supports descriptive analysis and risk investigation. It does not, by itself, establish underwriting risk, claim fraud or profitability.

### 2. Step map: from insurance data to business decisions

1. Insurance data collection

Policy number · Customer ID · Claim number · Policy type · Premium · Claim amount · Coverage


2. Data quality and validation

Check missing values, duplicate policies, amount fields, date validity and status consistency.


3. KPI development and data modeling

Calculate total premiums, claims, coverage, policy counts and claim-to-premium ratio.


4. Exploratory analysis in Power BI

Compare policy types, claim status, policy status, age groups, gender and individual records.


5. Identify patterns and investigate exceptions

Investigate high claim-to-premium ratios, unusual claim values, inactive policies and segment differences.


6. Business recommendations

Improve claims monitoring, policy reporting, portfolio review and management visibility.


### 3. Dashboard map: 

Page 1 — Overview
Executive summary
The page includes KPI cards for PremiumAmount, ClaimAmount and CoverageAmount, along with visuals for claim status, premium by policy type, claim amount by age group, policy status and a policy/claim summary matrix.

Explanation: “I designed an overview to bring key financial indicators and portfolio distributions together, allowing stakeholders to identify segments that deserve deeper analysis.”


Page 2 — Table matrix
Detailed investigation
The page includes policy type filtering and supports detailed review of policy numbers, customer IDs, claim numbers, gender, age, coverage, premium, policy dates and policy type.

Explanation: “I included a detailed view so users can move from portfolio-level summaries to individual records and validate where an observed pattern originates.”


### 4. Key insights to showcase

The report structure identifies the areas you can analyze, but the actual chart values have not been verified here. Treat these as insights to test, not as confirmed findings.

Insight 1 — Premium versus claims exposure

Visual: Premium, Claim and Coverage KPI cards

Compare the total premium amount against total claim amounts and coverage.
- Calculate the claim-to-premium ratio.
- Compare results across policy types.
- Investigate segments where claim amounts are high relative to premiums.
Business implication: Identify segments that may warrant closer financial and claims review.




Insight 2 — Policy mix and premium contribution

Visual: Premium amount by policy type

Identify which policy types contribute the largest share of total premiums.
- Rank policy types by premium contribution.
- Compare their policy counts and average premium.
- Check whether premium concentration is matched by a similar concentration in claims.
Business implication: Help management understand portfolio concentration and decide where further segment-level analysis is needed.




Insight 3 — Claim status distribution

Visual: Claim status ribbon chart

Examine the distribution of claim records across statuses.
- Compare approved, pending, rejected or other available statuses.
- Calculate the share of claims in each status.
- If dates and processing timestamps are available, investigate delays and ageing.
Business implication: Help claims teams identify workload imbalances and possible processing bottlenecks. Status counts alone cannot establish delays.




Insight 4 — Customer demographic patterns

Visuals: Claim amount by age group and gender distribution

Compare claim amounts and policy representation across customer segments.
- Identify age groups with the highest total claims.
- Compare average claim amount as well as total claim amount.
- Check sample sizes and policy mix before interpreting differences.
Business implication: Understand portfolio composition and identify areas for actuarial investigation. Demographic differences alone do not establish individual risk.




Insight 5 — Policy lifecycle monitoring

Visual: Policy status donut chart and policy dates in the detail table

Analyze how policies are distributed by status and compare policy start and end dates.
- Calculate active, expired and other policy-status proportions.
- Validate the status against policy dates and the relevant reporting date.
- Identify expired policies that may require follow-up, subject to business rules.
Business implication: Improve policy lifecycle reporting and help service teams prioritize appropriate follow-up.



### 5. KPIs to look into

KPI	Suggested calculation	Business purpose
Total Premium	Sum of premium amounts	Understand premium volume
Total Claims	Sum of claim amounts	Understand recorded claim exposure
Total Coverage	Sum of coverage amounts	Understand aggregate coverage values
Claim-to-Premium Ratio	Total claims ÷ total premium	Compare recorded claims with premiums
Average Claim Amount	Total claims ÷ distinct claims	Understand average claim size
Claim Count	Distinct claim numbers	Measure claims volume
Policy Count	Distinct policy numbers	Measure portfolio size
Pending Claim %	Pending claims ÷ all claims	Monitor outstanding claim workload
Active Policy %	Active policies ÷ all policies	Monitor policy status

Example DAX, assuming the table is named InsuranceData:
Total Premium =
SUM(InsuranceData[PremiumAmount])

Total Claims =
SUM(InsuranceData[ClaimAmount])

Total Coverage =
SUM(InsuranceData[CoverageAmount])

Policy Count =
DISTINCTCOUNT(InsuranceData[PolicyNumber])

Claim Count =
DISTINCTCOUNT(InsuranceData[ClaimNumber])

Claim-to-Premium Ratio =
DIVIDE(
    [Total Claims],
    [Total Premium],
    0
)

Average Claim Amount =
DIVIDE(
    [Total Claims],
    [Claim Count],
    0
)


