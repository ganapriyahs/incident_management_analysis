### Incident Management Process Analysis
Dataset: Incident Management Process Enriched Event Log (UCI)

1. Problem Setting
Incident management is critical for IT and service-based organizations, where delays in resolving incidents can disrupt operations and affect customer trust. This project analyzes event logs from incident management systems to uncover inefficiencies, identify delay factors, and propose workflow improvements to enhance resolution times and service delivery.

2. Problem Definition
The project aims to analyze and optimize the incident management process by:
Understanding resolution times for different incident types.
Identifying key factors contributing to delays.
Proposing actionable improvements to streamline workflows and reduce inefficiencies.

3. Objectives & Key Results (OKRs)
Objective: Improve the incident resolution process by identifying inefficiencies and proposing optimizations.
Key Result 1: Identify the top 3 factors causing delays in incident resolution.
Key Result 2: Recommend process improvements to reduce average resolution time by at least 10%.
Key Result 3: Improve workflow efficiency to enhance response times by 15%.

4. Key Performance Indicators (KPIs)
Average Resolution Time: Mean time to resolve incidents.
Incident Severity Distribution: Resolution time across severity levels (low, medium, high).
Team Efficiency: Average time per team to resolve incidents.
Incident Backlog: Unresolved incidents over time.

5. Dataset
Source: UCI Machine Learning Repository
Rows & Columns: 141,713 rows × 36 columns
Key Features:
incident_id: Unique identifier
severity: Low/Medium/High classification
assigned_team: Team handling the incident
resolution_time: Time taken to resolve (minutes)
incident_state: Status (open, in progress, resolved)
timestamps: (opened_at, resolved_at, closed_at)

6. Data Preprocessing
Datetime conversion: Converted all timestamp columns to datetime format.
Categorical encoding: Converted variables like incident_state, priority, assigned_to to categorical.
Missing values: Filled with “Unknown” or “Unassigned” categories.
Dropped irrelevant columns: problem_id, rfc, vendor, caused_by.

7. Exploratory Data Analysis (EDA)
Chi-Square Test: Examined relationships between incident_state and priority.
Correlation Analysis:
sys_mod_count & reassignment_count → strong positive correlation.
reopen_count moderately correlated with priority.
ANOVA: Checked differences in resolution time across priority levels.
t-SNE Visualization: Identified clusters for different incident states.

8. Model Selection
Tested multiple regression models for predicting incident resolution time:
Linear Regression (baseline)
Decision Tree Regressor
Random Forest Regressor
Gradient Boosting Regressor
Neural Network (MLP Regressor)

9. Model Evaluation
Train/Test Split: 80/20
Scaling: StandardScaler applied

Metrics:
R² Score – Variance explained by model
MAE – Mean absolute error
MSE & RMSE – Squared errors and root errors
MAPE – Mean absolute percentage error

Results:
Random Forest performed best (R² = 0.624) with lowest MSE/RMSE.
Linear Regression performed worst.
Neural Networks underperformed without tuning.

10. Insights & Recommendations
Top factors for delays: High reassignment counts, priority level escalation, and multiple state changes.
Recommendations:
Automate triage for high-priority incidents.
Reduce reassignment through clear ownership.
Streamline workflow for frequently reopened cases.

11. Conclusion
Random Forest proved most effective for predicting resolution times. Insights from this analysis can help organizations reduce incident resolution time by 10–15%, optimize workflows, and improve overall service delivery.
