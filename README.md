# Optimizing Old Age Security (OAS) Pension Deferrals

Course: Risk 360W Spring2025, Simon Fraser University

Team Members: Stuart Siu, Chloe Ma, Franklin Susanto

## Objective
Developed a dynamic calculator to determine the most financially advantageous age for Canadian seniors to commence their Old Age Security (OAS) benefits. 
The model calculates the optimal deferral age (down to the month) by maximizing the Actuarial Present Value (APV) of expected future payments.

## The Business Problem
Financial planners frequently provide inconsistent advice regarding when clients should begin drawing OAS benefits. 
Because payments are subject to statutory rules (including residency requirements, income clawbacks, and a 0.6% monthly deferral increase up to age 70), 
calculating the true break-even point requires rigorous mortality and time-value modeling rather than simple heuristics.

## Actuarial Methodology
To ensure precise, personalized recommendations, the calculator integrates several key actuarial components:
- Mortality Modeling: Utilized Statistics Canada life tables to derive gender-specific survival probabilities.
- Uniform Distribution of Death (UDD): Applied UDD assumptions over integer ages to accurately model monthly deferrals and accruals.
- Present Value Calculations: Discounted future cash flows using a baseline 3% interest rate (benchmarked against 10-year Government of Canada bond yields).
- Statutory Logic: Programmed conditional payment logic to account for years of residency, prior-year income thresholds, and the automatic 10% benefit increase at age 75.

## Scope & Key Assumptions
No Income Clawbacks: For simplicity, this model assumes the pensioner's net world income remains below the OAS Recovery Tax threshold. 
In real-world applications, income taxation plays a crucial role, and pensioners actively employ income-reduction strategies to avoid the 15% clawback, which would significantly alter the optimal deferral timeline.

## Tech Stack
- Mathematics: Actuarial Present Value, Survival Probabilities, UDD.
- Tools: Excel

## Key Insights
Data was gathered using <a href="https://estimateursv-oasestimator.digital.service.canada.ca/en">The Official OAS Calculator</a> that yielded several key observations on deferment:

<img width="60%" alt="image" src="https://github.com/user-attachments/assets/c683cc81-4458-4505-95ad-7fc68be763d0" />
<img width="50%" alt="image" src="https://github.com/user-attachments/assets/714a0caf-a875-4330-ae41-98cbe253720a" />


- Gender Impact: 
Because males generally have lower survival rates than females, early payments are heavily emphasized, often resulting in optimal deferral ages a full year earlier than a comparable female client.
- Interest Rate Sensitivity: 
Higher interest rates significantly decrease the present value of future payments. For example, shifting the assumption from 3% to 5% pushes the optimal start date nearly 11 months earlier.

<img width="40%" alt="image" src="https://github.com/user-attachments/assets/e6edfef4-eae5-4c63-9c60-5dcadb8a7ac1" />

- Residency Thresholds: 
For clients with fewer than 15 years of Canadian residency, the change in the statutory payment formula triggers a need for further deferral to maximize total payout.

<img width="40%" alt="image" src="https://github.com/user-attachments/assets/4f184dfe-53f7-4845-aeb6-0cae8be4b0b5" />



