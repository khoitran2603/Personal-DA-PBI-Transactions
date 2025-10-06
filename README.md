# Introduction

### About the Project
This project analyses my own bank transactions from **January to August 2025**, turning raw personal finance data into clear, actionable insights.
It aims to understand how real-world behaviours — like fixed commitments, family events, and convenience-driven habits — shape monthly spending patterns.

### Project Challenge
Personal finance data is often **unstructured, inconsistent, and event-driven**, making meaningful analysis difficult.
My biggest challenge was to **standardise multiple bank exports** (ANZ, Westpac, etc.) into one consistent dataset and classify transactions that mix essentials (rent, utilities) with one-off events (travel, car insurance).

<p align="center">
  <table>
    <tr>
      <td align="center">
        <img src="docs/data_raw.png" width="100%"/><br />
        <em>Westpac raw dataset</em>
      </td>
      <td align="center">
        <img src="docs/data_raw_anz.png" width="100%"/><br />
        <em>ANZ raw dataset</em>
      </td>
    </tr>
  </table>
</p>

Instead of focusing on daily precision, I built a system designed for monthly accuracy, allowing me to observe realistic spending trends while accepting small timing delays in transaction posting.

# Project Building Summary (SQL)

- **Data Preparation**: Collected bank transactions from ANZ and Westpac CSV files and loaded them into a SQL database. Cleaned and standardised descriptions by removing extra symbols, timestamps, and card numbers. Combined all banks into one consistent table so every transaction followed the same structure.
- **Data Cleaning & Categorisation**: Created logic to detect keywords in transaction details to assign spending categories such as Groceries, Entertainment, or Utilities. Added a suburb-matching step to estimate where each transaction occurred, allowing analysis by category and by location.
- **Automation Procedures**: Built simple stored procedures that automatically clean and update new data each time a bank file is added. This removed the need for manual re-cleaning and made the process repeatable and consistent.

  <p align="center">
  <img src="docs/dataset_clean.png" width="70%"/>
  <br />
  <em>Cleaned Dataset (combined)</em>
</p>

# Results
You can download the Power BI dashboard [here*](https://github.com/khoitran2603/Personal-DA-PBI-Transactions/blob/main/Spending%20Dashboard.pbix)

  <p align="center">
  <img src="docs/dashboard.png" width="80%"/>
  <br />
  <em>Monthly Transactions Dashboard</em>
</p>

## Snapshot

<p align="center">
  <img src="docs/kpi.png" width="80%"/>
  <br />
  <em>Fig. 1: KPIs</em>
</p>

<p align="center">
  <img src="docs/pie.png" width="40%"/>
  <br />
  <em>Fig. 2: Spending by Categories</em>
</p>

Paying rent (Housing) was the biggest expense every month. Motor Vehicle spending wasn’t about regular fuel use — it spiked from **annual insurance** and **plate renewal every 6 months**. Eating Out reflected day-to-day convenience and occasional social dining.

## Trends & Shifts

<p align="center">
  <img src="docs/income_expense.png" width="60%"/>
  <br />
  <em>Fig. 3: Monthly Trend</em>
</p>

- Income steady at ~$3,800/month.
- Expense spikes: **March (+25%)** from family trip flight + annual car insurance, and **April (+45%)** hosting family from Vietnam.
- Average spend per purchase dropped from **$71 → $47**, meaning more small, **everyday transactions** replaced fewer large ones.
- Net position peaked at **+$852 in Feb** before dipping to **–$55 in Aug**.

Temporary family-related events explain the spikes in overspending. Outside of these, spending followed smaller but more frequent habits (groceries, convenience food, subscriptions).

## Spending Structure

<p align="center">
  <table>
    <tr>
      <td align="center">
        <img src="docs/expense_anchor.png" width="100%"/><br />
        <em>Fig. 4.1: Anchor-Costs Distribution</em>
      </td>
      <td align="center">
        <img src="docs/expense_anchor_2.png" width="80%"/><br />
        <em>Fig. 4.2: Monthly Trend</em>
      </td>
    </tr>
  </table>
</p>

- **Fixed** cost: housing, utilities, subscriptions
- **Semi-fixed** cost: motor vehicle, groceries
- **Flexible** cost: eating out, entertainment, retail, vacations
- **Other** cost: new or irregular categories

Over half my budget is locked into fixed commitments. Semi-fixed costs (car and groceries) fluctuate slightly each month. Flexible spend is the main lever I can adjust — this is where lifestyle and choice-driven spending sit.

## Where I Spend It

<p align="center">
  <img src="docs/map.png" width="80%"/>
  <br />
  <em>Fig. 5: Spending in Victoria</em>
</p>

- **CBD**: 19% of Eating Out (restaurants, weekends) + 57% of Retail (clothes, electronics).
- My Suburbs **(Caulfield + Malvern East)**: 16% of Eating Out, mostly fast food + convenience tied to daily walks.
- **Motor Vehicle**:
    + 30% on fuel in **Oakleigh** (convenient refuel point between home and city).
    + Fuel in **Tottenham** (close to a friend’s place).
    + 15% on CBD parking (mainly weekends).

Location reflects practical choices: CBD for leisure/shopping, local suburb for daily routines, Oakleigh and Tottenham for convenient refuelling near travel routes or visits.

## Key Takeaways (Jan-Aug 2025)
1. **Housing dominates** at 43%, anchoring spending every month.
2. **Car costs were irregular but heavy** (insurance + plate renewal), not everyday fuel.
3. **Family visits** explain the sharpest spikes in March–April.
4. **Daily convenience** (fast food, local shops, subscriptions) shaped much of the flexible spending.
5. With a small net deficit (–$55), reducing flexible spend by 10–15% would easily bring me back into surplus.

# Conclusion
This project transformed eight months of personal transactions into clear spending insights. By cleaning, categorising, and automating the data in SQL, I uncovered how fixed costs anchor my budget while events and convenience choices shape the rest. It showed how real-life financial data can tell meaningful stories — and how small adjustments, like reducing flexible costs, can quickly improve stability.
