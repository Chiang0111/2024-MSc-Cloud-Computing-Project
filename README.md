# 2024-MSc-Cloud-Computing-Project
# Cloud Native API for Trading Strategy Risk and Profitability Analysis

## Project Overview
This project involves the development of a cloud-native API that uses multiple cloud services to analyze the risks and profitability of trading strategies. The API employs trading signals and Monte Carlo methods to provide risk assessments and profitability metrics.

## Aim
The main aim is to demonstrate the ability to critically explain and construct a cloud-native API using services across different cloud providers, ensuring user-specifiable scaling. The API supports the evaluation of trading strategies by analyzing financial time series data.

## Features
- **Warm-up and Scale-out**: Initialize and scale the cloud services for parallel analysis.
- **Risk Analysis**: Perform risk analysis using Monte Carlo simulations based on trading signals.
- **Profit/Loss Evaluation**: Calculate profit or loss after a specified number of days following the trading signal.
- **Audit and Reporting**: Provide audit logs of all analysis and generate URLs for visualizing risk values.

## API Endpoints
1. **/warmup**
   - **Description**: Initializes the specified scale for the analysis.
   - **Method**: POST
   - **Inputs**: `{ "s": "lambda", "r": 3 }`
   - **Outputs**: `{ "result": "ok" }`

2. **/scaled_ready**
   - **Description**: Checks if the specified scale is ready for analysis.
   - **Method**: GET
   - **Outputs**: `{ "warm": true }` or `{ "warm": false }`

3. **/get_warmup_cost**
   - **Description**: Retrieves the cost and time required for warm-up.
   - **Method**: GET
   - **Outputs**: `{ "billable_time": 227.44, "cost": 18.33 }`

4. **/get_endpoints**
   - **Description**: Retrieves the call strings for unique endpoints made available at warm-up.
   - **Method**: GET
   - **Outputs**: `{ "endpoint": "http://..." }`

5. **/analyse**
   - **Description**: Runs the risk analysis.
   - **Method**: POST
   - **Inputs**: `{ "h": 101, "d": 10000, "t": "sell", "p": 7 }`
   - **Outputs**: `{ "result": "ok" }`

6. **/get_sig_vars9599**
   - **Description**: Retrieves pairs of 95% and 99% VaR values for each signal.
   - **Method**: GET
   - **Outputs**: `{ "var95": [0.3345, ...], "var99": [0.3345, ...] }`

7. **/get_avg_vars9599**
   - **Description**: Retrieves average risk values over all signals at 95% and 99%.
   - **Method**: GET
   - **Outputs**: `{ "var95": 0.3345, "var99": 0.3345 }`

8. **/get_sig_profit_loss**
   - **Description**: Retrieves profit/loss values for all signals.
   - **Method**: GET
   - **Outputs**: `{ "profit_loss": [27.2, -51, 8, ...] }`

9. **/get_tot_profit_loss**
   - **Description**: Retrieves the total profit/loss.
   - **Method**: GET
   - **Outputs**: `{ "profit_loss": -99.99 }`

10. **/get_chart_url**
    - **Description**: Retrieves the URL for a risk values chart.
    - **Method**: GET
    - **Outputs**: `{ "url": "http://..." }`

11. **/get_time_cost**
    - **Description**: Retrieves the total billable time and cost for the analysis.
    - **Method**: GET
    - **Outputs**: `{ "time": 123.45, "cost": 88.32 }`

12. **/get_audit**
    - **Description**: Retrieves audit information of all previous runs.
    - **Method**: GET
    - **Outputs**: `{ "audit": [...] }`

13. **/reset**
    - **Description**: Resets the analysis.
    - **Method**: GET
    - **Outputs**: `{ "result": "ok" }`

14. **/terminate**
    - **Description**: Terminates the services to scale to zero.
    - **Method**: GET
    - **Outputs**: `{ "result": "ok" }`

15. **/scaled_terminated**
    - **Description**: Confirms if services have been terminated.
    - **Method**: GET
    - **Outputs**: `{ "terminated": true }` or `{ "terminated": false }`

## Setup and Installation
1. **Clone the Repository**:
   ```bash
   git clone <repository_url>
   cd <repository_folder>
