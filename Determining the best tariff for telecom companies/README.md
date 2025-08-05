# Telecom Tariff Profitability Analysis

## Project Description
This project involves a statistical analysis of a telecommunications company's data to determine the most profitable tariff plan for customers. The analysis examines data on calls, internet sessions, messages, and user tariffs.

## Data
The project utilizes the following datasets:
- `calls.csv` - Call records (date, duration, user)
- `internet.csv` - Internet session data (data usage in MB, date, user)
- `messages.csv` - Message records (date, user)
- `tariffs.csv` - Tariff information (included minutes, messages, data allowance, cost)
- `users.csv` - User data (demographics, registration date, tariff plan)

## Key Analysis Stages
1. **Data Loading and Preliminary Analysis**
   - Examining data structure
   - Checking for missing values and anomalies
   - Visualizing distributions

2. **Data Preprocessing**
   - Converting dates to proper format
   - Rounding call durations
   - Adding a month column for temporal analysis
   - Removing unnecessary columns

3. **Data Aggregation**
   - Calculating call counts, messages sent, and data usage per user per month
   - Determining tariff limit overages
   - Calculating additional charges

4. **Revenue Analysis**
   - Computing monthly revenue per user
   - Comparing tariffs by key metrics
   - Creating pivot tables with statistical indicators

## Results
The project includes:
- Detailed analysis of user behavior across different tariffs
- Calculation of overage charges
- Comparison of revenue between tariff plans
- Visualization of key performance indicators

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib (for visualization)
