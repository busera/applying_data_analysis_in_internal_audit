## Introduction & Problem Statement

The application of data analysis in internal audit has been a topic of increasing interest and discussion in my recent months. While numerous knowledge briefs and guides are available from respected organizations like the IIA[^1] and ISACA[^2][^3][^4], these resources often present a more high-level and generic approach. As a professional with a background in data science, I've found that many existing resources in this area lack some depth and specificity to better bridge the gap between data analysis theory and its practical application in internal audit.

This observation has motivated me to create this comprehensive guide. This guide explores the application of data analysis techniques in internal auditing, adapting key concepts from academic research methodologies[^5] to the practical world of internal audit focusing on two distinct concepts:

- Confirmatory vs. Exploratory Questions
- Causal vs. Non-Causal Questions

To further bridge the gap between theory and practice, I am planning to build a [GitHub repository](https://github.com/busera/applying_data_analysis_in_internal_audit) that will collect examples (generated and anonymized real-life data), including Python code for analysis and visualization.


[^1]: IIA Knowledge Briefs: Data Analytics, Parts 1-3. https://www.theiia.org/en/content/articles/global-perspectives-and-insights/2023/GlobalPerspectivesInsightsDataAnalyticsParts1-3/

[^2]: Internal Audit Data Analytics for Beginners. https://www.isaca.org/resources/news-and-trends/industry-news/2023/internal-audit-data-analytics-for-beginners

[^3]: Seven Steps to Empowerment With Data Analytics. https://www.isaca.org/resources/news-and-trends/newsletters/atisaca/2023/volume-34/seven-steps-to-empowerment-with-data-analytics

[^4]: Advanced Data Analytics for IT Auditors. https://www.isaca.org/resources/isaca-journal/issues/2016/volume-6/advanced-data-analytics-for-it-auditors

[^5]:	Card, D., Min, Y., & Serghiou, S. (2021, December 14). Open, rigorous and reproducible research: A practitioner's handbook. Stanford Data Science. https://stanforddatascience.github.io


## Definitions
The following definitions are taken from "Classification of different questions" (Section 1.1.2), Card et al. (2021).

 **Confirmatory Questions**
- Typically involve a set of hypotheses, including a null hypothesis with one or more alternatives. 
- These questions often require a concrete research design to test these hypotheses and are usually answered via inductive inference. 
- Confirmatory analyses are considered to make a "scientific step forward" and yield "strong inference”. 

**Exploratory Questions**
- These questions are not explicitly hypothesis-driven. Instead, they are often considered to be hypothesis-generating. 
- Exploratory analyses do not aim to achieve "strong inference" and may yield a higher false positive rate. 
- However, they are valuable for new discoveries and unexplored topics.

**Causal questions**
- Causal questions aim to draw conclusions about a causal relationship between the indexed exposures and outcomes. 
- They typically include:
	- A well-defined cause
	- A well-defined outcome
	- A scientifically plausible effect on the outcome that can be attributable to the cause

**Non-Causal questions**
- Non-causal questions are typically descriptive or observational/associational. 
- They describe the objective existence of certain phenomena or examine relationships between factors without considering underlying causal mechanisms.


## Confirmatory vs. Exploratory Approaches in Internal Audit

In internal audit, both confirmatory and exploratory approaches play crucial roles in providing assurance and adding value to the organization.

| Aspect             | Confirmatory Approach                        | Exploratory Approach                                   |
| ------------------ | -------------------------------------------- | ------------------------------------------------------ |
| Starting Point     | Specific hypotheses or expectations          | Open-ended questions or areas of interest              |
| Objective          | Verify, confirm, or refute/disprove          | Discover, understand, or generate hypotheses           |
| Analytical Methods | Statistical tests, compliance checking       | Data mining, pattern recognition, advanced analytics   |
| Outcomes           | Clear yes/no answers or quantifiable results | Insights, patterns, or areas for further investigation |

### Confirmatory Approach in Internal Audit

Characteristics:
- Based on specific audit objectives, known risks, or control expectations
- Often tied to compliance with policies, regulations, or industry standards
- Typically results in clear, definitive conclusions
- Uses structured analytical techniques and statistical methods

Purpose in Audit:
- Verify compliance with policies, laws, and regulations
- Test the effectiveness of internal controls
- Validate the accuracy of financial or operational data
- Confirm that processes are operating as intended

Example Questions:
- Is the error rate in expense reports less than the 5% threshold set by company policy?
- Are 100% of transactions over $10,000 approved by an authorised manager?
- Has the new inventory system reduced stockout incidents by at least 30% as projected?

### Exploratory Approach in Internal Audit

Characteristics:
- Open-ended and not driven by predefined hypotheses
- Aims to uncover unknown patterns, trends, or relationships
- May lead to new lines of inquiry or future audit objectives
- Often uses more advanced or flexible analytical techniques

Purpose in Audit:
- Identify potential risk areas or control weaknesses not previously considered
- Uncover inefficiencies or opportunities for process improvement
- Generate insights to inform risk assessment and audit planning
- Discover unexpected relationships or anomalies for further investigation

Example Questions:
- What factors influence the approval patterns for high-value transactions?
- How do error rates in financial reporting vary across different departments or processes?
- Are there any unusual patterns in inventory movement that might indicate fraud or inefficiency?

## Causal vs. Non-Causal Data Analysis in Internal Audit

### Causal Data Analysis

Aims to establish cause-effect relationships between variables.

Techniques:
- Difference-in-differences analysis
- Propensity score matching
- Instrumental variable analysis
- Regression discontinuity design

Example applications:
- Assessing the impact of a new training program on employee productivity
- Evaluating how changes in credit policies affect bad debt rates
- Determining the effect of implementing new controls on error rates

### Non-Causal Data Analysis

Describes relationships or current states without implying causation.

Techniques:
- Descriptive statistics
- Correlation analysis
- Time series analysis
- Network analysis

Example applications:
- Mapping the flow of transactions through different systems
- Analyzing the distribution of processing times for customer requests
- Identifying correlations between different risk indicators


## Application in Internal Audit Practice

To illustrate how confirmatory, exploratory, causal, and non-causal approaches can be applied in internal audit, let's examine some common audit areas.

### Example: Expense Report Auditing

#### Comparing Question Types

| Confirmatory                                                                   | Exploratory                                                                                    | Causal                                                                           | Non-Causal                                                                       |
| ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Are expense reports compliant with company policy?                             | What patterns exist in expense report submissions?                                             | Does the implementation of automated expense report software reduce error rates? | What is the distribution of expense report amounts across different departments? |
| Is the error rate in expense reports less than 5%?                             | How do error rates vary across departments or expense types?                                   | What is the effect of managerial review on expense report accuracy?              | How do expense categories correlate with report processing times?                |
| Are 100% of expense reports over $1,000 reviewed by a manager within 48 hours? | Is there a correlation between the complexity of expense reports and the likelihood of errors? |                                                                                  |                                                                                  |

#### Question Types and Data Analysis Techniques

| Type         | Example Question                                                                               | Data Analysis Techniques                                                                            |
| ------------ | ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Confirmatory | Are expense reports compliant with company policy?                                             | - Compliance testing - Rule-based analysis - Exception reporting                                    |
|              | Is the error rate in expense reports less than 5%?                                             | - Hypothesis testing - Statistical process control - Confidence intervals                           |
|              | Are 100% of expense reports over $1,000 reviewed by a manager within 48 hours?                 | - Compliance testing - Process mining - Control effectiveness testing                               |
|              | Has there been a consistent decrease in policy violations over the past year?                  | - Trend analysis - Time series decomposition - Regression analysis                                  |
| Exploratory  | What patterns exist in expense report submissions?                                             | - Clustering - Association rule mining - Sequence analysis                                          |
|              | How do error rates vary across departments or expense types?                                   | - Correlation analysis - ANOVA - Heat map visualization                                             |
|              | Is there a correlation between the complexity of expense reports and the likelihood of errors? | - Correlation analysis - Logistic regression - Decision tree analysis                               |
|              | Can we group employees based on their expense report submission patterns?                      | - Clustering - K-means analysis - Hierarchical clustering                                           |
|              | Are there any unusual or suspicious patterns in expense report submissions?                    | - Anomaly detection - Outlier analysis - Network analysis                                           |
| Causal       | Does the implementation of automated expense report software reduce error rates?               | - Difference-in-differences analysis - Propensity score matching - Interrupted time series analysis |
|              | What is the effect of managerial review on expense report accuracy?                            | - Regression analysis - Structural equation modelling - Causal inference techniques                 |
| Non-Causal   | What is the distribution of expense report amounts across different departments?               | - Descriptive statistics - Box plot analysis - Kernel density estimation                            |
|              | How do expense categories correlate with report processing times?                              | - Time series analysis - Cross-correlation analysis - Scatter plot matrix                           |

### Example: Inventory Management Auditing

#### Comparing Question Types

| Confirmatory Approach                                                                   | Exploratory Approach                                                               | Causal Analysis                                                           | Non-Causal Analysis                                                   |
| --------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Has the new inventory system reduced stockout incidents by at least 30%?                | What factors influence stockout incidents?                                         | What is the impact of implementing RFID technology on inventory accuracy? | What is the relationship between inventory levels and sales patterns? |
| Is the inventory turnover ratio within industry benchmarks?                             | How does inventory accuracy vary across different product categories or locations? | How does the frequency of cycle counts affect inventory discrepancies?    | How do lead times vary across different suppliers?                    |
| Are 95% of high-priority items restocked within 24 hours of reaching the reorder point? | What patterns emerge in slow-moving inventory items?                               |                                                                           |                                                                       

#### Question Types and Data Analysis Techniques

| Type         | Example Question                                                                        | Data Analysis Technique                                                                            |
| ------------ | --------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Confirmatory | Has the new inventory system reduced stockout incidents by at least 30%?                | - Hypothesis testing - Trend analysis - Statistical process control                                |
|              | Is the inventory turnover ratio within industry benchmarks?                             | - Ratio analysis - Benchmarking - Z-score analysis                                                 |
|              | Are 95% of high-priority items restocked within 24 hours of reaching the reorder point? | - Compliance testing - Process capability analysis - Control charts                                |
| Exploratory  | What factors influence stockout incidents?                                              | - Root cause analysis - Decision tree analysis Factor analysis                                     |
|              | How does inventory accuracy vary across different product categories or locations?      | - Cluster analysis - Heat mapping - Variance analysis                                              |
|              | What patterns emerge in slow-moving inventory items?                                    | - Time series analysis - Pattern recognition algorithms - Association rule mining                  |
| Causal       | What is the impact of implementing RFID technology on inventory accuracy?               | - Difference-in-differences analysis - Regression discontinuity design - Propensity score matching |
|              | How does the frequency of cycle counts affect inventory discrepancies?                  | - Regression analysis - Structural equation modelling - Instrumental variable analysis             |
| Non-Causal   | What is the relationship between inventory levels and sales patterns?                   | - Correlation analysis - Scatter plot analysis - Cross-tabulation                                  |
|              | How do lead times vary across different suppliers?                                      | - Descriptive statistics - Box plot analysis - Histogram analysis                                  |

### Example: High-Value Transactions Auditing

#### Comparing Question Types

| Confirmatory Approach                                                      | Exploratory Approach                                                                   | Causal Analysis                                                                              | Non-Causal Analysis                                                             |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Are 100% of transactions over $10,000 approved by an authorized manager?   | What patterns exist in high-value transaction approvals?                               | Does implementing a multi-level approval process reduce the rate of fraudulent transactions? | How do high-value transactions flow through different departments?              |
| Has the rate of policy exceptions for high-value transactions decreased?   | Are there any unusual timing patterns in high-value transactions?                      | What is the effect of real-time monitoring on policy exception rates?                        | What is the distribution of transaction values across different business units? |
| Is there two-factor authentication for all transactions exceeding $50,000? | Is there a correlation between transaction value and the number of approvals required? |                                                                                              |                                                                                 |

#### Question Types and Data Analysis Techniques

| Type         | Example Question                                                                             | Data Analysis Technique                                                                            |
| ------------ | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Confirmatory | Are 100% of transactions over $10,000 approved by an authorized manager?                     | - Compliance testing - Exception reporting - Control effectiveness testing                         |
|              | Has the rate of policy exceptions for high-value transactions decreased?                     | - Trend analysis - Statistical process control - Regression analysis                               |
|              | Is there two-factor authentication for all transactions exceeding $50,000?                   | - Control testing - System configuration review - Log analysis                                     |
| Exploratory  | What patterns exist in high-value transaction approvals?                                     | - Pattern recognition - Cluster analysis - Association rule mining                                 |
|              | Are there any unusual timing patterns in high-value transactions?                            | - Time series analysis - Anomaly detection - Seasonal decomposition                                |
|              | Is there a correlation between transaction value and the number of approvals required?       | - Correlation analysis - Scatter plot analysis - Regression analysis                               |
| Causal       | Does implementing a multi-level approval process reduce the rate of fraudulent transactions? | - Difference-in-differences analysis - Propensity score matching - Regression discontinuity design |
|              | What is the effect of real-time monitoring on policy exception rates?                        | - Interrupted time series analysis - Regression analysis - Causal inference techniques             |
| Non-Causal   | How do high-value transactions flow through different departments?                           | - Process flow analysis - Network analysis - Sankey diagrams                                       |
|              | What is the distribution of transaction values across different business units?              | - Descriptive statistics - Histogram analysis - Box plot analysis                                  |


## The Role of Exploratory Data Analysis (EDA)

Exploratory Data Analysis serves as a critical first step in the data analysis process for internal audits, bridging both confirmatory and exploratory approaches.

Key EDA Techniques:
- Data quality assessment (missing values, outliers, inconsistencies)
- Descriptive statistics (mean, median, standard deviation)
- Data visualization (histograms, scatter plots, box plots)
- Correlation analysis

EDA in the Audit Process:
1. Initial Data Exploration: Use EDA to gain insights into the dataset's characteristics and potential areas of interest.
2. Hypothesis Refinement: Based on EDA findings, refine existing hypotheses or generate new ones for confirmatory analysis.
3. Anomaly Detection: Identify unusual patterns or outliers that may warrant further investigation.
4. Variable Selection: Determine which variables are most relevant for subsequent analyses.

## The Value of Exploratory and Non-Causal Approaches


In my experience, exploratory and non-causal questions often provide the most valuable insights in internal auditing, particularly in larger organizations. This is due to several factors:

- Confirmatory questions are typically already addressed and implemented by first and second lines of defense, reducing the need for internal audit to focus heavily on these areas.
- Causal questions, while valuable, often face practical limitations:
	- Required data may not be available in sufficient quantity or quality
	- Results can be challenging to report and communicate, especially when dealing with complex statistical concepts
- Exploratory and non-causal approaches offer several advantages:
	- They can uncover unexpected patterns or risks that might be missed by more targeted approaches
	- They often require less stringent data requirements, making them more practical in many audit contexts
	- The insights gained can be more easily communicated and actioned by stakeholders


## Conclusion

This guide has explored four key approaches to data analysis in internal auditing, each serving a distinct purpose:
- **Confirmatory questions** verify specific hypotheses or compliance with established policies, using techniques like compliance testing, hypothesis testing, and trend analysis to provide assurance on known risks and controls.
- **Exploratory questions** uncover patterns or relationships in the data without preconceived notions, employing methods such as clustering, correlation analysis, and anomaly detection to identify emerging risks or unknown control weaknesses.
- **Causal questions** investigate cause-and-effect relationships between variables, utilizing techniques like difference-in-differences analysis and regression analysis to understand the impact of specific factors or interventions.
- **Non-causal questions** examine relationships or distributions in the data without implying causation, using descriptive statistics and time series analysis to describe complex relationships and patterns within data.

By integrating confirmatory, exploratory, causal, and non-causal approaches in internal audit data analysis, auditors can:
- Provide assurance on known risks and controls (confirmatory)
- Identify emerging risks or unknown control weaknesses (exploratory)
- Understand the impact of specific factors or interventions (causal)
- Describe complex relationships and patterns within data (non-causal)
- Offer deeper insights into business processes and potential improvements
- Support a more risk-based and value-added approach to internal auditing

This multifaceted strategy empowers auditors to move beyond traditional compliance-focused auditing. It enables a more comprehensive understanding of the audited environment, facilitating proactive risk management and strategic decision-making support.